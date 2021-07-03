---
layout: single
title: "Swift 언어 기본 문법 (2)"
tags: [swift,iOS]
categories: iOS



---

### Variables (변수)

변수 정의:  `var age = 18`
Incrementing: age = age + 1 or `age += 1`

Comparison Operators: `<, >, ==, !=`

### Constants (상수)

상수 정의: `let numberOfChances = 5`

### Types 

- type안에서 features 는 **properties** 라고 하고, behaviors는  **methods** 라고 한다.
- **Property** : type 안에 정의된 변수
- **Method** : type 안에 정의된 함수

![image-20210704032159488](/assets/images/image-20210704032159488.png)

**Dot Notation**

- dog 라는 instance 안의 "color" 라는 변수를 아래와 같이 접근할 수 있다:

  ```swift
  dog.color = "green"
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

  

