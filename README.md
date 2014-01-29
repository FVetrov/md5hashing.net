* Website: [md5#hasing.net](http://md5hashing.net)
* Changelog: [Versioning and functionality](https://github.com/FVetrov/md5hashing.net/wiki/Change-Log)
* Discussion: [Report about bugs or suggest improvements](https://github.com/FVetrov/md5hashing.net/issues)

--------------

####Few words:
At md5hashing.net you can hash (encrypt, encode) any string into 47! different hash types. As you know - decryption of hash is impossible, but we offer reverse decryption via our database (~245M records, and counting). Additionally we offer Encryption with salt - this method allows to decode your string later (But you need to remember the SALT).

--------------

####How it works:
Main database is based on MongoDB.
In our DB we store millions (soon billions) of words and different strings aside to their hash.
**Note:** all DB record was provided by users or taken from open dictionaries and digital libraries.

#####Structure:
* PHP Cache - (~1K records of super popular requests)
* MongoDB Special Indexed Collection (MDBSIC) - (~200K records of popular and last requests)
* MongoDB - (~300M records of all requests)

Any request goes thru PHP Cache -> MDBSIC -> MongoDB and vice versa.
Keys for all storages is original string and MD5 hash (as most popular searchable value right now, later we may change it or make/add other keys)
That gives very high availability of any part of service.

#####Encoding
* String provided by user, or taken from open resource (dictionary, library), or even random generated string goes thru all supported hashing algorithms
* Next we store string and it's hashes to PHP Cache, MongoDB

#####Reverse Decoding
* Search for string provided by user in next order:
 - PHP Cache -> MDBSIC -> MongoDB
* If value is found on some level it will be added into lowest, in next order:
 - PHP Cache <- MDBSIC <- MongoDB

------------

####Additional functionality
#####[Hash type checker](http://md5hashing.net/hash_type_checker)
Check based on Regular Expression
Returns to user possible variants of hash type

#####[Password Generator](http://md5hashing.net/generate/password)
* **Memorable and Human-readable** passwords based on word, and phrase library - we take random words and combine them in random order
* **Random** password - we take letter, numbers and symbols and combine them in random order

#####[Crypter](http://md5hashing.net/crypto)
* Encrypt/Decrypt text (multi-line string) with salt / aka password

#####[Anonymous secure/crypto chat](http://md5hashing.net/crypto/chat)
* Simple anonymous chat
* Password protected
* All messages is encrypted
* No sign up/registration
* No login (you need only chat name and password)
* free iFrame plugin

For contacts, questions, suggestions please use - [GitHub Issues](https://github.com/FVetrov/md5hashing.net/issues)
