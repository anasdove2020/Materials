# C#

## Class

## Object

## Access Modifier
1. Public (Accessible from anywhere)
2. Private (Accessible only within containing class)
3. Protected (Accessible within containing class and by derived class)
4. Internal (Accessible only within the same assembly/project)
5. Protected Internal (Accessible from derived class {same assembly or different assembly} or any class in the same assembly)
6. Private Protected (Accessible within the containing class or derived class only if they are in same assembly)

## Interface

- Define a contract (specify what class should do)
- Enable polymorphism (different class can implement the same interface)
- Allow multiple inheritance
- Define what to do, not how (enable flexible, maintainable, and testable code)

## Abstact

- It meant to be a base class for other classes
- Define shared logic or common base functionality
- Partial implementation
- Force derived class to implement specific methods

It is useful:
- We want common code in one place.
- Allow extension in child classes.

## Virtual

- Base class gives default behavior
- Derived class can override the method to provide their own specialized behavior
- Enable polymorphism with default implementation

## Read Only

- Field can only be assigned once (when it's declared or inside constructor)
- After that value can't be changed
- To make data immutable after initialization
- Protect important data from accidental changes

## Const

- Value must be assigned at declaration
- Value cannot change anywhere in code

## Static

- A member (class, property, method) belongs to the type itself, not to an instance of the class

## Constructor

## Collection

## IEnumerable

## IQueryable

## Dictionary

## List 

## HastSeh

## Boxing

- Convert value type to object type

```
int a = 10;
object obj = a;
```

## Unboxing

- Convert object type to value type

```
object obj = x;
int y = (int)obj;
```
