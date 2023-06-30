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
- Measure historic fulfillment of wants[+theories] on observations (realized value)
- Estimate future fulfillment of wants[+theories] on latest observations (expected value). Estimation of EV is subject to the theories used for reasoning and assumptions about who will do what.
- Given latest observations, current wants[+theories], and current commitments[+theories]: search through all possibilities and propose changes to commitments for one or more accounts
- Evaluate all proposals and change to any plan that is more +EV.

### Wants

Each want is a statement about: **how do we want it?**

Wants are represented as binary queries, stating whether that want is fulfilled or not in a given context. These queries are composed from semantic query interfaces of domain models.

The context to evaluate wants on can either be sourced from historic observations, providing a measurement of realized value. Or it is sourced from hypothetical observations, typically derived from reasoning about the causal impact of actions, providing a measure of potential value realization (proposals) and expected value (commitments).

### Proposals

Each proposal is an answer to the question: **what could we do?**

It is represented as changes to other peoples commitments.

### Commitments

Each commitment is a declaration of: **what will we do?**

Commitments are represented as conditional actions. Conditions are either satisfied or not in a given context. The action derived from a matching context is then either executed or not based on the committers final behavior.

Commiters are referred to via their network accounts and can relate to both beings and things.

## Economics

Evaluating conditional actions from proposals and commitments yields an estimation of how reality expectedly is affected by it when compared to the inaction scenario.

While the constraints embedded in the condition guarantee certain abstract truths in any matching context, an actual matching context usually carries additional information that may lead to more detailed or correct estimates about what might happen.

Conditional actions in commitments thus tend to include multiple conditions that represent different possible cases that are planned for ex-ante.

Such conditions may depend on previous actions which allows for the creation of multi-step action paths. Such action paths can be declared and executed across multiple subjects given there is a communication channel between them to share progress.

Multi-subject action paths can be gradually negitiated and built up by commitments that depend on: (1) other peoples commitments or (2) other peoples action traces.

(1) The former is akin to cooperation. I do this and you do that and if we both do it well we end up in a more desirable situation than otherwise. Most straight forward is a win-win situation where all of the participants have a desire for the expecte doutcome. Although even in win-win situations (shared goal) there might be a misalignment about who does what and how exactly actions should be done. For that, mutually dependent commitments can be used to negotiate the planned action path ex-ante, where the commit of one subject is conditioned on another subject having committed to the complementary action with the desired attriutes.

(2) The latter is akin to dispute resolution. I observed you doing something that you may like, but I didn't. In a purely anarchistic setting this would be the end of the story. But any advanced economy has established a legal system that regulate who has the right to do what, declares what others might do to you if you don't respect other subjects rights, and operate a dispute process where disagreements are evaluated and, possibly forcibly, a corrective action is decided on. Further there is an executive who enforce the official corrective action, and a legislative process that fine tune and adjust the rules to changing circumstances.

Coordination is concerned with: **How do we do, so we like it better?**

Rules are concerned with: **What should I not do so others don't have it worse?**


All wants of a single subject imply a priorization of all possible contexts, where all possible contexts are defined by the domain models referenced by the expression want.

The wants of all subjects in the network, together with ex-ante conflict prevention, fairness selector, and legal rights, imply a priorization of the consensus context.

Wants are transparent about how their fulfillment depends on observations, thus contributors can reason about what needs to get done in order to fulfill a want.

A given action ex-ante implies a difference in expected future observations compared to inaction.

A given action ex-post implies the actor to have caused related observations as they would be different if the action did not take place.

Note on credible commitments: A declaration does not guarantee the committer to actualy do the action as declared. Commitments may come with a stake, reputation, or insurance to make it more credible to others, although the fundamental mechanism does not force any of it. It is assumed that people tend to pull through with their commitments to avoid sanctions of others (=change of other ppls actions that the faulty committer may not like) while keeping the economic balance on the economies they are part of.

## Ask Economy

Economists teach that money has three functions, not one.

- It is a means of exchange: it lets you confer power to others.
- It is a store of value: it lets you delay the exercise of power in time.
- It is a unit of account: it lets you measure many things by a common yardstick.

The economy proposed here seperates these functions by solving them explicitly.

Most economic theories are answereng those questions:

- What is produced?
- How is it produced?
- How much is produced
- For whom is it produced

Standardizing ordering of production and productive output via (potentially unsuccessful) physical delivery.

- Create commitment schemes that point to possibly valuable action paths

Show how an actual service offering (with commited subjects) influences how the economies yield v/s is .

The initial account balance is always at 1MVL/s. Rewards

### Social Network

Each account keeps track of: balances, resource consumption, wants, commitments, action traces

### Commitment Schemes

### Operations

commitments and work; instatiations of commitment schemes with actual people and things commiting to offering a service.

### Self-determined floating Economy

Derive optimal parameters (of all possible economies) from peoples wants, and wants of wants (=morals), shared values ect.

## Example: Peer to Peer Ride Sharing

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

## Example: Peer to Peer Crypto Exchange

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
