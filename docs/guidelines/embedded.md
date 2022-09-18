This section addresses specific quality assurances for embedded software development. Other software does not need to abide by these low-level assurances.

## Memory and stack size management

Care shall be made to the following points:

+ no recursion
+ ensure there are no memory leaks
+ minimize use of non-static local variables (to minimize stack usage)
+ minimized nested function calls
+ no dynamic memory allocation after program initialization
+ no recursion


## Critical regions

Certain types of hardware interfaces (e.g. some memory accesses) are intolerant to interruption. Critical regions are sections of code that cannot be interrupted regardless of what else is occurring across the system. Critical regions shall be called out explicitly via comments and will be minimally sized to accomplish the necessary atomic function.

!!! note
    When making use of atomic operations, try to make use of the language's features. For example, both [C++ 20](https://en.cppreference.com/w/cpp/atomic) and [Rust](https://doc.rust-lang.org/core/sync/atomic/index.html) provide helpers for lockless concurrent programming.

## Interrupts

Interrupt-driven code will be minimally sized, called out explicitly via comments, and thoroughly documented in the detail design.

## Long-duration functions

All functions that perform work over a significant amount of time shall be designed to work in chunks, precluding CPU hogging.

Where necessary (hardware interfaces), callback functions will be used to enable nominal functionality of the system while awaiting a response. Under no circumstances is it acceptable to hold the processor in order to wait for an external interface.

In languages which support `async` co-routines in embedded software (i.e. without repeated dynamic memory allocations), these can be used if thread safety can be guaranteed at compiled time.
