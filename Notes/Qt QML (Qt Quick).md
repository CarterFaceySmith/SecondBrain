Qt QML (Qt Quick) is a framework for creating [[User Interface (UI)]]. It allows you to define user interfaces using a declarative language (QML) and extend it with C++ logic.

### Declarative UI with QML

QML allows you to define UI components declaratively, which are then rendered by the Qt Quick runtime.

**Example (main.qml):**
```qml
import QtQuick

Rectangle {
    width: 400
    height: 200
    color: "lightblue"

    Text {
        text: "Hello, QML!"
        anchors.centerIn: parent
        font.pixelSize: 24
    }
}
```

### Integrating QML with C++

You can integrate QML with C++ by exposing C++ classes to QML and accessing QML objects from C++.

**Example (main.cpp):**
```cpp
#include <QGuiApplication>
#include <QQmlApplicationEngine>
#include <QQmlContext>

class Backend : public QObject {
    Q_OBJECT
    /* Add other QML flags here, e.g. QML_ELEMENT, QML_UNCREATABLE */
    
public:
    Q_INVOKABLE QString greet() {
        return "Hello from C++!";
    }
};

int main(int argc, char *argv[]) {
    QGuiApplication app(argc, argv);

    QQmlApplicationEngine engine;
    Backend backend;
    engine.rootContext()->setContextProperty("backend", &backend);
    engine.load(QUrl(QStringLiteral("qrc:/main.qml")));

    return app.exec();
}

#include "main.moc"
```

### Exposing C++ to QML

To expose C++ classes to QML, use `Q_INVOKABLE` methods and properties.

**Example (Backend class):**
```cpp
class Backend : public QObject {
    Q_OBJECT
public:
    Q_INVOKABLE QString greet() {
        return "Hello from C++!";
    }

    Q_PROPERTY(QString version READ getVersion CONSTANT)

    QString getVersion() const {
        return "1.0";
    }
};
```

**Using in QML:**
```qml
Text {
    text: backend.greet()
    anchors.centerIn: parent
}

Text {
    text: "Version: " + backend.version
    anchors.bottom: parent.bottom
    anchors.right: parent.right
}
```

### `qmlRegisterSingletonInstance`

```c++
class Company : public QObject {
	Q_OBJECT
	Q_PROPERTY(double income)
	Q_PROPERTY(double losses)
	Q_PROPERTY(bool isOpened)
}

Company myCompany;
qmlRegisterSingletonInstance(
	"MyImport",
	1, // Major version num
	0, // Minor version num
	"MyCompany",
	&myCompany
);
```

```qml
import MyImport

Text {
	text: "Current profit: " +
	(MyCompany.income -
	 MyCompany.losses)
}
```

### Handling Events and Signals

[[Qt Signals]] and [[Qt Slots]] can be used to communicate between QML and C++.

**Example (Backend class):**
```cpp
class Backend : public QObject {
    Q_OBJECT
signals:
    void dataChanged();

public slots:
    void updateData() {
        // Update data here
        emit dataChanged();
    }
};
```

**Using signals in QML:**
```qml
Button {
    text: "Update Data"
    onClicked: backend.updateData()
}
```

### Dynamic QML Component Creation

You can create QML components dynamically from C++.

**Example (main.cpp):**
```cpp
QQuickView view;
view.setSource(QUrl("qrc:/main.qml"));

QObject *item = view.rootObject()->findChild<QObject*>("myItem");
if (item) {
    QQmlComponent component(&engine, QUrl("qrc:/MyDynamicComponent.qml"));
    QObject *dynamicObject = component.create();
    if (dynamicObject) {
        dynamicObject->setParent(item);
        QMetaObject::invokeMethod(dynamicObject, "initialize", Q_ARG(QVariant, QVariantList()));
    }
}
```

## Adding C++ models in a QML app

1. Create a C++ data model
```cpp
class MyModel : public QAbstractListModel /* also QAbstractItemModel */{
    Q_OBJECT
public:
    enum Roles {
        NameRole = Qt::UserRole + 1,
        AgeRole
    };

    // Constructor, destructor, and necessary methods for exposure to QML
};

```

2. Register it with QML
```cpp
#include <QQmlApplicationEngine>
#include "mymodel.h" // Include the C++ model header file

int main(int argc, char *argv[]) {
    QGuiApplication app(argc, argv);

    // Register the C++ model class for QML
    qmlRegisterType<MyModel>("MyApp", 1, 0, "MyModel");

    QQmlApplicationEngine engine;
    engine.load(QUrl(QStringLiteral("qrc:/main.qml")));
    if (engine.rootObjects().isEmpty())
        return -1;

    return app.exec();
}

```

3. Use the C++ model in QML
```qml
import QtQuick
import QtQuick.Controls
import MyApp 1.0 // Import the module where MyModel is registered

ApplicationWindow {
    visible: true
    width: 640
    height: 480
    title: "Using C++ Models in QML"

    MyModel {
        id: myCppModel
        // Optionally, populate the model or set properties
    }

    ListView {
        width: parent.width
        height: parent.height
        model: myCppModel // Bind the C++ model to the ListView
        delegate: ItemDelegate {
            text: model.name // Access properties defined in your C++ model
        }
    }
}

```

Further: [Qt Model-View Controller: How to Add C++ Models in QML App | Qt QML Tutorial #13](https://www.youtube.com/watch?v=xVZx57kxgyg&list=PLP7UmEJ9z4mpi0JXcPS0VRK-7eFAfROZI&index=14)

### Notes on QAbstractItemModel

- Roles define the different properties of an item in a model, each can have multiple, they are used to access and manipulate data from QML.


See also:
- [Qt Signals and Slots](https://doc.qt.io/qt-6/signalsandslots.html)
- [Qt Documentation](https://doc.qt.io/)
- [[Qt GUI Development]]
- [Scythe Studio GitHub: qt-qml-tutorial](https://github.com/scytheStudio/qt-qml-tutorial)
- [How to Register C++ Class in your QML Application | Qt QML Tutorial #12](https://www.youtube.com/watch?v=NrUK_ds1_t4)