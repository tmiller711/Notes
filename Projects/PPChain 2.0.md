- Create main logic in Rust
- Create the wallet GUI in PyQT

- General overview:
	- A decentralized network of nodes that communicate through TCP
	- A validation will take place every 5 minutes, this is called a block.
	- Each node will store a copy of the blockchain so they can validate it
	- Once you make a transaction you will send this transaction to all of the other nodes. These nodes will add the transaction to the end of the block. Once a miner verifies this block (at first I'll just use a command to verify it before mining get added) it will become an actual block and the transactions will be respected on the chain

- The chain
	- We could either have one file that is the file that stores all the validated blocks in one (this is what bitcoin does with it's blk.dat file)
	- Or we could have each block as a serparate file and have some marker to say if it has been validated or not

- Node communication
	- When a new node joins the network they have to discover other nodes to join the network. They do this by sending a 'version' message. This contains basic identifying information including:
		- 'PROTOCOL_VERSION' Might replace this with software version
		- the IP address on the remote node as seen from the node that sent the message
		- The ip address of the node that sent the message
		- 'BestHeight' the block height of this node's blockchain. Which is the number of blocks the node has
	- Once a new node has made a connection with one node that node will add it to it's available nodes and then send the IP address to all the nodes it knows and so on. The node a new node can connect to could be a 'seed' node. This is a long standing node that has many connections it knows about
	- Now that all/most of the nodes in the network have the new nodes IP the node has to ask for the IPs of everyone else
	- A node only needs to know a few other nodes as just by sending stuff to those nodes it can branch out to all other nodes
	- If a node can no longer connect to any of the nodes that it remembers than it will use the seed node to get more IPs

- Full Nodes (what all the nodes in PP chain will be)
	- Contain a full blockchain with all transactions
	- Can independently verify any transaction without reliance on any other node or source of information
	- Does rely on the network to receive updates about new blocks of transactions which it then verifies and incorporates into its local copy of the chain
	- 

- What a block will contain:
	- Block header
	- Transaction counter (number of transaction stored in the block)
		- Block header (contains information about the block) SEE BELOW FOR MORE DETAILS
	- All the transactions within the block
- What the block header contains
	- Version of the cryptocurrency being used
	- Previous block hash
	- Current blocks hash consisting off all the transactions within the block
	- Time

- A block's job
	- Check the coin supply
	- Prevent bitcoin from being spent twice
	- 