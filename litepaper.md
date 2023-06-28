# Ask Network

The network architecture seperates three areas of concern.

First, we'll define a database to house observations of reality. It is the cannonical representation of the world external to the network. Those measurements are used to reason about possible actions and an indicator of how realized economic value.

Next, we create a central collection point of peoples wants. That is, satisfiable statements of what people want. Those wants can be compared with observations to determine wether the wants are indeed satisfied or not. The networks goal is to satisfy those declared wants as adequate as possible.

Next, we create a strongly-typed conversation about (1) what we could do (proposals) and (2) what we declare to do (commitments).

## Observations

Data is our window into reality. All data in Ask Network is modelled as _Messages_. Messages can occur in the virtual as network traffic between computers, and in the actual as causal effects between physical systems. As cultural capital, messages are captured and preserved by default.

Software can only capture virtual messages as digital data and does not have direct access to causal effects in reality. For that there are sensors. We assume that all real world sensors are communicating their measurements as virtual messages via networking protocols. Thus, an Ask Network node records network protocol sessions only, with interpretations of reality being applied after consensus.

## Theories

That message history is used to derive reproducible representations of the actual and virtual external world. Such reproducible representations are specified as causal-semantic models [and data consistency constraints as ologs] that take observations as input, and derive conclusions about the external world.

One can instantiate a causal graph by integrating observations into the assumed causal relationships, producing a context. On that context, it can be reasoned backwards in time (I observed this, therefore that must have happened), and forwards in itme (if I do this, expectedly that will happen).

Once conclusions about hidden variables or counterfactuals where made, they can be queried through a semantic query interface. Queries are standard CQL expressions on the uniform data model of a semantic-causal context, combining semantic annotations with data types.

Domain modellers combine interpretation, authentication, causal assumptions, and semantic annotations into interoperable domain modules, producing an ever growing library of theories that further can be used to author coordination schemes.

Specifying interpretations of reality in standardized and thus interoperable causal-semantic models enables transferrable reasoning about the behavior of virtual and actual external systems (hidden variables), and unobserved observations or actions (counterfactuals).

## Coordination

- Establish wants[+theories]
- Measure fulfillment of wants[+theories] on observations
- Create commitment schemes that point to possible valuable action paths
- Search through all possibilities and propose commitments
- Evaluate all proposals and change to any plan that is more +EV.

Proposal: What could we do? As changes to other peoples todo list.

Commitment: What do we do? As declaration of own future conditional action.

Both proposals and commitments are expressed as conditional actions.

Condition: A CQL boolean query on the consensus view

Note on credible commitments: A declaration does not guarantee the committer to actualy do the action as declared. Commitments may come with a stake, reputation, or insurance to make it more credible to others, although the fundamental mechanism does not force any of it. It is assumed that people tend to pull through with their commitments to avoid sanctions of others (=change of other ppls actions that the faulty committer may not like) while keeping the economic balance on the economies they are part of.

## Economy

Standardizing ordering of production and productive output via (potentially unsuccessful) physical delivery.

Show how an actual service offering (with commited subjects) influences how the economies yield v/s is .

The initial account balance is always at 1MVL/s. Rewards

### Social Network

Each account keeps track of: balances, resource consumption, wants, commitments, action traces

### Commitment Schemes

### Operations

commitments and work; instatiations of commitment schemes with actual people and things commiting to offering a service.

### Self-determined floating Economy

Derive optimal parameters (of all possible economies) from peoples wants, and wants of wants (=morals), shared values ect.

## Example: Ride Sharing

show domain models used: cars, drivers, pickup, street navigation, pickup, dropoff, working schedule, smartphone usage

taxi ride voucher:
service: get from geospacial point $pickup to geospacial point $dropoff // ask template to be used as filter for ask flow
order form: { pickup: Herrfurthstr; dropoff: Hermannstr; } // data for order as extracted from an ask that matches the service template
offer: {
    actions: [
        #driver will drive #car to #dropoff
        #driver will wait at #dropoff for #you to enter the #car
        #
    ]
    estimations: [
        #car at #pickup: in 1-3 minutes;
        #car at #dropoff carrying #you (asker): in 25-29 minutes;
    ]
    // costs are estimated before delivery, fixed after delivery
    cost: {
        driver-time: 50minutes;
        fuel-consumption: 3l;
        car-usage: 50 car usage minutes;
        road-usage: 5km specific road usage
    }
    subjects: [ #driver ]
}

match with committed drivers:market maker propose order form of a service that exactly fulfills the users ask. The MM may have to invent that service on his own but then purely virtually orchestrate different service offerings, some of them actual services. Risk is on him to successfully deliver the orchestration, with risk of downstream suplliers failing possibly hedged in prediction markets. Are there any leftover, unclaimed values the MM can collect in that match?

## Positioning Ask Network

briefly illustrate history of banking, listing problems with their causes, and the solutions humans implemented (and are still in use today).

show how it eliminates most of these problems, and goes back to trusted personal ledgers and commodity money.

show how it is the next evolution in money/banking/finance.

and point to the big ecosystem of entrepreneurs creating organizations within the monetary for-profit framework, Ask Network will create a comparable spectrum of entrepreneurs who develop and operate coordination schemes.

## Next steps

We are implementing the first version of this.

Please either try to contribute with expertise and dedication in exchange for a minimum viable life (MVL),

or donate crypto assets to pay the MVLs of our contributors and get a spot on the seed list.

Either way, you get to be part of Spectrum DAO.
