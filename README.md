# CPP

Here are the solutions to the 10 questions based on the provided file contents:

### Q1: Student Class
```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
private:
    int rollNo;
    string name;
    int marks[3];

public:
    void input() {
        cout << "Enter Roll No: ";
        cin >> rollNo;
        cout << "Enter Name: ";
        cin >> name;
        cout << "Enter marks in 3 subjects: ";
        for (int i = 0; i < 3; i++) {
            cin >> marks[i];
        }
    }

    int totalMarks() {
        int total = 0;
        for (int i = 0; i < 3; i++) {
            total += marks[i];
        }
        return total;
    }

    float averageMarks() {
        return totalMarks() / 3.0;
    }

    void printDetails() {
        cout << "Roll No: " << rollNo << endl;
        cout << "Name: " << name << endl;
        cout << "Total Marks: " << totalMarks() << endl;
        cout << "Average Marks: " << averageMarks() << endl;
    }
};
```

### Q2: DistanceConverter Class
```cpp
#include <iostream>
using namespace std;

class DistanceConverter {
private:
    double kilometers;

public:
    void input() {
        cout << "Enter distance in kilometers: ";
        cin >> kilometers;
    }

    double toMeters() {
        return kilometers * 1000;
    }

    void printConverted() {
        cout << "Distance in meters: " << toMeters() << endl;
    }
};
```

### Q3: Discount Class
```cpp
#include <iostream>
using namespace std;

class Discount {
private:
    float price;
    float discountPercentage;

public:
    void input() {
        cout << "Enter price: ";
        cin >> price;
        cout << "Enter discount percentage (default is 10%): ";
        cin >> discountPercentage;
    }

    void calculateFinalPrice() {
        float finalPrice = price - (price * discountPercentage / 100);
        cout << "Final Price: " << finalPrice << endl;
    }
};
```

### Q4: Rectangle Class
```cpp
#include <iostream>
using namespace std;

class Rectangle {
private:
    double length, width;

public:
    void setDimensions(double l, double w) {
        length = l;
        width = w;
    }

    inline double area() {
        return length * width;
    }

    inline double perimeter() {
        return 2 * (length + width);
    }

    void display() {
        cout << "Area: " << area() << endl;
        cout << "Perimeter: " << perimeter() << endl;
    }
};
```

### Q5: Calculator Class
```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) {
        return a + b;
    }

    double add(double a, double b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }

    void displayResult(int result) {
        cout << "Result: " << result << endl;
    }

    void displayResult(double result) {
        cout << "Result: " << result << endl;
    }
};
```

### Q6: TimeClass
```cpp
#include <iostream>
using namespace std;

class TimeClass {
private:
    int hours, minutes, seconds;

public:
    void input() {
        cout << "Enter hours, minutes, seconds: ";
        cin >> hours >> minutes >> seconds;
    }

    void addTimes(TimeClass t1, TimeClass t2) {
        int totalSeconds = t1.seconds + t2.seconds;
        int totalMinutes = t1.minutes + t2.minutes + totalSeconds / 60;
        int totalHours = t1.hours + t2.hours + totalMinutes / 60;

        seconds = totalSeconds % 60;
        minutes = totalMinutes % 60;
        hours = totalHours % 24;
    }

    void display() {
        cout << hours << ":" << minutes << ":" << seconds << endl;
    }
};
```

### Q7: countOfDigit Class
```cpp
#include <iostream>
using namespace std;

class countOfDigit {
private:
    int N;

public:
    void input() {
        cout << "Enter a number: ";
        cin >> N;
    }

    void printCountOfDigit() {
        int count = 0;
        int temp = N;
        while (temp != 0) {
            temp /= 10;
            count++;
        }
        cout << "Number of digits: " << count << endl;
    }
};
```

### Q8: BankAccount Class
```cpp
#include <iostream>
using namespace std;

class BankAccount {
private:
    int accountNumber;
    float balance;
    static float interestRate;

public:
    static void setInterestRate(float rate) {
        interestRate = rate;
    }

    void input() {
        cout << "Enter account number: ";
        cin >> accountNumber;
        cout << "Enter balance: ";
        cin >> balance;
    }

    void displayDetails() {
        cout << "Account Number: " << accountNumber << endl;
        cout << "Balance: " << balance << endl;
        cout << "Interest: " << balance * interestRate / 100 << endl;
    }

    void updateBalance() {
        balance += balance * interestRate / 100;
    }
};

float BankAccount::interestRate = 0;
```

### Q9: Circle Class
```cpp
#include <iostream>
using namespace std;

class Circle {
private:
    float radius;

public:
    void setRadius(float r) {
        radius = r;
    }

    float area() const {
        return 3.14159 * radius * radius;
    }

    float circumference() const {
        return 2 * 3.14159 * radius;
    }

    void display() const {
        cout << "Radius: " << radius << endl;
        cout << "Area: " << area() << endl;
        cout << "Circumference: " << circumference() << endl;
    }
};
```

### Q10: Library Class
```cpp
#include <iostream>
#include <string>
using namespace std;

class Library {
private:
    string libraryName;
    static int bookCount;

public:
    class Book {
    public:
        string title;
        string author;
        float price;

        void input() {
            cout << "Enter title: ";
            cin >> title;
            cout << "Enter author: ";
            cin >> author;
            cout << "Enter price: ";
            cin >> price;
            Library::bookCount++;
        }

        void display() {
            cout << "Title: " << title << endl;
            cout << "Author: " << author << endl;
            cout << "Price: " << price << endl;
        }
    };

    void inputLibraryName() {
        cout << "Enter library name: ";
        cin >> libraryName;
    }

    void displayLibraryDetails() {
        cout << "Library Name: " << libraryName << endl;
        cout << "Total Books: " << bookCount << endl;
    }
};

int Library::bookCount = 0;
```

These solutions provide the implementation for each of the 10 questions as described in the files. Each class includes the necessary data members and member functions to fulfill the requirements.
