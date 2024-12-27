### Vectors in C++
This file contains information about dynamic arrays in C++ using the Standard Template Library (STL) vectors.
Vectors are sequence containers representing arrays that can change in size.

Basic functions and operations in vectors:

1. **Initialization**:
    - `vector<int> v;` : Initialize an empty vector
    - `vector<int> v(n);` : Initialize n elements with default value
    - `vector<int> v(n, value);` : Initialize n elements with value
    - `vector<int> v{1, 2, 3, 4};` : Initialize vector with elements

2. **Accessing elements**:
    - `v[i]` or `v.at(i)` - Access element at index i (O(1))
    - `v.front()` - Access the first element (O(1))
    - `v.back()` - Access the last element (O(1))

3. **Modifying elements**:
    - `v.push_back(value)` - Add element at the end (Amortized O(1))
    - `v.pop_back()` - Remove the last element (O(1))
    - `v.insert(position, value)` - Insert element at specified position (O(n))
    - `v.erase(position)` - Remove element at specified position (O(n))
    - `v.clear()` - Remove all elements (O(n))

4. **Capacity**:
    - `v.size()` - Number of elements (O(1))
    - `v.capacity()` - Size of allocated storage (O(1))
    - `v.empty()` - Check if vector is empty (O(1))
    - `v.resize(n)` - Change the number of elements to n (O(n))
    - `v.reserve(n)` - Request a change in capacity (O(n))

5. **Iterators**:
    - `v.begin()` - Iterator to the first element (O(1))
    - `v.end()` - Iterator to the element following the last element (O(1))
    - `v.rbegin()` - Reverse iterator to the last element (O(1))
    - `v.rend()` - Reverse iterator to the element preceding the first element (O(1))

Note: n represents the number of elements in the vector.


### Operations in Vectors

1. **Sorting a vector**:
    - `sort(v.begin(), v.end())` - Sort the vector in ascending order takes O(nlogn) time, uses hybrid sorting algorithm called **Introsort**. Introsort uses combination of quicksort, heapsort and insertion sort. So , it begins with quicksort and switches to heapsort when the recursion depth exceeds a level based on the number of elements being sorted.
    - `sort(v.rbegin(), v.rend())` - Sort the vector in descending order ,takes O(nlogn) time uses quicksort. 

2. **Reversing a vector**:
    - `reverse(v.begin(), v.end())` - Reverse the vector ,takes O(n) time 

3. **Searching in a vector**:
    - `binary_search(v.begin(), v.end(), key)` - Search for key in the vector, returns true if found, false otherwise. The vector must be sorted. Takes O(logn) time.
    - `find(v.begin(), v.end(), key)` - Search for key in the vector, returns an iterator to the first occurrence of key, or v.end() if not found. Takes O(n) time.
    - `count(v.begin(), v.end(), key)` - Count the number of occurrences of key in the vector. It takes O(n) time.

4. **Minimum and Maximum element**:
    - `*min_element(v.begin(), v.end())` - Find the minimum element in the vector. Takes O(n) time.
    - `*max_element(v.begin(), v.end())` - Find the maximum element in the vector. Takes O(n) time.

5. **Sum of elements**:
    - `accumulate(v.begin(), v.end(), 0)` - Calculate the sum of elements in the vector. Takes O(n) time.
    - `accumulate(v.begin(), v.end(), 0, plus<int>())` - Calculate the sum of elements in the vector using the plus operator. Takes O(n) time.

6. **Counting elements**:
    - `count(v.begin(), v.end(), key)` - Count the number of occurrences of key in the vector. Takes O(n) time.
    - `count_if(v.begin(), v.end(), predicate)` - Count the number of elements that satisfy the predicate. Takes O(n) time. 

### Program to demonstrate the operations in vectors

```cpp
#include <iostream>
#include <vector>
#include <algorithm>

using namespace std;

int main() {
    vector<int> v{1, 2, 3, 4, 5};

    // Accessing elements
    cout << "Element at index 2: " << v[2] << endl;
    cout << "First element: " << v.front() << endl;
    cout << "Last element: " << v.back() << endl;

    // Modifying elements
    v.push_back(6);
    cout << "After push_back: ";
    for (int i : v) {
        cout << i << " ";
    }
    cout << endl;

    v.pop_back();
    
    cout << "After pop_back: ";
    for (int i : v) 
    {
        cout << i << " ";
    }
    cout << endl;

    // Searching in a vector
    if (binary_search(v1.begin(), v1.end(), 3)) 
    {
        cout << "Element 3 found in the vector" << endl;
    } else 
    {
        cout << "Element 3 not found in the vector" << endl;
    }

    auto it = find(v1.begin(), v1.end(), 4);
    if (it != v1.end()) 
    {
        cout << "Element 4 found at position: " << distance(v1.begin(), it) << endl;
    } else 
    {
        cout << "Element 4 not found in the vector" << endl;
    }

    int count_3 = count(v1.begin(), v1.end(), 3);
    cout << "Element 3 occurs " << count_3 << " times in the vector" << endl;

    // Minimum and Maximum element
    cout << "Minimum element in the vector: " << *min_element(v1.begin(), v1.end()) << endl;
    cout << "Maximum element in the vector: " << *max_element(v1.begin(), v1.end()) << endl;

    // Sum of elements
    int sum = accumulate(v1.begin(), v1.end(), 0);
    cout << "Sum of elements in the vector: " << sum << endl;

    // Counting elements with a condition
    int count_even = count_if(v1.begin(), v1.end(), [](int x) { return x % 2 == 0; });
    cout << "Number of even elements in the vector: " << count_even << endl;
    ```
    cout << endl;

    v.insert(v.begin() + 2, 10);
    cout << "After insert: ";
    for (int i : v) 
    {
        cout << i << " ";
    }
    cout << endl;

    v.erase(v.begin() + 2);
    cout << "After erase: ";
    for (int i : v)
    {
        cout << i << " ";
    }
    cout << endl;

    v.clear();
    cout << "After clear: ";
    for (int i : v) 
    {
        cout << i << " ";
    }
    cout << endl;

    // Sorting a vector
    vector<int> v1{5, 3, 1, 4, 2};
    sort(v1.begin(), v1.end());
    cout << "Sorted vector: ";
    for (int i : v1) 
    {
        cout << i << " ";
    }
    cout << endl;

    // Reversing a vector
    reverse(v1.begin(), v1.end());
    cout << "Reversed vector: ";
    for (int i : v1) 
    {
        cout << i << " ";
    }
    cout << endl;

    return 0;
}
```