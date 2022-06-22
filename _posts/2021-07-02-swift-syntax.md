---
layout: single
title: "Swift 언어 기본 문법 (1)"
tags: [swift,ios]
categories: ios
toc: yes
---

### functions (함수)

```swift
func turnRight() {
	//code
}
```

- Parameter(매개 변수)를 가진 함수 정의:

```C#
//이 함수는 'Int' 타입을 가진 'Count' 매개변수를 가지고 있다.
func eat(count: Int) {
	for i in 1...count {
    //code
  }
}
...
eat(count: 3) //calling the function
```



### for (반복문)

```swift
for i in 1 ... 5 { //loops 5 times
	//code
}
```

### while (반복문)

```c#
while condition {
	//code
}
```

### if-else condition (조건문)

```c#
if condition {
	//code
}
else if condition2 {
	//code
}
```

### Logical Operators (논리 연산자)

`AND : &&``
``OR : ||``
``NOT : !`

```C#
if condition1 && condition2 {
	//code
}
else if condition1 || condition2 {
	//code
}
```

