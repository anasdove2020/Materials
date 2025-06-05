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

## Liskov Substitution Principle

## Interface Segregation Principle

## Dependency Inversion Principle
