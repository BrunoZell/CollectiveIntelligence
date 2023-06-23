# Ask Network Overview

## Technical Components

Three shared databases the network maintains:

- The _Knowledge Base_, answering **what happened?**
- An _Ask Pool_, answering **what do we want?**
- Our _Collective Strategy_, answering **what will we do?**

The _Knowledge Base_ contains observations of the external world, which is interpreted and validated to create a shared representation of the outer world. This shared representation is used as a common reference to talk about reality.

The _Ask Pool_ is a collection of user-defined Asks, which claim desired and undesired properties of the shared representation of the world.

The _Collective Strategy_ is the aggregate of every users individual strategy, declaring what each user will do under which circumstances. A strategy is defined as an ordered list of conditional action, essentially stating _"I do this if I observe that"_.

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

type ActionInitiation = {
    Domain: ContentId<DomainModel>
    Action: ContentId<ActionScmNodeType>
    Payload: ContentId<[this.Action]>
}
```

## Asks

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
