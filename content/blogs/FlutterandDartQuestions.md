+++
title = 'Flutter Interview Questions'
date = 2023-11-23T12:00:00+00:00
tags = ['Development', 'Flutter', 'Dart', 'Blog', 'Web']
author = "Praveen Maurya"
draft: false
+++

### Basic Flutter interview questions and answers

1. **What is the purpose of using the final keyword in Dart?**
    - The `final` keyword is used to declare a variable whose value cannot be changed once assigned. It is similar to const, but the value of a final variable can be determined at runtime. Using final allows you to ensure that a variable remains constant after its initialization, providing immutability and better performance in some cases.

2. **What is the difference between a List and a Set in Dart?**
    - A `List` is an ordered collection of elements that allows duplicate values. Elements in a list can be accessed using their index. On the other hand, a `Set` is an unordered collection of unique elements. It does not allow duplicate values, and the order of elements is not guaranteed. Sets are useful when you need to ensure uniqueness and perform operations like union, intersection, and difference on collections.

3. **What's the role of BuildContext in Flutter?**
    - BuildContext is an object that provides access to the location of a widget in the widget tree hierarchy and to various services such as Theme, MediaQuery, and Navigator. The BuildContext is used by widgets to access the properties of their parent widget, such as its size, position, and theme. It is is also used to navigate between screens using the Navigator widget.

4. **What are the advantages of using Flutter?**
    - **Fast development:** With the help of Flutter, you can save a lot of time while developing software. Hot reload is a flutter feature with which you can make changes to your code and see the results in real time.
    - **Flexible user interface:** Flutter provides your application with a sleek, beautiful, and modern look that is sure to impress your users.
    - **Provides native performance:** Flutter applications run faster and smoother on devices.
    - **Widgets:** When building your application in Flutter, you get access to a wide range of pre-loaded widgets that can be utilized in your app.
    - **Huge community support:** If you want to reach a global audience, then Flutter is for you because it supports internationalization. With it, you can create an application that is available in multiple languages.

5. **What is the lifecycle of a StatefulWidget?**
    - createState
    - initState
    - didChangeDependencies
    - build
    - didUpdateWidget
    - setState
    - deactivate
    - dispose

6. **What is the difference between Expanded and Flexible?**
    - Flexible takes the least space needed to fit in a child widget. On the other hand, expanded takes the rest of the size in the widget.

7. **Can you explain how to use streams and futures in Flutter? Also, tell us some similarities and differences between Future and Stream?**
    - Streams and futures are powerful tools for handling asynchronous operations in Flutter. You can use a stream to listen for a series of events, such as user input or network responses, and react to them in real-time. A future, on the other hand, represents a value that may not be available yet and allows you to execute asynchronous code and retrieve the result when it's ready.
    - **Similarities between future and stream:**
        - Both work asynchronously
        - Both have some potential value
    - **Differences between future and stream:**
        - Future has one response whereas a stream can have multiple responses.
        - Futures are used in HTTP calls.
        - A Stream is a series of futures.

8. **Can you state some difference between runApp() and main()?**
    - **Main():** Main() function starts the program. You cannot write a program in Flutter without using the main() function.
    -  **runApp():** runApp() is used to launch the software. RunApp() allows you to return the widgets that are connected to the screen as the widget tree’s root.







Happy coding!