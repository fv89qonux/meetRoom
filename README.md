## 本项目实现的最终作用是基于SSH会议室管理系统
## 分为2个角色
### 第1个角色为管理员角色，实现了如下功能：
 - 个人资料修改
 - 会议室管理
 - 会议管理
 - 增加会议
 - 增加会议室
 - 用户管理
 - 设备管理
 - 部门管理
### 第2个角色为用户角色，实现了如下功能：
 - 修改个人信息
 - 查看会议室
 - 用户添加会议
## 数据库设计如下：
# 数据库设计文档

**数据库名：** ssh_meetroom

**文档版本：** 


| 表名                  | 说明       |
| :---: | :---: |
| [boardroom](#boardroom) |  |
| [equipment](#equipment) |  |
| [group](#group) |  |
| [log](#log) | 日志表 |
| [mande](#mande) |  |
| [meet](#meet) |  |
| [user](#user) | 用户表 |

**表名：** <a id="boardroom">boardroom</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | boardroomid |   int   | 10 |   0    |    N     |  Y   |       | 主键id  |
|  2   | boardroomtype |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 会议室类型  |
|  3   | boardroomconten |   int   | 10 |   0    |    Y     |  N   |   NULL    | 会议室容纳人数  |
|  4   | state |   int   | 10 |   0    |    Y     |  N   |   NULL    | 状态  |

**表名：** <a id="equipment">equipment</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | equipmentid |   int   | 10 |   0    |    N     |  Y   |       | 设备id  |
|  2   | equipmentname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 设备名  |

**表名：** <a id="group">group</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | groupid |   int   | 10 |   0    |    N     |  Y   |       | 部门id  |
|  2   | groupname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 部门名  |
|  3   | membernumber |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 部门人数  |

**表名：** <a id="log">log</a>

**说明：** 日志表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |       | 自增主键  |
|  2   | log_date |   date   | 10 |   0    |    Y     |  N   |   NULL    |   |
|  3   | log_file |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  4   | log_line |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  5   | log_thread |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  6   | log_level |   varchar   | 255 |   0    |    Y     |  N   |   NULL    |   |
|  7   | log_message |   varchar   | 20000 |   0    |    Y     |  N   |   NULL    |   |

**表名：** <a id="mande">mande</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   int   | 10 |   0    |    N     |  Y   |   0    |   |
|  2   | equipmentid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 设备id  |
|  3   | meetid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 会议id  |

**表名：** <a id="meet">meet</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | meetid |   int   | 10 |   0    |    N     |  Y   |       | 会议id  |
|  2   | meetname |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 会议名  |
|  3   | boardroomid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 会议室id  |
|  4   | oid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 预定人id  |
|  5   | equipmentid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 设备id  |
|  6   | starttime |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 开始时间  |
|  7   | endtime |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 结束时间  |

**表名：** <a id="user">user</a>

**说明：** 用户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | oid |   int   | 10 |   0    |    N     |  Y   |       | 唯一id  |
|  2   | username |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 用户名  |
|  3   | password |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 密码  |
|  4   | repwd |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 确认密码  |
|  5   | age |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 年龄  |
|  6   | sex |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 性别  |
|  7   | phone |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 手机号码  |
|  8   | email |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 邮箱  |
|  9   | role |   varchar   | 255 |   0    |    Y     |  N   |   NULL    | 所属角色  |
|  10   | groupid |   int   | 10 |   0    |    Y     |  N   |   NULL    | 部门id  |

