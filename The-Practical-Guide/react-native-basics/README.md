# React Native Basics

[Completed CourseGoals Project](https://github.com/arjunkahlon/react-native/tree/main/react-native-the-practical-guide/section-2-react-native-basics/CourseGoals)

- [React Native Basics](#react-native-basics)
  - [Core Components & Styling](#core-components-and-styling)
  - [Working With Core Components](#working-with-core-components)
  - [Styling React Native Apps](#styling-react-native-apps)
  - [Core Components & Styling - More Information](#styling-more-information)
  - [React Native Flexbox](#react-native-flexbox)
  - [Quiz 1: Components, Styles, Layouts](#quiz-1)
  - [Handling Events](#handling-events)
  - [ScrollView](#scrollview)
  - [FlatList](#flatlist)
  - [Quiz 2: More Components and Lists](#quiz-2)
  - [Pressable](#pressable)
  - [Modal](#modal)
  - [Image](#image)



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

## Handling Events

  Handling events is performed in the same way as in web applications
    We can connect event listeners to event handler functions and we can manage state
    in our components with the useState hook. 

      <Button
        onPress={() => {
          console.log('You tapped the button!');
        }}
        title="Press Me"
      />

  For React Native, events are received over the bridge that links native code with React

## ScrollView

  The ScrollView Component is scrollable container provided by React Native

    ScrollView renders all its react child components at once, but this has a performance downside.

    ScrollView style={styles.scrollView}>
        <Text style={styles.text}>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
          eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad
          minim veniam, quis nostrud exercitation ullamco laboris nisi ut
          aliquip ex ea commodo consequat. Duis aute irure dolor in
          reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
          pariatur. Excepteur sint occaecat cupidatat non proident, sunt in
          culpa qui officia deserunt mollit anim id est laborum.
        </Text>
      </ScrollView>

## FlatList

  If we have a long list, using a ScrollView is very ineffecient. For dymanic lists, we want to
  use another built in component, FlatList.

  The FlatList is built for scrollable lists and will only render the items that are visible. All
  of the items off-screen will only be load and rendered lazily as they are needed. 

    import React from 'react';
    import {
      SafeAreaView,
      View,
      FlatList,
      StyleSheet,
      Text,
      StatusBar,
    } from 'react-native';

    const DATA = [
      {
        id: 'bd7acbea-c1b1-46c2-aed5-3ad53abb28ba',
        title: 'First Item',
      },
      {
        id: '3ac68afc-c605-48d3-a4f8-fbd91aa97f63',
        title: 'Second Item',
      },
      {
        id: '58694a0f-3da1-471f-bd96-145571e29d72',
        title: 'Third Item',
      },
    ];

    type ItemProps = {title: string};

    const Item = ({title}: ItemProps) => (
      <View style={styles.item}>
        <Text style={styles.title}>{title}</Text>
      </View>
    );

    const App = () => {
      return (
        <SafeAreaView style={styles.container}>
          <FlatList
            data={DATA}
            renderItem={({item}) => <Item title={item.title} />}
            keyExtractor={item => item.id}
          />
        </SafeAreaView>
      );
    };

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        marginTop: StatusBar.currentHeight || 0,
      },
      item: {
        backgroundColor: '#f9c2ff',
        padding: 20,
        marginVertical: 8,
        marginHorizontal: 16,
      },
      title: {
        fontSize: 32,
      },
    });

    export default App;

## Quiz 2

    How do you output a list (array) of content in React apps? You need a special component to output a list (array) of data. 
      You use map() to map (= transform) the array of data into 
      an array of components.

    Why might you need a <ScrollView> instead of a normal <View>?
      Unlike the browser, mobile apps don't give you automatic scrolling.
      <ScrollView> adds it.

    What's the core difference between <FlatList> and <ScrollView>?
      FlatList optimizes scrolling by only rendering what's required.

## Pressable

  Pressable is a Core Component wrapper that can detect various stages of press interactions on any of its defined children.

    We use Pressable by wrapping the item that should be pressable.
   
    <Pressable onPress={onPressFunction}>
      <Text>I'm pressable!</Text>
    </Pressable>

  How it works
  On an element wrapped by Pressable:

    onPressIn is called when a press is activated.
    onPressOut is called when the press gesture is deactivated.

  Example

    import React, {useState} from 'react';
    import {Pressable, StyleSheet, Text, View} from 'react-native';

    const App = () => {
      const [timesPressed, setTimesPressed] = useState(0);

      let textLog = '';
      if (timesPressed > 1) {
        textLog = timesPressed + 'x onPress';
      } else if (timesPressed > 0) {
        textLog = 'onPress';
      }

      return (
        <View style={styles.container}>
          <Pressable
            onPress={() => {
              setTimesPressed(current => current + 1);
            }}
            style={({pressed}) => [
              {
                backgroundColor: pressed ? 'rgb(210, 230, 255)' : 'white',
              },
              styles.wrapperCustom,
            ]}>
            {({pressed}) => (
              <Text style={styles.text}>{pressed ? 'Pressed!' : 'Press Me'}</Text>
            )}
          </Pressable>
          <View style={styles.logBox}>
            <Text testID="pressable_press_console">{textLog}</Text>
          </View>
        </View>
      );
    };

    const styles = StyleSheet.create({
      container: {
        flex: 1,
        justifyContent: 'center',
      },
      text: {
        fontSize: 16,
      },
      wrapperCustom: {
        borderRadius: 8,
        padding: 6,
      },
      logBox: {
        padding: 20,
        margin: 10,
        borderWidth: StyleSheet.hairlineWidth,
        borderColor: '#f0f0f0',
        backgroundColor: '#f9f9f9',
      },
    });

    export default App;

## Modal

  The Modal component provides an overlay of content over the main screen.

  We wrap the Modal component around the content we want to go into the Modal.

    import React, {useState} from 'react';
    import {Alert, Modal, StyleSheet, Text, Pressable, View} from 'react-native';

    const App = () => {
      const [modalVisible, setModalVisible] = useState(false);
      return (
        <View style={styles.centeredView}>
          <Modal
            animationType="slide"
            transparent={true}
            visible={modalVisible}
            onRequestClose={() => {
              Alert.alert('Modal has been closed.');
              setModalVisible(!modalVisible);
            }}>
            <View style={styles.centeredView}>
              <View style={styles.modalView}>
                <Text style={styles.modalText}>Hello World!</Text>
                <Pressable
                  style={[styles.button, styles.buttonClose]}
                  onPress={() => setModalVisible(!modalVisible)}>
                  <Text style={styles.textStyle}>Hide Modal</Text>
                </Pressable>
              </View>
            </View>
          </Modal>
          <Pressable
            style={[styles.button, styles.buttonOpen]}
            onPress={() => setModalVisible(true)}>
            <Text style={styles.textStyle}>Show Modal</Text>
          </Pressable>
        </View>
      );
    };

    const styles = StyleSheet.create({
      centeredView: {
        flex: 1,
        justifyContent: 'center',
        alignItems: 'center',
        marginTop: 22,
      },
      modalView: {
        margin: 20,
        backgroundColor: 'white',
        borderRadius: 20,
        padding: 35,
        alignItems: 'center',
        shadowColor: '#000',
        shadowOffset: {
          width: 0,
          height: 2,
        },
        shadowOpacity: 0.25,
        shadowRadius: 4,
        elevation: 5,
      },
      button: {
        borderRadius: 20,
        padding: 10,
        elevation: 2,
      },
      buttonOpen: {
        backgroundColor: '#F194FF',
      },
      buttonClose: {
        backgroundColor: '#2196F3',
      },
      textStyle: {
        color: 'white',
        fontWeight: 'bold',
        textAlign: 'center',
      },
      modalText: {
        marginBottom: 15,
        textAlign: 'center',
      },
    });

    export default App;

## Image

  React Native provides an Image component for displaying different types of 
  images, including network images, static resources, temporary local images, 
  and images from local disk, such as the camera roll.

    import React from 'react';
    import {View, Image, StyleSheet} from 'react-native';

    const styles = StyleSheet.create({
      container: {
        paddingTop: 50,
      },
      tinyLogo: {
        width: 50,
        height: 50,
      },
      logo: {
        width: 66,
        height: 58,
      },
    });

    const DisplayAnImage = () => {
      return (
        <View style={styles.container}>
          <Image
            style={styles.tinyLogo}
            source={require('@expo/snack-static/react-native-logo.png')}
          />
          <Image
            style={styles.tinyLogo}
            source={{
              uri: 'https://reactnative.dev/img/tiny_logo.png',
            }}
          />
          <Image
            style={styles.logo}
            source={{
              uri: 'data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADMAAAAzCAYAAAA6oTAqAAAAEXRFWHRTb2Z0d2FyZQBwbmdjcnVzaEB1SfMAAABQSURBVGje7dSxCQBACARB+2/ab8BEeQNhFi6WSYzYLYudDQYGBgYGBgYGBgYGBgYGBgZmcvDqYGBgmhivGQYGBgYGBgYGBgYGBgYGBgbmQw+P/eMrC5UTVAAAAABJRU5ErkJggg==',
            }}
          />
        </View>
      );
    };

    export default DisplayAnImage;