# How to use priority_queue in C++

**The syntax of it is: `priority_queue<Type, Container, ComparisonFunction>`**

- Default max heap: `priority_queue<int> pq1` , this comparison function is `less<int>`

- min heap: `priority_queue<int, vector<int>, greater<int>> min_pq;`

The container (second parameter) holds the elements of the type specified in the first parameter.

**How does comparison function work?**

1. The element is first placed at the bottom of the heap
2. Then it "bubbles up" by comparing with its parent (not the last element)
3. If comparison returns false, it swaps with its parent and continues up
4. This process continues until either:
   - It reaches the root (top), or
   - The comparison returns true (meaning it's in the right position)



**Example**

```c++
int main() {
    std::priority_queue<int> pq;
    std::priority_queue<int, std::vector<int>, std::greater<int>> pq2;
    std::vector<int> vec = {3,54,2,5,76,43,21,54,7,87,8,5};

    for (int i = 0; i < vec.size(); i++) {
        pq.push(vec[i]);
        pq2.push(vec[i]);
    }

    std::cout << "Max heap: ";

    while (!pq.empty()) {
        std::cout << pq.top() << " ";
        pq.pop();
    }

    std::cout << std::endl;

    std::cout << "Min heap: ";

    while (!pq2.empty()) {
        std::cout << pq2.top() << " ";
        pq2.pop();
    }
}
```

