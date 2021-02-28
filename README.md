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
![Flutter Doctor](https://pbs.twimg.com/media/EvVHzQAVoAIwfbx?format=jpg&name=large)

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


## Day2: Dart Language
