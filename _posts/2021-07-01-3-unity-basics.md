---
layout: single
title: "Unity-2D 공부일지: Unity 기본 (3)"
tags: [unity, game-dev, C#]
categories: unity-2d


---

### Unity 인터페이스 기본

![image-20210701223032087](/assets/images/image-20210701223032087.png?lastModify=1625149157)

위 사진에서 보이듯이 유니티를 키면 **Hiearchy, Scene, Game, Inspector, Project, Console** 와 같은 인터페이스들을 확인할 수 있다.

- Hiearchy 인터페이스에는 모든 게임 오브젝트들이 들어간다. (화면에 보이는 Main Camera도 게임 오브젝트이다)
  - ex) 카메라, 플레이어, 아이템, 환경, 등
  - 게임 오브젝트를 클릭하면 우측 Inspector 칸에서 해당 오브젝트에 대한 정보를 볼 수 있다.
  - Hierarchy 메뉴에서 우측 클릭하거나 Assets 메뉴에서 드레그하여 게임 오브젝트를 추가할 수 있다. 
  - 게임 오브젝트의 순서에 따라 Overlay 가 결정된다.

### C# Script 파일 생성

유니티 인터페이스의 하단 Assets 칸에 오른쪽 클릭을 하여 C# Script 를 생성할 수 있다.
C# Script 는 기본적으로 `void Start() { }` 와 `void Update () { }`로 이루어져 있다.

ex)

```c#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class NumberWizard : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
				//code here
    }

    // Update is called once per frame
    void Update()
    {
				//code here
    }
}
```

- void Start() {} 는 게임이 처음 실행될때 **한번** 실행된다.
- void Update() {} 는 매 프레임마다 **계속** 실행된다. 
  - 즉, 마우스 클릭 등 사용자 Input을 받아야 할때는 Update() {} 안에 코드를 넣는다. 
- Start() {} 에 정의된 변수들은 Update() {}에서 사용될 수 없다 (반대도 마찬가지).

### 사용자 Input 받기

- Input.GetKeyDown()과 같은 메서드를 Update() 함수안에서 사용.
  - 비슷한 메서드들은 Unity Documentation에서 확인
- Up 화살표와 Down 화살표 버튼 누르면 반응하는 예시:

```c#
	  void Update()
    {
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {
            Debug.Log("Up Arrow key was pressed.");
        }
        if (Input.GetKeyDown(KeyCode.DownArrow))
        {
            Debug.Log("Down Arrow key was pressed.");
        }
    }
```

- *key code 목록: https://docs.unity3d.com/ScriptReference/KeyCode.html.* 
- 만약 동시에 여러 키를 못 누르게 하고 싶으면 else if 를 사용하면 된다:

```c#
    void Update()
    {
        if (Input.GetKeyDown(KeyCode.UpArrow))
        {
            Debug.Log("Up Arrow key was pressed.");
        }
        else if (Input.GetKeyDown(KeyCode.DownArrow))
        {
            Debug.Log("Down Arrow key was pressed.");
        }
    }
```

### Sprites

- Sprite: 비트맵 이미지로 생성된 2D 오브젝트.
- 이동, 스케일, 회전, 등을 할 수 있다.

#### Sprites 생성

1. 하단 Assets칸에서 오른쪽 클릭 후 네모, 동그라미, 등의 Sprites 를 생성.
2. 생성된 Sprites를 Hiearchy, 또는 Scene 화면으로 드레그 (여러개 추가 가능).
3. 상단 좌측 메뉴들로 Sprites를 조정할 수 있음.

### Canvas 생성

Canvas는 Game Object중 하나이며 게임 스크린이라고 생각해보자.

1. GameObject --> UI --> Canvas 클릭하여 Canvas 생성
2. Canvas에 우측 클릭하여 Text, Image 와 같은 게임 오브젝트 생성. 
   1. 생성된 게임 오브젝트들은 Canvas의 Child 오브젝트가 됨.
   2. 우측 Inspector 화면의 체크박스를 이용해 Canvas를 비활성화하면 Children들까지 비활성화가 됨.

### Game Objects

**<u>Game Object -> Components -> Properties</u>**

모든 **Game Object**들은 Animation, Audio, Effects 와 같은 **Components** 들로 이루어져 있으며, Components 들은 Values, Reference와 같은 **Properties**들로 이루어져 있다. 

1. 우측 클릭으로 Game Object 생성 후 Inspector 메뉴에서 'Add Component' 버튼을 눌러 Component를 추가할 수 있다. 

<u>참고</u>: 

- 사용한 설정값
  - Game 화면 디스플레이: Full HD (1920x1080)

<u>출처</u>

https://docs.unity3d.com/ScriptReference/Input.html
https://docs.unity3d.com/ScriptReference/KeyCode.html
https://www.udemy.com/course/unitycourse/



