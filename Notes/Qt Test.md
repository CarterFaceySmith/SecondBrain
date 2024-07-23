Qt Test is a testing framework for [[Qt QML (Qt Quick)]] designed for [[Unit Testing]] of Qt GUI applications.

## Creating a Qt test

- Subclass `QObject` and add a private slot to it
	- Each private slot is a test function in your test (Use `QTest::qExec()` to execute all test funcs in the test object)

You can define private [[Qt Slots]] that are not treated as test functions, these can be used to init of clean up either the entire test or the current test [[Functions]].

- `initTestCase()`: Called before first test function executed
- `initTestCase_data()`: Called to create global test data table
- `cleanupTestCase()`: Called after the last test function is executed
- `init()`: Called before each test function is executed
- `cleanup()`: Called after every test function

## A practical example

```cpp
class MyFirstTest: public QObject{
	Q_OBJECT

private:
	bool myCondition(){
		return true;
	}

private slots:
	void initTestCase(){
		qDebug("Called before all else.");
	}

	void myFirstTest(){
		QVERIFY(true); // Check condi satisfied
		QCOMPARE(1 != 2); // Compare values
	}

	void mySecondTest(){
		QVERIFY(myCondition());
		QVERIFY(1 != 2);
	}

	void cleanupTestCase(){
		qDebug("Called after test 1 and 2.");
	}
};
```

Note: If the test class has a static public void `initMain()` method, it is called by the `QTEST_MAIN` macros before the `QApplication` object is instantiated.

Mark failures as `QEXPECT_FAIL`, don't manipulate the global state, use the `init()` and `cleanup()` methods.

### QML example

```qml
TestCase {
	name: "testOne"
	// Create property vars here

	function test_one(){
		return [
			{tag: "empty map", map: create("Map)},
			{tag: "map with background colour", map: create("Map",{backgroundColor: "red"})}
		]
	}
}
```

## Building Qt tests

### Using CMake

Using CMake and CTest we can specify what tests to include based on [[Regular Expressions (Regex)]].

We can also use the `LABELS` property on a test and CTest will include/exclude based on those if desired, labelled targets are run when `test` target is specified as a [[Command Line]] argument.

Example:
```cmake
project(mytest LANGUAGES CXX)

find_package(Qt6 REQUIRED COMPONENTS Test)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)

enable_testing(true)

qt_add_executable(mytest tst_mytest.cpp)
add_test(NAME mytest COMMAND mytest)

target_link_libraries(mytest PRIVATE Qt::Test)
```

### Using qmake

Add `QT == testlib` to your project file, if you want the tests to run when `make check` is called, add `CONFIG += testcase` to your project file.

`CONFIG += no_testcase_installs` to specify you don't want the tests installed to your target.

## Qt Test [[Command Line]] arguments

The following is directly from the Qt Test documentation.

The syntax to execute an autotest takes the following simple form:

`testname [options] [testfunctions[:testdata]]...`

Substitute `testname` with the name of your executable. `testfunctions` can contain names of test functions to be executed. If no `testfunctions` are passed, all tests are run. If you append the name of an entry in `testdata`, the test function will be run only with that test data.

For example:

`/myTestDirectory$ testQString toUpper`

Runs the test function called `toUpper` with all available test data.

`/myTestDirectory$ testQString toUpper toInt:zero`

Runs the `toUpper` test function with all available test data, and the `toInt` test function with the test data row called `zero` (if the specified test data doesn't exist, the associated test will fail and the available data tags are reported).

`/myTestDirectory$ testMyWidget -vs -eventdelay 500`

Runs the `testMyWidget` function test, outputs every signal emission and waits 500 milliseconds after each simulated mouse/keyboard event.

## Using [[Dependency Injection]] to mock tests

Often tests may skip or fail as a result of a missing dependency or network connection being down.

Using dependency injection we can simulate the network and remove our dependency on online services entirely, tests will also run quicker since a call doesn't need to be made to the network anymore.

## [[Continuous Integration and Deployment (CICD)]]

You can integrate Qt Test with CICD tools like [[Jenkins]] to automate testing during builds etc.


See also:
- [Qt Test Overview](https://doc.qt.io/qt-6/qtest-overview.html)