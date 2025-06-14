# C# Interview

## Fresher

1. How C# different with C



2. What is inheritance? Does C# support multiple inheritance?

3. What is the difference between an Array and ArrayList in C#?

4. What are Generics in C#?

5. What are extension methods in C#?

6. What are the differences between ref and out keywords?

7. What is the difference between an abstract class and an interface?

8. What is a managed and unmanaged code?

9. What are the types of classes in C#?

10. What is garbage collection in C#?

11. What is Common Language Runtime (CLR)?


## Experienced

1. What are partial classes in C#?

2. What is the difference between String and StringBuilder in C#?

3. What is the difference between constant and readonly in C#?

4. What is Reflection in C#?

5. What are the different ways in which a method can be Overloaded in C#?

6. Difference between the Equality Operator (==) and Equals() Method in C#?

7. What are Indexers in C#?

8. What are the Arrays in C#?

9. What is the difference between late binding and early binding in C#?

10. What are Properties in C#?

11. What is Boxing and Unboxing in C#?


Answer:

### Late Binding vs Early Binding

- Primary concept of Polymorphism
- Binding = Connecting a method call to the actual method implementation
- Early binding
  - The method to be called is known at Compile Time
  - Faster and Safer
  - Less flexible
  - Supports intellisense

```
PremiumCustomer p = new PremiumCustomer();
p.CalculateBill();
```

- Late binding
  - The method determined at runtime
  - More flexible
  - Slower
  - It happens in Polymorphism using virtual/override
  - Using dynamic
  - Reflection
 
```
Customer c = new PremiumCustomer();
c.CalculateBill();
```

```
dynamic c = GetCustomer();
c.CalculateBill();
```

### Properties

- Public members of class
- Provide ability to access private member of class
- Basic principle of encapsulation

### Boxing vs Unboxing

Boxing = Converts value type (int, char, bool) to reference type (object) - Implisit conversion process

```
int num = 123;
Object obj = num; // Boxing
```

Unboxing = Converts reference type (object) to value type (int, char, bool) - Explicit conversion process

```
int num = 123;
Object obj = num; // Boxing
int i = (int)obj; // Unboxing
```


