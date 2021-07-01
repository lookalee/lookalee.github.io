---
layout: single
title: "Unity-2D 공부일지: Unity 기본 (3)"
tags: [unity, game-dev]
categories: unity-2d


---

### C# Script 생성

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

### Creating Sprites

- Sprite: 2D graphic objected obtained from a bitmap image.

<u>참조</u>

https://docs.unity3d.com/ScriptReference/Input.html
https://docs.unity3d.com/ScriptReference/KeyCode.html
https://www.udemy.com/course/unitycourse/



