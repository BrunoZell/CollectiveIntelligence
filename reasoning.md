# Sematic-Causal Models

For each Effect-type a node listens to, it provides a function that reads the message, and puts it into the nodes CRDT sensory-information type. Each node defines one sensory-CRDT that every possible effect that is listened to is mapped into when it is received.
The sensor-CRDT can be merged independent of order and converges to a common maximum. The commulative sensor-CRDT that incorporates all incoming effects this round is then fed into this node current (derived from node state) behavior function, which takes a sensor-CRDT as input, and produces a CauseProbabilityMap as output.

There is one state-CRDT type per node. Every node defines a BehaviorConstructor function, which takes (the current nodes) state-CRDT as input, and produces a behavior function, which takes a sensori-crdt as input and produces a CauseProbabilityMap, listing all possible produced causes (every node has a single cause type) with assigned mutually-exclusive probability weights, all adding up to 1.

state-CRDTs is what instance data is in Olog.
state-CRDTs is what latent variables are in causal graphs
state-CRDTs are fully reproducable given an initial state and an ordered sequence of CauseProbabilityMaps

what happens if an order book absorbs an order, to then only later show changes is behavior (when it is matched).
It records some sensori-information into its memory cell. Control cell will stay the same, so there is no change in behavior.
Then later when a matching order is observed (incoming effect message), it will be matched with the order in the memory cell, the memory will be updated accordingly with that order removed, and a cause probability map listing: [trade broadcast, buyer fill, seller fill, book L3 update].

The memory cell is the state-crdt. It references observations with their virtual timestamp that references this instance id (this MAC cell, this semantic-causal node).

When a causal nodes behavior is evaluated, it has the option to overwrite parts of its memory cell with new values. A memory cell is an CUE data type (as keys) mapped to IPLD data structures for storing data. If the key is a type range, then the IPLD data structure is a special case merge-type able to accomodate all selected possible keys along the range each with it's disting IPLD primitive data value.

Key values can only be one of these scalar types. All of them are defined in both IPLD and CUE:

- bytes
- string
- bool
- int
- number
- link
- undefined

Each causal-semanitc node can only have one memory cell layout, which is a single IPLD data model node. To group multiple scalar values together and simultaneouely organize them, IPLD recursive types overlaid with CUE structs and usions are used:

- IPLD map + CUE struct
- IPLD list + CUE union, with IPLD list ordinal being the unions case-id. This specifically is unordered.

Each causal-semantic node type defines a single memory cell layout, which is a single IPLD node. That node can either be a scalar type or recorsive type. With a link, list, or map there could be more than one data node being referenced by the memory cell. The memory layout also specifies labels for the data nodes. It's semantic annotations. They are IPLD struct or union schemas (projected on map and list types) 



Cause-effect exchange is message based.
To escape discrete message passing, whole effect-ranges can be exchanged although all selected effect-instances come with the same probability (both emitted on the CauseProbabilityMap and received by all listening Nodes that listen on effect-ranges that are intersecting with some non-zero parts of the CauseProbabilityMap).
Still, each node can list distinct, mutually exclusive cases, with accordingly assigned probabilities that must add up to one for the CauseProbabilityMap being valid.
When a CPMap is evaluated, it can choose to evaluate one of its cases, with the other staying unevaluated.

Evaluation rounds:

Intervention: evaluate causal reach by following the arrows in the causal graphs. Under a specified set of domains that shall be evaluated, possibly referencing immutable dependency domains. In this mode, no behavior is executed. It is just analyzed. That's why each causal-semantic node type / each neuron class statically defines effect-selectors it receives signals from. All others, by definition and implementation, will not be forwarded to the neuron in case another node in the network would produce a matching effect.

Observation insert: New sensory information (as message sent/received) is integrated into the causal-graph. The new node is created, woith according equation being added to the variables equations of the SCM. Changes on probability maps are calculated via do-calculus. Serving the new base for predictions into the future (which is the probabilities of causal influence, combined from an assumed causal graph defined by the domain modeller, and sensori-informaton integrated into it as probabilities for the cause-effect exchange edges in the causal graph).
