# OOP

- A way to build a program using Objects.
- Each object represent a real-world thing.
- Example objects: Hotel, Guest, Room

Hotel System using OOP

Using OOP
1. We create a class (template)
2. We create object (real items) from defined class
3. We organize our code like real-world things in a hotel

It means with OOP, our code becomes easier to manage, reusable and closer to real life. OOP makes code easier to organise because it groups related group together, like putting everything about a Room in one place. Reusable because the class can be used in another sytem.

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

## Inheritance

## Polymorphism


