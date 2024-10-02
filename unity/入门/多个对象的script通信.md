### 多个对象通信
#### 单例设计模式
简介：单例设计模式就是游戏中某些类只创建一个对象。并把他暴露给全局。其他所有的对象都可以在全局见到他。


对象B
~~~csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class slingshot : MonoBehaviour
{
    // 创建全局单例引用
    public static slingshot Instance{get;private set}
    viod Awake(){
        // 生命周期开始时给静态全局实例对象赋值
        Instance = this;
    }
    void Start()
    {
    }

    // Update is called once per frame
    void Update()
    {
    }
}

~~~

对象A
~~~csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
public class redbird : MonoBehaviour
{

    void Start()
    {
        Debug.Log(slingshot.Instance);// 其他任何类都可以访问到静态全局对象。
    }

    void Update()
    {


    }

}

~~~
想要对象A调用对象B的方法。


#### 资源文件使用

Assets文件里的Resources文件，是Resources父类的数据。可以将预制件放在这里。

~~~csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class distoryable : MonoBehaviour
{
    private GameObject boomPrefab;
    void Start()
    {
        // 在Resource里加载
        boomPrefab = Resources.Load<GameObject>("boom1");
    }
    // Update is called once per frame
    void Update()
    {

    }
    void OnCollisionEnter2D(Collision2D collisionObj)
    {

    }
    private void dead()
    {
        // 实例化prefab。
        GameObject.Instantiate(boomPrefab,transform.position,Quaternion.identity);
    }
}

~~~