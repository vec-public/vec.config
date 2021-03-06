# 躲猫猫 地图配置说明
# 图池配置
- 基本的声明我将不再赘述
- 使用例子阐述配置
```
    "ar_monastery" // 这个地图的名字, 读取的是相对应的地图文件, 也即maps/xxxx.bsp
	{
		"m_Description"		"N/A" // 这个地图的描述, 比如说 "寒霜寺院"
		"m_CertainTimes"		"all" // 可用时间段 (0-23点)
		"m_Price"		"100"       // 预定价格
		"m_PricePartyBlock"		"3000"  // 包场价格
		"m_MinPlayers"		"0"     // 需要小于多少人才会启用 (0代表禁用该选项)
		"m_MaxPlayers"		"0"     // 需要大于多少人才会启用 (0代表禁用该选项)
		"m_MaxCooldown"		"2"     // 地图冷却时间, 即: 选了这个图后有多久是不能选的
		"m_NominateOnly"		"0" // 只能通过nominate选图
		"m_VipOnly"		"0"         // 只能是vip选图
		"m_AdminOnly"		"0"     // 只能是管理员选图
	}
```
添加新图只需要按照上述格式在后方直接添加即可

# 地图道具配置
___
## 综合
- 基本的声明我将不再赘述
- 配置文件以: ```这个地图的名字.cfg``` 命名, 比如 ```de_dust2.cfg```
- 我将使用一个例子用于阐述如何添加配置
```keyvalue
    "props_interiors/sofa02"
    {
        "name"		"沙发 (蓝色)"
        "hp"		"250"
        "speed"		"1.100000"
    }
```
其中:
- ```prop_interiors/sofa02```: 代表你想使用的模型(建议只使用CSGO原生模型)
> - 以本例来说, 在csgo里则是prop_interiors/sofa02.mdl
> - 如果你想找到可用的模型, 请使用GCFSpace: https://nemstools.github.io/pages/GCFScape-Download.html
- ```"name"		"沙发 (蓝色)"```: 模型名字(用于显示在模型选单里)
- ```"hp"          "250"```: 该物体血量
- ```"speed"       "1.1"```: 该物体移动速度

其他可用的配置设置
- ```gravity```: 该物体的重力(默认1.0, 越低代表越轻)
- ```offset_x```: 物体偏移 (X轴)
- ```offset_y```: 物体偏移 (Y轴)
- ```offset_z```: 物体偏移 (Z轴)
> 注: 这里指的是往原点偏移的方向, 比如说offset=1, 那么就代表着以原点为开始向右移动1个单位
- ```rotation_x```: 物体偏转 (X轴)
- ```rotation_y```: 物体偏转 (Y轴)
- ```rotation_z```: 物体偏转 (Z轴)
> 注: 这里指的是偏转方向, 比如说rotation_x=90, 那么久代表着向右偏转90度
- ```skin```: 使用的贴图集
___
所以, 假设我们想创建一个新物品, 那么在配置中, 我们可以这样写:
```keyvalue
    "prop_something/something" // 这里填入这个模型的路径(注意: 不要有.mdl后缀!)
    {
        "name"      "${Name}" // 这个模型的名字
        "hp"        "${Health}" //这个模型的血量
    }
```

完整的例子如下所示:
```
配置文件名: whatever_map.cfg

配置文件内容:
"Models"
{
    "prop_something/something" // 这里填入这个模型的路径(注意: 不要有.mdl后缀!)
    {
        "name"      "${Name}" // 这个模型的名字
        "hp"        "100" //这个模型的血量
    }
}

```