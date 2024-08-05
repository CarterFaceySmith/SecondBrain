## Retrieving Values from QML
To retrieve a return value from a [[Qt QML (Qt Quick)]] function linked to a [[JavaScript]] file via a Qt WebChannel, you need to wrap the return assignment variable and [[Functions]] call.

Example:
```js
var lat; // Value to assign to
entityManager.getEntityLat(<param>, function(lat) {
	entityManager.qmlLog("JS: Test entity logged latitude of " + lat);
	});
```

QML side:
```qml
function getEntityLat(<param>) { if (entityManager) return entityManager.getEntityByParam(<Param>).latitude }
```

[[C++]] side: Search the database for the entity and return the lat, you get the jist.