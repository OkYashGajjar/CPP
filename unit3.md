Here are the solutions to the C++ programming problems you provided:

---

### **1. Friend Function to Calculate Average of Two Numbers**

```cpp
#include <iostream>
using namespace std;

class ClassB; // Forward declaration

class ClassA {
public:
    int numA;
    ClassA(int a) : numA(a) {}
    friend void calculateAverage(ClassA, ClassB);
};

class ClassB {
public:
    int numB;
    ClassB(int b) : numB(b) {}
    friend void calculateAverage(ClassA, ClassB);
};

void calculateAverage(ClassA a, ClassB b) {
    float avg = (a.numA + b.numB) / 2.0;
    cout << "Average: " << avg << endl;
}

int main() {
    ClassA objA(10);
    ClassB objB(20);
    calculateAverage(objA, objB);
    return 0;
}
```

---

### **2. Friend Function to Find Maximum of Three Numbers**

```cpp
#include <iostream>
using namespace std;

class ClassB; // Forward declaration
class ClassC; // Forward declaration

class ClassA {
public:
    int num1;
    ClassA(int a) : num1(a) {}
    friend void findMax(ClassA, ClassB, ClassC);
};

class ClassB {
public:
    int numB2;
    ClassB(int b) : numB2(b) {}
    friend void findMax(ClassA, ClassB, ClassC);
};

class ClassC {
public:
    int num3;
    ClassC(int c) : num3(c) {}
    friend void findMax(ClassA, ClassB, ClassC);
};

void findMax(ClassA a, ClassB b, ClassC c) {
    int maxVal = max(a.num1, max(b.numB2, c.num3));
    cout << "Maximum: " << maxVal << endl;
}

int main() {
    ClassA objA(10);
    ClassB objB(20);
    ClassC objC(30);
    findMax(objA, objB, objC);
    return 0;
}
```

---

### **3. Student Data Management Using `this` Pointer**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Student {
public:
    int rollNo;
    string name;
    float marks;

    void setData(int rollNo, string name, float marks) {
        this->rollNo = rollNo;
        this->name = name;
        this->marks = marks;
    }

    void display() {
        cout << "Roll No: " << rollNo << ", Name: " << name << ", Marks: " << marks << endl;
    }
};

int main() {
    Student students[3];
    students[0].setData(1, "Alice", 95.5);
    students[1].setData(2, "Bob", 89.0);
    students[2].setData(3, "Charlie", 78.5);

    for (int i = 0; i < 3; i++) {
        students[i].display();
    }
    return 0;
}
```

---

### **4. Access Member of One Class from Another Using Friend Class**

```cpp
#include <iostream>
using namespace std;

class ClassB; // Forward declaration

class ClassA {
private:
    int numA;
public:
    ClassA(int a) : numA(a) {}
    friend class ClassB;
};

class ClassB {
public:
    void displayNumA(ClassA a) {
        cout << "NumA: " << a.numA << endl;
    }
};

int main() {
    ClassA objA(10);
    ClassB objB;
    objB.displayNumA(objA);
    return 0;
}
```

---

### **5. Find Largest and Smallest Number in an Array**

```cpp
#include <iostream>
using namespace std;

class ArrayOperations {
public:
    int arr[10];

    void readArray() {
        cout << "Enter 10 integers: ";
        for (int i = 0; i < 10; i++) {
            cin >> arr[i];
        }
    }

    void findMinMax() {
        int minVal = arr[0], maxVal = arr[0];
        for (int i = 1; i < 10; i++) {
            if (arr[i] < minVal) minVal = arr[i];
            if (arr[i] > maxVal) maxVal = arr[i];
        }
        cout << "Smallest: " << minVal << ", Largest: " << maxVal << endl;
    }
};

int main() {
    ArrayOperations obj;
    obj.readArray();
    obj.findMinMax();
    return 0;
}
```

---

### **6. Pass Array to Function and Find Maximum Value**

```cpp
#include <iostream>
using namespace std;

class ArrayOperations {
public:
    int findMax(int arr[], int size) {
        int maxVal = arr[0];
        for (int i = 1; i < size; i++) {
            if (arr[i] > maxVal) maxVal = arr[i];
        }
        return maxVal;
    }
};

int main() {
    ArrayOperations obj;
    int arr[] = {10, 20, 30, 40, 50};
    int size = sizeof(arr) / sizeof(arr[0]);
    cout << "Maximum: " << obj.findMax(arr, size) << endl;
    return 0;
}
```

---

### **7. Find Minimum Number Using Array and Return Array**

```cpp
#include <iostream>
using namespace std;

class ArrayOperations {
public:
    int* findMin(int arr[], int size) {
        int minVal = arr[0];
        for (int i = 1; i < size; i++) {
            if (arr[i] < minVal) minVal = arr[i];
        }
        return &minVal; // Returning address of the minimum value
    }
};

int main() {
    ArrayOperations obj;
    int arr[] = {10, 20, 30, 40, 5};
    int size = sizeof(arr) / sizeof(arr[0]);
    int* minVal = obj.findMin(arr, size);
    cout << "Minimum: " << *minVal << endl;
    return 0;
}
```

---

### **8. Function Pointer for Arithmetic Operations**

```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    int add(int a, int b) { return a + b; }
    int subtract(int a, int b) { return a - b; }
    int multiply(int a, int b) { return a * b; }
};

int main() {
    Calculator obj;
    int (Calculator::*funcPtr)(int, int) = nullptr;

    funcPtr = &Calculator::add;
    cout << "Addition: " << (obj.*funcPtr)(10, 20) << endl;

    funcPtr = &Calculator::subtract;
    cout << "Subtraction: " << (obj.*funcPtr)(20, 10) << endl;

    funcPtr = &Calculator::multiply;
    cout << "Multiplication: " << (obj.*funcPtr)(10, 20) << endl;

    return 0;
}
```

---

### **9. Array of Objects for Laptop Data**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Laptop {
public:
    string brand;
    float price;

    void getData() {
        cout << "Enter brand: ";
        cin >> brand;
        cout << "Enter price: ";
        cin >> price;
    }

    void display() {
        cout << "Brand: " << brand << ", Price: " << price << endl;
    }
};

int main() {
    Laptop laptops[5];
    for (int i = 0; i < 5; i++) {
        cout << "Enter details for laptop " << i + 1 << ":\n";
        laptops[i].getData();
    }
    for (int i = 0; i < 5; i++) {
        laptops[i].display();
    }
    return 0;
}
```

---

### **10. 2D Array Input and Display**

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[3][2];
    cout << "Enter 6 values for 3x2 matrix:\n";
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 2; j++) {
            cin >> arr[i][j];
        }
    }
    cout << "Matrix:\n";
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 2; j++) {
            cout << arr[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

---

### **11. Dynamic 2D Array Input and Display**

```cpp
#include <iostream>
using namespace std;

int main() {
    int rows, cols;
    cout << "Enter rows and columns: ";
    cin >> rows >> cols;

    int** arr = new int*[rows];
    for (int i = 0; i < rows; i++) {
        arr[i] = new int[cols];
    }

    cout << "Enter values:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cin >> arr[i][j];
        }
    }

    cout << "Matrix:\n";
    for (int i = 0; i < rows; i++) {
        for (int j = 0; j < cols; j++) {
            cout << arr[i][j] << " ";
        }
        cout << endl;
    }

    // Free memory
    for (int i = 0; i < rows; i++) {
        delete[] arr[i];
    }
    delete[] arr;

    return 0;
}
```

---

### **12. Matrix Addition**

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr1[2][2], arr2[2][2], sum[2][2];

    cout << "Enter values for matrix 1:\n";
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            cin >> arr1[i][j];
        }
    }

    cout << "Enter values for matrix 2:\n";
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            cin >> arr2[i][j];
        }
    }

    cout << "Sum:\n";
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            sum[i][j] = arr1[i][j] + arr2[i][j];
            cout << sum[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

---

### **13. Matrix Subtraction**

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr1[2][2], arr2[2][2], diff[2][2];

    cout << "Enter values for matrix 1:\n";
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            cin >> arr1[i][j];
        }
    }

    cout << "Enter values for matrix 2:\n";
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            cin >> arr2[i][j];
        }
    }

    cout << "Difference:\n";
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            diff[i][j] = arr1[i][j] - arr2[i][j];
            cout << diff[i][j] << " ";
        }
        cout << endl;
    }
    return 0;
}
```

---

### **14. Employee Data Management**

```cpp
#include <iostream>
#include <string>
using namespace std;

class Employee {
public:
    int id;
    string name, designation;
    float salary;

    void getData() {
        cout << "Enter ID: ";
        cin >> id;
        cout << "Enter Name: ";
        cin >> name;
        cout << "Enter Designation: ";
        cin >> designation;
        cout << "Enter Salary: ";
        cin >> salary;
    }

    void display() {
        cout << "ID: " << id << ", Name: " << name << ", Designation: " << designation << ", Salary: " << salary << endl;
    }
};

int main() {
    Employee employees[5];
    for (int i = 0; i < 5; i++) {
        cout << "Enter details for employee " << i + 1 << ":\n";
        employees[i].getData();
    }
    for (int i = 0; i < 5; i++) {
        employees[i].display();
    }
    return 0;
}
```

---

### **15. Calculate Square and Cube Using Pointer**

```cpp
#include <iostream>
using namespace std;

class Calculator {
public:
    void calculate(int num, int* square, int* cube) {
        *square = num * num;
        *cube = num * num * num;
    }
};

int main() {
    Calculator obj;
    int num, square, cube;
    cout << "Enter a number: ";
    cin >> num;

    obj.calculate(num, &square, &cube);
    cout << "Square: " << square << ", Cube: " << cube << endl;
    return 0;
}
```

---

Let me know if you need further clarification or additional help!