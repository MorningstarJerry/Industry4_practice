# Industry4_practice
projects for industry4

# 工业4.0 方案 应用层解决方案

## 1.PLC 数据采集服务中台 (PlcDataCollectorServiceCenter)
![PLCDataCollector](https://github.com/MorningstarJerry/Industry4_practice/blob/main/PLCDataCollector.png)

## PLC 边缘层地址配置
```
[
  {
    "IpAddress": "192.168.250.1",
    "Port": 9600,
    "BayCode": "iRobert-Wheel-Right",
    "DeviceGuid": "0E1A6937-2932-4E71-9D31-72BCAE329988",
    "DeviceName": "Weel Auto Press Fit",
    "SA1": 7,
    "DA2": 0,
    "IsChangeSA1AfterReadFailed": "false",
    "StopAddr": "C100.02",
    "StartAddr": "C100.00",
    "WarningAddr": "C100.04",
    "OutputAddr": "D200",
    "OCountsAddr": "D302",
    "ECountsAddr": "D208",
    "YieldAddr": "D306"
  },
  {
    "IpAddress": "192.168.250.1",
    "Port": 9600,
    "BayCode": "iRobert-Wheel-Right",
    "DeviceGuid": "5690E4E0-D7EE-42EA-A282-9FCD72DF2305",
    "DeviceName": "Auto Balance Test",
    "SA1": 7,
    "DA2": 0,
    "IsChangeSA1AfterReadFailed": "false",
    "StopAddr": "C100.02",
    "StartAddr": "C100.00",
    "WarningAddr": "C100.04",
    "OutputAddr": "D200",
    "OCountsAddr": "D302",
    "ECountsAddr": "D208",
    "YieldAddr": "D306"
  },
  {
    "IpAddress": "192.168.250.2",
    "Port": 9600,
    "BayCode": "iRobert-Wheel-Right",
    "DeviceGuid": "16217D45-0634-47D1-B22F-BBA7024E9B2D",
    "DeviceName": "Auto Soldring",
    "SA1": 7,
    "DA2": 0,
    "IsChangeSA1AfterReadFailed": "false",
    "StopAddr": "C101.02",
    "StartAddr": "C101.00",
    "WarningAddr": "C101.04",
    "OutputAddr": "D200",
    "OCountsAddr": "D200",
    "ECountsAddr": "D5",
    "YieldAddr": "D208"
  },
  {
    "IpAddress": "192.168.250.3",
    "Port": 9600,
    "BayCode": "iRobert-Wheel-Right",
    "DeviceGuid": "72DD721E-4984-4C9A-AB90-F701BD561E5A",
    "DeviceName": "Screws Auto Fastening",
    "SA1": 7,
    "DA2": 0,
    "IsChangeSA1AfterReadFailed": "false",
    "StopAddr": "C102.00",
    "StartAddr": "C102.02",
    "WarningAddr": "C102.04",
    "OutputAddr": "D200",
    "OCountsAddr": "D200",
    "ECountsAddr": "D5",
    "YieldAddr": "D208"
  }
]
```
## Power BI 数据分析
![pb1](https://github.com/MorningstarJerry/Industry4_practice/blob/main/pb1.png)
#### Power BI 图表分析
![pb2](https://github.com/MorningstarJerry/Industry4_practice/blob/main/pb2.png)

## Peakboard 动态展示
![peakboard](https://github.com/MorningstarJerry/Industry4_practice/blob/main/PeakBoard1.png)

## Peakboard Lua 脚本
```

--Skript Screen Line 12
data.Zaeler = data.Zaeler + 1
data.HostName = runtime.network.hostname
data.HostIP = runtime.network.hostipaddress
data.LanIP = runtime.network.hostipaddresslan
if data.MitsuP0[0].Stop == "true" then 
    if data.Zaeler % 3 ==1 then
	screens['Screen1'].Kreis1.visibility = visibility.visible
	screens['Screen1'].Kreis1.stroke = brushes.tomato
	screens['Screen1'].Halo1.visibility = visibility.visible
	screens['Screen1'].Halo1.stroke =brushes.tomato
	screens['Screen1'].R1.visibility = visibility.visible
	screens['Screen1'].R1.borderbrush = brushes.tomato
	
	elseif data.Zaeler % 3 ==2 then
	screens['Screen1'].Kreis1.visibility = visibility.visible
	screens['Screen1'].Kreis1.stroke = brushes.coral
	screens['Screen1'].Halo1.visibility = visibility.visible
	screens['Screen1'].Halo1.stroke =brushes.coral
	screens['Screen1'].R1.visibility = visibility.visible
	screens['Screen1'].R1.borderbrush = brushes.tomato
	else 
	screens['Screen1'].Kreis1.visibility = visibility.collapsed
	screens['Screen1'].Halo1.visibility = visibility.collapsed
	screens['Screen1'].R1.visibility = visibility.collapsed
	end
elseif data.MitsuP0[0].Warning == "true" then 
	if data.Zaeler % 3 ==1 then
		screens['Screen1'].Kreis1.visibility = visibility.visible
		screens['Screen1'].Kreis1.stroke = brushes.yellow
		screens['Screen1'].Halo1.visibility = visibility.visible
		screens['Screen1'].Halo1.stroke =brushes.yellow
		screens['Screen1'].R1.visibility = visibility.visible
		screens['Screen1'].R1.borderbrush = brushes.yellow
	elseif data.Zaeler % 3 ==2 then
		screens['Screen1'].Kreis1.visibility = visibility.visible
		screens['Screen1'].Kreis1.stroke = brushes.yellow
		screens['Screen1'].Halo1.visibility = visibility.visible
		screens['Screen1'].Halo1.stroke =brushes.yellow
		screens['Screen1'].R1.visibility = visibility.visible
		screens['Screen1'].R1.borderbrush = brushes.yellow
	else
		screens['Screen1'].Kreis1.visibility = visibility.collapsed
		screens['Screen1'].Halo1.visibility = visibility.collapsed
		screens['Screen1'].R1.visibility = visibility.collapsed
	end
else
	if data.Zaeler % 3 ==1 then
		screens['Screen1'].Kreis1.visibility = visibility.visible
		screens['Screen1'].Kreis1.stroke = brushes.green
		screens['Screen1'].Halo1.visibility = visibility.visible
		screens['Screen1'].Halo1.stroke =brushes.green
		screens['Screen1'].R1.visibility = visibility.visible
		screens['Screen1'].R1.borderbrush = brushes.green
	elseif data.Zaeler % 3 ==2 then
		screens['Screen1'].Kreis1.visibility = visibility.visible
		screens['Screen1'].Kreis1.stroke = brushes.green
		screens['Screen1'].Halo1.visibility = visibility.visible
		screens['Screen1'].Halo1.stroke =brushes.green
		screens['Screen1'].R1.visibility = visibility.visible
		screens['Screen1'].R1.borderbrush = brushes.green
	else
		screens['Screen1'].Kreis1.visibility = visibility.collapsed
		screens['Screen1'].Halo1.visibility = visibility.collapsed
		screens['Screen1'].R1.visibility = visibility.collapsed
	end
end

if data.MitsuP0[1].Stop == "true" then 
    if data.Zaeler % 3 ==1 then
	screens['Screen1'].Kreis2.visibility = visibility.visible
	screens['Screen1'].Kreis2.stroke = brushes.tomato
	screens['Screen1'].Halo2.visibility = visibility.visible
	screens['Screen1'].Halo2.stroke =brushes.tomato
	screens['Screen1'].R2.visibility = visibility.visible
	screens['Screen1'].R2.borderbrush = brushes.tomato
	
	elseif data.Zaeler % 3 ==2 then
	screens['Screen1'].Kreis2.visibility = visibility.visible
	screens['Screen1'].Kreis2.stroke = brushes.coral
	screens['Screen1'].Halo2.visibility = visibility.visible
	screens['Screen1'].Halo2.stroke =brushes.coral
	screens['Screen1'].R2.visibility = visibility.visible
	screens['Screen1'].R2.borderbrush = brushes.tomato
	else 
	screens['Screen1'].Kreis2.visibility = visibility.collapsed
	screens['Screen1'].Halo2.visibility = visibility.collapsed
	screens['Screen1'].R2.visibility = visibility.collapsed
	end
elseif data.MitsuP0[1].Warning == "true" then 
	if data.Zaeler % 3 ==1 then
		screens['Screen1'].Kreis2.visibility = visibility.visible
		screens['Screen1'].Kreis2.stroke = brushes.yellow
		screens['Screen1'].Halo2.visibility = visibility.visible
		screens['Screen1'].Halo2.stroke =brushes.yellow
		screens['Screen1'].R2.visibility = visibility.visible
		screens['Screen1'].R2.borderbrush = brushes.yellow
	elseif data.Zaeler % 3 ==2 then
		screens['Screen1'].Kreis2.visibility = visibility.visible
		screens['Screen1'].Kreis2.stroke = brushes.yellow
		screens['Screen1'].Halo2.visibility = visibility.visible
		screens['Screen1'].Halo2.stroke =brushes.yellow
		screens['Screen1'].R2.visibility = visibility.visible
		screens['Screen1'].R2.borderbrush = brushes.yellow
	else
		screens['Screen1'].Kreis2.visibility = visibility.collapsed
		screens['Screen1'].Halo2.visibility = visibility.collapsed
		screens['Screen1'].R2.visibility = visibility.collapsed
	end
else
	if data.Zaeler % 3 ==1 then
		screens['Screen1'].Kreis2.visibility = visibility.visible
		screens['Screen1'].Kreis2.stroke = brushes.green
		screens['Screen1'].Halo2.visibility = visibility.visible
		screens['Screen1'].Halo2.stroke =brushes.green
		screens['Screen1'].R2.visibility = visibility.visible
		screens['Screen1'].R2.borderbrush = brushes.green
	elseif data.Zaeler % 3 ==2 then
		screens['Screen1'].Kreis2.visibility = visibility.visible
		screens['Screen1'].Kreis2.stroke = brushes.green
		screens['Screen1'].Halo2.visibility = visibility.visible
		screens['Screen1'].Halo2.stroke =brushes.green
		screens['Screen1'].R2.visibility = visibility.visible
		screens['Screen1'].R2.borderbrush = brushes.green
	else
		screens['Screen1'].Kreis2.visibility = visibility.collapsed
		screens['Screen1'].Halo2.visibility = visibility.collapsed
		screens['Screen1'].R2.visibility = visibility.collapsed
	end
end
```

## 2. 电量数据采集动态分析 （IEPM）
### 根据智能电表对接实时采集电表数据, 根据预警规则预警， 实时分析生产线能耗产出比例
### 该项目基于 WPF 实现的 桌面监控系统
![Elec1](https://github.com/MorningstarJerry/Industry4_practice/blob/main/Elec1.png)

### MES 对接产出数据分析动态监控
![Ele2](https://github.com/MorningstarJerry/Industry4_practice/blob/main/Ele2.png)

### 每一条生产线监控
![Ele3](https://github.com/MorningstarJerry/Industry4_practice/blob/main/Ele3.png)

## 3.SMED  生产线一键换模方案
### 根据IEPlatform 中央发送 Command 实时通知生产线每一个工位一件换模， 自动打开对应的物料对比，指导文件对比
### 该项目基于 WPF 开发
### 登录
![Esmed1](https://github.com/MorningstarJerry/Industry4_practice/blob/main/Esmed1.png)

### main
![Esmed2](https://github.com/MorningstarJerry/Industry4_practice/blob/main/Esmed2.png)

### Change
![Esmed3](https://github.com/MorningstarJerry/Industry4_practice/blob/main/Esmed3.png)


## 工业4.0
### 工业4.0 涉及的面比较广， 目前 制造业大都在摸索中， 工业复杂性不同于其他消费行业， 有复杂性，多样性本人整理了部分 战略及战术设计文档可以参考
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9AAPP2019.pdf
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9A%E4%BA%92%E8%81%94%E7%BD%915G%E5%BA%94%E7%94%A8.pdf
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9A%E4%BA%92%E8%81%94%E7%BD%91%E4%BC%98%E7%A7%80%E8%BF%90%E7%94%A8%E6%A1%88%E4%BE%8B%E5%88%86%E6%9E%90.pdf
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9A%E4%BA%92%E8%81%94%E7%BD%91%E4%BD%93%E7%B3%BB%E6%9E%B6%E6%9E%841.0.pdf
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9A%E4%BA%92%E8%81%94%E7%BD%91%E4%BD%93%E7%B3%BB%E6%9E%B6%E6%9E%842.0.pdf
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9A%E4%BA%92%E8%81%94%E7%BD%91%E6%99%BA%E8%83%BD%E9%A2%84%E8%AD%A6.pdf
https://github.com/MorningstarJerry/Industry4_practice/blob/main/%E5%B7%A5%E4%B8%9A%E6%95%B0%E6%8D%AE%E9%87%87%E9%9B%86%E4%BA%A7%E4%B8%9A%E7%A0%94%E7%A9%B6%E6%8A%A5%E5%91%8A.pdf




