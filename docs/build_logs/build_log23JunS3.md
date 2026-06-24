
- Date: 23 June 2026 (Session 2)
Duration: 2 Hours 30 mins 
Goal():
Implementing different functions such as push_back,shrink in dynamic array and creating the abstractclass for the common methods like Insert(),remove(),size(),capacity().Complete Implementation of dynamic array and start working with linked list.

Problem():
Various functions show undefined behaviour. Some declarations are wrong using malloc and not using pplacment new for the constructor call.
**Error 1**
main.cpp:85:5: error: expected unqualified-id before 'catch'
     catch(const std::exception& e)
     ^~~~~
main.cpp:92:5: error: expected unqualified-id before 'return'
     return 0;
     ^~~~~~
main.cpp:93:1: error: expected declaration before '}' token
 }
 ^

What I tried:
I reasearched about the error and i found that it was just due to the declaration mistake i have done in the creating to scope to the function. After that I tried and implemented the functions for the dynamic array and thouroughly tested the dynamic array and now started to work on the linked list.

I understood the way to read the errors and how to handle them especially during the generic implementation. 

I used try catch  in some block of code for better exception handling 

I have also tried the valgrind for the memory leak check. I have attached the report for the same.

==725== Memcheck, a memory error detector
==725== Copyright (C) 2002-2024, and GNU GPL'd, by Julian Seward et al.
==725== Using Valgrind-3.26.0 and LibVEX; rerun with -h for copyright info
==725== Command: ./main.cpp
==725==
: not found 2:
./main.cpp: 3: Syntax error: "(" unexpected
==725==
==725== HEAP SUMMARY:
==725==     in use at exit: 1,100 bytes in 33 blocks
==725==   total heap usage: 38 allocs, 5 frees, 3,164 bytes allocated
==725==
==725== LEAK SUMMARY:
==725==    definitely lost: 0 bytes in 0 blocks
==725==    indirectly lost: 0 bytes in 0 blocks
==725==      possibly lost: 0 bytes in 0 blocks
==725==    still reachable: 1,100 bytes in 33 blocks
==725==         suppressed: 0 bytes in 0 blocks
==725== Reachable blocks (those to which a pointer was found) are not shown.
==725== To see them, rerun with: --leak-check=full --show-leak-kinds=all
==725==
==725== For lists of detected and suppressed errors, rerun with: -s
==725== ERROR SUMMARY: 0 errors from 0 contexts (suppressed: 0 from 0)

Outcome:
Implemented the dynamic array and thouroughly test the same.
