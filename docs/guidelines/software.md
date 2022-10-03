The following guidelines apply to any software project, and are applied for the Nyx tools.

## Reusability

First and foremost, if a thoroughly used and tested software exists and fulfills all of the requirements, use it, do not rewrite one from scratch.

!!! note
    This is especially applicable to math libraries like pseudo random number generators or linear algebra libraries: these are complicated algorithms where it's easy to get something wrong, and even easier to convince a team that the implementation is correct but in fact wrong.

If new software is in fact needed, the development of self-contained and reusable software components and libraries is strongly recommended. This allows them to be leveraged in future developments. 

## Variable naming

Variable names should be self-documenting as often as possible, i.e. any developer should be able to understand variable usage based on the name alone. If use of a self documenting name is cumbersome and leads to increased difficulty in reading, then an abbreviated name may be used. Variables with abbreviated or ambiguous names must be commented in detail. Variables that have units should be explicit either in name, or in type.

!!! example
    + For the norm of a radius of a vector in kilometers, use `radius_km` instead of `radius`. For the radial vector, use `radius_vec_km`.
    + If units are available as types, one should prefer those if the runtime overhead is negligible. For example, with `hifitime`, one can define a nanosecond precision duration as `let my_duration: Duration = 2.0.minutes()`.

## Variable initialization

Variables are always initialized with a value, unless the language prevents their use without a value at compilation time.

Initialization prevents use of garbage bytes, allocates any memory necessary for variables to minimize opportunities for memory leaks, and precludes dynamic memory allocation. Even if they will be mutated by a function call soon after their declaration, variables should still be initialized unless said function is not formally verified to always assign a value: such formal verification must be checked in the automated testing pipeline to prevent function behavior change to affect the potentially uninitialized value.

## Variable type

In strongly typed languages, variable types shall be chosen to fulfill precisely their purpose and no more, whose size is fixed at compiled time regardless of the platform.

!!! example
    + For loops, use `size_t` and `usize` in C and Rust, instead of the generic `int`.
    + For any integer, make sure to use a platform independent type from `<types.h>` such as `uint32_t` for an unsigned 32-bit integer instead of the generic `int` for an integer.

## Comments

Comments are expected to provide a knowledgeable developer with enough context to assist with debugging and maintenance activities.

All algorithms are described via comments or a link to a versioned document describing said algorithm is to be provided. Any unusual or interesting code will be described with comments. All code and header files contain high-level descriptions, and usage directions in file headers describing the intent of the file. Where applicable, all explicit pointer or memory address usage should be commented.

No commented code shall ever make its way into the main branch: commented code is a crime against clarity and maintainability.

## Function size and code complexity

Functions should be designed to minimize branching, function size, and complexity, thereby increasing their readability and maintainability. Depending on the project, a maximum cyclomatic complexity of functions may be set, although exceptions should be allowed as some functions are necessarily complex.

## Code formatting

Automatic formatting of the code is strongly recommended: this ensures that all of the code follows the same style, improving maintainability and reducing cognitive overload when reading code. The main purpose is to find a style that the team can agree on: consensus is key here, otherwise no one will comply with the rules.

For C and C++, `clang-formatter` is an excellent choice. For Python, `yapf`, `black`, or any other configurable tool should work well. For Rust, `rustfmt` is the default and perfectly fine tool.

## File naming and size

Source code files should perform minimal numbers of functions. This leads to a larger number of smaller sized source files, allowing easier maintenance and minimizing complexity.

## Programming language

Each project should define which languages it should support at an API level. If the API level does not matter, then the language should be chosen based on its features and the familiarity of the developers with said language.

!!! example
    Nyx is expected to only ever exposes its API to Rust and Python. However, ANISE is expected to support Rust, C, FORTRAN, and Python, since these are all languages that may benefit from an ANISE interface.
