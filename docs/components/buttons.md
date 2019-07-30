<!--docs:
title: ""
layout: detail
section: components
excerpt: "Material Buttons implementation article for iOS"
iconId:
path: /
api_doc_root:
initial_release:
-->

# Buttons

Buttons allow users to take actions and make choices with a single tap.
Buttons can be customized to meet your style requirements.

For more information, go to the [Buttons](https://material.io/components/buttons/#usage) guidance page.

## Buttons variants


* [Text button](#text-button)
* [Outlined button](#outlined-button)
* [Contained button](#contained-button)
* [Toggle button](#toggle-button)


## Using buttons


### Install `mcd-button`

Before using the `MDCButtons` component to implement its variants you must install `MCDButtons`. In your source files import the component, and then apply your theme:
1. Install `MDCButtons`
   * Use CocoaPods to install `MDCButtons`
     1. Add the following to your `Podfile`:
       ```bash
      pod MaterialComponents/Buttons
       ```
     1. Run the installer:
       ```bash
       pod install
       ```
1. Import `MDCButtons` and MDC buttons theming and initialize `MDCButtons` using `alloc`/`init`. Initialize your theme  before applying it to your button.

  **Note** For more information about themes, go to the [Theming page](https://material.io/develop/ios/components/theming/) for iOS.

       **Swift**
       ```swift
       import MaterialComponents.MaterialButtons
       import MaterialComponents.MaterialButtons_Theming
       /*...*/
       let <local theme name> = <theme name>
       let button = MDCButton()
       ```
       **Objective-C**
       ```objc
       #import "MaterialButtons.h"
       #import <MaterialComponentsBeta/MaterialButtons+Theming.h>
       /*...*/
       <theme name> *<local theme name> = [[<theme name> alloc] init];
       MDCButton *button = [[MDCButton alloc] init];
     ```
 1. Apply accessibility settings
    To help make your buttons usable to as many users as possible:
    * Set an appropriate [`accessibilityLabel`](https://developer.apple.com/documentation/uikit/uiaccessibilityelement/1619577-accessibilitylabel) value if your button does not have a title or only has an icon.
        **Objective-C**
        ```objc
        button.accessibilityLabel = @"Create";
        ```
        **Swift**
        ```swift
        button.accessibilityLabel = "Create"
        ```

### Related APIs

* [MDCRaisedButton](https://material.io/components/ios/catalog/buttons/api-docs/Classes.html#/c:objc(cs)MDCRaisedButton)
* [Themes](https://material.io/develop/ios/components/theming/)

### Text button

Text buttons are typically used for less-pronounced actions, including those located:
 * In dialogs
 * In cards
In cards, text buttons help maintain an emphasis on card content.

<img src="assets/ios-text-button.gif" alt="animated gif of an iOS text button">

---
NOTE TO DEVS
Is there more context to the code samples?
---

**Swift**
```swift
button.applyTextTheme(withScheme: <local theme name>)
```

**Objective-C**
```obj-c

MDCButton *button = [[MDCButton alloc] init];
[button applyTextThemeWithScheme:, <local theme name>];
```


#### Text button example using [MDCContainerScheme](https://github.com/material-components/material-components-ios/tree/stable/components/schemes/Container) theme

##### APIs used
* [Themes](https://material.io/develop/ios/components/theming/)
* [MDCButton](https://material.io/develop/ios/components/buttons)
-----------
Note to developers:
The current examples appear to be fragmentary. Are there other properties that need to be declared/set, or can a user copy/paste the examples to use in their own code?
------------
**Swift**

```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming

let containerScheme = MDCContainerScheme()
let button = MDCButton()
button.applyTextTheme(withScheme: containerScheme)
```

**Objective-C**

```ObjC
#import <MaterialComponents/MaterialButtons.h>
#import <MaterialComponents/MaterialButtons+Theming.h>

MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
MDCButton *button = [[MDCButton alloc] init];
[button applyTextThemeWithScheme:containerScheme];
```

### Outlined button

Outlined buttons are medium-emphasis buttons. They contain actions that are important, but aren’t the primary action in an app.

<img src="assets/ios-outlined.gif" alt="animated gif of an iOS outlined button">

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming

let containerScheme = MDCContainerScheme()
let button = MDCButton()
button.applyTextTheme(withScheme: containerScheme)
```
**Objective-C**
```objc

#import "MaterialButtons.h"
#import <MaterialComponentsBeta/MaterialButtons+Theming.h>

MDCContainerScheme *containerScheme = [[MDCContainerScheme alloc] init];
MDCButton *button = [[MDCButton alloc] init];

[self.button applyTextThemeWithScheme:self.containerScheme];
```

#### Outlined button example using [MDCContainerScheme](https://github.com/material-components/material-components-ios/tree/stable/components/schemes/Container) theme

##### APIs used
* [Themes](https://material.io/develop/ios/components/theming/)
* [MDCButton](https://material.io/develop/ios/components/buttons)

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming

let button = MDCButton()
button.applyTextTheme(withScheme: containerScheme)
```
**Objective-C**
```objc
#import <MaterialComponents/MaterialButtons.h>
#import <MaterialComponentsBeta/MaterialButtons+Theming.h>

MDCButton *button = [[MDCButton alloc] init];
[self.button applyTextThemeWithScheme:self.containerScheme];
```
### Contained button
Contained buttons are high-emphasis, distinguished by their use of elevation and fill. They contain actions that are primary to your app.

<img src="assets/ios-contained.gif" alt="animated gif of an iOS contained button">

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming

let button = MDCButton()
button.applyContainedTheme(withScheme: containerScheme)
```

**Objective-C**
```objc
#import <MaterialComponents/MaterialButtons.h>
#import <MaterialComponentsBeta/MaterialButtons+Theming.h>

MDCButton *button = [[MDCButton alloc] init];
[self.button applyContainedThemeWithScheme:self.containerScheme];
```

#### Contained button example using [MDCContainerScheme](https://github.com/material-components/material-components-ios/tree/stable/components/schemes/Container) theme


##### APIs used
* [Themes](https://material.io/develop/ios/components/theming/)
* [MDCButton](https://material.io/develop/ios/components/buttons)

**Swift**
```swift
import MaterialComponents.MaterialButtons
import MaterialComponents.MaterialButtons_Theming

let button = MDCButton()
button.applyContainedTheme(withScheme: containerScheme)
```
**Objective-C**
```objc
#import <MaterialComponents/MaterialButtons.h>
#import <MaterialComponentsBeta/MaterialButtons+Theming.h>

MDCButton *button = [[MDCButton alloc] init];
[self.button applyContainedThemeWithScheme:self.containerScheme];
```

### Toggle button

Icon buttons allow users to take actions, and make choices, with a single tap. The icon button can be used to toggle between an on and off icon.

**Swift**


**Objective-C**

#### Toggle button example

##### APIs used
