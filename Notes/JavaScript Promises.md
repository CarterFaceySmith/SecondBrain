A [[JavaScript]] object that represents the *eventual* completion or failure of an [[Asynchronous Programming]] operation, *and* its resultant value.

```js
// Retrieve the updated longitude asynchronously
new Promise((resolve, reject) => {
    entityManager.getEntityLongRadByUID("TEST", function(updatedLng) {
        if (updatedLng !== undefined) {
            resolve(updatedLng);
        } else {
            reject("Failed to retrieve updated longitude");
         }
    });
    }).then((updatedLng) => {
	    entityManager.qmlLog("JS: Test entity logged an updated longitude of " + updatedLng);
    }).catch((error) => {
        entityManager.qmlLog("JS: Error - " + error);
    });
```

- A new `Promise` is created to handle an asynchronous operation.
- The `entityManager.getEntityLongRadByUID` function is called to retrieve the updated longitude.
- Depending on whether the longitude is successfully retrieved or not, the promise is either resolved or rejected.
- The `then` method logs the retrieved longitude if successful.
- The `catch` method logs an error message if the operation fails.

## Comparing to Async Await

```js
async function logUpdatedLongitude() {
    try {
        // Wrap the async operation in a promise
        const updatedLng = await new Promise((resolve, reject) => {
            entityManager.getEntityLongRadByUID("TEST", function(updatedLng) {
                if (updatedLng !== undefined) {
                    resolve(updatedLng);
                } else {
                    reject("Failed to retrieve updated longitude");
                }
            });
        });
        // Log the result if successful
        entityManager.qmlLog("JS: Test entity logged an updated longitude of " + updatedLng);
    } catch (error) {
        // Handle any errors
        entityManager.qmlLog("JS: Error - " + error);
    }
}
```