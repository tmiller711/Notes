1. Nodes
	- node_bootstrapping in nodes.rs connects to a seed node and exchanges addresses with it
	- new_node in nodes.rs is called when the node receives the message "new node : ". This function checks wether the current node already has this node, if not it will add it, and then it will send this node to all of it's known nodes
	- If a node receives a message "\*node : " it will check if it already knows about the node it just received. If it does not then it will add it

2. Blockchain
	- blah
	- blah

- New node sequence {DONE}:
	- node_bootstrapping paired with new_node
	- blockchain_startup paired with send_blocks

- Having a working blockchain
- Being able to make transactions