# Hash Table
A simple Python implementation of a hash table using a dictionary to store key-value pairs.

The HashTable class includes methods for adding, removing, and looking up values using a custom hash function.

# Features
* Create a hash table.
* Generate hash values from strings.
* Add key-value pairs.
* Look up values using a key.
* Remove key-value pairs.
* Handle hash collisions by storing multiple keys under the same hash value.
* Automatically remove empty hash buckets.

# HashTable Class
The HashTable class manages the collection of stored key-value pairs.

## HashTable()
Creates a new, empty hash table.

table = HashTable()

The table starts with an empty collection dictionary.

## hash(string)
Creates a hash value for a string by adding together the Unicode value of each character.

table.hash("hello")

For example, each character in "hello" is converted using Python's ord() function, and the values are added together.

## add(key, value)
Adds a key-value pair to the hash table.

table.add("name", "Alice")

table.add("age", 25)

The key is hashed first, and the value is stored using the resulting hash value.

## remove(key)
Removes a key-value pair from the hash table.

table.remove("name")

If removing the key leaves an empty hash bucket, the empty bucket is also removed.

## lookup(key)
Searches for a key and returns its associated value.

value = table.lookup("age")

print(value)

If the key does not exist, the method returns None.

# Hash Collisions
Different keys can sometimes produce the same hash value. This implementation handles collisions by storing multiple key-value pairs inside a nested dictionary.

For example:

Hash value

    |
    
    +-- key1: value1
    
    +-- key2: value2

The actual key is also checked during lookup and removal, so keys with the same hash value can coexist.

# Example
table = HashTable()

table.add("name", "Alice")

table.add("city", "Charlotte")

table.add("age", 25)

print(table.lookup("name"))

print(table.lookup("city"))

print(table.lookup("age"))

table.remove("age")

print(table.lookup("age"))

Output:

Alice

Charlotte

25

None

# Requirements
* Python 3.x
* No external libraries are required.
