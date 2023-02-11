# Designs Patterns
Design patterns are solutions to recurring problems that occur in software design. They are widely recognized and used by developers to create well-structured, maintainable, and scalable code. There are several types of design patterns, including creational, structural, and behavioral patterns.

## Creational Design Patterns:
 Creational design patterns deal with the process of object creation. These patterns provide a way to create objects in a manner that is suitable for a particular situation, without specifying the exact class of the object that will be created. Some of the most common creational patterns are:

- Factory Method: Defines an interface for creating an object, but allows subclasses to alter the type of objects that will be created.

- Abstract Factory: Provides a way to create families of related or dependent objects without specifying their concrete classes.

- Builder: Separates the construction of a complex object from its representation so that the same construction process can create different representations.
 
- Prototype: Specifies the kinds of objects to create using a prototypical instance, and create new objects by copying this prototype.

- Singleton: Ensures that a class has only one instance, while providing a global access point to this instance.
## Structural Design Patterns:
 Structural design patterns deal with the composition of classes and objects. These patterns provide a way to assemble objects and classes into larger structures, while preserving their individual identities. Some of the most common structural patterns are:

- Adapter: Allows classes with incompatible interfaces to work together by wrapping its own interface around that of an already existing class.

- Bridge: Decouples an abstraction from its implementation so that the two can vary independently.

- Composite: Composes zero-or-more similar objects so that they can be manipulated as one object.

- Decorator: Adds behavior to individual objects in a transparent manner, without affecting other objects.

- Facade: Provides a unified interface to a set of interfaces in a subsystem, thereby reducing the complexity of the system.

## Behavioral Design Patterns:
 Behavioral design patterns deal with communication between objects and the ways in which objects operate on each other. These patterns provide a way to define the communication between objects, so that the objects can be reused and their interactions can be modified independently. Some of the most common behavioral patterns are:

- Chain of Responsibility: Delegates commands to a dynamic sequence of receivers.

- Command: Encapsulates a request as an object, thereby letting you parameterize clients with different requests, queue or log requests, and support undo-redo.

- Interpreter: Implements a specialized language by providing its grammar and defining how to evaluate sentences in the language.

- Iterator: Accesses elements of an object sequentially without exposing its underlying representation.

- Mediator: Defines simplified communication between classes to ensure loose coupling.

Each design pattern provides a specific solution to a common problem and can be used in different ways depending on the requirements of the software being developed. Design patterns are not a one-size-fits-all solution, and the choice of which pattern to use depends on the specific context and requirements of the project.


# Architectural patterns
Architectural patterns are higher-level structures that organize code into smaller, reusable components. These patterns provide a way to design the overall architecture of a software system, making it easier to understand, maintain, and extend.

- Model-View-Controller (MVC): MVC is a classic architectural pattern that separates the application into three main components: the model, which represents the data and business logic; the view, which displays the data to the user; and the controller, which manages the interaction between the model and view. This separation of concerns makes it easier to maintain the code, as changes in one component do not affect the other components.

- Model-View-ViewModel (MVVM): MVVM is a variation of MVC that is commonly used in Android and WPF applications. It is similar to MVC, but the controller is replaced by a view model, which acts as a bridge between the model and the view. The view model contains the data and logic that the view needs to display, and the view binds to the view model to automatically update the UI whenever the data changes.

- Model-View-Presenter (MVP): MVP is another variation of MVC that is often used in Android and iOS applications. Like MVVM, the presenter acts as a bridge between the model and view, but it is more tightly coupled to the view than the view model. The presenter handles the user interaction and updates the view, while the view is responsible for rendering the data.

- Microservices Architecture: Microservices architecture is a style of software design where the application is divided into a collection of small, independent services that communicate with each other over a network. Each service is responsible for a specific business capability, such as user management or product catalog, and can be developed and deployed independently. This architecture makes it easier to scale the application, as services can be added or removed as needed, and it also makes it easier to maintain the code, as changes in one service do not affect the other services.

- Event-Driven Architecture: Event-driven architecture is a style of software design where the application is structured as a series of events that are triggered by user actions or system events. When an event occurs, the application broadcasts a message to all interested components, which can then take action. This architecture is well-suited to applications that require real-time updates, such as chat apps or trading platforms.

Each architectural pattern provides a specific solution to a common problem and can be used in different ways depending on the requirements of the software being developed. Like design patterns, architectural patterns are not a one-size-fits-all solution, and the choice of which pattern to use depends on the specific context and requirements of the project.
