Here are the complete solutions for all 10 questions, written in standard C++ format, including `main()` functions and `return 0;` where applicable. Each program is self-contained and can be compiled and executed independently.

---

### **Q1: Student Class**
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

int main() {
    Student s;
    s.input();
    s.printDetails();
    return 0;
}
```

---

### **Q2: DistanceConverter Class**
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

int main() {
    DistanceConverter d;
    d.input();
    d.printConverted();
    return 0;
}
```

---

### **Q3: Discount Class**
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

int main() {
    Discount d;
    d.input();
    d.calculateFinalPrice();
    return 0;
}
```

---

### **Q4: Rectangle Class**
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

int main() {
    Rectangle r;
    r.setDimensions(5.0, 3.0);
    r.display();
    return 0;
}
```

---

### **Q5: Calculator Class**
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

int main() {
    Calculator calc;
    cout << "Adding 2 integers: " << calc.add(5, 3) << endl;
    cout << "Adding 2 doubles: " << calc.add(5.5, 3.3) << endl;
    cout << "Adding 3 integers: " << calc.add(5, 3, 2) << endl;
    return 0;
}
```

---

### **Q6: TimeClass**
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

int main() {
    TimeClass t1, t2, result;
    t1.input();
    t2.input();
    result.addTimes(t1, t2);
    result.display();
    return 0;
}
```

---

### **Q7: countOfDigit Class**
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

int main() {
    countOfDigit c;
    c.input();
    c.printCountOfDigit();
    return 0;
}
```

---

### **Q8: BankAccount Class**
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

int main() {
    BankAccount::setInterestRate(5.0); // Set interest rate to 5%
    BankAccount acc;
    acc.input();
    acc.displayDetails();
    acc.updateBalance();
    cout << "After updating balance with interest: " << endl;
    acc.displayDetails();
    return 0;
}
```

---

### **Q9: Circle Class**
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

int main() {
    Circle c;
    c.setRadius(7.0);
    c.display();
    return 0;
}
```

---

### **Q10: Library Class**
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

int main() {
    Library lib;
    lib.inputLibraryName();

    Library::Book b1, b2;
    b1.input();
    b2.input();

    lib.displayLibraryDetails();
    b1.display();
    b2.display();

    return 0;
}
```

---

These programs are complete and include `main()` functions for testing. Each program ends with `return 0;` to indicate successful execution. You can compile and run each program independently.
