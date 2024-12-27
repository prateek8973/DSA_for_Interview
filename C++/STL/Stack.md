### Stack in C++

Basic Program to demonstrate the use of stack in C++.

```cpp
#include <iostream>
#include <stack>

using namespace std;

int main() {
    stack<int> s;
    s.push(1); // O(1)
    s.push(2); // O(1)
    s.push(3); // O(1)
    s.push(4); // O(1)

    cout << "Stack size: " << s.size() << endl; // O(1)
    cout << "Top element: " << s.top() << endl; // O(1)

    cout << "Stack elements: ";
    // s.empty() is an O(1) operation
    while (!s.empty()) {
        cout << s.top() << " ";
        s.pop();
    }
    cout << endl;

    return 0;
}
```
