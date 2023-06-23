# Ask Network Overview

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
type DomainModel = {
    Causality: Cid<ScmDag>
    Actions: ActionScmNodeType list
}

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
    Domain: ContentId<DomainModel>
    Action: ContentId<ActionScmNodeType>
    Payload: ContentId<[this.Action]>
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
