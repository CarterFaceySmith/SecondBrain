File systems ey? What is one and why do they matter?

## The Concept
Your file system *generallyyy* consists of two parts:
1. A collection of files storing related data
2. A directory structure for organising those files

## Files
A named collection of related information stored on secondary storage.
- Attributes vary by OS
- Different sorts of info can be stored
- OS can provide system calls to read a file, reposition within it, delete, truncate, etc.

## Access Methods
1. Sequential Access
2. Direct Access
	1. Other access methods are defined on top of the direct access method, which involves creating an index for the file which is then kept in memory

Note: In the event an index file is too large, another index is created *for* the index file lol.

## Partitioning

Storage devices can be subdivided into partitions which can each hold a seperate file system. Partitions can also be used as raw disk space or swap space.

Storages entities containing file systems are generally known as volumes.

## The Structure/Implementation

- IO Control
	- Made of device drivers and interrupt handlers
		- Device driver = translator from high-level to hardware specific instructions
	- Transfers information between main memory and disk system

- Basic File System
	- Issues generic commands to appropriate device driver

- File Organisation Module
	- Translates logic block addresses to physical block addresses for file system to transfer

- Logical File System
	- Manages the directory structure to provide file organisation module with information
	- Does this via some bullshit called a 'file-control block' which contains informatino about the file (ownership, permissions, location, etc.)

## On-Disk Data Structures
- Boot Control Block (per volume)
	- Contains information needed by system to boot into OS from that volume
- Volume Control Block (per volume)
	- Contains volume or partition details, eg number of blocks, their size, free-block count, etc.
- Directory Structure
- File Control Block (per file)

## In-Memory Data Structures
- In-memory directory-structure cache holds information of recently accessed directories
- System-wide open-file table has a copy of the FCB of each open file
- Per-process open-file table has a pointer to the appropriate entry in the sys open-file table

## Allocation Methods
1. Contiguous
	1. Each file occupies a set of contigous blocks on the disk
2. Linked
	1. Each file is linked list of disk blocks, these disk blocks may be anywhere on the disk
2. Indexed
	1. Brings together all the file pointers involved in linked into one location, the index block


See also:
- [[Operating Systems]]
- [[Computer Science Fundamentals]]
- 