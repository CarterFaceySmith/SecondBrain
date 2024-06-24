Custom widgets/items can be created and reused throughout your application using Qt.
## Creating custom QML items

1. Create a .qml file
2. import QtQuick
3. Define some Item
## Incorporating custom QML items into a project
CMakeLists.txt
```qml
qt_add_qml_module(MyAppTarget
	URI MyAppImport
	VERSION 1.0
	QML_FILES MyFile.qml
)
```

OtherFile.qml
```qml
import QtQuick
import MyAppImport

MyFile {
	id: myObj
	// ...
}
```

MyFile.qml
```qml
import QtQuick
Item {
	id: root
	// ...
}
```

See also:
- [[Qt QML]]