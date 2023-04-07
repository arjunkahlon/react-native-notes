# React Native Basics

[Completed CourseGoals Project](https://github.com/arjunkahlon/react-native/tree/main/react-native-the-practical-guide/section-2-react-native-basics/CourseGoals)

- [React Native Basics](#react-native-basics)
  - [Core Components & Styling](#core-components-and-styling)
  - [Working With Core Components](#working-with-core-components)
  - [Styling React Native Apps](#styling-react-native-apps)
  - [Core Components & Styling - More Information](#styling-more-information)
  - [React Native Flexbox](#react-native-flexbox)
  - [Quiz 1: Components, Styles, Layouts](#quiz-1)


## Core Components and Styling

[Core Components & API Provided by React Native](https://reactnative.dev/docs/components-and-apis)

  Core Components are translated to native UI elements. We can
  combine these core components to build our user interface.

    const MyTitle = props => {
      return (
        <View>
          <Text>{props.title}</Text>
        </View>
      );
    };

  There is no CSS. We instead use either inline styles or StyleSheet Objects. While
  this styling is based on CSS syntax, only a subset of properties and feature are
  supported. This styling also uses camelCase naming convention.

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        backgroundColor: '#fff',
        alignItems: 'center',
        justifyContent: 'center',
      }
    })

## Working With Core Components

  Basic Components:

  The View Component is the most fundamental component for building a UI.

  The Text Component is used for displaying text.

  The Image Component is used for displaying Images.

  The TextInput Component is used for inputting text into the app via a keyboard.

  The ScrollView Component provides a scrolling container that can host multiple 
  components and views.


    <View style={styles.container}>
      <Text>Hello World!</Text>
    </View>

    <View style={styles.container}>
      <Text>Hello World!</Text>
      <View>
        <Text>Hello Inner World!</Text>
      <View>
    </View>

## Styling React Native Apps

  There is no CSS support in React Native. Instead styling is added
  inline or through StyleSheet Objects.

  Inline Styling

    <Text
      style = {{
        margin: 16,
        borderWidth: 2,
        borderColor: 'red',
        padding: 16
      }}
    >
      Hello World!    
    </Text>

  StyleSheet Styling

    <Text style = {styles.textStyle}>
      Hello World!
    </Text>

    const styles = StyleSheet.create({
      textStyle: {
        margin: 16,
        borderWidth: 2,
        borderColor: 'red',
        padding: 16
      }
    })
    
## Styling More Information

[React Native Styling Documentation](https://reactnative.dev/docs/style)

[React Native Styling - Colors](https://reactnative.dev/docs/colors)

[React Core Component - View Documentation](https://reactnative.dev/docs/view)

[React Core Component - Text Documentation](https://reactnative.dev/docs/text)

[React Core Component - Image Documentation](https://reactnative.dev/docs/image)

[React Core Component - ScrollView Documentation](https://reactnative.dev/docs/scrollview)

[React Core Component - TextInput Documentation](https://reactnative.dev/docs/textinput)

## React Native Flexbox

  Layouts are typically created with Flexbox (similar to CSS Flexbox). Elements
  are positioned inside containers.

  flexDirection controls the orientations of the Main-Axis and Cross-Axis.

    flexDirection: 'column'
      Main-Axis: Top-to-Bottom
      Cross-Axis: Left-to-Right

    flexDirection: 'row'
      Main-Axis: Left-to-Right
      Cross-Axis: Top-to-Bottom

  In CSS Flexbox, flex-direction defaults to 'row', but in React Native, 
  flexDirection defaults to 'column'.

  justify-content aligns items on the main axis while align-items aligns
    items on the cross-axis. These axis are determined by flexDirection.

  flex will define how your items are going to “fill” over the available space along your main axis. Space will be divided according to each element's flex property. If View 1 uses flex: 2 and View
  2 uses flex: 4, then View 1 will occupy 2/6 of the available space while View 2 will occupy 4/6.

## Quiz 1

    What's one of the main roles of the built-in <View> component?
      Structure/Group other child components.

    Can you use HTML elements (e.g. <div>, <p>, <input>) in React Native apps?
      No, React Native doesn't recognizes these components - it doesn't
      know how to compile them to native views.

    What's the relation between React Native component styling and CSS (Cascading Style Sheets) for the Web?
      React Native styling is inspired by CSS (comparable/similar property 
      names and values)

    Which of the following example style rules does NOT work in React Native?
      'background-color': '#ccc'

    Why would you use const styles = StyleSheet.create({}) instead of a regular JavaScript object (const styles = {})?
      Using a StyleSheet adds validation and potential performance improvements.

    What is "Flexbox"?
      A concept/set of styling properties that allows you to structure content.
  
    What's the default styling/ layout behavior of a <View> component?
      It uses Flexbox to organize its child components.

    If a <View> has flexDirection: 'column' (which is the default) - what does alignItems: 'flex-end' do in that case?
      It positions all child elements at the end of the column
        - on the horizontal axis.
