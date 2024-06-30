# B+ Tree Implementation
Welcome to the B+ Tree Implementation project! This project provides a comprehensive and efficient implementation of a B+ Tree in Java. A B+ Tree is an advanced data structure commonly used in databases and file systems to store and retrieve data efficiently. It is a self-balancing tree that maintains sorted data and allows for efficient insertion, deletion, and search operations.

## Features
**Balanced Tree Structure:** Ensures that the tree remains balanced with all leaf nodes at the same level, providing consistent performance for search, insert, and delete operations.\
**Efficient Data Storage:** Supports a high volume of data with efficient storage and retrieval.\
**Range Queries:** Supports range queries for values greater than, less than, or between specified keys.\
**Update Operations:** Allows updating the value associated with a specific key.\
**Level-order Printing:** Prints the tree in a pyramid shape, showing the keys in each node.\
**Serialization:** Implements Serializable for easy storage and retrieval of the tree structure.

## Class Overview
### BTree<TKey, TValue>
This is the main class for the B+ Tree implementation. It supports the following operations:

**Insert:** insert(TKey key, TValue value) - Inserts a new key and its associated value into the tree. \
**Search:** search(TKey key) - Searches for a key and returns its associated value. \
**Update:** update(TKey key, TValue value) - Updates the value of an existing key.\
**Delete:** delete(TKey key) - Deletes a key and its associated value from the tree.\
**Range Queries:**
1. searchRangeGreaterThan(TKey key, boolean inclusive)
2. searchRangeLessThan(TKey key, boolean inclusive)
3. searchRange(TKey key1, TKey key2) 

**Print:** print() - Prints the tree by level order showing the keys in each node in a pyramid shape.
### How It Works
Internal and Leaf Nodes
The B+ Tree consists of internal nodes and leaf nodes. Internal nodes store keys and references to child nodes, while leaf nodes store key-value pairs and pointers to the next leaf node.

Insert Operation
Find the appropriate leaf node for the key.
Insert the key-value pair into the leaf node.
Handle overflow by splitting the node and propagating the split to the parent node if necessary.
Delete Operation
Find the appropriate leaf node for the key.
Delete the key-value pair from the leaf node.
Handle underflow by redistributing keys or merging nodes and propagating the underflow to the parent node if necessary.
Search Operation
Find the appropriate leaf node for the key.
Return the value associated with the key if it exists.
Range Queries
Traverse the leaf nodes to find all key-value pairs within the specified range.
Print Operation
Traverse the tree in level order and print the keys in each node.
Example Usage
To use the B+ Tree implementation, create an instance of BTree and perform operations such as insert, search, update, delete, and range queries.

### Java - Sample code
Copy code
```
public class Main {
    public static void main(String[] args) {
        BTree<Integer, String> bTree = new BTree<>();
        
        // Insert keys and values
        bTree.insert(1, "one");
        bTree.insert(2, "two");
        bTree.insert(3, "three");
        
        // Search for a key
        String value = bTree.search(2);
        System.out.println("Value for key 2: " + value);
        
        // Update a key
        bTree.update(2, "TWO");
        System.out.println("Updated value for key 2: " + bTree.search(2));
        
        // Range query
        ArrayList<String> rangeValues = bTree.searchRange(1, 3);
        System.out.println("Values in range [1, 3]: " + rangeValues);
        
        // Print the tree
        bTree.print();
    }
}
```

## Contributing
Feel free to fork the repository and submit pull requests. Contributions are welcome!

## Contact
For any questions or suggestions, please contact me @*georgeelswefy@gmail.com*

Enjoy exploring the world of B+ Trees with this implementation! **Happy coding! 🚀**
