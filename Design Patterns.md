Design patterns are typical solutions to common problems in software design. They are like pre-made blueprints that you can customise to solve a recurring design problem in your code.

## Creational Patterns

These design patterns provide a way to create objects while hiding the creation logic, rather than instantiating objects directly using a constructor. This gives the program more flexibility in deciding which objects need to be created for a given use case.

- **Singleton**: Ensures a class has only one instance and provides a global point of access to it.
- **Factory Method**: Provides an interface for creating objects, but allows subclasses to alter the type of objects that will be created.
- **Abstract Factory**: Lets you produce families of related objects without specifying their concrete classes.

## Structural Patterns

These design patterns concern class and object composition. They use inheritance to compose interfaces and define ways to compose objects to obtain new functionality.

- **Adapter**: Allows objects with incompatible interfaces to collaborate.
- **Decorator**: Lets you attach new behaviours to objects by placing these objects inside special wrapper objects that contain the behaviours.
- **Facade**: Provides a simplified interface to a library, a framework, or any other complex set of classes.

## Behavioural Patterns

These design patterns are specifically concerned with communication between objects.

- **Observer**: Lets you define a subscription mechanism to notify multiple objects about any events that happen to the object they’re observing.
- **Strategy**: Lets you define a family of algorithms, put each of them into a separate class, and make their objects interchangeable.
- **Command**: Turns a request into a stand-alone object that contains all information about the request.