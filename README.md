# Most important new features in C++11

## Smart pointers

## Move semantics

## Lambda functions

## std::function

## Automatic type deduction

In many cases an object's declaration includes the initializer, thus the compiler infers the type of a variable at the point of declaration. It is most useful when the type is either hard to know or hard to write.

Instead of 
```
std::vector<int>::const_iterator itMyVector = myVector.begin();
```
you can write
```
auto itMyVector = myVector.begin();
```


## Decltype

## Initializer lists

## Defaulted and deleted functions

## Strongly-typed enum

## Range based for loop

## nullptr

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

## Unicode string literals
