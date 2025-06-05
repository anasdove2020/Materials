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

- Define what class should do
- Allow each class to decide how it will do it

## Abstact

- Define shared logic
- Force derived class to implement specific methods

It is useful:
- We want common code in one place.
- Allow extension in child classes.

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
