Imagine you have some data, like a list of names or numbers, and you want to show it in a Qt widget, like a table or list view. Sometimes, you might want to tweak how that data appears without changing the original data itself. That's where proxy models come into play.

## What are Proxy Models?

Proxy models in Qt act as intermediaries between your original data (let's call it the source model) and the view that displays it. They sit between the source model and the view, modifying how the data is presented or filtering what's shown, all without touching the source data directly.

## Why Use Proxy Models?

1. **Filtering and Sorting**: Say you have a list of contacts, but you only want to show contacts that have email addresses. A proxy model can filter out contacts without emails.
    
2. **Custom Data Manipulation**: You might want to combine data from different columns or change how dates are formatted. Proxy models let you do these tweaks easily.
    
3. **Item Handling**: They can handle things like changing how items are selected or managing multiple views of the same data differently.

`QAbstractProxyModel` is the base proxy model class and allows for more customisation than the premade proxy models like `QSortFilterProxyModel` and `QIdentityProxyModel`.

Example:
```qml
model = ...;

proxy = new QSortFilterProxyModel(parent);

proxy->setSourceModel(model);

view.rootContext()->setContextProperty("_cppModel", model);
view.rootContext()->setContextProperty("_cppProxyModel", proxy);
```

## How to Use Them?

1. **Set Up the Source Model**: First, you'll have your original model, like a `QStandardItemModel` or a `QSqlTableModel`, filled with your data.
    
2. **Create the Proxy Model**: Decide which proxy model suits your needs. For basic filtering or sorting, `QSortFilterProxyModel` is usually your go-to.
    
3. **Set the Proxy Model's Source Model**: Tell the proxy model where it should get its data from (i.e., your source model).
    
4. **Connect the Proxy Model to the View**: Finally, connect your proxy model to the view (like a `QTableView` or `QListView`). The view will now display the data as filtered or sorted by your proxy model.
## A practical example

```cpp
#include <QApplication>
#include <QMainWindow>
#include <QVBoxLayout>
#include <QWidget>
#include <QLineEdit>
#include <QListView>
#include <QStringListModel>
#include <QSortFilterProxyModel>
#include <QDebug>

class MainWindow : public QMainWindow {
    Q_OBJECT

public:
    MainWindow(QWidget *parent = nullptr)
        : QMainWindow(parent)
    {
        setWindowTitle("Proxy Model Example");
        resize(400, 300);

        // Create a simple string list model with some data
        QStringList names = {"Alice", "Bob", "Charlie", "David", "Eve"};
        model = new QStringListModel(names, this);

        // Create a QSortFilterProxyModel
        proxyModel = new QSortFilterProxyModel(this);
        proxyModel->setSourceModel(model);

        // Create widgets
        searchBox = new QLineEdit();
        searchBox->setPlaceholderText("Search names...");

        listView = new QListView();
        listView->setModel(proxyModel);

        // Layout setup
        QWidget *centralWidget = new QWidget(this);
        QVBoxLayout *layout = new QVBoxLayout(centralWidget);
        layout->addWidget(searchBox);
        layout->addWidget(listView);
        setCentralWidget(centralWidget);

        // Connect signal for filtering
        connect(searchBox, &QLineEdit::textChanged, this, &MainWindow::filterNames);
    }

private slots:
    void filterNames(const QString &text) {
        proxyModel->setFilterCaseSensitivity(Qt::CaseInsensitive); // Case insensitive filter
        proxyModel->setFilterFixedString(text);
    }

private:
    QStringListModel *model;
    QSortFilterProxyModel *proxyModel;
    QLineEdit *searchBox;
    QListView *listView;
};

#include "main.moc"

int main(int argc, char *argv[]) {
    QApplication app(argc, argv);

    MainWindow window;
    window.show();

    return app.exec();
}
```


See also:
- [Qt Model/View Programming - Proxy Models](https://doc.qt.io/qt-6/model-view-programming.html#proxy-models)