<!-- TOC -->
* [Mobile-Development-Checklist](#Mobile-Development-Checklist)
  * [Run the project](#run-the-project)
    * [Install the dependencies](#install-the-dependencies)
    * [Run the storybook server](#run-the-storybook-server)
    * [Run the project for Android](#run-the-project-for-android)
    * [Run the project for IOS](#run-the-project-for-ios)
  * [Code Guidelines](#code-guidelines)
    * [Naming Conventions:](#naming-conventions-)
    * [Imports:](#imports-)
    * [Component Structure:](#component-structure-)
  * [Steps](#steps)
  * [Rules](#rules)
  * [Theme and styles](#theme-and-styles)
<!-- TOC -->

# Mobile-Development-Checklist


## Run the project
### Install the dependencies

`yarn install`

### Run the storybook server

`yarn storybook`

### Run the project for Android

`yarn android`

### Run the project for IOS

`yarn ios`

## Code Guidelines

### Naming Conventions:

- **Component names:**
  Use PascalCase to name components.\
  `const MyComponent = () => {
  ...
  };`

- **Variable names:**
  Use camelCase to name variables.\
  `const myVariable = "Hello, world!";`

- **Interface and type names:**
  Use PascalCase to name interfaces and types.\
  `interface MyInterface {
  ...
  }`

- **Enum names:**
  Use PascalCase to name enums.\
  `enum MyEnum {
  ...
  }`

- **Function names:**
  Use camelCase to name functions.\
  `const myFunction = () => {
  ...
  };`

- **Constant names:**
  Use uppercase and snake_case to name constants.\
  `const MY_CONSTANT = "Hello, world!";`

- **Storybook file names:**
  Use kebab-case to name files and ends with the word stories.\
  `my-component-stories.tsx`

- **Variable names for React elements:**
  Use PascalCase to name variables that hold React elements.\
  `const MyElement = <Text>Hello, world!</Text>;`

- **Props:**
  Use camelCase to name props.\
  `interface MyComponentProps {
  myProp: string;
  }`

### Imports:

- **React imports:**
  Always import React from ‘react’ at the top of your file when you’re creating a new component that will use React.

  ```
  import React from 'react';
  ```

- **Library imports:**
  Import libraries and third-party packages before any other imports.

  ```
  import React from 'react';
  import { StyleSheet, View } from 'react-native';
  import { useNavigation } from '@react-navigation/native';
  ```

- **Component imports:**
  Import your own custom components after any library imports.

  ```
  import React from 'react';
  import { StyleSheet, View } from 'react-native';
  import { MyComponent } from './MyComponent';
  ```

- **Group imports:**
  Group your imports by type, with React imports at the top, followed by libraries, components, and other files.

  ```
  import React from 'react';
  import { StyleSheet, View } from 'react-native';

  import { MyComponent } from './MyComponent';
  import { MyOtherComponent } from './MyOtherComponent';

  import myFunction from './myFunction';
  import myOtherFunction from './myOtherFunction';
  ```

### Component Structure:

- **Import statements:**
  Import any necessary dependencies at the top of the file, before the component definition.

  ```
  import React from 'react';
  import { StyleSheet, View, Text } from 'react-native';

  interface MyComponentProps {
    title: string;
  }

  const MyComponent: React.FC<MyComponentProps> = ({ title }) => {
    // ...
  };
  ```

- **Props:**
  Define the props interface above the component definition, using PascalCase for the interface name and camelCase for the prop names.

  ```
  interface MyComponentProps {
    title: string;
  }

  const MyComponent: React.FC<MyComponentProps> = ({ title }) => {
    // ...
  };
  ```

- **Structure:**
  Use the following structure for a component:
  ```
  Imports
  Props
  State
  Component lifecycle methods
  Helper functions
  Render function
  ```

## Steps

After running the App:

1. Press on Storybook
2. At the bottom you will see the Navigator button, you can see from there the list of available components
3. Go to the components folder, add a folder with the name of the component you will be working on and add 3 files
    - `index.tsx`
    - `styles.ts`
    - `[name].stories.tsx`
4. Go to the storybook folder and add your component to the storybook at the bottom
5. Go back to the `index.tsx` and `styles.ts` and code your components
6. In the file `[name].stories.tsx` add all the possible views of the components by trying all the possible combinations of the props, and add an explanation
7. Before doing anything, check these 3 components (View, Pressable, Text), it's what you will be using instead of the default components provided by react-native

## Rules

- A component must contain UI only, no logic inside, if we need logic, we will create another component that wraps that component
- Every component must be in it's own branch, a PR must contain only a single component
- The name of the branch must be in this format `feature/component_componentName`
- Prettify your code before making a commit using `yarn prettify` or using your editor shortcuts
- Be sure that linting rules are all applied, otherwise the commit will not be accepted and will not pass

## Theme and styles

- Don't use these components [Text, Pressable, View] provided by react-native, use the ones that are in the components folder
- Use only colors that exists in `constantStyles\colors.ts` by importing them using `import { Colors } from 'constantStyles'`
- For Typography styles to use in other texts for example in navigation, other libraries, use the Typography variants from `import { TypographyStyles } from 'constantStyles'`
- For margins, paddings, use the values from `import { Spacing } from 'constantStyles'`
- For widths and heights, use the values from `import { Dimensions } from 'constantStyles'`

