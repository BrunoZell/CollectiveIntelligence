# Ask Network Overview

We are researching the viability of computer-mediated non-monetary economies in an effort to find more suitable mechanisms for global social coordination. Traditional coordination schemes like money, democracy, and organizations of various kinds seemingly are unable to remove current global challenges like wealth inequality, climate change, war, advertising, transaction inefficiencies, information asymetry, ect.

By formalizing algorithmic trading we saw that financial markets may evolve into coordination markets, where action & effect in physical reality are negotiated semi-automatically within a shared data environment. It seems more pragmatic coordination can be uncovered once individual data silos are connected by a higher bandwidth than possible through price discovery. It also seems to tend towards positive-sum coordination due to efficiency gains from collaboration.

## Comparison to other networks

CRDT knowledge base:
- Pretty much Convex Protocol without the VM and no account balances or fork choice rules;
-> really it's just a Merkle Clock, with sequencing never yielding any conflicts.

Want (Intent) Proposal (match) and matchmakers
- pretty much Anoma except that no VM state changes are there except that of the messages themselves, which are append-only (although possibly signed by the author or HGTP-authenticated).
-> Anoma VM public state and transaction execution model is replaced with user-defined causal-semantic models that specify just the assumed behavior of relevant reality (reason about observations and actions)

All downstream causal-semantic model dependencies imply their own assumptions on reality (whether accurate or not), with the upstream dependants being somewhat on a mercy of them. Validity checks are local to the model.

## Three Layers of the Network

1. Computable sensory-motor cycle to create and communicate representations of reality
2. Coordination markets to negitiate who does what directly, creating a new design space for productive economies
3. The Asknet Economy, which creates a structure of service providers and benefitiaries with the aim of being fair and humane.

Each layer is standardizing one of three concerns by defining message templates that guide the conversation:

- _Representation_ as **Observe ➡️ Interpret ➡️ Decide ➡️ Act**
- _Coordination_ as **Ask ➡️ Propose ➡️ Commit ➡️ Do ➡️ Measure**
- _Economy_ as **Offer ➡️ Order ➡️ Deal ➡️ Production ➡️ Delivery ➡️ Settlement**

### Representation

- Observe: **what do I sense?**
- Interpret: **how do I see it?**
- Decide: **what do I do now?**
- Act: **I do this now**

### Coordination

This conversation guides the negotiation of who does what. It helps to shape reality so we like it more.

- Ask: **what do we want?**
- Propose: **what could we do differently?**
- Commit: **what do I declare to do?**
- Do: **what did I end up doing?**
- Measure: **what was the effect of my actions?**

### Economy

- Offer: **what would I do for you?**
- Order: **I'd like you to do that for me**
- Deal: **I commit to do that for you**
- Production: **I make it happen**
- Delivery: **Here it is, enjoy!**
- Settlement: **Any problems or are we good?**

## Technical Components

Three shared databases the network maintains:

- The _Knowledge Base_, answering **what happened?**
- An _Ask Pool_, answering **what do we want?**
- Our _Collective Strategy_, answering **what will we do?**

The _Knowledge Base_ contains observations of the external world, which is interpreted and validated to create a shared representation of the outer world. This shared representation is used as a common reference to talk about reality.

The _Ask Pool_ is a collection of user-defined Asks, which claim desired and undesired properties of the shared representation of the world.

The _Collective Strategy_ is the aggregate of every users individual strategy, declaring what each user will do under which circumstances. A strategy is defined as an ordered list of conditional action, essentially stating _"I do this if I observe that"_.

## Domain Models

Domain Models are packages of ideas to communicate how one may think about the world. It allows the unambiguous sharing of assumptions about how the world works, and enables reproducible automatic reasoning. They specify:

- A set of observations one could make, defined by the imperative behavior of _Observers_ which source sensory information from a network connection.
- A set of actions one could take
- A causal model of assumed behavior to reason backwards from observations, and forwards from actions
- A semantic query interface that specifies latent (unobservable) variables of the represented external system to allow the construction of custom queries to answer questions about a given representation of the world.

## Network Consensus State

### Standardizing Asks (wants & aversions) and Coordination (who does what to fulfill asks)

```yaml
knowledgeBase: cid<ObservationPool>
asks: cid<AskBook>
proposals: cid<ProposalBook>
strategy: cid<CollectiveStrategy>
```

## Domain Model

```fsharp
module DomainModel<InterventionalNode, ObservationalNode, HiddenNode> = 

/// This type represents the type-space of any causal node instances in a scene instance.
type CausalNode =
    | Interventional of InterventionalNode
    | Observational of ObservationalNode
    | Hidden of HiddenNode

type CausalLink<'Message> = {
    Receiver: IdOf<CausalNode> // A type constraint on the space of all possible observation-node[-types] in this domain module, to select a specific observation-subnode. It means all node instances that match this type selector will receive.
    // Validation criteria: All selected types must be able to receive effects of 'Message

    Producer: IdOf<CausalNode>
}

type ScmDag<'Message> = {
    Nodes: CausalNode list
    Effects: CausalLink<'Message>

    InstantiateLinks =
        // Todo: Iterate all links, for each: select producers & consumers and put a link between all of them (all selected consumers receive from all selected producers messages of type 'Message)
        failwith ""
}

let instantiateScene : ContentId<ObservationPool> -> ScmDag =
    // Todo: interpret & analyze ObservationPool according to domain-specific rules.
    /// Then put it into this domains causal graph and return the instance that
    /// descries the passed situation (ObservationPool).
    failwith ""

/// Defines an action space of somebody or something.
/// Describes an action executed by somebody or something if instantiated.
/// Instantiated on the graph ex-ante (before doing it) to estimate that actions effect,
/// Or it's instantiated on the graph ex-post (after observation) just as a hidden variable to mark that some subject might have done an action, or could have done an action, in the past.
type InterventionalNode = interface end

/// Defines the space of all possible measurements after interpretation. Each type of percept is it's own type (of interface ObservationalNode), with each type defining the space of all possible observations.
/// Describes an observation made:
/// Ex-ante (before actual observation) to reason about hypothetical observations (either backwards in time toward possible causes, or forwards in time toward possible downstream effects).
/// Post-ante (derived from an actual observation, via interpretation) to reason about the representation of the actual.
type ObservationalNode = interface end

/// Defines a state space of external system (orchestration of somebodies and somethings) this domain module aims to represent.
/// It is freely invented as needed by the causal-observational theory defined in this domain module. Hidden nodes may also be called "latent state".
type HiddenNode = interface end

type ActionInitiation = {
    Situation: ContentId<ObservationPool>
    Action: ContentId<[DomainModule].[InterventionalNode]>
}
```

## Wants as Asks

_Asks_ are satisfiable queries on a given world representation. They are used to communicate what one might want and don't want to see in the world.

```fsharp
type Fulfillment = Fulfilled | Unfulfilled
type Ask = Scene -> Fulfillment
type AskTree = Dag<Ask> // defines an ordering of asks (i.e. what to fill first, limit-like)
type AskBook = Map<UserId, ValueTree>
```

## Strategy

```fsharp
type Decision =
    | Inaction
    | Initiate of Initiatives:ActionInitiation array

type ConditionalAction = {
    Condition: Scene -> bool
    Action: Scene -> Decision
}

type DeclaredStrategy =
    DeclaredStrategy of ConditionalAction list

type CollectiveStrategy = Map<UserId, DeclaredStrategy>
```

## Proposals

```fsharp
type ProposerUserId = UserId
type ProposalBook = Map<ProposerUserId>

type Proposal = {
    Proposer: UserId // receiver of rewards if this proposal ended up being (1) accepted or (2) realized value to someone (=filled Asks)

    Changes: Map<UserId, StrategyChange>
    // Validation criteria: strategy change must be compatible with currently declared strategy of the UserId
}

type StrategyChange = {
    Added: ContentId<ConditionalAction> list
    Removed: ContentId<ConditionalAction> list
}
```

### Standardizing products and services to build a self-sustainable economy

Offer
Receipt
Voucher
Voucher basket
Value set
$ASK



## Runtime

Each Runtime Module comes with:

- **A domain interface:** SDK interface types and function signatures that domain models target
- **Imperative behavior**
- **Data structures** that are produced by executing the Runtime
- **Control messages** that are passed between Runtime Module instances

List of modules:

- Observer Group
- Observation Pool
- Live Analysis
- Action Execution
