# Hashing

### Hashing Algorithms and Security

A hash is a long hexadecimal (usually) summary of what's in a file, it is created by feeding the file into a hashing algorithm. These hashes are usually irreversible, with the only way of deciphering being brute forcing every input.

These algorithms need to be fast (but not too quick or it's easily broken), and need to have an avalanche effect where if one bit of the hash or file is changed then the entire hash is completely different, hashes can't be the same as well (this is called a 'hash collision').

