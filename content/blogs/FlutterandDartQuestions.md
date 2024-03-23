+++
title = 'Flutter Interview Questions'
date = 2023-11-23T12:00:00+00:00
tags = ['Development', 'Flutter', 'Dart', 'Blog', 'Web']
author = "Praveen Maurya"
draft = false
+++

### Basic Flutter interview questions and answers

1. **Explain what flutter is?**

   - Flutter is an open-source UI software development kit created by Google for building natively compilled application for mobile, web and desktop from a single codebase.
   - Flutter uses the Dart programming language for development.
   - It’s architecture is based on the concept of widgets, which are declarative UI elements that can be composed and customized to build complex user interfaces.
   - Flutter flramework provides a rich set of built-in widgets for commoan Ui component, as well as support for custom widget creation.


2. **Difference b/w hot reload and hot restart?**

   **Hot reload**

   - Hot reload allows to make changes to their flutter code and see those changes reflected most instantly in the running application without losing the current state.
   - Hot reload is partically useful for tweaking UI elements, fixing bugs, and experimenting with diffeternt design apporaches, as it provides a rapid feedback loop during development.

   **Hot restart**

   - Hot restart completely restart the flutter application, including the dart VM. It reloads all the dart code from scratch and rebuilds the entire application state.
   - Hot restart is useful when, need to make changes that affect the application’s initialization process or when they want to resent the application’s state to its initial state. It’s also necessary when changes made to code require modification to the application’s startup behavior.

3. **Difference b/w stateful vs stateless widget?**

   **Stateful widget**

   - Stateful widgets are mutable and can maintain state, meaning they can change their appearance or behavior over time.
   - It consist if two classes: the widget class itself and a corresponding state class.
   - The state is stored in the State object, which is separate from the widget itself.
   - Stateful widgets are used when the UI component needs to update dynamically in response to user interactions, data changes, or other events.

   **Stateless widget**

   - Stateless widget are immutable and do not maintain any state internilly. Once built, they cannot change their appearance or behavior.
   - It lightweight and are simply defined by their configuration and properties.
   - Its more performant that stateful widgets because they don’t need to manage state.
   - Stateless widgets are used when the UI component’s appearance or behavior remains constant throughtout its lifetime and doesn’t need to updated dynamically.

4. **Explain setState() method?**

   - ‘setState()’ method is a fundamental part of managing state within a Stateful widget.
   - It is provided by flutter to update the state of Stateful widgets and trigger a rebuild of the UI to reflect the changes. It plays a crucial role in managing dynamic user interfaces and responding to events in Flutter applications.

5. **Difference b/w function and method?**

   **function**

   - A function is a self-contained block of code that performs a specific task and can be called from anywhere within a program.
   - It can accept input paramenters(arguments) and may return a value as output.
   - Functions can be standalone entities, meaning they are not associated with any specific object or class.

   **method**

   - A method is a function that is associated with an object or a class. It defines behavior specific to that object or class.
   - It operates on the data contained within the object and can access its properties and other methods.
   - Methods are invoked on objects using dot notation(e.g., object.method()), and they implicity have access to the object’s context.

6. **Difference b/w MainAxisAlignment vs CrossAxisAlignment ?**

   **MainAxisAlignment**

   - MainAxisAlignment determines how children are positioned along the main axis of their parent container.
   - The main axis is defined based on the direction in which children are laid out within the container. For a row, the main axis is horizontal, and for a column, it’s vertical.
   - Examples of MainAxisAlignmnet values inclued ‘start’, ‘end’, ‘center’,’spaceBetween’, and ‘spaceEvenly’.

   **CrossAxisAlignment**

   - CrossAxisAlignment determines how children are positioned along the cross axis of their parent container.
   - The cross axis is perpendicular to the main axis. In a row, the cross axis is vertical, and in a column, it’s horizontal.
   - Examples of CrossAxisAlignmnet values inclued ‘start’, ‘end’, ‘center’,’stretch’, and ‘spaceEvenly’.

7. **Difference b/w packages vs plugins ?**

   **packages**

   - Packages are collections of code and resources that can be easily shared and reused across different projects.
   - They typically contain Dart code, assets (such as image, fonts), configuration files, and documents.
   - Packages in Dart are managed by the Dart package manager called ‘pub’.
   - Packages are often used to encapsulate comman functionalities, utility functions, or UI components that can be easily integrated inti flutter applications.
   - e.g., http (for making HTTP requests), shared_preferences (for storing key-value pairs locally), provider (for state management)

   **plugins**

   - Plugins are pacakges that provide access to native platform functionality in Flutter application.
   - They bridge the gap betweeb Flutter’s Dart code and native code written in languages like Java/kotlin of swift/Objective-C.
   - Plugins allow Flutter applications to leverage device-specific fetures and APIs that are not available through Flutter’s core framework.
   - Examples of plugins include camera plugins for accessing the device’s camera, location plugins for obtaining the device’s location, and Firebase plugins for integrating Firebase services into Flutter apps.
   - Plugins are typically distributed as Dart packages but may include platform-specific code and configuration files for each supported platform.


8. **What is the purpose of using the final keyword in Dart?**
    - The `final` keyword is used to declare a variable whose value cannot be changed once assigned. It is similar to const, but the value of a final variable can be determined at runtime. Using final allows you to ensure that a variable remains constant after its initialization, providing immutability and better performance in some cases.

9. **What is the difference between a List and a Set in Dart?**
    - A `List` is an ordered collection of elements that allows duplicate values. Elements in a list can be accessed using their index. On the other hand, a `Set` is an unordered collection of unique elements. It does not allow duplicate values, and the order of elements is not guaranteed. Sets are useful when you need to ensure uniqueness and perform operations like union, intersection, and difference on collections.

10. **What's the role of BuildContext in Flutter?**
    - BuildContext is an object that provides access to the location of a widget in the widget tree hierarchy and to various services such as Theme, MediaQuery, and Navigator. The BuildContext is used by widgets to access the properties of their parent widget, such as its size, position, and theme. It is is also used to navigate between screens using the Navigator widget.

11. **What are the advantages of using Flutter?**
    - **Fast development:** With the help of Flutter, you can save a lot of time while developing software. Hot reload is a flutter feature with which you can make changes to your code and see the results in real time.
    - **Flexible user interface:** Flutter provides your application with a sleek, beautiful, and modern look that is sure to impress your users.
    - **Provides native performance:** Flutter applications run faster and smoother on devices.
    - **Widgets:** When building your application in Flutter, you get access to a wide range of pre-loaded widgets that can be utilized in your app.
    - **Huge community support:** If you want to reach a global audience, then Flutter is for you because it supports internationalization. With it, you can create an application that is available in multiple languages.

12. **What is the lifecycle of a StatefulWidget?**
   The lifecycle of a stateful widget in Flutter consits of sevral stages, each of which plays a crucial role in managing its state and UI.

   **1. createState()**

   - When flutter create a stateful widget, it’s called ‘createState()’ method, which is reponsible for creating the corresponding State object.
   - This method is typically overridden to return an instance of class that extend‘State<StatefulWidget>’.

   **2. initState()**

   - ‘initState()’ is called excatly once during the lifecycle of the State object and is used for initializing state that depends on the context.
   - This is where you would perform tasks like initializing variables, subscribing to streams, or loading data from APIs.

   **3. didChangeDependencies() (optional)**

   - If the widget’s dependencies change (e.g., theme, localization), flutter calls the ‘didChangeDependencies()’ method.
   - This method is called immediately after ‘initState()’ and can be overridden to handle changes to dependencies.

   **4. build()**

   - The ‘build()’ method is called whenever flutter needs to rebuild the UI of the Stateful widget.
   - It returns a widget hierarchy that represents the UI of the widget based on the current state.
   - ‘build()’ is called frequently, such as when the widget’s state changes, when the parent widget rebuilds, or when the device orientation changes.

   **5. setState()**

   - When the state of a Stateful widget changes, you call the ‘setState()’ method to trigger a rebuild of the widget’s UI.
   - This method schedules a call of the ‘build()’ method and notifies flutter that the widget needs to be updated.

   **6. didUpdateWidget()**

   - If the parent widget changes and causes the Stateful widget to rebuild, flutter calls the ‘didUpdateWidget()’ method.
   - This method provides an opportunity to compare old and new widget configurations and perform any neccessary updates to the state.

   **7. dispose()**

   - When a Stateful widget removed from the widget tree (e.g., when navigation to a different screen), Flutter calls the ‘dispose()’ method.
   - ‘dispose()’ is called to release resources, unsubscribe from streams, or perform cleanup tasks.
   - It is the last lifecycle method called on the State object.

13. **What is the difference between Expanded and Flexible?**
    - Flexible takes the least space needed to fit in a child widget. On the other hand, expanded takes the rest of the size in the widget.

14. **Can you explain how to use streams and futures in Flutter? Also, tell us some similarities and differences between Future and Stream?**
    - Streams and futures are powerful tools for handling asynchronous operations in Flutter. You can use a stream to listen for a series of events, such as user input or network responses, and react to them in real-time. A future, on the other hand, represents a value that may not be available yet and allows you to execute asynchronous code and retrieve the result when it's ready.
    - **Similarities between future and stream:**
        - Both work asynchronously
        - Both have some potential value
    - **Differences between future and stream:**
        - Future has one response whereas a stream can have multiple responses.
        - Futures are used in HTTP calls.
        - A Stream is a series of futures.

15. **Difference b/w  main() vs runApp() ?**

   **main()**

- ‘main()’ is standard entry point for all the Dart applications, including flutter apps.
- It serves as the starting point of execution for the application and typically contains the code that initializes the application and sets up its environment.

   **runApp()**

- ‘runApp()’ is a method provided by Flutter framework that takes a widget as its argument and starts the Flutter application.
- It is called within the main() function to specify the root widget of the application, which represents the top-level UI element of the app.
- The widget passed on the ‘runApp()’ becomes the root widget tree and define the entire UI hierarchy of the application.
- ‘runApp()’ is responsible for setting up the rendering environment , managing the widget tree, nad handling the lifecycle of the application.







Happy coding!