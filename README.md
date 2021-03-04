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

Flutter offers an extensive set of widgets, closely matching the Material Design specification. The Flutter widget catalog also includes Cupertino widgets, which are high-fidelity replicas of all the UI components found on iOS.

Because Flutter controls every pixel on the screen, you can even create your own widgets to deliver a completely custom experience that delights your users.

So what are some good resources to learn about widgets & layouts?

Flutter layouts
A good place to start is this official guide about Layouts in Flutter, showing you how to build some common layouts with useful illustrations.

​Flutter Widget of the week: This is truly an amazing video series from the Flutter team. Most videos are 1-to-2 minutes long and help you learn about the most useful widgets. You don't need to watch the entire series at once, but I won't stop you if you do 😀. And sometimes knowing that a widget exists means that you don't have to create one yourself.
In addition to this, I have also made some video walkthroughs of the most useful layout widgets:

​Flutter Layouts Walkthrough: Row, Column, Stack, Expanded, Padding​
​Flutter Layouts Walkthrough: PageView, ListView, GridView, Slivers, CustomScrollView​
And if you want to create more complex layouts with a lot of scrollable elements, my slivers tutorials have you covered:

​Flutter Slivers Overview: SliverAppBar, SliverPersistentHeader​
​Flutter Slivers Overview: SliverList, SliverGrid, SliverToBoxAdapter, SliverFillRemaining​
All the links above are enough to build common layouts on mobile.

But sooner or later, you may encounter some layout errors (bottom overflow anyone? 😅). To get past that, I highly recommend this page that explains how constraints work in Flutter:

​Understanding constraints​
What's good about this is that it includes a list of nearly 30 example layouts, showing you why sometimes things don't work, and how to fix them.

Responsive Layouts
Once you need to support multiple form factors, you'll need to learn about responsive layouts and how to implement them in Flutter.

For that, I highly recommend this tutorial:

​How to build responsive layout in Flutter​
This will show you how to use MediaQuery, LayoutBuilder, and other useful widgets for creating responsive UIs.

And while you can build a fully responsive Flutter app just with MediaQuery, LayoutBuilder, and other built-in widgets, there are packages that make this process easier.

One such package is responsive_builder, which makes it easy to set custom screen breakpoints, and manage various form factors with an ergonomic API. This is based on this video series about Flutter responsive UI.

## Day 5: State management basics
### State Management
Onn day 3 we discovered that Flutter is declarative, in that it builds the UI to reflect the current state of your app:

UI = f(state)

This is briefly explained in this page called Start thinking declaratively.

But what is state exactly? The Flutter documentation defines state as:

whatever data you need in order to rebuild your UI at any moment in time

It also introduces a clear distinction between app state and ephemeral (or local) state:

- [​Differentiate between ephemeral state and app state​]()
As a rule of thumb, you can use setState and the State class every time you're dealing with local state. This keeps things simple.

When it comes to app state, there are multiple approaches and techniques that you can use. Before going any further, I recommend you check this out:

Flutter Widgets 101
This series covers the basics of state management in Flutter. Make sure you watch and understand this before moving to any of the more complex solutions:

- [​How to Create Stateless Widgets - Flutter Widgets 101 Ep. 1​]()
- [​How Stateful Widgets Are Used Best - Flutter Widgets 101 Ep. 2​]()
- [​Inherited Widgets Explained - Flutter Widgets 101 Ep. 3​]()
- [​When to Use Keys - Flutter Widgets 101 Ep. 4​]()

You can go pretty far and build non-trivial applications with the built-in StatelessWidget, StatefulWidget, and InheritedWidget classes. More importantly, it's critical to understand the foundations of state management before you can move to more complex solutions.

For a comprehensive overview about Flutter's built-in tools for state management, you can also check this:

- [​Flutter State Management Basics and Useful Resources​](https://codewithandrea.com/videos/flutter-state-management-basics/)


## Day 6: State management & architecture

## Day 7: Navigation

## Day 8: Interactivity & user input

## Day 9: Animations

## Day 10: Local data persistence

## Day 11: Networking

## Day 12: Platform Channels

## Day 13: Testing

## Day 14: Continuous integration & delivery

## Day 15: 
