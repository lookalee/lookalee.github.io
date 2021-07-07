---
layout: single
title: "Swift 언어 기본 문법 (2)"
tags: [swift,iOS]
categories: iOS



---

### Variables (변수)

변수 정의:  `var age = 18`
Incrementing: age = age + 1 or `age += 1`

비교 연산자: `<, >, ==, !=`

### Constants (상수)

상수 정의: `let numberOfChances = 5`

### Types 

- type안에서 features 는 **properties** 라고 하고, behaviors는  **methods** 라고 한다.
- **Property** : type 안에 정의된 변수
- **Method** : type 안에 정의된 함수

![image-20210704032159488](/assets/images/image-20210704032159488.png)

- **Initialization:** to initialise an instance of an animal: `let animal = Animal()`
- Then, use dot notation to call the property/method of that instance: `animal.dog` 

### Arrays (배열)

- "Arrays in Swift are ordered lists"

- 배열 정의:  `var ingredients = ["banana", "almonds", "milk"]`

- 아이템 수정: `ingredients[0] = "strawberry"`

- Swift의 배열에는 `.remove(at: x)` 와 같은 함수를 사용하여 아이템 추가, 삭제 등 간단한 수정을 할 수 있다

  - ex) 

    ```swift
    var ingredients = ["banana", "almonds", "milk"]
    ingredients.remove(at: 2)
    ingredients.append("water")
    ingredients.insert("yoghurt", at: 1) //새로운 아이템이 remove/insert 되면 그 이후 아이템의 인덱스들은 자동으로 바뀐다.
    for item in ingredients { //looping array
      someFunction(item)
    }
    ```

    

### Algorithms (알고리즘)

#### Right Hand Rule Algorithm

- 주로 미로찾기에서 사용되는 알고리즘으로 탈출로를 찾을때까지 오른손을 벽에 대고 앞으로 가는 방식이다.

- 일자 표면을 따라 원을 그리는 형식으로 Navigate 하는 알고리즘 예시:

  ```pseudocode
  func navigateAroundWall() {
      if 'right side is blocked' {
          'move forward 1 step'
      }  else {
          'turn right'
          'move forward 1 step'
      }
  }
  ```

  

