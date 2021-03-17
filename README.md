# 15 days of Flutter
## Day 1: Flutter Installation and Setup
### Installation
Full installation instructions are available on the official website:

- [​Install Flutter​](https://flutter.dev/docs/get-started/install)

If you want to build Flutter apps on Android and iOS, you'll need to install the corresponding SDKs, as well as the Android emulator and iOS simulator. The installation guide above explains how to do this.

Note: You can only develop Flutter apps for iOS on a macOS system. If you're on Windows, you can only build for Android. With that said, you could explore services like macincloud and Remote Mac to build iOS apps remotely.

### Configuring your IDE
You'll also need a code editor such as [Android Studio](https://developer.android.com/studio/) or [Visual Studio Code](https://code.visualstudio.com/), along with the Dart and Flutter plugins:
- [​Set up an editor​](https://flutter.dev/docs/get-started/editor?tab=androidstudio)

To make the most of your IDE, check out the documentation for tips on running and debugging your apps, using code snippets, keyword shortcuts, and more:
- [​Android Studio and IntelliJ​](https://flutter.dev/docs/development/tools/android-studio)
- [​Visual Studio Code​](https://flutter.dev/docs/development/tools/vs-code)

### Flutter doctor

Once everything is installed (don't forget to configure your system PATH on [Windows](https://flutter.dev/docs/get-started/install/windows#update-your-path) or [macOS](https://flutter.dev/docs/get-started/install/macos#update-your-path)!), you should be able to type flutter doctor on your terminal. And your output should look something like this:
![Flutter Doctor](https://pbs.twimg.com/media/EvVHzQAVoAIwfbx?format=jpg&name=small)

If flutter doctor doesn't report any errors, you already have everything you need to get started building apps.

Time for a quick test drive. This page shows you how to create a new Flutter project and run it:
- [​Test drive​](https://flutter.dev/docs/get-started/test-drive?tab=androidstudio)

### Bonus: VS Code extensions for Pro Flutter development
If you use VSCode, I highly recommend adding some useful extensions. These are my favourites:

- [​Bracket Pair Colorizer 2​](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)
- [​Dracula official theme](https://marketplace.visualstudio.com/items?itemName=dracula-theme.theme-dracula) (who doesn't like Dark Mode? 😉)
- [​Error Lens](https://marketplace.visualstudio.com/items?itemName=usernamehw.errorlens) (get any feedback about errors as you type: super useful)
- [​Pubspec assist​](https://marketplace.visualstudio.com/items?itemName=jeroen-meijer.pubspec-assist)
- [​Todo Tree​](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)

There are [many others](https://medium.com/flutter-community/must-have-vs-code-extensions-for-working-with-flutter-e31a421b9c68), but these are the ones I use all the time.

Congratulations, your Flutter development environment is ready to go!



## Day 2: Dart Language
Flutter apps are built using Dart, which is an easy language to learn.

The official [Dart language tour](https://dart.dev/guides/language/language-tour) is a great place to start **if you're already familiar with other languages** such as JavaScript, Swift, or Kotlin.

You can also check out the guides in the [official documentation](https://dart.dev/guides) to make the most of Dart. These include [codelabs](https://dart.dev/codelabs), guidelines about writing [effective Dart](https://dart.dev/guides/language/effective-dart) code, and much more.

You don't need to read the entire documentation. Rather, you can come back to it as you improve your Dart coding style over time.

[​Dartpad](https://dartpad.dev/) is a free online editor that you can use to experiment with the Dart language, without having to install anything on your machine.

### Null Safety
Null Safety is a big change to the Dart language.

It's very likely that Null Safety will be be enabled by default in the upcoming Flutter stable release in early 2021. So it's worth getting familiar with how it works (if you haven't already).

The documentation alredy covers everything you need to know about Null Safety:
- [​Overview: Sound null safety​](https://dart.dev/null-safety)
- [​Migrating to null safety​](https://dart.dev/null-safety/migration-guide)
- [​Understanding null safety​](https://dart.dev/null-safety/understanding-null-safety)

Alternatively, you can check out the [Null safety introduction video](https://www.youtube.com/watch?v=iYhOU9AuaFs&feature=youtu.be) from the Flutter team, or watch my in-depth tutorial:
- [​Dart Null Safety: The Ultimate Guide to Non-Nullable Types​](https://codewithandrea.com/videos/dart-null-safety-ultimate-guide-non-nullable-types/)

### Other Dart resources
If you're looking for a fast-paced tutorial about Dart tips and tricks, I've got you covered:
- [​Top 16 Dart Tips and Tricks Every Flutter Developer Should Know​](https://codewithandrea.com/videos/top-dart-tips-and-tricks-for-flutter-devs/)

All the resources above are a good way to learn about the Dart language.
You can make the most of the links above if you're already familiar with other programming languages.
But if you're new to programming and Dart is your fist language, I recommend take this [complete Dart course](https://www.udemy.com/course/complete-dart-guide/?couponCode=MAR-21) on Udemy.



## Day 3: Flutter architecture & project setup
### Flutter Architecture
Whether you have made a Flutter app before or not, it's useful to get a high-level overview of the Flutter architecture from a conceptual point of view.

![Flutter architecture](https://pbs.twimg.com/media/Evf4F0wVoAUx5n2?format=jpg&name=small)

Flutter uses its own rendering engine called Skia. This is written in C/C++ and provides low-level APIs for rendering, text layout, and more. When you write Flutter apps, your code doesn't call directly the Flutter engine APIs. Rather, it uses a set of high-level APIs provided by the Flutter framework.

By design, **Flutter controls every single pixel that is drawn on screen**. The Flutter framework offers a rich set of UI components (called widgets) that closely match the native UI controls on iOS and Android.

### Declarative programming model
Flutter uses a declarative programming model.

Flutter widgets define their UI by overriding the **build()** method, which is a function that converts state to UI:

**UI = f(state)**

Small, single-purpose widgets are composed together to create more complex, specialized ones that represent your application UI. Hence, the entire application is represented by a so-called widget-tree.

For example, here's what the widget tree looks like for the default Flutter counter app:
![widget tree](https://pbs.twimg.com/media/Evf4F0-VoAU3Ls_?format=jpg&name=small)

In the upcoming lesson about state management we will talk about how to rebuild the UI when some state changes, and what techniques are available to do so.

But for now this is all the theory you need. And if you want a more in-depth explanation of the Flutter architecture, there is no better place than the official documentation:

- [​Flutter architectural overview​](https://flutter.dev/docs/resources/architectural-overview)

This is a long read, but worthwhile if you want to understand how Flutter works under the hood.

On to something more practical.

### Project setup
When you create a new Flutter project, some files and folders will be generated for you.
![new generated file](https://pbs.twimg.com/media/Evf4F0vUYAIHtcz?format=jpg&name=small)

The most important file is called pubspec.yaml. This is used to specify your application's dependencies. These resources explain how this file works and how to use it to install packages:

- [​The pubspec file​](https://dart.dev/tools/pub/pubspec)
- [​Using packages​](https://flutter.dev/docs/development/packages-and-plugins/using-packages)

In addition to this, I highly recommend adding an analysis_options.yaml file. This can be used to specify linter rules and enable extra warnings and errors for your project. Here's an in-depth guide about it:

- [​Getting started: Creating your Flutter project​](https://dash-overflow.net/articles/getting_started/)

In particular, read the "Managing your lint rules easily" section at the end. This explains how to create a clean and maintainable set of rules that you can tweak in your apps.

You can download an "official" analysis_options.yaml file [from here](https://dart-lang.github.io/linter/lints/options/options.html), and also view a [list of all the supported rules with explanations](https://dart-lang.github.io/linter/lints/index.html).



## Day 4: Flutter widgets + basic & responsive layouts
Flutter really shines when it comes to building beautiful UIs.

With Flutter, you build UIs by using widgets and composing them together in a declarative manner. You can think of widgets as UI components that describe what your application looks like.

Flutter offers an extensive set of widgets, closely matching the [Material Design](https://flutter.dev/docs/development/ui/widgets/material) specification. The Flutter [widget catalog](https://flutter.dev/docs/development/ui/widgets) also includes [Cupertino widgets](https://flutter.dev/docs/development/ui/widgets/cupertino), which are high-fidelity replicas of all the UI components found on iOS.

Because Flutter controls every pixel on the screen, you can even create your own widgets to deliver a completely custom experience that delights your users.

So what are some good resources to learn about widgets & layouts?

### Flutter layouts
A good place to start is this official guide about [Layouts in Flutter](https://flutter.dev/docs/development/ui/layout), showing you how to build some common layouts with useful illustrations.

- [​Flutter Widget of the week](https://www.youtube.com/watch?v=b_sQ9bMltGU&list=PLjxrf2q8roU23XGwz3Km7sQZFTdB996iG): This is truly an amazing video series from the Flutter team. Most videos are 1-to-2 minutes long and help you learn about the most useful widgets. You don't need to watch the entire series at once, but I won't stop you if you do 😀. And sometimes knowing that a widget exists means that you don't have to create one yourself.
In addition to this, I have also made some video walkthroughs of the most useful layout widgets:

- [​Flutter Layouts Walkthrough: Row, Column, Stack, Expanded, Padding​](https://www.youtube.com/watch?v=RJEnTRBxaSg)
- [​Flutter Layouts Walkthrough: PageView, ListView, GridView, Slivers, CustomScrollView​](https://www.youtube.com/watch?v=-zJ6CnOVndE)

And if you want to create more complex layouts with a lot of scrollable elements, my slivers tutorials have you covered:

- [​Flutter Slivers Overview: SliverAppBar, SliverPersistentHeader​](https://www.youtube.com/watch?v=E3-WdYBrEDc)
- [​Flutter Slivers Overview: SliverList, SliverGrid, SliverToBoxAdapter, SliverFillRemaining​](https://www.youtube.com/watch?v=k2v3gxtMlDE)

All the links above are enough to build common layouts on mobile.

But sooner or later, you may encounter some layout errors (bottom overflow anyone? 😅). To get past that, I highly recommend this page that explains how constraints work in Flutter:

- [​Understanding constraints​](https://flutter.dev/docs/development/ui/layout/constraints)

What's good about this is that it includes a list of nearly 30 example layouts, showing you why sometimes things don't work, and how to fix them.

### Responsive Layouts
Once you need to support multiple form factors, you'll need to learn about responsive layouts and how to implement them in Flutter.

For that, I highly recommend this tutorial:

- [​How to build responsive layout in Flutter​](https://blog.codemagic.io/building-responsive-applications-with-flutter/)

This will show you how to use [MediaQuery](https://api.flutter.dev/flutter/widgets/MediaQuery-class.html), [LayoutBuilder](https://api.flutter.dev/flutter/widgets/LayoutBuilder-class.html), and [other useful widgets for creating responsive UIs](https://flutter.dev/docs/development/ui/layout/adaptive-responsive).

And while you can build a fully responsive Flutter app just with MediaQuery, LayoutBuilder, and other built-in widgets, there are packages that make this process easier.

One such package is [responsive_builder](https://pub.dev/packages/responsive_builder), which makes it easy to set custom screen breakpoints, and manage various form factors with an ergonomic API. This is based on this [video series](https://www.youtube.com/playlist?list=PLQQBiNtFxeyJbOkeKBe_JG36gm1V2629H) about Flutter responsive UI.

## Day 5: State management basics
With over 40 packages available, state management is likely the hottest topic in Flutter.
Here's the full list on Flutter Gems:
- [​Flutter Gems - State Management](https://fluttergems.dev/state-management/)

### State Management
Onn day 3 we discovered that Flutter is declarative, in that it builds the UI to reflect the current state of your app:

UI = f(state)

This is briefly explained in this page called [Start thinking declaratively](https://flutter.dev/docs/development/data-and-backend/state-mgmt/declarative).

But what is state exactly? The Flutter documentation defines state as:

whatever data you need in order to rebuild your UI at any moment in time

It also introduces a clear distinction between **app state** and **ephemeral (or local) state**:

- [​Differentiate between ephemeral state and app state​](https://flutter.dev/docs/development/data-and-backend/state-mgmt/ephemeral-vs-app)

As a rule of thumb, you can use setState and the State class every time you're dealing with local state. This keeps things simple.

When it comes to app state, there are multiple approaches and techniques that you can use. Before going any further, I recommend you check this out:

### Flutter Widgets 101
This series covers the basics of state management in Flutter. Make sure you watch and understand this before moving to any of the more complex solutions:

- [​How to Create Stateless Widgets - Flutter Widgets 101 Ep. 1​](https://www.youtube.com/watch?v=wE7khGHVkYY)
- [​How Stateful Widgets Are Used Best - Flutter Widgets 101 Ep. 2​](https://www.youtube.com/watch?v=AqCMFXEmf3w)
- [​Inherited Widgets Explained - Flutter Widgets 101 Ep. 3​](https://www.youtube.com/watch?v=Zbm3hjPjQMk)
- [​When to Use Keys - Flutter Widgets 101 Ep. 4​](https://www.youtube.com/watch?v=kn0EOS-ZiIc)

You can go pretty far and build non-trivial applications with the built-in StatelessWidget, StatefulWidget, and InheritedWidget classes. More importantly, it's critical to understand the foundations of state management before you can move to more complex solutions.

For a comprehensive overview about Flutter's built-in tools for state management, you can also check this:

- [​Flutter State Management Basics and Useful Resources​](https://codewithandrea.com/videos/flutter-state-management-basics/)


## Day 6: State management & architecture
Once you're feeling **confident** with the built-in state management capabilities in Flutter, you can start looking at some of the other solutions.

Here I focus on the most **stable, well documented, maintained**, and **supported** packages. The ones I used personally and can recommend without hesitation are:

- [​provider​](https://pub.dev/packages/provider)
- [​flutter_bloc​](https://pub.dev/packages/flutter_bloc)
- [​riverpod​](https://pub.dev/packages/riverpod)

Other honorable mentions are `rxdart`, `get_it`, `stacked`, `mobx`, `states_rebuilder` and `redux`.

But you know what? **You only need one of these**, and only after you've covered the basics from day 5.

### Provider
Simply put, **Provider = InheritedWidget + Generics**. Provider gives you scoped access to things in your widget tree, **by type**. It is officially endorsed by the Flutter team. It's mature, and you'll find a lot of documentation and Q/A on StackOverflow about it.

For a good conceptual overview of Provider, I recommend [Flutter Provider video series](https://www.youtube.com/playlist?list=PLNnAcB93JKV-IarNvMKJv85nmr5nyZis8) on YouTube.

### flutter_bloc
Just like Provider, flutter_bloc is a very mature and robust solution for state mangement, and has been around for over 2 years.

If you head over to [bloclibrary.dev](https://bloclibrary.dev/#/), you'll find the **highest-quality documentation**. This includes all the most important core concepts, along with tutorials showing how to build real apps, with full source code.

The earlier versions of flutter_bloc were criticized for requiring too much boilerplate code. But since then, the package also includes cubit, a light-weight version of bloc.

The best place to learn Flutter Bloc (along with many important concepts) is this 3-hour free course on YouTube:

- [​The Best Flutter Bloc Complete Course - Visualise, Understand, Learn & Practice Bloc Concepts​](https://www.youtube.com/watch?v=THCkkQ-V1-8)

### Riverpod
Riverpod is a rewrite of Provider to make improvements that would be otherwise impossible.

It borrows many concepts from Provider, but is fundamentally different in that it does not depend on Flutter and the widget-tree. Riverpod uses **global providers** that are **referenced by name, not type**. This is a big departure from a conceptual point of view.

You can head to [riverpod.dev](https://riverpod.dev/) to find extensive documentation about the most important concepts, along with official and 3rd party example apps.

My essential guide to Riverpod covers everything you need to know:

- [​Flutter State Management with Riverpod: The Essential Guide​](https://codewithandrea.com/videos/flutter-state-management-riverpod/)

Having used Provider, flutter_bloc and Riverpod in my projects, I can say that Riverpod is my favorite. Riverpod allows you to manage state in **complex** applications in a **type-safe** way with **minimal boilerplate code**. It has great support for testing, and works really well when combining providers together.

Ultimately, all these packages help you separate your business logic from the UI code. Here's a complete tutorial showing how to refactor a simple app for better separation of concerns, immutability, and type safety using Freezed& StateNotifier:

- [​Flutter State Management: Going from setState to Freezed & StateNotifier with Provider​](https://codewithandrea.com/videos/flutter-state-management-setstate-freezed-state-notifier-provider/)

For a direct comparison of Provider, flutter_bloc, and Riverpod, you can check this movie app that I've built using all three packages:

- [​Flutter State Management: Movie App with Provider, Riverpod, flutter_bloc | GitHub​](https://github.com/bizz84/movie_app_state_management_flutter)

All these packages are great, but don't let my perspective influence your decision. Many other packages are also very good. If you come from JavaScript and you're familiar with redux, then that may be the right solution for you. After all, tools are only valuable if you know how to use them correctly.

What about Architecture?
The state management solutions above are tools that you can use to build your apps.

But tools alone are not enough. To build an app, you need to use them as part of a broader application structure or design.

In building Flutter apps over the last 3 years, I've identified three main application layers that are common to most apps:

UI Layer: this is where we put our widgets
Domain layer: this is where we define our data models and business logic
Service Layer: this contains wrappers for networking/backend code (e.g. REST APIs, authentication, Cloud Firestore etc.)
For a more complete overview about app architecture and my approach to building complex Flutter apps, see this tutorial:

- [​Starter Architecture for Flutter & Firebase Apps​]()

This includes a GitHub repo with a full example app built with Flutter & Firebase, using Riverpod.

State management & architecture is a broad topic and it can be challenging to "get it right" when building complex apps. I'll be covering this topic more in detail in my upcoming tutorials.

For now my advice is to see how far you can get with the built-in solutions, and then try one of solutions above. They all have a learning curve, but the package authors are very supportive and keen to help, so don't be afraid to reach out and ask questions.

One more thing
Check out the flutter_architecture_samples repo by Brian Egan and others. This shows how to build a simple TODO app using nearly all of the state mangement solutions in Flutter.

This is a great way to learn about their differences.

## Day 7: Navigation
Basic navigation
And as long as you don't want to do anything too complex, Flutter provides a simple API for navigating to a new screen and back:

​Navigate to a new screen and back​
In very simple terms, navigation is performed by:

Getting a Navigator object for the current context (e.g. Navigator.of(context)).
Calling push() to add a new route to the navigation stack. This is most commonly done with a MaterialPageRoute that builds the widget/page you want to show.
When done, calling pop() to return to the previous route.
When using the basic push() and pop() methods, it is also very easy to pass arguments to the new route, and return a value when the route is dismissed.

But when you have a lot of screens in your app, it is more appropriate to define a set of named routes and keep them in the same place:

​Navigate with named routes​
As the article above shows, this is done by defining your application's routes inside your MaterialApp widget (or alternatively, using onGenerateRoute).

However, this approach makes it harder to pass typed arguments to your routes. This is because the Navigator.pushNamed() method takes an arguments parameter of type Object.

For example, if you have a route named /movie-details and a MovieDetails argument, you can pass this directly when calling pushNamed():


## Day 8: Interactivity & user input
All mobile apps need to react to user input. And Flutter provides various ways of making apps interactive.

For example, a common requirement is to let the user fill in some text data inside a form.

An email & password sign-in flow may look simple from the outside, but there is a lot of detail going on:

- input text validation
- handling the selected focus and dismissing the keyboard when needed
- getting and setting the text fields' data and updating the form state
- text field appearance (decoration, placeholder text, error hints etc.)

You can use a **TextField** widget to let the user enter some text in your app. Because Flutter is declarative, you need to pass a TextEditingController as an argument to TextField and use it to control the text inside it. This is typically done inside a StatefulWidget subclass that is the parent of your TextField(s).

Though if you have more than one text field in your page, you'll need a TextEditingController for each TextField, and this can lead to a lot of boilerplate.

One way to make your life easier is to use the built-in Form and FormTextField widgets, and this tutorial explains how to do so:

- [​Flutter - How To Use Form and TextFormField​]()

By the way, FormTextField uses TextField under the hood. TextField is a very customizable widget with many useful properties.

The best place to learn how to use all these input widgets is the Flutter forms cookbook, which includes various interactive examples:

- [​Forms | Flutter Cookbook​]()

TextField is quite powerful, and you can learn all about it here:

- [​A Deep Dive Into Flutter TextField​]()

### Too much boilerplate
Working with TextEditingController can add a lot of boilerplate to your apps. flutter_hooks provides an elegant solution for this, and comes with a useTextEditingController API that you can use to streamline your text editing code.

You can see an example of how to do this in my BMI calculation app on GitHub.

### More than just text fields
Text input is just one of many ways users can interact with our app.

Other common input widgets are date and time pickers, checkboxes, radio boxes, sliders, and switches.

These are all listed as part of the Material Components widgets catalog.

And if you're targeting iOS, you can also use the corresponding Cupertino (iOS-style) widgets.

### Gestures
All the widgets we discussed above are visual UI components that you can show on screen. But Flutter also gives you some rich APIs for detecting user gestures.

For a good overview about how to listen for, and respond to, gestures in Flutter, see this page:

- [​Taps, drags, and other gestures​]

And if you want to take a deep dive, this article has you covered:

- [​Flutter Deep Dive: Gestures​]




## Day 9: Animations
Flutter offers some well-designed animation APIs that make it easy to implement complex animations, and make your apps stand out.

The Flutter team has produced an extensive set of video tutorials, articles and samples that you can browse.

You can learn all about Flutter animations here:

- [​Introduction to animations​]()

I recommend you watch every one of the linked tutorials, as they explain everything in detail. [Various codelabs]() are also available, so you can get some practice working with animations and learn what's possible.

There's also a section about [other resources](), which points to additional samples, recipes and documentation that you can browse.

But there is more.

The Flutter team has created an official [animations]() package that you can use to add pre-canned animations to your apps.

You can use the [simple_animations]() package to more easily create custom animations with less boilerplate code. This includes additional features such as [Stateless animations]() and [MultiTween]().

And if you want to go beyond writing your animations with code, you can use the [Rive app](). This is a complete editor that you can use to create sophisticated interactions. These can then be loaded into your Flutter projects using the [rive package]() (tutorial [here]()).

Also, if you want to know what Flutter's animation system is capable of, I recommend this talk:

- [​Implementing complex UI with Flutter - Marcin Szałek | Flutter Europe]()

## Day 10: Local data persistence
Data persistence is an important requirement in many different apps.

So what is data persistence and why is it important?

Suppose you're writing an app where the user can track his/her weight every day. It would be bad if the user entered some data, and this was lost after the app was backgrounded or killed by the operating system.

By saving this data locally to disk, you can retrieve it the next time the app is started, and present it again.

In Flutter, there are various ways to save data locally:

Using a key-value store
You can use Shared Preferences to store non-sensitive user data. This may include things like app preferences and settings (such as light/dark mode), or even a local flag to verify if the user has completed the app onboarding.

Another popular key-value store is Hive, which is used and loved by many developers. Hive is very fast, however it appears to have a lot of open issues and some devs have been voicing concerns about it on Reddit.

Using a secure key-value store
Sensitive data such as the user's email and address should not be saved in an unencrypted form.

In this scenario it's best to use a secure key-value store such as flutter_secure_storage. This has an API that is very similar to shared preferences, but uses the underlying Keychain on iOS, and KeyStore on Android.

Using a relational-database
If you need to store relational data you can use sqflite, the SQLite plugin for Flutter.

This provides some asynchronous APIs for reading from and writing to a local database using the SQL language.

Though sqlite is not type-safe, and this can lead to bugs that are hard to diagnose.

To solve this problem the Moor package was created. Moor is a type-safe reactive persistence library for Flutter and Dart, built on top of sqflite. Moor has extensive documentation covering everything you need to know. And you can also check out this video for a complete overview.

Reading and writing files to disk
Key-value stores and relational databases are great, but sometimes you just want to write data directly to files on disk.

This is done by combining the path_provider plugin with the dart:io library.

Use case: the image_picker plugin offers a Future-based API that you can use to take a picture using the native camera. When you use this, the picture is saved on disk and returned as a File object that you can read with dart:io or show inside a widget.

Local vs remote data persistence
So far we have only talked about local data persistence.

This works fine as long as you don't need to sync data across multiple devices. With local persistence, users will lose their data if they move to a new device without making a backup.

But many apps need access to user-generated content that is saved remotely in the cloud. In this case you'll need to create your own backend, or use a Backend-as-a-Service such as Firebase. Firebase offers things like authentication, a real-time persistent document store, and many useful features. I won't cover Firebase as part of this email course, but you can take my Flutter & Firebase course on Udemy to learn how to build a complete app using Firebase authentication and Cloud Firestore.

I also recommend watching this tutorial by the Flutter team, which covers local data persistence in detail:

- [​Keeping it local: Managing a Flutter app's data]()

## Day 11: Networking
If you want your apps to read data from public APIs (here's a list with thousands of APIs), or communicate with your own custom backend, you'll need to write some networking code.

Networking basics
Simple apps that need to talk to a REST API can use the Dart http package. This offers a Future-based API for making network requests, and it works across multiple platforms since it's a pure Dart package.

Most REST APIs will respond with data in JSON format. This can be decoded into unstructured maps of key-value pairs that are not type-safe.

When reading JSON data, it's best practice to de-serialize it into strongly-typed model classes. Likewise, you can serialize your models back to JSON data that can be sent over the network. You can find more about working with JSON on this page.

Code Generation
Doing all this by hand is ok if you have very few simple model classes. But if you're working with a lot of endpoints returning complex data, code generation may be a better option, and the json_annotation package helps with that.

Along with that, you can consider using the freezed package.

If you need a good intro to code generation and the freezed package, this is a good tutorial:

​Flutter Code Generation - What You Need To Know​
Other networking packages
The http package is easy to use and works well for simple apps.

But for apps with more complex requirements, the dio package may be more appropriate.

Dio supports more advanced features such as sending form data, request cancellation, file downloading, and much more.

So if you need any of the above, dio is a better choice than http.

But even then, you still need to deal with JSON serialization. Wouldn't it be nice if there was a package that can auto-generate all the networking and serialization code for you?

Luckily, flutter_data was created for this purpose. This can auto-generate REST clients for all your models with minimal boilerplate code, and even has integrations for the most popular state management packages. So check out the documentation for more info. Though as you can see on pub.dev, Flutter Data has many dependencies and it looks like the documentation is out of date.

## Day 12: Platform Channels
"Single codebase, multiple platforms" is one of the winning points of Flutter.

But sometimes we need to use platform-specific APIs. A few examples: camera input, geolocation, connectivity, notifications.

By now there are many packages that can do the heavy-lifting for you, so that you don't have to write platform-specific code **directly**.

But it's still very useful (and interesting!) to understand how Flutter apps communicate with the underlying platform APIs.

A good place to start is this page that shows how to use platform channels to read the battery level on iOS and Android:
- [​Writing custom platform-specific code​](https://flutter.dev/docs/development/platform-integration/platform-channels)

There is also a more detailed guide, which explains everything you need to know (including how to **stream** data through channels, and how to **test** your platform channels code):
- [​Flutter Platform Channels​](https://medium.com/flutter/flutter-platform-channels-ce7f540a104e)

To write platform-specific code, you'll need to become familiar with Swift (on iOS) and Kotlin (on Android). This is a **good** thing because it makes you a better developer who is comfortable with more than just one language or framework.

You don't need to reach expert-level knowledge of other languages. But knowing just enough to find your way around is a valuable skill. And since many of the existing plugins are [far from perfect](https://www.reddit.com/r/FlutterDev/comments/jrt8hu/am_i_the_only_one_frustrated_by_the_status_of/), sooner or later you may find yourself working with platform-specific APIs.


## Day 13: Testing

Testing is paramount if you're serious about building robust, production-ready apps.

The main point of testing is to verify that our code is bug-free and behaves as expected.

While manual tests can be carried out by trying all your application's features, they are very error prone and time consuming. If bugs are not caught early on, they can occur in production, leading to a poor user experience.

Automated tests solve this problem as they are fast to run, and they can run often. They are also a good safety netthat can help you find out if something breaks when you refactor your code.

In Flutter, there are three types of tests: unit tests, widget tests and integration tests. This page on the official documentation offers a quick overview:

​Testing Flutter apps​
For a complete tutorial about writing tests with some examples, I recommend this video:

​Flutter Testing For Beginners - The Ultimate Guide​
This covers unit, widget, and integration tests, and also explains how to use the mockito package. This is useful when testing individual parts of your application in isolation from the rest of the code (e.g. networking).

Alongside unit, widget and integration test, a technique known as golden tests is sometimes used.

Golden tests allow you to compare a screen of your app with some reference image file, to ensure that each pixel in the UI matches exactly with the golden version.

This technique is quite useful if you want to verify that you don't get UI regressions as you make changes. It is explained well in this article:
​Flutter: Golden tests — compare Widgets with Snapshots.

## Day 14: Continuous integration & delivery
The most popular CI systems for Flutter are Codemagic and Github Actions. These systems let you automate your tests by setting up workflows that run when you want.

For example, you could use them to run your entire test suite when you push a new branch or open/update a pull request. This is quite useful as you can ensure that all the tests are green before merging changes to the main branch.

You can also use CI tools to build release versions of your apps and deliver them to the App Store or Play Store.

Or if you want to distribute internal builds to your beta testers, you can do that too.

So how are Codemagic and GitHub Actions different?

Codemagic
The main strength of Codemagic is that it's easy to use. You can setup and customize your workflows in a completely visual way, and it has support for custom build steps and various 3rd party integrations. For example, you can configure it to send a Slack notification when your builds succeed or fail.

This article offers a good overview of Codemagic:

​7 reasons why Codemagic should be your CI/CD provider for your Flutter apps in 2020​
Codemagic offers 500 build minutes for free every month. See this pricing page for more information.

GitHub actions
Unlike Codemagic, GitHub Actions does not offer a UI interface. Instead, you write custom build workflows in yaml format, and you can use pre-built actions that are freely avaiable in the GitHub marketplace.

For an example of how GitHub workflows look like, you can check the documentation for the Flutter action:

​Flutter action​
For a detailed introduction to GitHub Actions, you can follow this guide:

​Introduction to GitHub Actions​
Actions are quite powerful but they come with a steeper learning curve. If you make a typo or mistake in your workflow file, you can only find out what went wrong by inspecting the build log once the build has completed.

In terms of pricing, GitHub Actions offers 2000 minutes per month on the Free plan, though macOS minutes are 10x more expensive than the basic Linux minutes. For a full overview of GitHub Actions pricing, see this page:

​About billing for GitHub Actions​
Fastlane
​Fastlane is an open-source tool that makes it easy to automate beta deployments and releases for your iOS and Android apps.

Fastlane is particularly useful when it comes to managing and updating the code signing certificates (notably a painful thing to do on iOS), and signing release apps.

As such, many people use Fastlane in their Flutter build workflows, either with GitHub Actions or Codemagic.

The official Flutter documentation offers a good overview about continuous delivery with fastlane:

​Continuous delivery with Flutter​
It can take a bit of time to setup Fastlane the first time, but once it's up and running it can save a lot of time in the future.

Releasing to the app stores
Once your app is ready, it's time to release it to your users.

The official documentation includes some important steps that you need to follow in preparation for this:

​Build and release an Android app​
​Build and release an iOS app​
If your app uses Firebase, you may also find this release checklist useful:

​Firebase Launch Checklist

## Day 15: 
