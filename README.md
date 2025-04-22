# Programming Fundamental
**Submitted By:** Muhammad Qasim  
**Reference ID:** F2024332122  

---

## Assignment on Functions, Arrays, Structures, and Classes  

---

### Here Are Some Queries and Their Answers with Explanation

---

### Q1: How Can We Return Multiple Values by a Function in C?  
**Answer:**  
In C, we cannot return multiple values directly using the `return` statement. However, we can use **structures**, **arrays**, or **pointers**.

#### Example Using `struct`:  
```cpp
#include <iostream>
using namespace std;

struct Result {
    int sum;
    int product;
};

Result calculate(int a, int b) {
    Result res;
    res.sum = a + b;
    res.product = a * b;
    return res;
}

int main () {
    Result result = calculate(5, 3);
    printf("Sum: %d, Product: %d\n", result.sum, result.product);
    return 0;
}
```

**Explanation:**  
- `Result` groups `sum` and `product`.  
- The function returns a structure.  
- Values are accessed through the struct.  

---

### Q2: Returning Array from a Function in C  
**Answer:**  
C cannot return entire arrays directly, but a **pointer** to the array can be returned.

#### Example:  
```cpp
#include <iostream>
using namespace std;

int* createArray() {
    static int arr[3] = {10, 20, 30}; // Static to retain memory
    return arr;
}

int main() {
    int *arr = createArray();
    printf("Array Elements: %d, %d, %d\n", arr[0], arr[1], arr[2]);
    return 0;
}
```

**Explanation:**  
- Static arrays retain memory.  
- The pointer to the first element is returned.  
- Access the array using the pointer.

---

### Q3: Calling a Function Inside Another Function  
**Answer:**  
Yes, one function can call another (or itself – recursion).

#### Example:  
```cpp
#include <iostream>
using namespace std;

void greet() {
    printf("Hello!\n");
}

void callFunction() {
    greet();  // Calling inside another
}

int main() {
    callFunction();
    return 0;
}
```

**Explanation:**  
- Modular code by dividing logic.  
- One function invokes another directly.

---

### Q4: Meaning of `Num[10]` in C  
**Answer:**  
`Num[10]` means an array of **10 integers**.

#### Example:  
```cpp
#include <iostream>
using namespace std;

int main() {
    int Num[10];
    for (int i = 0; i < 10; i++) {
        Num[i] = i + 1;
        printf("%d ", Num[i]);
    }
    return 0;
}
```

**Explanation:**  
- Index starts from 0.  
- Loop initializes and prints values 1 to 10.

---

### Q5: `sum(Num)` Function for Arrays  
**Answer:**  
Arrays can be passed to functions.

#### Example:  
```cpp
#include <iostream>
using namespace std;

int sum(int arr[], int size) {
    int total = 0;
    for (int i = 0; i < size; i++) {
        total += arr[i];
    }
    return total;
}

int main() {
    int Num[5] = {1, 2, 3, 4, 5};
    printf("Sum: %d\n", sum(Num, 5));
    return 0;
}
```

**Explanation:**  
- Function receives array and size.  
- Adds elements in a loop.

---

### Q6: Recursive Function to Find Sum of First N Numbers  
**Answer:**  
Recursion = function calling itself.

#### Example:  
```cpp
#include <iostream>
using namespace std;

int sum(int n) {
    if (n == 0) return 0;
    return n + sum(n - 1);
}

int main() {
    printf("Sum of first 5 numbers: %d\n", sum(5));
    return 0;
}
```

**Explanation:**  
- Base condition stops recursion.  
- Each call adds up the total.

---

### Q7: Structure with an Array Example  
**Answer:**  
Structures can contain arrays.

#### Example:  
```cpp
#include <iostream>

struct Example {
    int sum[3];
};

int main() {
    Example obj = {{2, 5, 7}};
    printf("First element: %d\n", obj.sum[0]);
    return 0;
}
```

**Explanation:**  
- Structure groups multiple elements.  
- Access via `obj.sum[index]`.

---

### Q8: Classes and Member Functions in C++  
**Answer:**  
Functions can be inside or outside a class.

#### Example:  
```cpp
#include <iostream>
using namespace std;

class Sample {
    public:
        void show(); // Declared
};

void Sample::show() {
    cout << "Hello from class function!" << endl;
}

int main() {
    Sample s;
    s.show();
    return 0;
}
```

**Explanation:**  
- Member function declared inside, defined outside.  
- `ClassName::FunctionName` syntax used.

---

### Q9: Accessing Private Data Members in C++  
**Answer:**  
Use **getter/setter** methods for private data.

#### Example:  
```cpp
#include <iostream>
using namespace std;

class Example {
    private:
        int data;
    public:
        void setData(int x) { data = x; }
        int getData() { return data; }
};

int main () {
    Example obj;
    obj.setData(5);
    cout << "Data: " << obj.getData() << endl;
    return 0;
}
```

**Explanation:**  
- `setData()` sets value, `getData()` retrieves it.  
- Maintains encapsulation.

---

### Q10: Local Variable & Data Member with Same Name  
**Answer:**  
Use `this->` to distinguish when names conflict.

#### Example:  
```cpp
#include <iostream>
using namespace std;

class Example {
    public:
        int a;
        void show () {
            int a = 10;
            cout << "Local Variable: " << a << endl;
            cout << "Data Member: " << this->a << endl;
        }
};

int main () {
    Example obj;
    obj.a = 5;
    obj.show();
    return 0;
}
```

**Explanation:**  
- `a` inside `show()` is local.  
- `this->a` refers to class member.

---

**Thanks for Reading!**  
**Happy Coding!**  
---
