
---

## 💻 `pointers.cpp`
# 1. Global, Local, Dynamic + Memory Region

```cpp
#include <iostream>
using namespace std;

int globalVar = 100;   // Global → Data segment

int main() {
    int localVar = 50;         // Local → Stack
    int* heapVar = new int(25); // Dynamic → Heap

    cout << "Global address: " << &globalVar << endl;
    cout << "Local address: " << &localVar << endl;
    cout << "Heap address: " << heapVar << endl;

    delete heapVar;
    return 0;
}

```

# 2. Function call normally & by function pointer

```cpp
#include <iostream>
using namespace std;

int square(int n) {
    return n * n;
}

int main() {
    cout << square(4) << endl;  // Normal call

    int (*fp)(int) = square;    // Function pointer
    cout << fp(5) << endl;

    return 0;
}

```
# 3. Value, address, pointer value
```cpp
#include <iostream>
using namespace std;

int main() {
    int num = 30;
    int* ptr = &num;

    cout << "Value: " << num << endl;
    cout << "Address: " << &num << endl;
    cout << "Pointer holds: " << ptr << endl;

    return 0;
}


```
# 4. Copy value using dereferencing

```cpp
#include <iostream>
using namespace std;

int main() {
    int first = 15;
    int second;
    int* p = &first;

    second = *p;

    cout << "Second = " << second << endl;
    return 0;
}

```
# 5. Swap two numbers using pointers

```cpp
#include <iostream>
using namespace std;

void swapNums(int* a, int* b) {
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main() {
    int x = 3, y = 7;
    swapNums(&x, &y);

    cout << x << " " << y << endl;
    return 0;
}

```
# 6. Dynamic integer using new, modify, delete

```cpp
#include <iostream>
using namespace std;

int main() {
    int* p = new int;
    *p = 9;

    cout << "Before: " << *p << endl;

    *p = 20;

    cout << "After: " << *p << endl;

    delete p;
    return 0;
}
```
# 7. Pointer arithmetic example 

```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {5,10,15,20,25};
    int* p = arr;

    cout << *p << " ";
    p += 3;
    cout << *p << endl;

    return 0;
}
```
# 8. Pointer increment & array modification

```cpp
#include <iostream>
using namespace std;

int main() {
    int a[] = {1,2,3,4,5};
    int* p = a;

    (*p)++;
    p++;
    (*p) += 5;

    for(int i=0;i<5;i++)
        cout << a[i] << " ";

    return 0;
}
```
# 9. Double pointer modification

```cpp
#include <iostream>
using namespace std;

int main() {
    int value = 40;
    int* p = &value;
    int** pp = &p;

    **pp = 80;

    cout << value << endl;
    return 0;
}
```
# 10. Offset pointer access

```cpp
#include <iostream>
using namespace std;

int main() {
    int a[] = {10,20,30,40,50};
    int* p = a + 2;

    cout << *(p - 1) << " " << *(p + 2) << endl;

    return 0;
}
```
# 11. Pointer re-assignment effect 

```cpp
#include <iostream>
using namespace std;

int main() {
    int m = 11, n = 22;
    int* ptr = &m;

    ptr = &n;
    *ptr = 100;

    cout << m << " " << n << endl;
    return 0;
}
```
# 12. Post-increment and pre-increment with pointer
    
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5;
    int* p = &x;

    cout << (*p)++ << " " << x << endl;
    cout << ++(*p) << " " << x << endl;

    return 0;
}
```
# 13. Complex pointer movement in array
    
```cpp
#include <iostream>
using namespace std;

int main() {
    int arr[] = {3,6,9,12,15};
    int* p = arr + 1;

    cout << *(p + 1) << " ";
    cout << *(p - 1) << endl;

    return 0;
}



