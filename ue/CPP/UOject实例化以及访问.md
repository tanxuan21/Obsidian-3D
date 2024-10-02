创建MyObject.h类

在Pawn类内测试：

MyPawn.h
```cpp
#include "MyObject.h"
class MyPawn{
public:
	UPROPERTY()
	UMyObject* MyTestObject;
}
```

MyPawn.cpp
```cpp
// 开始游戏打印输出
void AMyPawn::BeginPlay()
{
	Super::BeginPlay();
	// 实例化UObject
	TSubclassOf<UMyObject> MySubClassObject = UMyObject::StaticClass();
    // 使用NewObject函数来创建UObject对象，这样就可以将垃圾回收的工作丢给UE而不是你自己
	MyTestObject = NewObject<UMyObject>(GetWorld(),MySubClassObject);
    // 如果创建成功，打印值。
	if (MyTestObject) {
		UE_LOG(LogTemp, Warning, TEXT("%s"), *MyTestObject->GetName());
		UE_LOG(LogTemp,Warning, TEXT("Health: %f"), MyTestObject->MyDataTableStruct.Health);
	}
}
```

压根不允许这样创建UObject。实际上可以通过编译，但是无法运行。
```cpp
UMyObject uo;
UE_LOG(LogTemp, Warning, TEXT("UObject：%f"),uo.MyDataTableStruct.Health);
UMyObject* uo = new UMyObject(); // new 运算符没有关于UMyObject的重载
UE_LOG(LogTemp, Warning, TEXT("UObject：%f"), uo.MyDataTableStruct.Health);
```