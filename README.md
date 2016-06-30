* Website: [md5#hasing.net](http://md5hashing.net)
* Changelog: [Versioning and functionality](https://github.com/FVetrov/md5hashing.net/wiki/Change-Log)
* Discussion: [Report about bug or suggest an improvement](https://github.com/FVetrov/md5hashing.net/issues)
* Q&A: [Ask a question](https://md5hashing.net/QnA)

-------------

#### Few words:
At md5hashing.net you can hash (*encrypt*) any string into 66! different hash types. As you probably know - decryption of any hash is impossible, but we offer reverse decryption via our database (~1000M records, and counting). Additionally we offer Encryption with password (*salt*) - this method allows to encrypt string with strongest algorithm and decrypt it later, you only need to remember the password (*salt*).

--------------

#### How it works:
We use stack of MongoDBs (*shards + replicas*).
In our DB we store billions of strings aside to their hash.
**Note:** all DB record was provided by users or taken from open dictionaries and digital libraries.

##### Structure:
1. Application fence
2. Application nodes (*round robin*)
3. MongoDB Shards
4. MongoDB replicas

Special set of indexes used for best performance

##### Hashing
1. String goes throught all supported hashing algorithms
2. Next we store string and its hashes to available MongoDB replica, next going to be synchronised with all shards and replicas

##### Crypto Chat
1. User types new message
2. Right before message is going to be sent to server it is encrypted with room's password
3. When other users received new message it's going to be decrypted with room's password
4. Decrypted message shown to all participants

------------

#### Additional functionality
##### [Hash type checker](http://md5hashing.net/hash_type_checker)
Check based on Regular Expression
Returns to user possible variants of hash type

##### [Disposable anonymous mailbox](http://md5hashing.net/anonymous/email)
* Disposable mailbox
* Random unlimited mailbox names (addresses)
* Support all kind of attachments
* Free of charge and does not require any registration

##### [Cryptography Questions & Answers](http://md5hashing.net/QnA)
* Ask a question about cryptography anonymously
* Get the best solution from community members

##### [Password Generator](http://md5hashing.net/generate/password)
* **Memorable and Human-readable** passwords based on word generator library

##### [Crypter](http://md5hashing.net/crypto)
* Encrypt/Decrypt text (*multi-line string*) with salt / a.k.a. password

##### [Anonymous secure/crypto chat](http://md5hashing.net/crypto/chat)
* Simple anonymous chat
* Password protected
* All messages is encrypted
* No sign up/registration
* No login (you need only chat name and password)
* Free iFrame plugin
* Open rooms
* Message TTL

##### [Anonymous open chat](http://md5hashing.net/open/chat)
* Simple anonymous and open chat
* No sign up/registration
* No login

For contacts, questions, suggestions please use - [GitHub Issues](https://github.com/FVetrov/md5hashing.net/issues)
