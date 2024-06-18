# SOLID

The SOLID principles are a set of guidelines that help developers write clean, maintainable, and scalable object-oriented code. Let's dive in with examples:

**1. Single Responsibility Principle (SRP):**

- **Idea:** A class should have only one reason to change.
- **Example:** Imagine a `Book` class. It should only be responsible for managing book data (title, author, ISBN) and not things like formatting the book for printing or storing the book in a database.

**2. Open/Closed Principle (OCP):**

- **Idea:** Software entities (classes, modules, functions, etc.) should be open for extension, but closed for modification.
- **Example:** Consider a `PaymentProcessor` class. You could create different subclasses for specific payment methods (like `CreditCardPayment`, `PayPalPayment`) instead of modifying the base class every time you add a new payment method.

**3. Liskov Substitution Principle (LSP):**

- **Idea:** Objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program.
- **Example:** If you have a `Bird` class and a `Duck` subclass, any code that works with a `Bird` object should also work seamlessly with a `Duck` object.

**4. Interface Segregation Principle (ISP):**

- **Idea:** Clients should not be forced to depend on interfaces they do not use.
- **Example:** Instead of having one giant `Worker` interface with methods for all kinds of work, split it into smaller interfaces like `Digger`, `Builder`, and `Driver`, so that a `CarMechanic` class doesn't have to implement methods for digging.

**5. Dependency Inversion Principle (DIP):**

- **Idea:** High-level modules should not depend on low-level modules. Both should depend on abstractions.
- **Example:** If you have a `ReportGenerator` that needs data from a `Database`, don't hardcode the dependency on the specific database class. Instead, create an interface (`IDataSource`) that both the `ReportGenerator` and the `Database` class implement. This makes your code more flexible and easier to test.

#it #widmo