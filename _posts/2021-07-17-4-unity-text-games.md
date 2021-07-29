---
layout: single
title: "텍스트 기반 게임 개발: text component, scriptable object, state (1)"
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
- 하나의 게임에 100개가 넘는 State 이 있을 수 있고, 각 State 는 여러 시나리오를 담을 수 있음. 이러한 State 들을 관리할 수 있어야 함.
- 하나의 C# 파일로 이걸 관리하면 코드가 굉장히 길어지고 관리가 힘들어짐 (비효율적).
  - 그래서 **Scriptable Object** 를 활용! 

**Scriptable Objects**

- **ScriptableObject** 는 데이터를 asset에 보관할 수 있게 해주는 **Class**이다.  

- 이걸 활용하면 Script 파일에 들어가는 데이터의 양을 획기적으로 줄일 수 있다.

- 가볍고 편리함

- ![image-20210719174919215](/assets/images/image-20210719174919215.png)

  script 파일에는 여러 용도의 코드가 들어가는 반면, Scriptable Object에는 데이터만 들어감. 

Scriptable Objects 사용법:

1. 먼저 Unity 의 하단 Asset 칸에 "State"라는 C# Script파일을 생성한다 (이 파일은 좌측 메뉴의 Game Object에 링크를 안해도 사용 가능 함. 이 외의 모든 Script 는 'Game' Object에 링크해야함)

2. 파일 열고 'MonoBehavior' 를 'ScriptableObject'로 바꿔줌. 이러면 'State'라는 클래스 이름이 'ScriptableObject'라는 클래스를 가지게 됨.

3. 클래스 안 모든 코드를 지운 후 아래와 같이 코드 추가:

   ```c#
   using System.Collections;
   using System.Collections.Generic;
   using UnityEngine;
   
   [CreateAssetMenu(menuName = "State")] //allows us to create a scriptable object in Unity's asset menu interface
   public class State : ScriptableObject
   {
       [TextArea(10, 14)] [SerializeField] string storyText; //SerializeField makes it available in the inspector
       //TextArea() makes the Story Text box on the right side of Unity interface to be bigger
   }
   ```

   

4. Unity 하단 Asset 인터페이스에서 우측 클릭 후 'State'눌러서 'StartingText'라는 Scriptable Object 생성. 우측에 우리가 만든 Story Text 칸안에 텍스트 입력. 

### 게임 시작하면 시작 state의 Story Text 칸안에 있는 텍스트를 띄우기

1. State.cs 파일에 전 단계에서 지정한 Story Text 를 리턴해주는 함수 추가:

   ```C#
       public string GetStateStory()
       {
           return storyText;
       }
   ```

2. 메인 script 파일의 Start() 함수를 다음과 같이 지정:

   ```C#
       [SerializeField] Text textComponent; //variable of type Text
       [SerializeField] State startingState;
   
       State state;
   
       // Start is called before the first frame update
       void Start()
       {
           state = startingState;
           textComponent.text = state.GetStateStory();//modifying text property WITHIN the text component
       }
   ```

   

### 키보드 누르면 Next State로 이동

1. 먼저, State.cs 파일에 아래와 같이 'SerializeField' 를 해준다

   ```c#
   [SerializeField] State[] nextStates;
   ```

   이러면 Unity에서 scriptable object 를 클릭하면 우측 inspector에 'Next States'라는 배열이 생긴다. 

2. Assets 칸에서 Create -> State 를 통해 'Room 1', 'Room 2' 등 새로운 state 들을 만든 후, 위에서 말했던 'Next States'에 원하는 state 들을 drag해준다 (추가할 state 가 굉장히 많을 시 우측 상단 자물쇠 버튼을 이용해 inspector 칸을 잠근 후 추가할 state 들을 한꺼번에 선택 후 drag 한다).

3. Next States 지정이 끝났으면 메인 script 파일의 Update() 함수에 다음과 비슷한 코드를 추가해준다:

   ```C#
       void Update()
       {
           ManageState();
       }
   
       private void ManageState()
       {
           var nextStates = state.GetNextStates();
           if (Input.GetKeyDown(KeyCode.Alpha1)) //key number 1 on keyboard
           {
               state = nextStates[0];
           }
           else if (Input.GetKeyDown(KeyCode.Alpha2)) //key number 1 on keyboard
           {
               state = nextStates[1];
           }
           else if (Input.GetKeyDown(KeyCode.Alpha3))
           {
               state = nextStates[2];
           }
           textComponent.text = state.GetStateStory();
       }
   ```

   이러면 키보드에서 1를 누를 시 전 과정에서 지정된 첫번째 state로 이동된다.  

   이때, State.cs 파일에서 지정된 state 배열을 리턴하는 GetNextStates()라는 함수를 생성해줘야 함:

   ```C#
       [SerializeField] State[] nextStates;
   
       public State[] GetNextStates()
       {
           return nextStates;
       }
   ```

   

<u>참고</u>: 

<u>참조</u>

https://docs.unity3d.com/ScriptReference/Input.html
https://docs.unity3d.com/ScriptReference/KeyCode.html
https://www.udemy.com/course/unitycourse/



