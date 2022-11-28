# Qml-Material-Design-Icons-Font
Provide the ability to use Material Design Icons Font in Qml elements

This repository is a bridge to use [Material Design Icons Font](https://materialdesignicons.com/) in QML application.

## How To Use
Just copy the all files to a folder named `mdi` in your project and use [Mdi.qml](https://github.com/alirezah95/Qml-Material-Design-Icons-Font/blob/master/Mdi.qml) to set Qml Item's font and text!

### Note
* Since Qml `AbstractButton` does not automatically render an html entity of a unicode value, for setting an `AbstractButton`'s text use `forButton()` method of [Mdi.qml](https://github.com/alirezah95/Qml-Material-Design-Icons-Font/blob/master/Mdi.qml). But for `Text` directly use the string properties inside [Mdi.qml](https://github.com/alirezah95/Qml-Material-Design-Icons-Font/blob/master/Mdi.qml).
* You might need to update [qmldir](https://github.com/alirezah95/Qml-Material-Design-Icons-Font/blob/master/qmldir) file and update the module uri based on the directory in which the contents are. See [QML Modules](https://doc.qt.io/qt-6/qtqml-modules-identifiedmodules.html) for more detail.

### Examples
* For `Text` items:
  
    ```qml
    import mdi 1.0

    ...

    Text {
        font.family: Mdi.mdiFont.name
        textFormat: Text.RichText
        text: Mdi.eyeOff
    }

    ```
* For `AbstractButton` derived items:
  
    ```qml
    import mdi 1.0

    ...

    Button {
        font.family: Mdi.mdiFont.name
        text: Mdi.forButton(Mdi.eyeOff)
    }

    ```
