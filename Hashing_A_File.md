# What is Hashing?
Hashing refers to the process of generating a fixed-size output from an input of variable size using the mathematical formulas known as hash functions.

- It mainly supports search, insert and delete in O(1) time on average which is more efficient than other popular data structures like arrays, Linked List and Self Balancing BST.

- We use hashing for dictionaries, frequency counting, maintaining data for quick access by key, etc.

- Real World Applications include Database Indexing, Cryptography, Caches, Symbol Table and Dictionaries.

Hash Set : Collection if unique keys  
Hash Map : Collection of key value pairs with keys being unique

- Wherever need to maintain sorted data along with search, insert and delete. We use a self balancing BST in these cases.

# Self-Balancing Binary Search Trees
Self-Balancing Binary Search Trees are height-balanced binary search trees that automatically keep the height as small as possible when insertion and deletion operations are performed on the tree. 

The most common examples of self-balancing binary search trees are 

- AVL Tree
- Red Black Tree and 
- Splay Tree

TreeSet  
TreeMap  

References: 
https://www.geeksforgeeks.org/introduction-to-hashing-2/ 
https://www.geeksforgeeks.org/self-balancing-binary-search-trees/ 


# Cryptographic Hash Function

MD2
MD5

SHA-1, SHA-2, and SHA-3 are all cryptographic hash functions that are part of the Secure Hash Algorithm (SHA) family: 

**SHA-1** 
Released in 1995, SHA-1 is no longer considered standard for most applications because it's considered weak and vulnerable. It produces a 160-bit (20-byte) hash value, which is typically represented as a 40-digit hexadecimal string. 
**SHA-2**
A family of algorithms that includes SHA-256 and SHA-512, SHA-2 is the current standard for data encryption and authentication on the web. SHA-2 uses longer hash values than SHA-1, making it more resistant to attacks. 
**SHA-3**
Released in 2015, SHA-3 is considered more secure and faster than SHA-2 on the hardware side. However, it's slower on the software side. SHA-3 may become the industry standard in the future once SHA-2 becomes unsafe or deprecated.

SHA encryptions are used for digital signatures, certificates, and cryptocurrencies. They are also integral to TLS/SSL protocols and secure communications.

SHA-1 
https://www.geeksforgeeks.org/sha-1-hash-in-java/
SHA-2 [SHA-224, SHA-256, SHA-384, SHA-512] 
https://www.geeksforgeeks.org/sha-512-hash-in-java/?ref=asr5
SHA-3 
https://www.geeksforgeeks.org/sha-256-and-sha-3/?ref=asr1

