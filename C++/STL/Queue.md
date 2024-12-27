### Queue Operations
The time complexities of the queue operations are as follows:

- **Insertion (`push`)**: O(1)
- **Deletion (`pop`)**: O(1)
- **Accessing the front element (`front`)**: O(1)
- **Accessing the rear element (`back`)**: O(1)
- **Checking if the queue is empty (`empty`)**: O(1)
- **Getting the size of the queue (`size`)**: O(1)
```cpp
#include <iostream>
#include <queue>

int main() {
    std::queue<int> q;

    // Inserting elements into the queue
    q.push(10);
    q.push(20);
    q.push(30);

    // Displaying the front element
    std::cout << "Front element: " << q.front() << std::endl;

    // Displaying the rear element
    std::cout << "Rear element: " << q.back() << std::endl;

    // Removing the front element
    q.pop();
    std::cout << "Front element after pop: " << q.front() << std::endl;

    // Checking if the queue is empty
    if (q.empty()) {
        std::cout << "Queue is empty" << std::endl;
    } else {
        std::cout << "Queue is not empty" << std::endl;
    }

    // Displaying the size of the queue
    std::cout << "Size of the queue: " << q.size() << std::endl;

    return 0;
}
```