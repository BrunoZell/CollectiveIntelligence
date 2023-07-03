# Ask Network

The network architecture seperates three areas of concern.

First, we'll define a database to house observations of reality. It is the cannonical representation of the world external to the network. Those measurements are used to reason about possible actions and an indicator of how realized economic value.

Next, we create a central collection point of peoples wants. That is, satisfiable statements of what people want. Those wants can be compared with observations to determine wether the wants are indeed satisfied or not. The networks goal is to satisfy those declared wants as adequate as possible.

Next, we create a strongly-typed conversation about (1) what we could do (proposals) and (2) what we declare to do (commitments).

## Observations

Data is our window into reality. All data in Ask Network is modelled as _Messages_. Messages can occur in the virtual as network traffic between computers, and in the actual as causal effects between physical systems. As cultural capital, messages are captured and preserved by default.

Software can only capture virtual messages as digital data and does not have direct access to causal effects in reality. To capture real world data one must use sensors. We assume that all real world sensors are communicating their measurements as virtual messages via networking protocols. Thus, an Ask Network node records network protocol sessions only, with interpretations of reality being applied after consensus.

## Domains

That message history is used to derive reproducible representations of the actual and virtual external world. Such reproducible representations are specified as domains that take observations as input, and derive conclusions about the past, present, and future external world, subject to explicit assumptions about causal relationships.

At each domains core lies a causal graph. One can instantiate a causal graph by integrating observations into explicitly assumed causal relationships, producing a context. On that context, it can be reasoned backwards in time (I observed this, therefore that must have happened), and forwards in itme (if I do this, expectedly that will happen).

Once conclusions about hidden variables or counterfactuals where made, they can be queried through a semantic query interface. Nodes in the causal graphs carry semantically computable annotations in IEML[1]. Queries are standard CQL expressions on the uniform data model of a semantic-causal context, combined with the domains semantic annotations in the formulation of the query.

Domain modellers combine observation procedures, interpretation, authentication, causal assumptions, and semantic annotations into interoperable domain modules, producing an ever growing library of domains that further can be used to facilitate efficient and effective social coordination.

Specifying representations of reality in standardized and thus interoperable causal-semantic models enables transferrable reasoning about the behavior of virtual and actual external systems (hidden variables), and unobserved but possible observations or actions (counterfactuals).

Furthermore the network provides a continuous integration pipeline for domain modellers by testing their causal theories against real world data[2: by connecting to HGTP L0].

## Subjects and Objects

While the causal-semantic models of domains are free to define arbitrary processes with arbitrary semantic annotations, this section defines an abstract ontology that underly coordination markets.

Of primary importance are individuals which represent a physical embodyment of single living organisms, virtually represented as a _subject_.

Of secondary importance are

Special emphasis lies on the spacial process. This is where all actual economic exchange happens. Either production or consumption or both.

Within the geospacial process we interconnect many domains of value, especially that of physical items.

Each account keeps track of: balances, resource consumption, wants, commitments, action traces

## Economics

Evaluating conditional actions from proposals and commitments yields an estimation of how reality expectedly is affected by it when compared to the inaction scenario.

While the constraints embedded in the condition guarantee certain abstract truths in any matching context, an actual matching context usually carries additional information that may lead to more detailed or correct estimates about what might happen.

Conditional actions in commitments thus tend to include multiple conditions that represent different possible cases that are planned for ex-ante.

Such conditions may depend on previous actions which allows for the creation of multi-step action paths. Such action paths can be declared and executed across multiple subjects given there is a communication channel between them to share progress.

Multi-subject action paths can be gradually negotiated and built up by commitments that depend on: (1) other peoples commitments or (2) other peoples action traces.

(1) The former is akin to cooperation. I do this and you do that and if we both do it well we end up in a more desirable situation than otherwise. Most straight forward is a win-win situation where all of the participants have a desire for the expecte doutcome. Although even in win-win situations (shared goal) there might be a misalignment about who does what and how exactly actions should be done. For that, mutually dependent commitments can be used to negotiate the planned action path ex-ante, where the commit of one subject is conditioned on another subject having committed to the complementary action with the desired attriutes.

(2) The latter is akin to dispute resolution. I observed you doing something that you may like, but I didn't. In a purely anarchistic setting this would be the end of the story. But any advanced economy has established a legal system that regulate who has the right to do what, declares what others might do to you if you don't respect other subjects rights, and operate a dispute process where disagreements are evaluated and, possibly forcibly, a corrective action is decided on. Further there is an executive who enforce the official corrective action, and a legislative process that fine tune and adjust the rules to changing circumstances.

Coordination is concerned with proactively planning actions. A given action ex-ante implies a difference in expected future observations compared to inaction, which when evaluated against wants may or mat not be desireable for some subjects. It answers the question: **How do we make it, so we like it better?**

Ruling is concerned with reactive counter-actions. It is coordinated by the subjects whichs value got destructed, and is aimed at recreating a desirable situation that was inadequately taken from them by another subject. A given action ex-post implies the actor to have caused related observations as they would be different if the action did not take place.
It  **What should I not do so others don't have it worse?**

Neither coordination nor rulings are defined explicitly in the base layer of coordination. Such constructs are higher level abstractions that can be compiled down into wants, proposals, and commitments. Such higher level abstractions are defined by commitment schemes as defined later. They are a collection of abstract (parameterized) and mutually dependent commitment templates which can be used to find proposals that point to action plans with expectedly desirable outcomes.

All wants of a single subject imply a priorization of all possible contexts, where all possible contexts are defined by the domain models referenced by the expression want.

The wants of all subjects in the network, together with ex-ante conflict prevention, fairness selector, and legal rights, imply a priorization of the consensus context.

Wants are transparent about how their fulfillment depends on observations, thus contributors can reason about what needs to get done in order to fulfill a want.

Note on credible commitments: A declaration does not guarantee the committer to actualy do the action as declared. Commitments may come with a stake, reputation, or insurance to make it more credible to others, although the fundamental mechanism does not force any of it. It is assumed that people tend to pull through with their commitments to avoid sanctions of others (=change of other ppls actions that the faulty committer may not like) while keeping the economic balance on the economies they are part of.

## Coordination

This section defines an abstract conversation to semi-automatically comunicate the wants of subjects, pointing to potential action paths, and declaring commitment to conditional actions.

The conversation categorizes three types of messages:

- **Wants**, answering: **how do we like it?**
  
  _(Represented as binary queries (fulfilled or not) in a given context.)_

- **Proposals**, answering: **what could we do?**

  _(Represented as changes (additions and removals) of commitments of one or more subjects.)_
  
- **Commitments**, answering: **what will we do?**

  _(Represented as conditional actions. Conditions are either satisfied or not in a given context. The action choice is derived from the matching context via a specified query.)_

Recall that the public observation pool together with applied domain knowledge answers: **how is it?**

Those queries can be combined into a formalization of the foundational question of social coordination:

**what could we do | so we like it | in the future?**

Which translates into scanning the corpus of _Proposals_ for action paths that increase the probability of _Wants_ being satisfied according to future observations.

After desired action paths have been identified, users commit to conditional actions by publishing _Commitments_. A commitment is an official statement of executing a specified act when the attached condition was satisfied by the latest observations.

Do it. Or not. Record evidence.

Evaluate wants continuously on all observations as a measure for economic health. Fulfilled wants are indicators of realized value.

## Coordination Markets

- Measure historic fulfillment of wants[+domains] on observations (realized value)
- Estimate future fulfillment of wants[+domains] on latest observations (expected value). Estimation of EV is subject to the domains used for reasoning and assumptions about who will do what.
- Given latest observations, current wants[+domains], and current commitments[+domains]: search through all possibilities and propose changes to commitments for one or more accounts
- Evaluate all proposals and change to any plan that is more +EV.

The context to evaluate wants on can either be sourced from historic observations, providing a measurement of realized value. Or it is sourced from hypothetical observations, typically derived from reasoning about the causal impact of actions, providing a measure of potential value realization (proposals) and expected value (commitments).

Standardizing ordering of production and productive output via (potentially unsuccessful) physical delivery.

Create commitment schemes implementing the abstract product structure, to be picked up by the generalized matchmaking algorithm that crawls possible action paths for desired outcomes.

Operations: commitments and work; instatiations of commitment schemes with actual people and things commiting to offering a service.

## Tokenomics

Show how an actual service offering (with commited subjects) influences how the economies yield v/s is .

The initial account balance is always at 1MVL/s. Rewards

Derive optimal collective strategy from all peoples wants, and wants of wants (=morals, and further sanctions), commitments, dependency, power.

Economists teach that money has three functions:

- It is a means of exchange: it lets you confer power to others.
- It is a store of value: it lets you delay the exercise of power in time.
- It is a unit of account: it lets you measure many things by a common yardstick.

The economy proposed here seperates these functions by solving them explicitly.

Most economic theories are answereng those questions:

- What is produced?
- How is it produced?
- How much is produced
- For whom is it produced

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

## Positioning Ask Network

briefly illustrate history of banking, listing problems with their causes, and the solutions that humans implemented over the time with some of them still in use today. Please mention in this order, allowing each solution one paragraph with a sentence or two:

- Debt and dependence on trust
- Bartering and double concidents of wants
- Commodity money, mentioning barting as just a transitionary phenomenon only rarely used
- First bank notes
- Central banks
- first ERMA computer
- clearinghouse systems (automatic payments and ATM transactions)
- SWIFT

Also touch on how increased volume of pairwise transactions only worsens global wealth inequality, referencing _John Angle_ and the _Angle Process_.

show how it eliminates most of these problems, and goes back to trusted personal ledgers and commodity money, while entering the new frontier of automatic multi-party transactions and realtime adaptive economies.

show how Ask Network is the next evolution in money/banking/finance.

and point to the big ecosystem of entrepreneurs creating organizations within the monetary for-profit framework, Ask Network will create a comparable spectrum of entrepreneurs who develop and operate coordination schemes.

## Theoretical Foundations

- Counterfactual reasoning with structural causal models (Judea Pearl).
- Structured data modelling with the IPLD Data Model (InterPlanetary Linked Data)
- Consistent data migration between domains with Ologs
- Information querying on the ologs with CQL (the Categorical Query Language)
- Interoperable semantic annotations of olog objects with IEML (the Information Economy MetaLanguage)
- Interoperability with virtual and actual reality (external blockchain networks and physical reality) with the HGTP data standard (Hypergraph Transfer Protocol)
- Implementation of tokenomics on Constellation Network

## Next steps

We are implementing the first version of this: First we implement a generalized +EV-Crawler with applications in algorithmic trading of electricity and crypto assets. Then we go on an implement the Ask Economy as a public network.

In case you want to contribute, you can do so by:

- (i) help implementing this using your technical expertise and dedication in exchange for a minimum viable life (MVL), or
- (ii) donating crypto assets to pay for the MVLs of our contributors and get a spot on the networks seed list.

If (i) applies to you, look for further instructions in the _#builders_-channel on our Discord.

If (ii) applies to you, send crypto assets into our SAFE on either Ethereum, Arbitrum, or Polygon. The address is the same for all networks: `0x5cf266bb7b5EFE578C2C63A14Ea2b644710E153e`.
