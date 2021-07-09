# 日历模块需求分析与设计

[TOC]



## 第一章  需求分析

1. ### 工厂日历功能需求分析

   - 修改HOLON日历休息日及班制
   - 修改部门日历及班制
   - 批量修改部门班制
   - 班制维护
   - 查看部门日历或者某个HOLON日历

2. ### 资源日历功能需求分析

   - 查看HOLON设备状态总况

   - 设备日历里添加设备日历计划

     

   

## 第二章  概要设计

1. ### 功能结构设计

   ![1590020365621](C:\Users\smc7050u01\AppData\Roaming\Typora\typora-user-images\1590020365621.png)

   

2. ### 数据库建模

   2.1 工厂日历

   2.1.1 工厂日历数据库逻辑设计

   ​	

   2.1.2  工厂日历数据库表结构设计

   MES_Calendar表

   | 列名        | 类型     | 主键 | 可空 | 自增 | 默认值 | 说明                         |
   | ----------- | -------- | ---- | ---- | ---- | ------ | ---------------------------- |
   | guid        | varchar  | 是   |      |      |        | id                           |
   | company     | nvarchar |      |      |      |        | 公司                         |
   | department  | nvarchar |      |      |      |        | 部门                         |
   | class       | nvarchar |      |      |      |        | 科                           |
   | holon       | int      |      |      |      |        | holon                        |
   | year        |          |      |      |      |        | 年                           |
   | month       |          |      |      |      |        | 月                           |
   | day         |          |      |      |      |        | 日                           |
   | week        |          |      |      |      |        | 星期                         |
   | holiday     | nvarchar |      |      |      |        | 节日                         |
   | calendar_zh | nvarchar |      |      |      |        | 农历                         |
   | isRest      | int      |      |      |      |        | 是否休息:0.工作 1.休息       |
   | shifts      |          |      |      |      |        | 班制                         |
   | isupdate    | int      |      |      |      |        | 是否更新过:0.未更新 1.更新过 |
   | updateUser  | nvarchar |      |      |      |        | 修改人                       |
   | createUser  | nvarchar |      |      |      |        | 添加人                       |
   | createDate  | Date     |      |      |      |        | 创建时间                     |
   | updateDate  | Date     |      |      |      |        | 更新时间                     |

   MES_shifts表

   | 列名       | 类型     | 主键 | 可空 | 自增 | 默认值 | 说明                 |
   | ---------- | -------- | ---- | ---- | ---- | ------ | -------------------- |
   | shiftsGuid | nvarchar | 是   |      |      |        | 班制id               |
   | shiftsCode | nvarchar |      |      |      |        | 班制代码             |
   | shiftsName | nvarchar |      |      |      |        | 班制名称             |
   | startTime  | date     |      |      |      |        | 开始时间             |
   | endTime    | date     |      |      |      |        | 结束时间             |
   | isCross    | int      |      |      |      |        | 是否跨日:  0.否 1.是 |
   | createUser | nvarchar |      |      |      |        | 添加人               |
   | createTime | DateTime |      |      |      |        | 创建时间             |
   | updateUser | nvarchar |      |      |      |        | 修改人               |
   | updateTime | Datetime |      |      |      |        | 更新时间             |

   

   2.2 资源日历

   2.2.1 设备日历数据库逻辑设计

   2.2.2 设备日历数据库表结构设计

   MES_EquipmentCalender表

   | 列名                  | 类型     | 主键 | 可空 | 自增 | 默认值 | 说明                              |
   | --------------------- | -------- | ---- | ---- | ---- | ------ | --------------------------------- |
   | equipmentCalenderGuid | varchar  | 是   |      |      |        | 主键id                            |
   | company               | nvarchar |      |      |      |        | 公司                              |
   | department            | nvarchar |      |      |      |        | 部门                              |
   | holon                 | int      |      |      |      |        | holon                             |
   | equipmentCode         | nvarchar |      |      |      |        | 设备号                            |
   | equipmentName         | nvarchar |      |      |      |        | 设备名                            |
   | startTime             | date     |      |      |      |        | 开始时间                          |
   | endTime               | date     |      |      |      |        | 结束时间                          |
   | state                 | int      |      |      |      | 0      | 设备状态:0.正常1.停用2.维护3.弃用 |
   | reason                | nvarchar |      |      |      |        | 原因                              |
   | createUser            |          |      |      |      |        | 创建时间                          |
   | createDate            |          |      |      |      |        | 创建日期                          |
   | updateUser            |          |      |      |      |        | 更新人                            |
   | updateDate            |          |      |      |      |        | 更新时间                          |

   

## 第三章  详细设计与实现

​	