# File System

## Continuous Allocation
Allocate a continuous set of blocks to a file when the file created.

* Pre-allocation: Since we need to decide how much block to allocate to the file.

* Single entry for each file.

* Best view of the individual file.

* Multiple blocks can be read in at a time-- improve I/O.

* Easy to retrieve a single block

#### Disadvantage
* External fragmentation
* Declare the size of the file at the time of creation.

## Linked Allocation(Non-contiguous allocation)
Allocation is on an individual block basis, each block contains a **pointer to the next block** in the chain.

* Single entry for each file.

* Allocate blocks as needed

* Any free block can be added to the chain.

* Increase in file size is always possible as long as free disk block is available.

* No external fragmentation

#### Disadvantage

* Internal fragmentation: only exists in the last disk block of file.

* Overhead of maintaining the pointer in every disk block.

* If the pointer of any disk block is lost, the file will be truncated.

* Supports only the sequential access of files.

## Indexed Allocation
The file allocation table contains a separate one-level index for each file: The index has one entry for each block allocated to the file.

The most popular form of file allocation.

![Indexed allocation image](https://cdncontribute.geeksforgeeks.org/wp-content/uploads/directory-indexing.jpg)

* Either fixed-size blocks or variable-sized blocks.

* Allocation by blocks eliminates external fragmentation.

* Variable-size blocks improves locality

* Supports both sequential and direct access to the file
