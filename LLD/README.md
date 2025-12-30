

## 🎯 Overview
Low Level Design focuses on the implementation details of a system, including class diagrams, design patterns, and object-oriented principles.

## 📚 Design Patterns

### Creational Patterns
- [ ] **Singleton** - Ensure only one instance of a class exists
- [ ] **Factory** - Create objects without specifying exact class
- [ ] **Abstract Factory** - Create families of related objects
- [ ] **Builder** - Construct complex objects step by step
- [ ] **Prototype** - Clone existing objects

### Structural Patterns
- [ ] **Adapter** - Make incompatible interfaces work together
- [ ] **Decorator** - Add behavior to objects dynamically
- [ ] **Facade** - Provide simplified interface to complex subsystem
- [ ] **Proxy** - Control access to objects
- [ ] **Composite** - Compose objects into tree structures
- [ ] **Bridge** - Separate abstraction from implementation

### Behavioral Patterns
- [ ] **Observer** - Define one-to-many dependency between objects
- [ ] **Strategy** - Define family of algorithms
- [ ] **Command** - Encapsulate requests as objects
- [ ] **State** - Alter object behavior when state changes
- [ ] **Chain of Responsibility** - Pass request along chain of handlers
- [ ] **Template Method** - Define skeleton of algorithm
- [ ] **Iterator** - Access elements sequentially

## 🏗️ Classic LLD Problems

### 1. Parking Lot System
**Difficulty**: Medium  
**Key Concepts**: OOP, Strategy Pattern, State Pattern

**Requirements**:
- Multiple floors and spots
- Different vehicle types (bike, car, truck)
- Pricing based on vehicle type and duration
- Entry/Exit management

**Classes to Design**:
- ParkingLot, Floor, ParkingSpot, Vehicle, Ticket, PaymentSystem

---

### 2. Elevator System
**Difficulty**: Medium-Hard  
**Key Concepts**: State Pattern, Strategy Pattern

**Requirements**:
- Multiple elevators
- Request handling (up/down)
- Optimal elevator selection
- Emergency handling

---

### 3. Library Management System
**Difficulty**: Medium  
**Key Concepts**: OOP, Observer Pattern

**Requirements**:
- Book catalog management
- Member management
- Issue/Return books
- Fine calculation
- Search functionality

---

### 4. ATM System
**Difficulty**: Medium  
**Key Concepts**: State Pattern, Chain of Responsibility

**Requirements**:
- Card authentication
- Account operations (withdraw, deposit, balance)
- Cash dispenser
- Transaction history

---

### 5. Ride Sharing (Uber/Ola)
**Difficulty**: Hard  
**Key Concepts**: Strategy Pattern, Observer Pattern

**Requirements**:
- Driver-Rider matching
- Ride request handling
- Fare calculation
- Rating system
- Real-time location tracking

---

### 6. Movie Ticket Booking
**Difficulty**: Medium  
**Key Concepts**: Factory Pattern, Observer Pattern

**Requirements**:
- Theater and show management
- Seat selection and booking
- Payment processing
- Ticket cancellation

---

### 7. SplitWise
**Difficulty**: Medium-Hard  
**Key Concepts**: Strategy Pattern, Graph Algorithms

**Requirements**:
- Expense tracking
- Group management
- Split strategies (equal, percentage, exact)
- Debt simplification

## 📋 Design Checklist

For each LLD problem, ensure you cover:

- [ ] **Requirements Clarification**: Ask questions, define scope
- [ ] **Class Diagram**: Identify entities and relationships
- [ ] **Design Patterns**: Choose appropriate patterns
- [ ] **SOLID Principles**: 
  - Single Responsibility
  - Open/Closed
  - Liskov Substitution
  - Interface Segregation
  - Dependency Inversion
- [ ] **Code Implementation**: Core classes and methods
- [ ] **Edge Cases**: Handle error scenarios
- [ ] **Extensibility**: Design for future changes

## 💡 Best Practices

1. **Start with Use Cases**: Understand what the system should do
2. **Identify Entities**: Find nouns in requirements (potential classes)
3. **Define Relationships**: IS-A (inheritance) vs HAS-A (composition)
4. **Apply Design Patterns**: Don't force patterns, use when appropriate
5. **Keep it Simple**: Avoid over-engineering
6. **Document Assumptions**: Write down what you're assuming
7. **Think About Concurrency**: Consider thread safety where needed

## 📝 Template for LLD Problems

```
## [Problem Name]

### Requirements
- Functional Requirements
- Non-Functional Requirements
- Constraints

### Use Cases
1. Use case 1
2. Use case 2
...

### Class Diagram
[ASCII or image]

### Core Classes
- Class 1: Responsibility
- Class 2: Responsibility
...

### Design Patterns Used
- Pattern 1: Reason
- Pattern 2: Reason

### Implementation
[Code snippets for key classes]

### Trade-offs
- Decision 1: Pros/Cons
- Decision 2: Pros/Cons
```

## 🔗 Resources
- Head First Design Patterns
- Refactoring Guru (Design Patterns)
- GeeksforGeeks LLD Articles
