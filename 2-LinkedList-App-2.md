# Common Linked List Applications
## Hash Tables
Hash tables, also known as hash maps, are data structures that provide efficient key-value pair storage and retrieval. While hash tables are often implemented using arrays, linked lists can be utilized in handling collisions within the hash table.

In a hash table, keys are hashed to determine their corresponding index in the underlying array. Each index holds a linked list that stores the key-value pairs. In the case of collisions, where two keys map to the same index, the linked list allows for chaining, ensuring multiple elements can be stored at the same index.

Hash tables support the following primary operations:

* **Insertion:** Adds a key-value pair to the hash table.
* **Retrieval:** Retrieves the value associated with a given key.
* **Deletion:** Removes a key-value pair from the hash table.

Here's an example of a hash table using linked lists for collision handling:

````python
class HashTable:
    def __init__(self, size):
        self.size = size
        self.buckets = [LinkedList() for _ in range(size)]
    
    def _hash(self, key):
        return hash(key) % self.size
    
    def insert(self, key, value):
        index = self._hash(key)
        bucket = self.buckets[index]
        bucket.insert(key, value)
    
    def retrieve(self, key):
        index = self._hash(key)
        bucket = self.buckets[index]
        return bucket.retrieve(key)
    
    def delete(self, key):
        index = self._hash(key)
        bucket = self.buckets[index]
        bucket.delete(key)
````
In this example, the HashTable class creates an array of linked lists called buckets. The size attribute determines the number of buckets in the hash table.

* The _hash method takes a key as input and uses the hash() function to compute the hash value. It then applies the modulo operation with the size to obtain the index of the bucket for the key.

* The insert method calculates the index for the key and retrieves the corresponding bucket. It then calls the insert method of the linked list to add the key-value pair to the bucket.

* The retrieve method calculates the index for the key and retrieves the corresponding bucket. It calls the retrieve method of the linked list to retrieve the value associated with the key.

* The delete method calculates the index for the key and retrieves the corresponding bucket. It calls the delete method of the linked list to remove the key-value pair from the bucket.

### Example

Let's see an example of using a hash table with linked lists for collision handling:

````python
# Create a hash table
my_table = HashTable(10)

# Insert key-value pairs
my_table.insert("apple", 5)
my_table.insert("banana", 10)
my_table.insert("cherry", 15)

# Retrieve values
print(my_table.retrieve("apple"))
print(my_table.retrieve("banana"))

# Delete a key-value pair
my_table.delete("cherry")
````
In this example, we create a hash table my_table with a size of 10. We then insert three key-value pairs into the hash table, retrieve the values for two keys, and delete a key-value pair. The retrieved values and the deletion operation demonstrate the functionality of the hash table.


[GO BACK - LINKED LIST Main](2-LinkedList.md)

[NEXT - LINKED LIST - Problem 1](2-LinkedList-Prob-1.md)