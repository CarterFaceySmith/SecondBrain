Each [[Qt QML (Qt Quick)]] object can have one parent which gets set by the [[Constructor]], each child can then of course become a parent to their own children. This defines the basic concept behind Qt object trees.

This is useful because when a [[Destructor]] is called, it will iterate over the object tree and destroy all children of the object as well.

**Note**: Qt objects have their copy constructor removed by default because of this, if you could copy it you might end up copying a massive quantity of children too and there children etc.

## Practical Example of Qt Object Trees

Let's say you have some main window which can open sub windows based on tasks, if you close the main window you likely want the sub windows to close too right? 

Here's an example from a calculator, the calls to `connect` are simply connecting [[Qt Signals]] to [[Qt Slots]] upon construction. The main line to note is the parameter `parent` which defines the base window with the MainWindow being a child of that.

```cpp
MainWindow::MainWindow(QWidget *parent)
    : QMainWindow(parent)
    , ui(new Ui::MainWindow)
    , first(0.0)
    , second(0.0)
    , toClear(false)
    , sign("\0")
{
    ui->setupUi(this);

    setFixedSize(260, 270);

    connect(ui->button1, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button2, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button3, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button4, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button5, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button6, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button7, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button8, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button9, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));
    connect(ui->button0, SIGNAL(clicked(bool)), this, SLOT(EnterNum()));

    connect(ui->buttonDot, SIGNAL(clicked(bool)), this, SLOT(EnterDot()));
    connect(ui->buttonAdd, SIGNAL(clicked(bool)), this, SLOT(EnterSign()));
    connect(ui->buttonSub, SIGNAL(clicked(bool)), this, SLOT(EnterSign()));
    connect(ui->buttonMult, SIGNAL(clicked(bool)), this, SLOT(EnterSign()));
    connect(ui->buttonDiv, SIGNAL(clicked(bool)), this, SLOT(EnterSign()));
    connect(ui->buttonPow, SIGNAL(clicked(bool)), this, SLOT(Square()));
    connect(ui->buttonSqrt, SIGNAL(clicked(bool)), this, SLOT(SquareRoot()));

    connect(ui->buttonEq, SIGNAL(clicked(bool)), this, SLOT(Equals()));
    connect(ui->buttonC, SIGNAL(clicked(bool)), this, SLOT(ClearScreen()));

    std::setlocale(LC_ALL, "C"); // changing locale to make std::stod work correctly with Qt (to not delete decimal parts while converting)
}

MainWindow::~MainWindow()
{
    delete ui;
}
```