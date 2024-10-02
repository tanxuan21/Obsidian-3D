基本脚本框架
```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class redbird : MonoBehaviour
{
    // Start is called before the first frame update
    void Start()
    {
        // Debug方法
        Debug.Log("fuck");
    }

    // Update is called once per frame
    void Update()
    {
    }
}

```

输入事件
Input类
~~~csharp
// 检测键盘按下事件  
if (Input.GetKey(KeyCode.Space))  
{  
    // 执行代码当按下空格键时  
}  
    
// 检测鼠标左键点击事件  
if (Input.GetMouseButtonDown(0))  
{  
    // 执行代码当鼠标左键被点击时  
}  
    
// 检测鼠标右键点击事件  
if (Input.GetMouseButtonDown(1))  
{  
    // 执行代码当鼠标右键被点击时  
}  
~~~

~~~csharp
Vector2 mousePosition = Input.mousePosition;// 鼠标相对屏幕位置
Vector2 mouseDeltaPosition = Input.mouseDeltaPosition;// 相对变化位移
// 支持触摸平台
bool touchSupported = Input.touchSupported;
Touch touch = Input.GetTouch(0); // 获取第一个触摸的信息
bool leftButtonPressed = Input.GetMouseButton(0); // 检查鼠标左键是否被按下
float axisValue = Input.GetAxis("Horizontal"); // 获取水平轴的值这个方法返回一个浮点数，表示指定的轴的值。这个轴可以是设备的轴，如游戏手柄的摇杆，或者是模拟摇杆的虚拟轴。
~~~