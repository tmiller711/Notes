- Combine the random access of an [[Array]] with the dynamism of a [[Singly-Linked Lists]]
- With hash functions the data we insert into the structure gives us a clue about where we will find the data
- Hash tables aren't good at ordering or sorting data
- A hash table consists of 2 main things:
	1 - A [[hash hunction]] which returns a nonnegative integer value called a hash code
	2 - An [[array]] capable of storing data of the type we wish to place into the data structure
	- The idea is we store our data in the [[array]] at the spot the [[hash function]] returned
- We make each element of the initial [[array]] a pointer to the head of a [[Singly-Linked Lists]], then if multiple pieces of data yield the same hash code we'll still be able to store it all