# Intermediate Topics of OOPS 

### What are methods ? 

Methods are nothing but function that belongs to a class. 

eg:

```
Class Pen{
    Public:
    float nibsize;
    string brand;
    string penmodel;

    Public:
    void Write()  <--- this here a void function named "Write" is a method that belongs to class "Pen"
    {
        cout<<"We are writing with "<<penmodel;

    }
}
```



# Ways to define functions that belongs to a class:

### Inside class definition
In the example that you just saw: 
```
Class Pen{
    Public:
    float nibsize;
    string brand;
    string penmodel;

    Public:
    void Write()  <<---  The function is written inside the class 
    {
        cout<<"We are writing with "<<penmodel;

    }
}
```


### Outside class definition

Sometimes it is better to declare the method in the class and define it later (especially in large programs).
This is done by specifying the name of the class, followed the "scope resolution" "::" operator, followed by the name of the function:

Here's and example:

```
class FountainPen {       
  public:             
    void Write(){
        Cout<<"Writing with a fine nib foutain pen";
    };   
};


void FountainPen :: NibSize() {
  cout << "This pen has a ultrafine nib";
}

int main() {
  FountainPen HauserXO;     // Creating an Pen object  " here Hauser XO is just a Pen name "
  HauserXO.NibSize();      // Call the method
  return 0;
}
```

# Parameters

Just like normal function you can also pass values to these methods

#include <iostream>
using namespace std;

```
class Pen {
  public:
    int Price(int pen_price_set_by_brand) //<---- here Price is a method of Type integer and pen_price_set_by_brand is a parameter
    {
        return pen_price_set_by_brand;

    }
};


int main() {
  Pen HauxerXo; 
  cout << HauserXO.Price(200); // Call the method with an argument( Argument is nothing but value given to the parameter we set while declaring our method)
  return 0;
}
```




# Constructor 

A constructor is a special method that is automatically called when an object of a class is created.

To create a constructor, use the same name as the class, followed by parentheses ()

E.g.:


```
#include <iostream>
using namespace std;

class Pen {
  public:
    int price;

    // Constructor
    
    Pen(int pen_price_set_by_brand)   //<--- Constructor parameter  ( It is fine if you do not give a parameter )
    {
        price = pen_price_set_by_brand;
        cout << "Constructor called. Pen price set to: " << price << endl;
    }

    // Method
    int Price()
    {
        return price;
    }

   
};

int main() {

    Pen HauserXO(200);  //<--- Constructor is called here automatically

    cout << "Pen Price is: " << HauserXO.Price() << endl;

    return 0; 
}
```


//Note: Like other methods , Constructor can also be defined outside the Class 



# Destructor 

A destructor is a special member function in object-oriented programming (specifically C++) that is automatically called when an object is destroyed. It is used to clean up resources such as memory, files, or connections before the object is removed from memory.

E.g.:

```
#include <iostream>
using namespace std;

class Pen {
  public:
    int price;

    
    Pen(int pen_price_set_by_brand)   //<--- Constructor parameter
    {
        price = pen_price_set_by_brand;
        cout << "Constructor called. Pen price set to: " << price << endl;
    }

    // Member function (method)
    int Price()
    {
        return price;
    }

    // Destructor
    // It is automatically called when object goes out of scope
    // It is used to clean up resources before object is destroyed
    ~Pen() //<--- Declared using tilde (~) followed by class name
    {
        cout << "Destructor called. Pen object destroyed." << endl;
    }
};

int main() {

    // Object creation
    // Constructor is automatically called here
    Pen HauserXO(200);

    // Calling member function
    cout << "Pen Price is: " << HauserXO.Price() << endl;

    // Destructor will be automatically called when main() ends
    return 0;
}

```

# Access Modifier
By now you must have seen those "Public " and "Private " inside our class those are Access specifiers ,they control how the members (attributes and methods) of a class can be accessed. They help protect data and organize code so that only the right parts can be seen or changed.


**Types:**

- public - members are accessible from outside the class ( No Protection )
- private - members cannot be accessed (or viewed) from outside the class  (There is a certain way to access them )
- protected - members cannot be accessed from outside the class, however, they can be accessed in inherited classes.







