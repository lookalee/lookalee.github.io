---
layout: single
title: "[Competitive Coding] Useful C++ syntax for solving coding problems"
tags: [c++, competitive-coding]
categories: competitive-coding


---

# Useful C++ Syntax

### auto

- automatically uses the type of the element

- use it to avoid unnecessary conversions!

- ex) 

  ```c++
  int count = 10;
  auto myAuto = count; //'auto' becomes  'int'
  ```

  

### Arrays

##### **size of vector array: **`.size()`

ex)

```c++
std::vector<int> myints;
std::cout << myints.size(); 
```

### 

### Strings

length of strings: `str.length()`

##### Int -> String Conversion:

```c++
#include <string> 
int x = 10;
std::string s = std::to_string(x); 
```

##### Find content in strinfg: `.find()`

ex)

```c++
#include <string> 
string str ("hello, world");
return str.find(','); //6
```

- if no matches are found, returns `string::npos`

##### Substring: `.substr()`

ex)

```c++
#include <string> 
string str ("hello, world");
return str.substr(6); //" world"
```

##### Splitting strings using getline():

```c++
//Include necessary libraries
#include <iostream>
#include <sstream>
#include <vector>
#include <string>

int main()
{
    //Define string data that will be splitted
    std::string strData = "Learn C++ Programming";
    //Define contant data that will be worked as delimiter
    const char separator = ' ';
    //Define the dynamic array variable of strings
    std::vector outputArray;
    //Construct a stream from the string
    std::stringstream streamData(strData);
    /*
    Declare string variable that will be used
    to store data after split
    */
    std::string val;
    /*
    The loop will iterate the splitted data and
    insert the data into the array
    */
    while (std::getline(streamData, val, separator)) {
        outputArray.push_back(val);
    }
    //Print the splitted data
    std::cout << "The original string is:" << strData << std::endl;
    //Read the array and print the splitted data
    std::cout << "\nThe values after splitting the string based on space:" << std::endl;
    for (auto &val: outputArray) {
        std::cout << val << std::endl;
    }
    return 0;
}
```



### map

- Maps contain key value pairs, where each keys are unique.

**Creating a map with 3 strings as keys**:

```c++
std::map<std::string, int> m { 	{"Banana", 10}, {"Apple", 12},     	{"Pear", 20}, };
```

**Inserting new/ updating value**:

```c++
m["Banana"] = 5; //updates 10 to 5
m["Avocado"] = 1; //creates new key with value 1
```

**Iterating the map's value**:

```c++
for(auto it:m) 
{
	sum += it.second; //use '.first' for key, '.second' for value
}
```



### References:

- https://linuxhint.com/split-string-cpp/
