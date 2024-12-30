# Cornerstones of Object-Oriented Programming

* It is a programming model that is dependent on the concepts of objects and classes.
* OOP is a programming style, not a tool.
* Every objects has its own unique set of properties.
* These properties are later accessed and modified through the use of various operations.

## Real Life Examples:

<p align="center">
  <img src="Images/EmployeeObject.png" alt="EmployeeRecord" />
</p>


## Building blocks of OOP

* Attributes
* Methods
* Classes
* Objects

## Examples

* Calculator (Object)
    * State (ON/OFF)
    * Behavior (add, subtract, division etc)
    * Where do objects come from? - Classes
    * Classes - Can be thought of as a blueprint for creating object

## Methods

* Like function that represent the behavior of the object.
* Methods have access to a class attributes.
* They can accept parameters, return values and are used to perform an action on an object of a class.

## Calculator class with Attributes and methods

<p align="center">
  <img src="Images/Calculator.png" alt="EmployeeRecord" />
</p>

## Principles of OOP

* Encapsulation
* Abstraction
* Inheritance
* Polymorphism

## Encapsulation

* Technique used to achieve data hiding in OOP.
* Binding data and the methods to manipulate that data together in a single unit-class.

#### Components of data hiding:

* Encapsulation
* Abstraction

#### Basic Movie class implementation

```C#
class Movie {
    // Data members
    private string title;
    private int year;
    private string genre;

    // Default constructor
    public Movie() {
        title = "";
        year = -1;
        genre = "";
    }

    //Parameterized constructor
    public Movie(string t, int y, string g) {
        title = t;
        year = y;
        genre = g;
    }
}

```

* There must be a way to interact with variables. They include all of the movie's information.
* We can create a getTitle() method, which will return the title to us. Similarly, the other two members can also have corresponding getters.

```C#

class Movie {
  // Data members
  private string title;
  private int year;
  private string genre;

  // Default constructor
  public Movie() {
    title = "";
    year = -1;
    genre = "";
  }

  // Parameterized constructor
  public Movie(string t, int y, string g) {
    title = t;
    year = y;
    genre = g;
  }
  
  // getters setters
  public string getTitle() {
    return title;
  }

  public void setTitle(string t) {
    title = t;
  }
  
  public int getYear() {
    return year;
  }

  public void setYear(int y) {
    year = y;
  }
  
  public string getGenre(){
    return genre;
  }
  
  public void setGenre(string g) {
    genre = g;
  }
  
  void PrintDetails() {
    System.Console.WriteLine("Title: " + title);
    System.Console.WriteLine("Year: " + year);
    System.Console.WriteLine("Genre: " + genre);
  }
  

  public static void Main(string[] args) {
    Movie movie = new Movie("The Lion King", 1994, "Adventure");
    movie.PrintDetails();
    
    System.Console.WriteLine("---");
    movie.setTitle("Forrest Gump");
    System.Console.Write("New title: " + movie.getTitle());
    
  }
}

```

#### Advantages of encapsulation

* Classes are simpler to modify and maintain.
* Which data member wish to keep hidden or accessible can be specified.
* We choose variables are read-only and write-only.
