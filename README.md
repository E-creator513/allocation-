# allocation-
yet unix environment 
### Prerequisites for this lab session are the:

- Object header
- Virtual Memory and Memory Layout
- Mutator, Collector, Allocator
### Build & run

- To build you need to type `make` in the root directory.
- After that to run you need to type `./build/allocator`
### Example of execution 
```
____________Test ##1 ____________
Init heap
  --- Heap ---
     start   capacity   status   contents
 0x4040000      12271     free   0000
____________Test ##2 ____________
Normal successful memory allocation
  --- Heap ---
     start   capacity   status   contents
 0x4040000        100    taken   0000
 0x4040075        400    taken   0000
 0x4040216        100    taken   0000
 0x404028b         24    taken   0000
 0x40402b4       1000    taken   0000
 0x40406ad      43330     free   0000
____________Test ##3 ____________
Freeing one block from several allocated
  --- Heap ---
     start   capacity   status   contents
 0x4040000        100    taken   0000
 0x4040075        400    taken   0000
 0x4040216        100    taken   0000
 0x404028b         24     free   0000
 0x40402b4       1000    taken   0000
 0x40406ad      43330     free   0000
____________Test ##4 ____________
Freeing two blocks from several allocated
  --- Heap ---
     start   capacity   status   contents
 0x4040000        517     free   0000
 0x4040216        100    taken   0000
 0x404028b         24     free   0000
 0x40402b4       1000    taken   0000
 0x40406ad      43330     free   0000
____________Test ##5 ____________
The memory is over, the new region of memory expands the old
  --- Heap ---
     start   capacity   status   contents
 0x4040000        200    taken   0000
 0x40400d9        300     free   0000
 0x4040216        100    taken   0000
 0x404028b         24     free   0000
 0x40402b4       1000    taken   0000
 0x40406ad      10000    taken   0000
 0x4042dce      10300    taken   0000
 0x404561b        666    taken   0000
 0x40458c6      55081     free   0000
____________Test ##6 ____________
Free heap
  --- Heap ---
     start   capacity   status   contents
 0x4040000      77807     free   0000
```
