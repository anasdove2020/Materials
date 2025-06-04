# OOP

- A way to build a program using Objects.
- Each object represent a real-world thing.
- Example objects: Hotel, Guest, Room

Hotel System using OOP

Using OOP
1. We create a class (template)
2. We create object (real items) from defined class
3. We organize our code like real-world things in a hotel

It means with OOP, our code becomes easier to manage, reusable and closer to real life. OOP makes code easier to organise because it groups related code together, like putting everything about a Room in one place. Reusable because the class can be used in another sytem.

Room Class
Data: Room Number, Room Type, and IsAvailable
Function: BookRoom() and CleanRoom()

Guest Class
Data: Guest Name, Email, Phone Number
Function: CheckIn(), CheckOut()

Hotel Class
Data: Hotel Name, Address, List of Room
Function: GetAvailableRooms(), AddGuest()

## Abstraction      

Abstraction means:

- Show the "what", Hide the "how"
- Show only what is needed
- Hide complex internal details

Foe example, a guest wants to book room. They just call asimple method like bookRoom(). they don't need to know how rooms are stored, how room availability is checked, and how booking is saved in the database. This is useful because the guest or developer uses a simple interface, the messy logic is hidden (abstracted away), and if the internal logic changes later, the rest of the code does not need to change.

## Encapsulation

Encapsulation means:
- Bundle data menthod together inside a class
- Protect the data from being accessed oor changed directly from outside 

It is useful because we keep important data private and expose only safe (public) methods to control how the data is changed. Encapsulation keeps our system secure, consistent, and easier to maintain.

For example:
Room class: 
- We protect the isBooked data so it cannot be accessed or changed directly from outside. instead, we expose a Book() menthod to update the value using business logic (e.g., check availability before booking)

## Inheritance

Inheritance means:
- Create a new class that reuses the fields and methods of an existing class. 
- Reuse code from base class in child class.

This is important to:
- Avoid code duplication 
- grup related type
- Extend base behavior

Example:

Base Class: Staff
 
Child Class: Receptionist & Cleaner 

Staff: 
- Property: Name 
- Method: Clockln()

Receptionist inherist from Staff:
- Method: CheckInGuest()

Cleaner inherist from Staff:
- Method: CleanRoom

## Polymorphism

Polymorphis means:
- One method can have different behavior depending on which class is using it.
- Word poly = many, morph =  form, so many from of the same method

it is useful because code becomes flexible, reusable, and easier to extend. In c#, use virtual in base class and override in derived class.

Example:

Create a base class:

```
public class Staff
{
    public virtual void Work()
    {
        Console.WriteLine("Staff is working.");
    }
}
```

Now we create subclasses with different behavior

```
public class Receptionist : Staff
{
    public override void Work()
    {
        Console.WriteLine("Receptionist is checking in guests.");
    }
}

public class Cleaner : Staff
{
    public override void Work()
    {
        Console.WriteLine("Cleaner is cleaning the rooms.");
    }
}
```

Using polymorphism:

```
List<Staff> staffList = new List<Staff>
{
    new Receptionist(),
    new Cleaner()
};

foreach (Staff staff in staffList)
{
    staff.Work();  // Will call the correct version!
}
```

Outout:


Receptionist is checking in guests.

Cleaner is cleaning the rooms.

Even though we call the same method work(), it behaves differently based on the actual class.

