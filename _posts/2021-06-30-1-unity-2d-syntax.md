---
layout: single
title: "Unity-2D 공부일지: C# 기본 (1)"
tags: [unity, game-dev, C#]
categories: unity-2d
---

## 콘솔에 출력하기

- C#를 사용할때 `print("test");` 를 활용하거나 `Debug.Log("test");`를 활용하여 출력 할 수 있다. 
- 추후에 설명하겠지만 `Debug.Log()` 을 사용하는데에 장점이 있기 때문에 미리 `Debug.Log()`의 사용을 습관화 하면 좋다. 

## C# 변수 (Variables)

- int형 변수 ex: `int hitPoints = 20;`
- float형 변수 ex: `float speed = 3.8f;`
- bool형 변수 ex:  `bool isAlive = true;`
- string형 변수 ex: `string name = "Rick";`

### 변수 프린트하기

```c#
int max = 100;
Debug.Log("The Highest Number is" + max);
```

### var

변수 정의할때 int, string, bool 등 대신 var 을 사용할 수 있다. 그럼 변수 내용에 따라 var이 아래 예시와 같이 자동 지정된다.

```c#
var nextStates = state.GetNextStates();
//state.GetNextStates() 에서 불려오는 내용이 string이면, var는 자동으로 string으로 지정됨.
```

 

## 조건문 : if, else if, else

```c#
if (/* 조건 */) {
  //위 조건을 충족하면 이곳에 있는 코드를 실행
}
else if (/* 다른 조건 */) {
  //위 조건을 충족하면 이곳에 있는 코드를 실행
}
else {
  //위 조건들을 충족하지 못하면 이곳에 있는 코드를 실행
}
```

## 기본 구조 및 범위 : Scope

- namespace -> class -> method -> statements 순으로 정리된다.

![image-20210701035829166](/assets/images/image-20210701035829166.png)

- 하나의 method안에 정의된 변수는 다른 method에서 사용될 수 없지만, class-level에서 정의된 변수는 같은 class 안에 있는 모든 method에서 사용될 수 있다. 

## 코드 리팩터링 (Refactoring)

- 리팩터링: 코드를 읽기 쉽게 구조를 재조정하는 과정
- ex) 

```c#
void Start()
{
    Debug.Log("Do stuff");
    Debug.Log("Do more stuff");
}
```

위 코드를 리팩토링하여 아래와 같이 만들어야 나중에 프로그램 스케일이 커졌을때 코드를 직관적으로 해석할 수 있게된다.
코드를 함수로 옮기는 과정은 Encapsulating 이라고 칭한다.

```c#
    void Start()
    {
        StartGame();
    }

    void StartGame() //Refactoring을 하기 위해 새로운 함수 추가
    {
        Debug.Log("Do stuff");
        Debug.Log("Do more stuff");
    }
```

> Refactoring & Encapsulating 하는 과정은 코드를 보기 쉽게 만들어 주고 추후 관리도 용이하게 해주기 때문에 굉장히 중요하다!

## 함수 (Methods)

함수 정의 예) 

```c#
public string getStory() {
	//code
}
```

## 배열 (Array)

배열 정의 예)

```c#
int[] oddNumbers = {1, 3, 5, 7, 9};
```

<u>참조</u>

https://docs.unity3d.com/ScriptReference/Input.html
https://docs.unity3d.com/ScriptReference/KeyCode.html
https://www.udemy.com/course/unitycourse/

