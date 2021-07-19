---
layout: single
title: "Unity-2D 공부일지: Unity 게임 개발 기본 기능들 (4)"
tags: [unity, game-dev, C#]
categories: unity-2d



---

### Text Component 업데이트 하는 법

1. 좌측 메뉴 에서 우측 클릭 후 "Create Empty" 를 클릭하여 Game Object 생성.
2. Inspector Menu 에서 포지션 모두 0으로 초기화
3. Inspector Menu 에서 Add Component 클릭하여 Script Component 를 추가. 
4. Script에서 Text형 변수를 하나 생성해주고 (UnityEngine.UI namespace 추가해줘야함) Unity 에서 이걸 원하는 Text Object 에 연결.
5. 아래 코드를 사용하여 게임이 시작되면 텍스트가 표시되게 설정 (`[SerializeField]` 를 사용하면 'Game'의 Inspector 메뉴에 'Text Component' 칸이 생김. 이걸 원하는 Text box 로 연결하면 됨 )

```C#
public class AdventureGame : MonoBehaviour
{
    [SerializeField] Text textComponent; //variable of type Text
    void Start()
    {
        textComponent.text = ("I will show when game starts!"); //modifying text property WITHIN the text component
    }
		...
```

![image-20210702013031600](/assets/images/image-20210702013031600.png)

### States and State Machines

- State - Action / process / behavior
- State Machine 은 한번에 하나의 State만 있다고 가정함
- ![image-20210719173059344](/assets/images/image-20210719173059344.png)







<u>참고</u>: 

<u>참조</u>

https://docs.unity3d.com/ScriptReference/Input.html
https://docs.unity3d.com/ScriptReference/KeyCode.html
https://www.udemy.com/course/unitycourse/



