# Software Architectural Pattern

This means:
- **Basic design idea** used to organize and structure a software system.
- It helps decide how parts of the system talk each other.
- It is like blueprint for building software.

1. Event Driven Architecture
2. Layered Architecture
3. Monolithic Architecture
4. Microservice Architecture
5. Model View Controller (MVC)
6. Master Slave Architecture

![image](https://github.com/user-attachments/assets/b0983816-cbb0-4e67-bf32-f3b32af6812c)


## Event Driven Architecture

- Decoupled Components
- Asyncronous Communication

```
using System;

// 1. Define the event and data
public class UserEventArgs : EventArgs
{
    public string Email { get; set; }
}

// 2. Publisher - raises the event
public class UserService
{
    public event EventHandler<UserEventArgs> UserRegistered;

    public void RegisterUser(string email)
    {
        Console.WriteLine($"User {email} registered.");
        
        // Raise the event
        UserRegistered?.Invoke(this, new UserEventArgs { Email = email });
    }
}

// 3. Subscriber - listens and reacts to the event
public class EmailService
{
    public void OnUserRegistered(object sender, UserEventArgs e)
    {
        Console.WriteLine($"Sending welcome email to {e.Email}");
    }
}

// 4. Connect everything
class Program
{
    static void Main()
    {
        var userService = new UserService();
        var emailService = new EmailService();

        // Subscribe to the event
        userService.UserRegistered += emailService.OnUserRegistered;

        // Trigger the event
        userService.RegisterUser("test@example.com");
    }
}

```

Good for Application:
- Event trigger action application
- Promoting scalability and responsiveness

## Layered Architecture

- Hierarchical structure with distinct layers (presentation, business logic, data)

Good for Application:
- Enterprise
- Improving maintainability & modular development

## Monolythic Architecture

- Unified codebase and deployment unit

Good for Application:
- Small application
- Simplicity focused instances

## Microservice Architecture

- Distributed system with independent and interoperable services

Good for Application:
- Large and complex system
- Enhancing scalability
- Fault isolation
- Development of independence service

## Model View Controller

- Separation of concerns into model, view, and controller components

Good for Application:
- Web Application
- Improving code organization and Maintenance
  - Separating complex logic from User Interface

## Master Slave Architecture

- Centralized control (master) with multiple worker nodes (slaves)

Good for Application:
- Ubiquitous in distributed computing
- Optimizing paraller processing and load balance
