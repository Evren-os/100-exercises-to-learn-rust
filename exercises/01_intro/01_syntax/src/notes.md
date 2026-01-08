Functions Syntax
Defined by the `fn` keyword.
**Structure:**
```
fn <function_name>(<input params>) -> <return_type> { 
    <body> 
}
```

Example:
fn greeting() -> &'static str {
    "I'm ready to learn Rust!"
}

String Slices (&str)
*   Concept: A part or a view of a larger block of text data; essentially just a piece of a whole string.
*   Referencing: Basically means pointing towards that string data.
*   Technical Distinction:
    *   Technically, str is the "string slice" (the data).
    *   & is the "reference" (the pointer).
    *   Note: In Rust, we effectively cannot use str on its own without &. Therefore, when we say "string slice" or see &str, we are referring to the reference to the slice.

'static Lifetime
*   This indicates how long the data will exist.
*   'static specifically means the data lives forever (the entire duration the program runs).

Return Type
If a function doesn't produce any result, it returns an empty value called "unit", written as `()`. If a function doesn't produce any result, we don't have to define the return type in the function definition, Rust already assumes it. Like :
```
fn test_welcome() {
    assert_eq!(greeting(), "I'm ready to learn Rust!");
}
```
We can write it like this (but we don't need it) :
```
// Spelling out the unit return type explicitly
fn test_welcome() -> () {
    assert_eq!(greeting(), "I'm ready to learn Rust!");
}
```

Returning Values
*   Implicit Return: Inside a function, the very last line (without a semicolon) is automatically the output/result. We don't have to "explicitly" return it; Rust knows it is the output.
*   Explicit Return: We can use the return keyword to return a value early. If used in the middle of a function, execution stops immediately and returns that value without running the rest of the code.
*   Idiomatic Rust: If the value is at the end of the function, omit the return keyword. This is best practice.

Input Parameters
Parameters are declared by their name, followed by a colon, followed by their type.
Syntax: name: type
Example:
fn greet(param1: &str) { ... }

Type Annotations
*   Statically Typed: The Rust compiler checks the data type of every value in the code before running the program. This process is called "static analysis".
*   Rule: Every single value in Rust has a type, and that type must be known to the compiler at compile-time.