# SOLID

A set of 5 design principles in OOP to help use write clean, flexible, and maintainable code.

## Single Responsibility Principle

SRP means:
- A class should have only one reason to change.

It is useful:
- Easier to maintain
  - Each class does only one thing.
  - If booking logic changes => change only RoomService
  - If DB query changes => change only RoomRepository
  - We don't break unrelated code by accident
- Easier to test
- Easier for teamwork

Example:
1. RoomRepository

- Responsible for Data Access (database operation)

2. RoomService

- Responsible for business logic (rules for booking, availability)

3. RoomController

- Responsible for handling HTTP request and sending response (API endpoints)

## Open Close Principle Principle

OCP means:
- Open for extension
- Close for modification
- We should be able to add new behavior without changing existing code

It is useful:
- Add new features safely
- Less risk of bug in old code
- Follows "plug and play" style
- Easier testing and extension

Example:
- Payment
  - We want to support multile payment methods:
    - Credit Card
    - PayPal
    - Others
   
Without OCP:
```
public class PaymentService
{
    public void Pay(string method)
    {
        if (method == "CreditCard")
        {
            // pay with credit card
        }
        else if (method == "PayPal")
        {
            // pay with PayPal
        }
        // every time you add a new method → must modify this class
    }
}
```

With OCP:
- Use abstraction (base class or interface)
```
public interface IPaymentMethod
{
    void Pay(decimal amount);
}
```
- Then each methods implement it
```
public class CreditCardPayment : IPaymentMethod
{
    public void Pay(decimal amount)
    {
        Console.WriteLine("Paid by credit card.");
    }
}

public class PayPalPayment : IPaymentMethod
{
    public void Pay(decimal amount)
    {
        Console.WriteLine("Paid via PayPal.");
    }
}
```
- Main service uses abstraction
```
public class PaymentService
{
    public void ProcessPayment(IPaymentMethod method, decimal amount)
    {
        method.Pay(amount);
    }
}
```
- Use it anywhere (Plug and Play) style
```
var service = new PaymentService();

service.ProcessPayment(new CreditCardPayment(), 100);
service.ProcessPayment(new PayPalPayment(), 200);
```

## Liskov Substitution Principle

## Interface Segregation Principle

## Dependency Inversion Principle
