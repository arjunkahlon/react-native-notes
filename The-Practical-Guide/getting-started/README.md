# Getting-Started

- [Getting Started](#getting-started)
  - [What is React Native](#what-is-react-native)
  - [Under the Hood](#under-the-hood)
  - [Creating React Native Projects](#creating-react-native-projects)
  - [Creating a New React Native Project](#creating-a-new-react-native-project)
  - [Analyzing Created Project](#analyzing-created-project)
  - [Running First App](#running-app)
  - [Local Environment](#environment)
  - [Course Content](#course-content)


## What is React Native

    React.js + React Native -> Real Native Mobile Apps for iOS and Android

    React.js is a library that is independent of both React Native and React DOM.
        Web support for React is accomplished through react-dom. React on its own 
        is a standalone library for building user interfaces. React itself is platform-agnostic.
        React Native is an alternative to ReactDOM
    
    React Native ships with built in components that are compiles into native UI elements for iOS and Android.
        React Native also exposes native platform APIs such as device camera.

## Under the Hood

    React Native exposes special components which will be compiled by React Native
        The views (JSX code) is compiled while the JavaScript logic code is not.

        For example, the React Native JSX element <View> is compiled to android.View native 
        component for Android and UIView native component for iOS. The equivalent in the web 
        browser is a <div>. The React Native JSX element <TextInput> is compiled to an EditText 
        native component on Android and UITextField native component on iOS. React Native maps 
        (and compiles) re-usable components to respective platform equivalents.
    
    Unline the UI elements, the lgoic is not compiled. Instead it is ran on a JavaScript thread
    hosted by React Native (in the app).
        React Native spins up a simple JavaScript process as part of the native app and allows this
        process to talk to the underlying native platform. 

## Creating React Native Projects

Official documentation for React Native can be found at:
        https://reactnative.dev/docs/getting-started
    
    To get started with React Native, we can set up our app and development environment with two 
    tools: Expo CLI and React Native CLI
        For new React Native Developers, Expo is the recommended choice due to the provided tools. 
        It only requires a recent version of Node as well as a phone/simulator. We will be using 
        Expo for this course.

        Native CLI requires macOS in order to build iOS apps, meaning Windows users must use obtuse
        workarounds.

        Expo is a free third-party service for building and shipping React Native apps. It provides
        a manages app development workflow. You can leave the Expo ecosystem at any time.

        React Native CLI is created by the React Native team and community. It provides a bare-bone
        development setup which requires more manmul configuation. An advantage over Expo, is that
        it is easier to integrate with native source code. 

## Creating a New React Native Project

Official documentation for React Native Environment Setup can be found at:
        https://reactnative.dev/docs/environment-setup
    
    Installation 
        1. We must first confirm that we have Node 12 LTS or greater installed. Node
            will be used by some packages under the hood. 
        2. We then run the command: "npx create-expo-app AwesomeProject" to create a 
            new React Native project called "AwesomeProject".
        3. Navigate into the project directory and run the command "npx expo start"
            to start the development server.
        4. We have the option of either using a physical phone or simulator. An iOS 
            simulator will requrie XCode and Android will require Android Studio. To
            use our physical phone, install the Expo Go app and scan the QR Code in
            the terminal of our running server. 
        5. Once we have our app successfully running, we can modify App.js and see the
            changes reflected with automatic reload. 
    
    For TypeScript
        1. We create a tsconfig.json file with the comand "touch tsconfig.json"
        2. Run the "npx expo start command". We will be prompted to isntall 
            dependencies (typescript, @tpyes/react, @types/react-native), and
            automatically configure our tsconfig.json.
        3. We can also create a TypeScript project at the start by using the comman
            "expo init <AppName>" and selecting the blank (TypeScript) option with
            TypeScript configuration.


## Analyzing Created Project

    After creating our Expo project, we see the contents of our project folder.
        .expo-shared: Holds internally used information for our project

        assets: Directory that holds any file that lives along the source code 
            of app. Examples include images, fonts, and sounds.

        node-modules: Directory of packages used under-the-hood. 

        package.json: Lists project description and functional metadata such 
            as name, version, and dependencies. 

        babel.config.js: Configures how code is transpiled under the hood.

        app.json: Configure settings and behaviors of out React Native app. This file
            will be picked up by Expo when our app is built for preview or for the 
            actual app store.

        App.js: Starting point of our React Native Application. We use Special JSX
            elements exposed by 'react-native'. The SyleSheet is an abstraction
            similar to CSS StyleSheets. 

## Running First App

    With Expo, it is easy to preview our App on our physical device. 
        1. Install the Expo Go app from the App Store of your phone (App Store/Google Play).
        2. Scan the QR code in the terminal of your running development server. This QR
            code and also be found in the browser tab that has opened up. Here we will 
            find log methods printed by Expo as our app is running. 
        3. Once we scan the QR code, grant the permissions.
        4. The JavaScript bundle will be built and the app will open in the Expo Go app
            on our device. 
        5. Make a change in App.js and save the changes. This change will update on our 
            device due to automatic reload. 

## Local Environment

    If we want to develop for a device we don't own, we can install a simulator.
        Android simulator provided by Android Studio. iPhone simulator provided
        by Xcode. Unfortunately, Xcode is only provided on Mac, and not on Windows
        or Linux. Thus, for Windows developers, a physical device or cloud
        configuration is required. 

    Android Studio
        1. Click the More Actions button and select Virtual Device Manager.
        2. This manager will allow us to select from a variety of device presets
            and Android versions. Choose the latest version of Android and keep
            the default settings.
        3. Click finish and we will see the device in our list of devices. Click
            the Play button to launch the simulator. 
        4. In our VS Code terminal, we can press "a" to open Android. This will
            install the Expo Go app on our simulator, and then build and open our 
            application. 

    XCode
        1. Open package contents of XCode App.
        2. Under Contents -> Developer -> Applications, we will find the Simulator.app.
        3. Double click Simulator.app to start the iOS simulator. Under File -> Open 
            Simulator, we can choose from a variety of iPhone simulators.
        4. In our VS Code terminal, we can press "i" to install the Expo Go app on our
            iOS simulator, and then build and open our application. 

## Course Content

    React Native Essentials
        1. Basics and Fundamentals
        2. Dynamic and Adaptive Layouts
        3. Navigation

    React Native Intermediate Modules
        1. React & React Native
        2. Redux & React Native
        3. Complete Example App
        4. Handling User Input
        5. Network Requests
    
    React Native Advanced Modules
        1. User Authentication
        2. Native Device Features
        3. Push Notifications
        4. Publishing Apps
