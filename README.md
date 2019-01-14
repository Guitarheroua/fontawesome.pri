# FontAwesome.pri

FontAwesome.pri bundle FontAwesome font and icon table into a single module for QML project.

## Features

 1. Installable by qpm
 2. Work well with Qt Quick Designer. Able to show icons in "Design" mode
 3. Auto-completion of icon name works in Qt Creator.

## Example

 ```qml
import QtQuick 2.12
import FontAwesome 1.0

Text {
  // The font will be loaded once the singleton object, FontAwesome, is referred in the application.
  text: FontAwesome.icon.addressBook
  font.family: FontAwesome.fontAwesomeFreeSolid
}
```

![Screenshot](https://raw.githubusercontent.com/benlau/fontawesome.pri/master/docs/designmode.png)

## Installation

Install FontAwesome.pri by qpm:

    qpm install font.awesome.pri

Add "qrc://" to your QML import path

    engine.addImportPath("qrc:///"); // QQmlEngine

## API

### FontAwesome

FontAwesome is a singleton object. 
Once it is referred in your code, it will load the font into memory. 
Then it will be available for all other components.
Therefore, it is recommended to refer it to main.qml.

### Font Families

1. FontAwesome.fontAwesomeFreeSolid
2. FontAwesome.fontAwesomeBrandsRegular
3. FontAwesome.fontAwesomeFreeRegular

They hold the font names, as, from Font Awesome version 5, fonts separated. You may pass them to the `font.family` in a Text component

### Icons Table

Moreover, FontAwesome object also holds an icon table. You can get needed icon by calling  `FontAwesome.icon.{ICON_NAME}`
For complete icon list, please check the source of [FontAwesome.qml](./FontAwesome/FontAwesome.qml) file, or go to [Font Awesome website](https://fontawesome.com/icons) to find an icon.

--------