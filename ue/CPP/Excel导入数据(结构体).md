```cpp
#include "Engine/Classes/Engine/DataTable.h" // 数据表格加上这个头文件
// 这个是接受Ecxel数据表格为结构体的操作。直接将Excel拖拽进入内容文件夹即可创建
USTRUCT(BlueprintType)
struct FMyDataTableStruct :public FTableRowBase{// 共有继承这个表格类
	FMyDataTableStruct();
	GENERATED_USTRUCT_BODY() // 一定要加上这个宏
	UPROPERTY(EditAnywhere,BlueprintReadWrite,Category = "MyTestDataTableStruct")
	float Health;
	UPROPERTY(EditAnywhere,BlueprintReadWrite,Category = "MyTestDataTableStruct")
	FString Name;
	UPROPERTY(EditAnywhere,BlueprintReadWrite,Category = "MyTestDataTableStruct")
	int32 Level;

};
```

其他细则和要求以后补充