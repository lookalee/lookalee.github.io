---
layout: single
title: "[Competitive Coding] Useful C++ syntax for solving coding problems"
tags: [c++, competitive-coding]
categories: competitive-coding


---

## Useful C++ Syntax

#### auto

- automatically uses the type of the element

- use it to avoid unnecessary conversions!

- ex) 

  ```c++
  int count = 10;
  auto myAuto = count; //'auto' becomes  'int'
  ```

  

#### Int -> String Conversion:

```c++
#include <string> 
int x = 10;
std::string s = std::to_string(x); 
```

#### **size of vector array: **`.size()`

ex)

```c++
std::vector<int> myints;
std::cout << myints.size(); 
```

#### map

- Maps contain key value pairs, where each keys are unique.

**Creating a map of three strings**:

```c++
std::map<std::string, int> m { {"Banana", 10}, {"Apple", 12}, {"Pear", 20}, };
```

**Inserting new/ updating value**:

```c++
m["Banana"] = 5; //updates 10 to 5
m["Avocado"] = 1; //creates new key with value 1
```

