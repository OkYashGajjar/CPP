
### **Practical Assignment – 4 (Unit 4)**

#### **1. Find Largest Element Using Dynamic Memory Allocation**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;
    
    int *arr = new int[n];
    cout << "Enter elements: ";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
    }

    int largest = arr[0];
    for (int i = 1; i < n; i++) {
        if (arr[i] > largest) {
            largest = arr[i];
        }
    }

    cout << "Largest element: " << largest << endl;
    delete[] arr;
    return 0;
}
```

#### **2. Dynamic Memory Allocation for an Integer**
```cpp
#include <iostream>
using namespace std;

int main() {
    int *ptr = new int;
    cout << "Enter a number: ";
    cin >> *ptr;
    
    cout << "You entered: " << *ptr << endl;
    delete ptr;
    
    return 0;
}
```

#### **3. Find Average Using Dynamic Memory Allocation**
```cpp
#include <iostream>
using namespace std;

int main() {
    int n;
    cout << "Enter number of elements: ";
    cin >> n;

    double *arr = new double[n];
    double sum = 0;

    cout << "Enter elements: ";
    for (int i = 0; i < n; i++) {
        cin >> arr[i];
        sum += arr[i];
    }

    cout << "Average: " << sum / n << endl;
    delete[] arr;
    return 0;
}
```

#### **4. Employee Class with Dynamic Object Creation**
```cpp
#include <iostream>
using namespace std;

class Employee {
    string name;
    double salary;
public:
    Employee(string n, double s) : name(n), salary(s) {}
    void display() {
        cout << "Name: " << name << ", Salary: " << salary << endl;
    }
};

int main() {
    Employee *emp = new Employee("John Doe", 50000);
    emp->display();
    delete emp;
    return 0;
}
```

#### **5. Class A with `new` and `delete`**
```cpp
#include <iostream>
using namespace std;

class A {
public:
    void get_data() {
        cout << "Getting Data..." << endl;
    }
    void display() {
        cout << "Displaying Data..." << endl;
    }
};

int main() {
    A *obj = new A();
    obj->get_data();
    obj->display();
    delete obj;
    return 0;
}
```

#### **6. Student Class with Constructor**
```cpp
#include <iostream>
using namespace std;

class Student {
    string name;
    int age;
public:
    Student(string n, int a) : name(n), age(a) {}
    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }
};

int main() {
    Student s("Alice", 20);
    s.display();
    return 0;
}
```

#### **7. Rectangle Class with Area Calculation**
```cpp
#include <iostream>
using namespace std;

class Rectangle {
    double length, breadth;
public:
    Rectangle(double l, double b) : length(l), breadth(b) {}
    double area() {
        return length * breadth;
    }
};

int main() {
    Rectangle rect(5, 10);
    cout << "Area: " << rect.area() << endl;
    return 0;
}
```

#### **8. Complex Number Class with Constructor Overloading**
```cpp
#include <iostream>
using namespace std;

class Complex {
    double real, imag;
public:
    Complex() : real(0), imag(0) {}
    Complex(double r) : real(r), imag(0) {}
    Complex(double r, double i) : real(r), imag(i) {}

    void display() {
        cout << real << " + " << imag << "i" << endl;
    }
};

int main() {
    Complex c1, c2(5), c3(3, 4);
    c1.display();
    c2.display();
    c3.display();
    return 0;
}
```

#### **9. Header File for Math Operations**
**math_operations.h**
```cpp
#ifndef MATH_OPERATIONS_H
#define MATH_OPERATIONS_H

double add(double, double);
double subtract(double, double);
double multiply(double, double);
double divide(double, double);

#endif
```

**math_operations.cpp**
```cpp
#include "math_operations.h"

double add(double a, double b) { return a + b; }
double subtract(double a, double b) { return a - b; }
double multiply(double a, double b) { return a * b; }
double divide(double a, double b) { return b != 0 ? a / b : 0; }
```

**main.cpp**
```cpp
#include <iostream>
#include "math_operations.h"
using namespace std;

int main() {
    cout << "Sum: " << add(10, 5) << endl;
    cout << "Difference: " << subtract(10, 5) << endl;
    cout << "Product: " << multiply(10, 5) << endl;
    cout << "Quotient: " << divide(10, 5) << endl;
    return 0;
}
```

#### **10. `cmath` Functions**
```cpp
#include <iostream>
#include <cmath>
using namespace std;

int main() {
    double num = 16;
    cout << "Square Root: " << sqrt(num) << endl;
    cout << "Power: " << pow(num, 2) << endl;
    cout << "Logarithm: " << log(num) << endl;
    return 0;
}
```

---

### **Practical Assignment – 5 (Unit 5)**

#### **1. Single Inheritance: Vehicle and Car**
```cpp
#include <iostream>
using namespace std;

class Vehicle {
public:
    string engineType;
    Vehicle(string e) : engineType(e) {}
};

class Car : public Vehicle {
public:
    int numSeats;
    Car(string e, int s) : Vehicle(e), numSeats(s) {}

    void display() {
        cout << "Engine Type: " << engineType << ", Seats: " << numSeats << endl;
    }
};

int main() {
    Car c("Petrol", 4);
    c.display();
    return 0;
}
```

#### **2. Multiple Inheritance: Father, Mother, Child**
```cpp
#include <iostream>
using namespace std;

class Father {
public:
    int height;
    Father(int h) : height(h) {}
};

class Mother {
public:
    string eyeColor;
    Mother(string e) : eyeColor(e) {}
};

class Child : public Father, public Mother {
public:
    string hobby;
    Child(int h, string e, string ho) : Father(h), Mother(e), hobby(ho) {}

    void display() {
        cout << "Height: " << height << ", Eye Color: " << eyeColor << ", Hobby: " << hobby << endl;
    }
};

int main() {
    Child c(180, "Brown", "Painting");
    c.display();
    return 0;
}
```

### **3. Multilevel Inheritance: Grandparent, Parent, Child**
```cpp
#include <iostream>
using namespace std;

class Grandparent {
public:
    string surname;
    Grandparent(string s) : surname(s) {}
};

class Parent : public Grandparent {
public:
    string job;
    Parent(string s, string j) : Grandparent(s), job(j) {}
};

class Child : public Parent {
public:
    string school;
    Child(string s, string j, string sch) : Parent(s, j), school(sch) {}

    void display() {
        cout << "Surname: " << surname << ", Job: " << job << ", School: " << school << endl;
    }
};

int main() {
    Child c("Smith", "Engineer", "Greenwood High");
    c.display();
    return 0;
}
```

---

### **4. Hierarchical Inheritance: Shape, Circle, Rectangle**
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    string color;
    Shape(string c) : color(c) {}
};

class Circle : public Shape {
public:
    double radius;
    Circle(string c, double r) : Shape(c), radius(r) {}

    void display() {
        cout << "Color: " << color << ", Radius: " << radius << endl;
    }
};

class Rectangle : public Shape {
public:
    double length, width;
    Rectangle(string c, double l, double w) : Shape(c), length(l), width(w) {}

    void display() {
        cout << "Color: " << color << ", Length: " << length << ", Width: " << width << endl;
    }
};

int main() {
    Circle c("Red", 5);
    Rectangle r("Blue", 10, 6);
    c.display();
    r.display();
    return 0;
}
```

---

### **5. Hybrid Inheritance: Person, Student, Teacher, TeachingAssistant**
```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;
    Person(string n) : name(n) {}
};

class Student : public Person {
public:
    int rollNumber;
    Student(string n, int r) : Person(n), rollNumber(r) {}
};

class Teacher : public Person {
public:
    string subject;
    Teacher(string n, string s) : Person(n), subject(s) {}
};

class TeachingAssistant : public Student, public Teacher {
public:
    TeachingAssistant(string n, int r, string s) : Student(n, r), Teacher(n, s) {}

    void display() {
        cout << "Name: " << Student::name << ", Roll Number: " << rollNumber << ", Subject: " << subject << endl;
    }
};

int main() {
    TeachingAssistant ta("Alice", 101, "Mathematics");
    ta.display();
    return 0;
}
```

---

### **6. Constructor & Destructor Order in Multilevel Inheritance**
```cpp
#include <iostream>
using namespace std;

class Grandfather {
public:
    Grandfather() { cout << "Grandfather Constructor\n"; }
    ~Grandfather() { cout << "Grandfather Destructor\n"; }
};

class Father : public Grandfather {
public:
    Father() { cout << "Father Constructor\n"; }
    ~Father() { cout << "Father Destructor\n"; }
};

class Child : public Father {
public:
    Child() { cout << "Child Constructor\n"; }
    ~Child() { cout << "Child Destructor\n"; }
};

int main() {
    Child c;
    return 0;
}
```

---

### **7. Multiple Inheritance with Vehicle, Car, and Bike**
```cpp
#include <iostream>
using namespace std;

class Vehicle {
public:
    Vehicle() { cout << "Vehicle Constructor\n"; }
    ~Vehicle() { cout << "Vehicle Destructor\n"; }
};

class Car : public Vehicle {
public:
    Car() { cout << "Car Constructor\n"; }
    ~Car() { cout << "Car Destructor\n"; }
};

class Bike : public Vehicle {
public:
    Bike() { cout << "Bike Constructor\n"; }
    ~Bike() { cout << "Bike Destructor\n"; }
};

int main() {
    Car c;
    Bike b;
    return 0;
}
```

---

### **8. Parameterized Constructor in Inheritance**
```cpp
#include <iostream>
using namespace std;

class Person {
public:
    string name;
    Person(string n) : name(n) {}
};

class Employee : public Person {
public:
    int employeeID;
    Employee(string n, int id) : Person(n), employeeID(id) {}
};

class Manager : public Employee {
public:
    string department;
    Manager(string n, int id, string d) : Employee(n, id), department(d) {}

    void display() {
        cout << "Name: " << name << ", Employee ID: " << employeeID << ", Department: " << department << endl;
    }
};

int main() {
    Manager m("Bob", 1001, "Sales");
    m.display();
    return 0;
}
```

---

### **9. Virtual Base Class Constructor Execution**
```cpp
#include <iostream>
using namespace std;

class University {
public:
    University() { cout << "University Constructor\n"; }
};

class Department : virtual public University {
public:
    Department() { cout << "Department Constructor\n"; }
};

class Club : virtual public University {
public:
    Club() { cout << "Club Constructor\n"; }
};

class Student : public Department, public Club {
public:
    Student() { cout << "Student Constructor\n"; }
};

int main() {
    Student s;
    return 0;
}
```

---

### **10. Abstract Class with Virtual Functions**
```cpp
#include <iostream>
using namespace std;

class Shape {
public:
    virtual double area() = 0;
    virtual double perimeter() = 0;
};

class Rectangle : public Shape {
public:
    double length, width;
    Rectangle(double l, double w) : length(l), width(w) {}

    double area() override { return length * width; }
    double perimeter() override { return 2 * (length + width); }
};

class Circle : public Shape {
public:
    double radius;
    Circle(double r) : radius(r) {}

    double area() override { return 3.14 * radius * radius; }
    double perimeter() override { return 2 * 3.14 * radius; }
};

int main() {
    Shape *s1 = new Rectangle(5, 10);
    Shape *s2 = new Circle(7);

    cout << "Rectangle Area: " << s1->area() << endl;
    cout << "Circle Area: " << s2->area() << endl;

    delete s1;
    delete s2;
    return 0;
}
```

---

### **11. Virtual Function Behavior Using Pointers**
```cpp
#include <iostream>
using namespace std;

class Employee {
public:
    virtual void displaySalary() { cout << "Employee Salary\n"; }
};

class Manager : public Employee {
public:
    void displaySalary() override { cout << "Manager Salary\n"; }
};

class Developer : public Employee {
public:
    void displaySalary() override { cout << "Developer Salary\n"; }
};

int main() {
    Employee *e1 = new Manager();
    Employee *e2 = new Developer();

    e1->displaySalary();
    e2->displaySalary();

    delete e1;
    delete e2;
    return 0;
}
```

---

### **12. Virtual Functions for Product Details**
```cpp
#include <iostream>
using namespace std;

class Product {
public:
    virtual void showDetails() = 0;
};

class Electronics : public Product {
public:
    void showDetails() override { cout << "Electronics Product Details\n"; }
};

class Furniture : public Product {
public:
    void showDetails() override { cout << "Furniture Product Details\n"; }
};

int main() {
    Product *p1 = new Electronics();
    Product *p2 = new Furniture();

    p1->showDetails();
    p2->showDetails();

    delete p1;
    delete p2;
    return 0;
}
```

---
