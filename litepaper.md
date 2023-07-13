# Ask Network

The network architecture seperates three areas of concern.

First, we'll define a database to house observations of reality. It is the cannonical representation of the world external to the network. Those measurements are used to reason about possible actions and an indicator of how realized economic value.

Next, we create a central collection point of peoples wants. That is, satisfiable statements of what people want. Those wants can be compared with observations to determine wether the wants are indeed satisfied or not. The networks goal is to satisfy those declared wants as adequate as possible.

Next, we create a strongly-typed conversation about (1) what we could do (proposals) and (2) what we declare to do (commitments).

## Observations

Data is our window into reality. All data in Ask Network is modelled as _Messages_. Messages can occur in the virtual as network traffic between computers, and in the actual as causal effects between physical systems. As cultural capital, messages are captured and preserved by default.

Software can only capture virtual messages as digital data and does not have direct access to causal effects in reality. To capture real world data, hardware sensors must be utilized. We assume that all real world sensors are communicating their measurements as virtual messages via networking protocols. Thus, an Ask Network node records network protocol sessions only, with interpretations of reality being applied after consensus.

## Domains

That message history is used to derive reproducible representations of the actual and virtual external world. Such reproducible representations are specified as domains that take observations as input, and derive conclusions about the past, present, and future external world, subject to explicit assumptions about causal relationships.

At each domains core lies a causal graph. One can instantiate a causal graph by integrating observations into explicitly assumed causal relationships, producing a context. On that context, it can be reasoned backwards in time (I observed this, therefore that must have happened), and forwards in itme (if I do this, expectedly that will happen).

Once conclusions about hidden variables or counterfactuals where made, they can be queried through a semantic query interface. Nodes in the causal graphs carry semantically computable annotations in IEML. Queries are standard CQL expressions on the uniform data model of a semantic-causal context, combined with the domains semantic annotations in the formulation of the query.

Domain modellers combine observation procedures, interpretation, authentication, causal assumptions, and semantic annotations into interoperable domain modules, producing an ever growing library of domains that model reality increasingly accurate.

Specifying representations of reality in standardized and thus interoperable causal-semantic models enables transferrable reasoning about the behavior of virtual and actual external systems (hidden variables), and unobserved but possible observations or actions (counterfactuals).

Furthermore, the network provides a continuous integration pipeline for domain modellers by testing their causal theories against real world data.

Essentially it is an accounting system for everything measurable, with an attached unambiguous reasoning machine for everything unmeasurable.

## Network of Beings and Things

Expressing semantic annotations in IEML ensures that all conceptualization has exact positions in the semantic sphere, which allows for rich analysis across domains.

Most importantly for social coordination is the identification of beings and things, with all of them being embedded in the same physical reality, although at different positions in the geospatial process. What follows is a virtual representation of the actual economy that is acted out, through which past economic activity can be analyzed and future economic activity arranged.

Let us first differentiate economic participants from everything else. An economic participant is everything and everybody that influences voluntary participants to a degree that the influenced participant accounts for. Essentially it's the set of everything that is directly or indirectly important to at least one voluntary participant, with voluntary participant referring to a being that uses Ask Network to coordinate.

Let us further differentiate between passive and active  participants:

Passive participants are things with no behavior of their own other than the natural laws that govern their physical body. Desired things are economic goods (for example, a glass of wine) whereas undesired things are economic costs (like waste).

Active participants are those beings or things that operate a sensory-motor cycle and posess decision making abilities over their action space. Senses (like eyes and ears) or sensors (like cameras or microphones) on their body are employed to capture sensory information, which further is interpreted and reasoned about with their mental capacity, and finally acted out in their motor system (like legs or electric motors). Notably, such a situational awareness implies each active participant has certain desires and aversions, regardless of them being self-conscious or not. Picking one action over another always comes with a tradeoff about what has happened and what could have happened.

Now let's distinguish between communicating and silent participants. Communicating participants are those that have mastered languages to a degree that allows them to communicate with other speakers of the language in use, whereas silent participants can't. Communicating participants are first of all humans, and second of all smart things with embedded computers that communicate through networking protocols.

We identify a human as every communicating participant which is not labeled as a thing. Simply because we haven't yet observed any animal being able to make use of internet protocols.

Humans can authenticate themselves by claiming spots on the economic social graph. Smart things can authenticate themselves with an onboard private key.

## Economics

This section analyzes the dynamics of active participants interacting with each other. First we'll analyze interaction in the actual, and then show how communication in the virtual gives rise to coordinating such interactions so that everyone is better off.

From here onwards, we call an active economic participant an _agent_. Further, let's call all agents that are beings _subjects_, and all agents that are things _objects_.

Furthermore we assume all agents aim to optimize desires and aversions of their own. We refer to such an aim as the subjects or objects _wants_.

Each agent can or can't do a given action. The group of all actions available to an agent is called its _action space_. What the agent ended up doing is called his _acts_.

Each agent is assumed to do whatever it wants at any given moment as the default strategy. But beings and things may influence each other with their acts, positively or negatively. This soon will give rise to coordination between subjects.

For that, subjects communicate a shared world view via digital communication networks, and negotiate social coordination directly. A general scheme for such a conversation is layed out in the next section.

## Coordination

This section defines an abstract conversation to semi-automatically negotiate social coordination directly in terms of conditional actions (_"I do this if I observe that"_), from which then commitment schemes are constructed (_"I do this if you do that"_).

The goals for this conversaition is:

- (i) We recognize that subjects carry their own individual wants and each subject should be heard
- (ii) We also would welcome an open and unambiguous conversation about what we can do, esentially searching through our possible action paths.
- (iii) Further, an unambiguous social contract with automatic accounting and trustless settlement could help to coordinate on what we do.

The conversation defines three communication channels:

- (i) Broadcasting of wants for each subject
- (ii) Broadcasting of potential action paths
- (iii) Declaring of own commitment to action paths

With three types of messages, respectively:

- (i) **Wants**, answering: **how do we like it?**
  
  _(Represented as binary queries (fulfilled or not) in a given context.)_

- (ii) **Proposals**, answering: **what could we do?**

  _(Represented as changes (additions and removals) of commitments of one or more subjects.)_
  
- (iii) **Commitments**, answering: **what will we do?**

  _(A signed action path, represented as an ordered set of conditional actions. Conditions are either satisfied or not in a given context. The action choice is derived from the matching context via a specified query.)_

Recall that the public observation pool together with applied domain theories answers: **how is it?**

Those queries can be combined into a formalization of the foundational question of social coordination:

**what could we do | so we like it | in the future?**

Which translates into scanning the corpus of _Proposals_ for action paths that increase the probability of _Wants_ being satisfied according to future observations.

After desired action paths have been identified, users commit to them by signing the selected action path and publishing it as a _Commitment_. A commitment is an official statement of executing a specified act when the attached condition was satisfied by the latest observations.

Then the subjects go ahead and actually do it accordingly, or they won't, depending in their final decision in the moment of the act. Subjects may purposefuly record evidence to later prove they caused certain economic activity.

Wants are evaluated continuously on all observations as a measure for economic health. Fulfilled wants are indicators of realized value, possibly from successful coordination. Unfulfilled critical wants are indicators of unsuccessful coordination taking place.

## Coordination Markets

Coordination schemes combine commitments (I [commit to] do this if I observe that) into commitments that are conditioned on (a) other commitments (I [commit to] do this if [I observe] you commit to that). Assuming commitments to be followed, it translates into "I do this if you do that", subject to the actual decisions (derived from their actual wants, possibly different than their declared wants) each agent acts on.

Further we define an _offer_ as a parameterizable commitment scheme that essentially represents a futures product with physical delivery taken care of by a _service provider_. An offer standardizes ordering of the offered productive output and guides the process of production, delivery, and settlement.

An offer is specified by a coordination scheme a service provider commits to, which defines what commitments are entered when a deal is closed to then orchestrate production and delivery. A coordination scheme is defined as conditional commitments, in the form of "I commit to this if I observe that", where the observations are incoming orders (from consumers) and acknowledged deals (from the referenced service provider).

Conditional commitments (different from the condition on the action in the commitment itself) can be either conditioned on (a) the conditional action of other commitments, (b) the expected abstract effect of the other commitments conditional actions, or (c) declared wants of others resulting in automatic services useful for subscription services, or (d) on proposals that yield a certain (typically desired) effec

Further, coordination schemes can conditon commitments on published action traces, which describe what act actually happened. The condition of the commitment may not be able to measure directly or is not available to whoever is interested in it, but the form of an acts evidence (action trace) can be aligned on upfront, with the actor commiting to publishing the according action trace, otherwise counter-actions may be triggered by whoever desires the action to have happened.

Action traces are published either by the account owner to provide evidence of an act. Coordination schemes may require to post action traces to be fulfilled. Also accounts can submit action traces of other economic participants. That can be non-communicating participants or passive participants who don't have the ability to post an action trace of their own, or the action trace is evidence for value destruction which could trigger commitments of still other active participants which aim to counter-act that value destruction (examples are settlement procedures for failed deliveries or a police force protecting the wants of agents.

Also, commitments that depend on other commitments can be automatically committed once all upstream dependencies are committed. This mechanic of "committing to something if you commit to something" is understood by the network and opens up the space of commitment negotiations. Since commitments are virtually binding, a recursive commitment is a form of binding intent, with all virtual stake attached to the commitment possibly being a bounty on matching complementary commitments, with complementary commitments referring to those commitments who, when committed, would lead to the dependant being committed immediately too.

The uniform nature of service offerings allow for an efficient generalized matchmaking algorithm that crawls orders made possible by active service offerings that would fulfill active wants in case of a successful delivery.

Operations refers to instatiations of commitment schemes, which are actual people and things commiting to offering a service.

## Tokenomics

Goals:

- Generate proposals that increases the probability of wants being fulfilled if the proposed commitments are actually committed to.

Tokenomics are defined in terms of service offerings as defined in the previous section. So:

- Have service providers committing to causing successful deliveries of products that are wanted
- Have operating solvers who actively find and propose proposals.

Observations: pay per entropy
Domains: pay per reduction in surprise x useful economic activity caused (=used in completed deals):

- historically: immediately, relative to theories that have been improved upon
- future: pay/deal, gradually decreased based on how quickly it is replaced by newer theories
proposals + deals: payment through commitment negotiations, whatever you can get from others.

At some point, some participants may feel happy with a proposed alternative action path.
[this is where ask Network comes in to play the role of a mediator, especially across time (pay salary now from treasury, sell product later on, leaving to time-sensitive risk other than that of the economy to the worker. Those risks would carry entrapreneurs nowadays, but must not be carried at all by an Ask Network contributor. Essentially everybody is now selft employed and enjoys those benefits, but without additional accounting (data exports into various jurisdictions can be automated) and no risk of bankruptcy (risk is taken by the networks onchain +EV-selectoror, compensate by the economic value of the produce that the network auctions off to other active economic participants (agents)), and capital (you can use the networks treasury to bridge the production<>consumption capital requirements and fees like €25k for a GmbH is lender to you by the network, and further monitored by standard online banking HTTPS session captures to monitor the usage of the network funds.

MVLs are freely sellable. The network auctions them off (with price control to raise money for development) to acquire a treasury, and pay contributors at the point of the gift act, with the network "speculating" on that acts economic productivity which the network is free to sell at a later point in time to somebody else. This treasury basically bridges the gap of production<>consumption, with costs accuring during production (by possibly many actors or organizations along the value chain).

subsidized tipping: every MVL that is actually consumed has a certain amount of subsidized tips available to him. During production, delivery, and after delivery you can rate the service and optionally annotate with what you liked about it. Negative ratings pay nothing to nobody. Positive ratings pay a tip to the immediate service provider and to workers down the value chain. The distribution is equal with most weight to the servant, then downwards the chain decreasing, but can be customized by an annotation about what you liked and disliked, which then is attributed to the teams of the individual deals that made the service possible.

Vertical integration is more cost effective: you share the cash buffer, risk of final valuation of produce, and all coordinate to achieve a shared goal (otherwise there wouldn't be a sustainable organization running full vertical production for a given product)

Each voluntary participant of coordination markets creates a permissionless account. Each account automatically keeps track of: wants, commitments, action traces, balances, resource consumption.

Wants and commitments are explicitly updated by the account owner, with each account having a set of active wants and another set of active commitments.

The context to evaluate wants on can either be sourced from historic observations, providing a measurement of realized value. Or it is sourced from hypothetical observations, typically derived from reasoning about the causal impact of actions, providing a measure of potential value realization (proposals) and expected value (commitments).

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

Further, each subject is related to one physical embodiment in the actual. By default, every subject with an active account is considered human and given the _Native Human Action Space_, assuming that no other life on earth is capable of using modern computer user interfaces.

- Quantify causal influence on somebody or something on somebody or something
- Good: Attribution of economic productivity (compared to inaction)
- Informative: Quantifying power balances between people = as lever over people by actions in action space that positively or negatively influce other subjects.

With all beings and things embedded in the geospatial process, it indexes humans, animals, physical items, and natural resources.

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

Define work as undesirable time spent. Declared vs real values.

Show matrix of human work. The show how coordination can decrease total work, shift work from one person to another (like building a washing machine).

Derive case-tree from all commitments: If people do it don't follow commits, usual inaccuracies or derivations in action execution: show what might happen. Especially evaluate how other people will react to you doing or not doing certain things. Essentially showing you the practical ramifications of your decisions which takes the burden off from you to understand the social contract and just shows you how your values are effected by the actions of all affecting agents.

(Political) governance biases induced by the technical architecture of Ask Network:
a) In support of this goal, transparency of online processes seems a sine qua non. In particular, but not only, I am aiming at a clear, brief and natural language description of AI training algorithms and data. (optimization goals (wants), and the +EV-optimizatiion process is explicitly reasoned about and can be automatically described in natural languages, like the why of a decision)
b) Following the example of Wikimedia, let us strive to maximize the knowledge commons. (maximizing entropy on the knowledge base)
c) Let’s open up the data sets and algorithms along the lines of the free software movement. (=domain models must be executably open sourced to be used, like smart contracts)
d) Let’s ensure the practical and legal sovereignty of individuals and groups over the data they produce. (permissionlessness nature, everybody can get a new account no problem, made possible by not requiring more than one MVL to get everything you need (so marginal benefit of a second MVL in your account approaches zero by analyzing the social graph and identify distinct humans), but it still has marginal value to people with less than 1MVL or people who want a new account without economic history (their economic credit and debt they may want to escape from))
e) Finally, let’s decentralize the governance of online interactions by promoting consensual procedures. The social movement that supports the blockchain indicates a possible path here. (ex-ante conversation about wants, proposals, and commitments; only commit when there is consensus.Along with technical crypto-economic consensus about the underlying raw data base)

essentially it comes down to small, immediate gates (locking the door of your apartment, watching your bags, locking your car, having a 1m people-free sphere around you).
What the network gets rid of are large scale gates, because coordination liquidity is globally liquid and everyone thus has paid "taxes" in every place that.

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

## Guiding Principles

There are three guiding principles every active participant is asked to follow to get the most value out of the network:

1. Do whatever you want, as long as everybody is cool with it.
2. Feel free to ask, then look out for an answer.
3. Don't expect a change in behavior.

If you are about to do an act for which you are not sure you won't negatively effect anyone, you shall use the Wants Verification function. You can privately check any action against other contributors wants and see whether your act would cause other contributors wants to turn unfulfilled.

Further, it privately proposes to you what you could to instead in order to fulfill your wants while not

Do whatever you want, as long as everybody is cool with it: We need a verification function for that. Any action can be evaluated against latest observations+domains and all active asks (wants) in the network, so you can (locally in private and publicly in EV-Selection) verify that everybody is cool with what you're about to do.
This mechanisms also serves as a identification and verification of successful-delivery% for any action plan. Considering everything we don't know which has assumed causal mechanisms the user subscribes to (=the domain models he's okay with to reason through, usually science and his own political/societal ego.

Feel free to ask, look out for a response, but don't expect a change in behavior: In the sense of actions: You can ask somebody to do something or don't do something, or do something differently. They may answer to your request with counter-asks which would change their minds, although it's up to them to communicate or not. Multiple Ask-rounds essentially are direct negotiations of social coordination.

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
