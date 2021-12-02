---
layout: single
title: "[Unity-Delivery Driver] Intro (1)"
tags: [unity, game-dev, C#]
categories: unity-2d


---



**Creating a car object and make it rotate**:
Create a Sprite -> Connect to C# script -> Add following code to Update(): 

```c++
transform.Rotate(0, 0, 0.1f);
```

**make it move forward**:

```c++
transform.Translate(0, 0.01f, 0);
```



**To adjust variables in Unity interface instead of doing it in code:** 

- Use **SerializeField**.

- ex) 

  ```c++
  [SerializeField]float moveSpeed = 0.01f;
  ```

  Now, an input box appears for moveSpeed on Unity's interface at the right. 

  Changing the value here overrides the code!

**Input System (convert player actions such as button press, into info for the game)**:

- Refer to : Edit -> Project Settings -> Input Manager -> Axes -> Horizontal/Vertical

- ```c++
  float steerAmount = input.GetAxis("Horizontal") * steerSpeed;
  ```

**Time.deltaTime**: 

- we can make our game "frame rate independent", so that it behaves same on fast and slow computers

- ex)

  ```c++
          float steerAmount = Input.GetAxis("Horizontal") * steerSpeed * Time.deltaTime;
  
  ```

**Making sprites collidable**:

![image-20211201214723716](/images/2021-11-30-unity-delivery-driver-1/image-20211201214723716.png)

- Add Components called '__ Collider 2D' and 'Rigidbody 2D'.
  - 'Rigidbody 2D' adds physics to the objects so they act like objects in real life.
  - '__ Collider 2D' determines the boundaries of the object, depending on which collider you select (ex: Capsult, Circle, etc)

- Print to console when objects bump into something:

  - In a separate script, use built-in method called **OnCollisionEnter2d()**:

  - ```c++
    public class Collision : MonoBehaviour
    {
        void OnCollisionEnter2D(Collision2D other) {
            Debug.Log("You Collided!");
        }    //in-built method
    }
    ```

