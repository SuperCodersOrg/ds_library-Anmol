
- Date: 23 June 2026 (Session 1)
Duration: 2 Hours 30 mins 
Goal():
Implementing the methods restricting the new keyword and using the concept of malloc calloc and mannual memory allocation for the implementation.


Problem():
1. The malloc cannot take the non-primitive.
2. The malloc checks and allocate the memory at the continous block when it finds it.


What I tried:
I reasearched about malloc and how the lifecycle of malloc works. the lifecycle is given below.

malloc()
   ↓
raw memory
   ↓
placement new
   ↓
constructed object
   ↓
explicit destructor call
   ↓
free()



Outcome:
Understood about the advantages and disadvantages of using malloc function for the mannual memory allocation.

