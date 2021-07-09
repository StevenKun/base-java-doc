# 人员模块需求分析与设计

[TOC]



## 第一章  需求分析

1. ### 人员管理功能需求分析

   - 查看人员列表
   - 支受援管理
   - 操作设备分配
   - 人员履历(包括培训经历,证书)

   



## 第二章  概要设计

1. ### 功能结构设计

   

   

2. ### 数据库建模

   2.1 人员管理

   2.1.1 人员管理数据库逻辑设计

   ​	

   2.1.2  人员管理数据库表结构设计

   MES_User表

   | 列名       | 类型         | 主键 | 可空     | 自增 | 默认值 | 说明                                 |
   | ---------- | ------------ | ---- | -------- | ---- | ------ | ------------------------------------ |
   | Id         | int          | 是   |          | 是   |        | id                                   |
   | Company    | nvarchar(30) |      |          |      |        | 公司                                 |
   | Department | nvarchar(30) |      |          |      |        | 部门                                 |
   | UserCode   | nvarchar(10) |      |          |      |        | 员工编号                             |
   | Duty       | nvarchar(50) |      |          |      |        | 职责                                 |
   | Status     | nvarchar(30) |      |          |      |        | 员工状态1.休息 2.工作 3.请假 4. 加班 |
   | Class      | nvarchar(20) |      |          |      |        | 班次                                 |
   | IsSupport  | int          |      | not null |      |        | 1.支援  2.受援  3.正常               |
   | Superior   | nvarchar(20) |      |          |      |        | 直接上级                             |
   |            |              |      |          |      |        |                                      |
   |            |              |      |          |      |        |                                      |
   | isRest     | int          |      |          |      |        | 是否休息:0.工作 1.休息               |
   | shifts     |              |      |          |      |        | 班制                                 |
   | isupdate   | int          |      |          |      |        | 是否更新过:0.未更新 1.更新过         |
   | updateUser | nvarchar     |      |          |      |        | 修改人                               |
   | createUser | nvarchar     |      |          |      |        | 添加人                               |
   | createDate | Date         |      |          |      |        | 创建时间                             |
   | updateDate | Date         |      |          |      |        | 更新时间                             |

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
   | createDate | Date     |      |      |      |        | 创建时间             |
   | updateUser | nvarchar |      |      |      |        | 修改人               |
   | updateDate | Date     |      |      |      |        | 更新时间             |

   

   2.2 资源日历

   2.2.1 设备日历数据库逻辑设计

   ​	

   2.2.2 设备日历数据库表结构设计

   MES_表

   | 列名                  | 类型     | 主键 | 可空 | 自增 | 默认值 | 说明                              |
   | --------------------- | -------- | ---- | ---- | ---- | ------ | --------------------------------- |
   | EquipmentCalenderGuid | varchar  | 是   |      |      |        | 主键id                            |
   | Company               | nvarchar |      |      |      |        | 公司                              |
   | Department            | nvarchar |      |      |      |        | 部门                              |
   | Holon                 | int      |      |      |      |        | holon                             |
   | EquipmentCode         | nvarchar |      |      |      |        | 设备号                            |
   | EquipmentName         | nvarchar |      |      |      |        | 设备名                            |
   | StartTime             | date     |      |      |      |        | 开始时间                          |
   | EndTime               | date     |      |      |      |        | 结束时间                          |
   | State                 | int      |      |      |      | 0      | 设备状态:0.正常1.停用2.维护3.弃用 |
   | Reason                | nvarchar |      |      |      |        | 原因                              |
   | CreateUser            | nvarchar |      |      |      |        | 创建时间                          |
   | CreateDate            | date     |      |      |      |        | 创建日期                          |
   | UpdateUser            | nvarchar |      |      |      |        | 更新人                            |
   | UpdateDate            | date     |      |      |      |        | 更新时间                          |

   

   

   

## 第三章  详细设计与实现

​	