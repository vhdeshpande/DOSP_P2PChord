# Project 3: Chord - P2P System and Simulation
This project aims to simulate the Chord protocol implementing the Scalable Key Lookup using the actor model in Erlang.
### Authors:
* Vaibhavi Deshpande
* Ishan Kunkolikar
### Pre-requisites:
* Erlang/OTP version - 25.1
### Steps to run:
Commands to start the algorithm:
``` 
c(chord).
chord : start_main_process ( number_of_nodes, number_of_requests ).
```
Where ‘number_of_nodes’ is the number of nodes to be created in the peer-to-peer system and ‘number_of_requests’ is the number of requests that each node has to make.

### What is working?
* Creating the Chord Ring and Fixing Finger Tables:
According to the number of nodes received in the input, the chord ring is created by spawning each peer actor/node and each node is assigned a key using consistent hashing enabling the nodes to join the network. Every node maintains its successor node, predecessor nodes, and finger tables which are stabilized and fixed periodically. The information stored in the finger table should be updated periodically as different nodes join the system.
* Requests Lookup using Scalable Key Lookup and Find Successor:
Once the chord ring is created, every node randomly generates a request according to the input received. For any request generated, the node searches the finger table using find_successor in accordance with the algorithm from the paper which returns the successor node if the node to lookup is between that node and the successor otherwise it searches for the node whose ID most immediately precedes the ID of the node which is requested and it generates a request to that node.
* Average Hop Count: The average hop is calculated after every node in the system completes the specified number of requests from the input value.

### Largest network
* Maximum number of nodes: 4000
* Maximum number of requests: 10 * 4000 = 40,000
