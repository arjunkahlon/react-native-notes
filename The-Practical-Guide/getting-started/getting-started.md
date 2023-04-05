# Getting-Started

- [Getting Started](#getting-started)
  - [What is React Native](#what-is-react-native)
  - [Under the Hood](#under-the-hood)
  - [Creating React Native Projects](#creating-react-native-projects)
  - [Creating a New React Native Project](#creating-a-new-react-native-project)
  - [Analyzing Created Project](#analyzing-created-project)
  - [Running First App](#running-app)
  - [Local Environment](#environment)

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
    



## Analyzing Created Project

## Running First App

## Local Environment