## Adding to your CMake for compilation
```
qt_add_executable(appExampleName
	main.cpp
)

qt_add_qml_module(appExampleName
	URI ExampleName
	VERSION 1.0
	QML_FILES main.qml xyz1.qml
	
	RESOURCES
	assets/images/image1.png
	// ...
)
```
## Example UI element using [[Qt QML]]
```qml
import QtQuick
import QtQuick.Controls

ApplicationWindow {
    visible: true
    width: 400
    height: 400
    title: qsTr("Grid UI Example")

    GridView {
        id: gridView
        anchors.fill: parent
        cellWidth: 100
        cellHeight: 100
        model: 9  // 3x3 grid

        delegate: Rectangle {
            width: griid UI Example"dView.cellWidth
            height: gridView.cellHeight
            color: "lightblue"
            border.color: "blue"
            border.width: 2

            Text {
                anchors.centerIn: parent
                text: model.index + 1  // Display index (1-9)
                font.bold: true
                font.pixelSize: 20
            }

            MouseArea {
                anchors.fill: parent
                onClicked: {
                    var person = generateRandomPerson();
                    console.log("Selected person:", person);
                    // Simulate displaying person info (name and age)
                    parent.color = "lightgreen"; // Example of visual feedback
                }
            }

			// Can add images with the following
			// imageSource: "<path to image>"

            function generateRandomPerson() {
                var names = ["Alice", "Bob", "Charlie", "David", "Emma", "Frank", "Grace", "Henry", "Ivy"];
                var ages = [20, 25, 30, 35, 40, 45, 50, 55, 60];
                var randomIndex = Math.floor(Math.random() * names.length);
                return {
                    name: names[randomIndex],
                    age: ages[randomIndex]
                };
            }
        }
    }
}
```


See also:
- [Qt Quick Application Development Basics: Learning QML | Qt QML Tutorial #7](https://www.youtube.com/watch?v=VPW3y3RVlLw&pp=ygURcXQgcW1sIHR1dG9yaWFsIDc%3D)