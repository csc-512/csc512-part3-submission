# THIS IS THE SUBMISSION REPOSITORY - PART 3
- Amay Gada | ahgada
- Mushtaq Shaikh | unity id

# Compilation

```bash
build the pass

$ mkdir build
$ cd build && cmake .. && make && cd ..

compile the logger code

$ gcc -shared -o liblogger.so logger.c -fPIC

set the correct path

$  export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:.

choose the test_program you want to test

$ clang -fpass-plugin=`echo build/branch_trace_pass/SkeletonPass.*` -fpass-plugin=`echo build/seminal_pass/SeminalPass.*` -g test<choose>.c -L. -llogger

the functioning of llvm pass will be proved by the above compilation command, however if you wish to run the binary output:

$ ./a.out

```

# Part 1 - branch trace
- This talks about the branch_trace_pass
- The code for this pass is in ./branch_trace_pass/Skeleton.cpp
- The details for this are in the repository
    - https://github.com/csc-512/csc512-part1-submission

# Part 2 - seminal behavior detection
- This talks about seminal behavior detection
- The code for this is in ./seminal_pass/SeminalPass.cpp   &   ./seminal_pass/sp.hpp
- The details for this are in this repository
    - https://github.com/csc-512/csc512-part2-submission

# About the test programs
- We have 7 test programs
- Each program shows how our code works on different structures in c.
- test0.c and test1.c are small programs derived from the problem statement document.
- test2.c and test3.c are 2 real world (but small) programs that our code works on
- test4.c, test5.c and test6.c are larger (greater than 200 lines) programs from the real world.
- All these test files show that the llvm pass can handle
    - multiple functions.
    - loops
    - function pointers
    - variable passing accross multiple passing to do def-use analysis
    - malloc
    - structs
    - multiple input functions like (fopen, fread, fwrite, fgetc, getc, scanf)
- Note these are the 7 programs that we submit for our final combined submissions too.

# Sources of the test programs
- test0.c and test1.c are modified programs from the course project document description
- test 2 is an interactive contact management system code.
- test3.c is a simple file encryption code which encrypt any given file.
- test4.c is a binary tree implementation to print words in a file alphabetically
    - https://github.com/TheAlgorithms/C/blob/master/data_structures/binary_trees/words_alphabetical.c
- test5.c is a segment tree code
    -  https://github.com/TheAlgorithms/C/blob/master/data_structures/binary_trees/segment_tree.c
- test6.c is a bank management system
    -  https://github.com/AlgolRhythm/C-Bank-Management-Program/tree/master