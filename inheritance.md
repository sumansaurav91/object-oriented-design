# Inheritance

* Way to create a new class from existing class.
* New class is specialized version of the existing class such that it inherits all the public attributes and methods of existing class.
* Wherever we come across IS-A relationship between objects, we can use inheritance.

## Example:

* Square IS-A Shape.
* Dog IS-A animal.
* Car IS-A Vehicle.

## Types of Inheritance

* Single Inheritance:
    * Fuel Car IS-A Vehicle.

* Multiple Inheritance
    * Hybrid car IS-A fuel car.
    * Hybrid card IS-A electric car as well.

* Multi-level Inheritance
    * Fuel car IS-A vehicle.
    * Gasoline car IS-A fuel car.

* Hierarchical Inheritance
    * Fuel car IS-A vehicle.
    * Electric car IS-A vehicle

* Hybrid Inheritance
    * Fuel car IS-A vehicle.
    * Electric car IS-A vehicle.
    * Hybrid car IS-A fuel car and IS-A electric car.

## Simple implementation of a ```Vehicle``` class and implement different classes that will extend from it.

```C#

// Include namespace system
using System;


// Base class (Parent)
public class Vehicle
{
    private string name;
    private string model;
    public Vehicle(string name, string model)
    {
        this.name = name;
        this.model = model;
    }
    public void getName()
    {
        Console.Write("The car is a " + this.name + " " + this.model);
    }
}
// Single inheritance
// FuelCar class extending from Vehicle class
// Derived class (Child)
public class FuelCar : Vehicle
{
    private string combustType;
    public FuelCar(string name, string model, string combustType):base(name, model)
    {
        this.combustType = combustType;
    }
    public void getFuelCar()
    {
        this.getName();
        Console.Write(", combust type is " + this.combustType);
    }
}
// Hierarchical inheritance
// Alongside the FuelCar class, the ElectricCar class is also extending from Vehicle class
// Another Derived class (Child)
public class ElectricCar : Vehicle
{
    private string batteryPower;
    public ElectricCar(string name, string model, string batteryPower):base(name, model)
    {
        this.batteryPower = batteryPower;
    }
    public void getElectricCar()
    {
        this.getName();
        Console.Write(", battery power is " + this.batteryPower);
    }
}
// Multi-level inheritance
// GasolineCar class is derived from the FuelCar class, which is further derived from the Vehicle class
// Derived class (Grandchild)
public class GasolineCar : FuelCar
{
    private string gasCapacity;
    public GasolineCar(string name, string model, string combustType, string gasCapacity):base(name, model, combustType)
    {
        this.gasCapacity = gasCapacity;
    }
    public void getGasolineCar()
    {
        this.getName();
        Console.Write(", gas capacity is " + this.gasCapacity);
    }
}

// C# does not support Multiple inheritance via classes

// main
public class main
{
    public static void Main(string[] args)
    {
        Console.WriteLine("Single inheritance:");
        var Fuel = new FuelCar("Honda", "Accord", "Petrol");
        Fuel.getFuelCar();
        Console.WriteLine("\n");
        Console.WriteLine("Hierarchical inheritance:");
        var Electric = new ElectricCar("Tesla", "ModelX", "200MWH");
        Electric.getElectricCar();
        Console.WriteLine("\n");
        Console.WriteLine("Multi-Level inheritance:");
        var Gasoline = new GasolineCar("Toyota", "Corolla", "Gasoline", "30 liters");
        Gasoline.getGasolineCar();

        Console.WriteLine("\n");
        Console.WriteLine("C# does not support Multiple Inheritance through classes");
    }
}

```

## Advantages of inheritance

* Reusability
* Code modification
* Extensibility
* Data hiding


**Next:** [➡️ Polymorphism](./polymorphism.md)