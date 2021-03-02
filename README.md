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

## Day 5: State management basics

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
