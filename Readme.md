﻿# The Next Car

Aplikasi ini berisi tentang mobil masa depan dengan konsep MVC.

# Scope & Functionalities

- User dapat mengklik tombol started
- User dapat menutup pintu dengan tombol closed
- User dapat mengunci pintu dengan tombol locked
- User dapat menghidupkan power dengan tombol power

# How does it works?

Diawali dari method `MainWindow` pada class MainWindow.xaml.cs

```  csharp
public MainWindow()
        {
            InitializeComponent();

            AccubatteryController accubatteryController = new AccubatteryController(this);
            DoorController doorController = new DoorController(this);
            nextCar = new Car(doorController, accubatteryController, this);
        }
```


logika pintu ada pada `Door.cs` 

``` csharp
       public void close()
        {
            this.closed = true;
        }

        public void open()
        {
            this.closed = false;
        }

        public void activateLock()
        {
            this.locked = true;
        }

        public void unlock()
        {
            this.locked = false;
        }

        public bool isLocked()
        {
            return this.locked;
        }

        public bool isClosed()
        {
            return this.closed;
        }
```

logika power ada pada `Accubattery.cs`

``` csharp
 public Accubattery(int voltage)
        {
            this.voltage = voltage;
        }

        public void turnOn()
        {
            this.stateOn = true;
        }
        public void turnOff()
        {
            this.stateOn = false;
        }
        public bool isOn()
        {
            return this.stateOn;
        }
```

