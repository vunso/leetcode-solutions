## What is the vector?
A vector is a sequence container that stores elements of a specific data type, such as integers, floating-point numbers, or characters. It is a part of the Standard Template Library (STL) and is defined in the <vector> header file.

### Key features of vectors
1. Dynamic size: Vectors can grow or shrink in size as elements are added or removed.
2. Random access: Elements in a vector can be accessed using an index, just like an array. e.g., vector[index]
3. Efficient insertion and deletion: Vectors provide efficient insertion and deletion of elements at any position.
4. Memory management: Vectors automatically manage memory for the elements they store.

### Syntax to declare vector
```cpp
 std::vector<dataType> vectorName;
```

### 1. Initalization

- **Declaring and defining like lists**
```cpp
std::vector<int> vec {10, 20, 30};
```

- **Declaring an empty vector and then pushing values**
```cpp
// creates an empty vector
std::vector<int> vec;
// push value into vector
vec.push_back(10);
```

- **From another vector**
```cpp
// creates an empty vector
std::vector<int> vec1 = {10, 20, 30};
std::vector<int> vec2(vec1.begin(), vec1.end());
std::vector<int> vec3 = vec2;
```

### 2. Iterating through vector

- **Using for loop**
```cpp
std::vector<int> vec = {1, 2, 3};
for(unsigned int i = 0; i < vec.size(); i++)
    std::cout << vec[i];
```

- **Using iterator**
element in the vector.
```cpp
std::vector<int> vec = {1, 2, 3};
for(vector<int>::iterator itr = vec.begin(); itr < vec.end(); itr++)
    std::cout << *itr;
```

- **Using auto keyword**
```cpp
std::vector<int> vec = {1, 2, 3};
for(auto & item: vec)
    std::cout << item;
```
