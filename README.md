# Most important new features in C++11

## Smart pointers

## Move semantics

## Automatic type deduction: `auto`

In many cases an object's declaration includes the initializer, thus the compiler infers the type of a variable at the point of declaration. It is most useful when the type is either hard to know or hard to write.

Instead of 
```
std::vector<int>::const_iterator itMyVector = myVector.begin();
```
you can write
```
auto itMyVector = myVector.begin();
```

Given `const auto& i = expr;`, the type of i is exactly the type of the argument u in an imaginary `template template<class U> void f(const U& u)` if the function call `f(expr)` was compiled.

If `auto` is used to declare multiple variables, the deduced types must match.
```
auto i = 0, d = 0.0   // Error
auto i = 0, *p = &i;  // OK
```

Please don't do this: `auto i = 3;`

## Lambda functions

A lambda is an unnamed function. A lambda expression lets you define a function locally, at the place of the call, eliminating the tedium and security risks of function objects. The primary use for a lambda is to specify a simple action to be performed by some function. Use lambdas only for common and/or simple actions.

A lambda expression has the form:
```
[capture](parameters)->return-type {body}
```
Example:
```
auto nth_fibonacci = [](int n, auto& self) -> int
{
  if (n == 0)
  {
    return 0;
  }
  if (n == 1)
  {
    return 1;
  }
  return self(n - 1, self) + self(n - 2, self);
}
```
The return-type is optional.
```
auto isEven = [](int n)
{
  return n % 2;
}
```
A lambda expression can access (a.k.a capture) local variables in the scope in which it is used. You can capture by value or by reference.
```
int n = 314;
auto func = [n](int d){ n += d; }   // Capture by value. n is unchanged
auto func2 = [&n](int d){ n+= d; }  // Capture by reference. n is incremented
```
You can capture all local variables by value or by reference.
```
auto func = [=](int d){ n += d; }   // Capture all local variable by value
auto func2 = [&](int d){ n+= d; }  // Capture all local variable by reference
```
You can pass a lambda as a function parameter. Check [std::for_each](#std::for_each) below

## std::function

## Decltype

## Initializer lists

## Defaulted and deleted functions

## Strongly-typed enum

## Range based for loop

## nullptr

The previously used `NULL` is actually just a macro, what created many bugs
```
#define NULL 0
```
The new `nullptr` is a strongly-typed literal and not an integer. `nullptr` is applicable to all pointer categories, including function pointers and pointers to members.

Please use the type-safe `nullptr` instead of `NULL`.

In newer implementation versions the `NULL` macro is also redefined:
```
#define NULL nullptr
```

## rvalue reference

## Variadic templates

## Delegating constructors

## override

## final

## std::thread

## Unordered containers
### std::unordered_map
### std::unordered_multimap
### std::unordered_set
### std::unordered_multiset

## noexcept

## std::tuple

## std::for_each

## std::transform

## Unicode string literals
