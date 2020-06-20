
# RESTful API 接口设计文档

<!-- TOC -->

- [RESTful API 接口设计文档](#restful-api-接口设计文档)
    - [用户接口](#用户接口)
        - [1用户登录界面](#1用户登录界面)
        - [2 管理员退出登录](#2-管理员退出登录)
        - [3.用户修改密码](#3用户修改密码)
    - [竞赛数据模块接口](#竞赛数据模块接口)
        - [4.导入竞赛信息 （导入excel)](#4导入竞赛信息-导入excel)
    - [活动数据详情页](#活动数据详情页)
        - [5.按年份获取竞赛信息](#5按年份获取竞赛信息)
    - [学生数据模块_首页](#学生数据模块_首页)
        - [6.获取学生参赛统计信息](#6获取学生参赛统计信息)
    - [学生数据第一版块-个人数据详情页面](#学生数据第一版块-个人数据详情页面)
        - [7.获取学生个人竞赛信息](#7获取学生个人竞赛信息)
    - [数据统计可视化](#数据统计可视化)
        - [8.获取学生竞赛/获奖视图](#8获取学生竞赛获奖视图)
    - [学校数据接口](#学校数据接口)
        - [9.获取学校参与竞赛的数据](#9获取学校参与竞赛的数据)
    - [平台数据接口](#平台数据接口)
        - [10.获取平台历年数据](#10获取平台历年数据)
        - [11.获取年度对比数据](#11获取年度对比数据)
    - [API 错误码](#api-错误码)

<!-- /TOC -->

## 用户接口

### 1用户登录界面

接口地址：`http://hostname/user/Login/login`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/Login/login/user_name/Maverick/password/123
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   user_name   |   string  |    N      |  用户名       |
|   password    |  string   |    N      |  密码      |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   token          |   string   |   用户登录令牌，用于标识唯一登录者    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response": {
            "code": "20000",
            "messsage": "登陆成功",
            "data": {
                "token":"RVBNIOKJIHIIIJ"
            }
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response": {
            "code": "50001",
            "messsage": "用户名不存在"
        }
    }
    ```

     ```json
    {
        "response": {
            "code": "50002",
            "messsage": "密码错误"
        }
    }
    ```

### 2 管理员退出登录

接口地址：`http://hostname/user/Login/logout`  
支持格式：`json`  
请求方法：*`DELETE`*  
请求示例：

```url
http://hostname/user/Login/logout/token/AJKDJSLN
```

- 请求参数

|  参数名称     |   类型  |    必填   |  说明     |
|   ----       |  :----: |  :----:  |  :----:     |
|   token   |  string   |    y    |  用户登录令牌，用于标识唯一登录者    |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response":{
            "code":"20000",
             "message":"成功退出"
    }
    ```

  - 错误示例：

    ```json
    {
        "response":{
            "code":"50015",
             "message":"管理员退出登录 失败"
    }
    ```

### 3.用户修改密码

接口地址：` http://hostname/user/Login/password `  
支持格式：`json`  
请求方法：*`POST`*  
请求示例：

```url
http://hostname/user/Login/old_pswd/123456/new_password/123123/token/AJKDJSLN
```

- 请求参数

|  参数名称    |   类型    |    必填    |  说明     |
|   ----      |  :----:   |  :----:   |  :----:     |
| old_pswd    |   string  |    y     |  旧密码    |
| new_pswd    |  string   |    y      |  新密码      |
| token       |  string   |    y      | 用户登录令牌，用于标识唯一登录者      |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response":{
            "code":"20000",
            "message":"旧密码正确，新密码修改成功"
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response":{
            "code":"50003",
            "message":"旧密码错误"
        }
    }
    ```

## 竞赛数据模块接口

### 4.导入竞赛信息 （导入excel)

接口地址：`http://hostname/user/competition/excel`  
支持格式：`json`  
请求方法：*`POST`*  
请求示例：

```url
暂无
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   file  |   type  |    y      |  excell文件       |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response":{
            "code":"20000",
             "message":"文件导入成功"
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response":{
            "code":"50004",
            "message":"文件导入失败"
        }
    }
    ```

## 活动数据详情页

<img src="https://s1.ax1x.com/2020/06/19/NumLzd.png" />

### 5.按年份获取竞赛信息 

接口地址：`http://hostname/user/competition/info`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/competition/info
http://hostname/user/competition/info/year/2020
http://hostname/user/competition/info/keyword/机器人
http://hostname/user/competition/info/year/2020/keyword/传媒大奖赛
```

- 请求参数：

|  参数名称   |   类型     |    必填    |  说明     |
|   ----     |  :----:   |  :----:   |  :----:     |
|   year     |   string  |    y      |  活动举办年份    |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   信息相关数组    |
|   name      |   string |   活动名称   |
|   year       |   string |   活动举办年份    |
|   status       |   string |   活动进行状态（结束、进行中、未开始）    |
|   hold_time       |   array  |   活动举办日期（开始时间、结束时间）    |
|   type       |   string |   活动类别（线上比赛、线下比赛）    |
|   event       |   array |   活动项目数组    |
|   num_total       |   int  |   参赛学生总人数    |
|   num_male       |   int  |   男生总人数    |
|   num_female       |   int  |   女生总人数    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
    "response": {
        "code": "20000",
        "message": "活动数据：按年份获取竞赛信息 成功",
        "data": [
            {
                "name": "",
                "year": "",
                "status": "",
                "hold_time": [
                    "",
                    ""
                ],
                "type": "",
                "event": [
                    "俯卧撑",
                    "仰卧起坐"
                ],
                "num_total": 12,
                "num_male": 21,
                "num_female": 2
            },
            {
                "name": "",
                "year": "",
                "status": "",
                "hold_time": [
                    "",
                    ""
                ],
                "type": "",
                "event": [
                    "俯卧撑",
                    "仰卧起坐"
                ],
                "num_total": 12,
                "num_male": 21,
                "num_female": 22
            }
        ]
    }
    }
    ```

  - 错误示例：

    ```json
    {
        "response":{
            "code":"50005",
             "message":"活动数据页面:按年份搜索竞赛信息 失败"
        }
    }
    ```

## 学生数据模块_首页

<img src="https://s1.ax1x.com/2020/06/19/Nul4Ld.png"/>

### 6.获取学生参赛统计信息

接口地址：`http://hostnamem/user/student/info`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/student/info
http://hostname/user/student/info/year/2020
http://hostname/user/student/info/year/2020/keyword/机器人
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   year   |   string  |    n      |  参赛年份       |
|   keyword  |   string  |    n      | 关键字       |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   学生信息相关数组    |
|   name        |   string   |   学生姓名    |
|   id        |   string   |   学号    |
|   sex        |   string   |   性别    |
|   grade        |   string   |   年级    |
|   school        |   string   |   学校    |
|   num_attendance        |   int   |   参赛次数    |
|   num_awards        |   int  |   获奖次数    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response": {
            "code": "20000",
            "message": "学生数据首页:查看所有学生参赛统计信息 成功",
            "data": [
                {
                    "name": "",
                    "id": "",
                    "sex": "",
                    "grade": "",
                    "school": "",
                    "num_attendance": 16,
                    "num_awards": 21
                }
        ]
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response": {
            "code": "50006",
            "message": "学生数据首页:所有学生参赛统计信息 失败",
        }
    }
    ```

## 学生数据第一版块-个人数据详情页面

<img src="https://s1.ax1x.com/2020/06/19/NuNjZF.png"/>

### 7.获取学生个人竞赛信息

接口地址：`http://hostname/user/student/details`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/student/details/id/20001
http://hostname/user/student/details/id/20001/year/2000
http://hostname/user/student/details/id/20001/award/一等奖
http://hostname/user/student/details/id/20001/keyword/机器人
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明           |
|   ----       |  :----:   |  :----:   |  :----:         |
|   id   |   string  |    y      |  学号       |
|   year   |   string  |    n      |  参赛年份       |
|   award   |   string  |    n      |  获奖情况       |
|   keyword   |   string  |    n     | 关键字       |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   信息相关数组    |
|   name       |   string   |   活动明长城    |
|   year        |   string   |   活动举办年份    |
|   status        |   string   |   活动状态（未开始、已开始、已结束）   |
|   type        |   string   |   活动类别（线上比赛、线下比赛……）    |
|   event        |   array   |   活动项目名称+奖项    |

- JSON响应示例：
  - 正确示例：

   ```json
    {
        "response": {
            "code": "20000",
            "message": "学生数据详情：获取学生个人竞赛信息 成功",
            "data": [
                {
                    "name": "",
                    "year": "",
                    "status": "",
                    "hold_time": [
                        "",
                        ""
                    ],
                    "type": "",
                    "event": [
                        [
                            "俯卧撑","一等奖"
                        ],
                        [
                            "俯卧撑","一等奖"
                        ]
                    ]
                },
                {
                    "name": "",
                    "year": "",
                    "status": "",
                    "hold_time": [
                        "",
                        ""
                    ],
                    "type": "",
                    "event": [
                        [
                            "俯卧撑","一等奖"
                        ],
                        [
                            "俯卧撑","一等奖"
                        ]
                    ]
                }
            ]
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response": {
            "code": "50007",
            "message": "学生数据详情：获取学生个人竞赛信息 成功失败",
        }
    }
    ```

## 数据统计可视化

<img src="https://s1.ax1x.com/2020/06/19/NuNjZF.png"/>

### 8.获取学生竞赛/获奖视图

接口地址：`http://hostname/user/student/view`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/student/view/id/201/year/2020
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   id   |   string  |    N      |  学号       |
|   year    |  string   |    N      |  参赛年份      |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   信息相关数组    |
|   num_attendance        |   array  |   某年参赛月次数的数组    |
|   num_awards        |   array |   某年获奖月次数的数组    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response": {
            "code": "20000",
            "message": "学生详情可视化:查看学生个人参赛月数据 成功",
            "data": {
                "num_attendance": [
                    12, 12, 12, 32, 13, 14, 15, 14, 15, 0, 0, 0
                ],
                "num_awards": [
                    12, 24, 154, 214 , 2, 24, 5, 2, 0, 0, 0, 0
                ]
            }
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response": {
            "code": "50009",
            "message": "学生详情可视化:查看学生个人参赛月数据 失败",
        }
    }
    ```

## 学校数据接口

### 9.获取学校参与竞赛的数据

<img src="https://s1.ax1x.com/2020/06/19/Nu2CA1.png"/>

接口地址：`http://hostname/user/school/info`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/school/info
http://hostname/user/school/info/name/中国传媒大学
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   name  |   string  |    N      |  学校名       |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   信息相关数组    |
|  name       |   string   |   学校名称   |
|   num_competition_attend        |   int   |   学校总参赛次数    |
|  num_awards       |   int   |   学校总获奖次数    |
|  num_award_students        |   int   |   学校总个人奖数量    |
|   num_group_awards       |   int  |   学校总团体奖数量    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response": {
            "code": "20000",
            "message": "学校数据页面：获取学校参与竞赛数据成功",
            "data": [
                {
                    "name": "",
                    "num_competition_attend": 21,
                    "num_awards": 55,
                    "num_award_students": 54,
                    "num_indi_awards": 72,
                    "num_group_awards": 15
                },
                {
                    "name": "",
                    "num_competition_attend": 21,
                    "num_awards": 55,
                    "num_award_students": 54,
                    "num_indi_awards": 72,
                    "num_group_awards": 15
                }
            ]
        }
    }
    ```

    - 错误示例：

    ```json
    {
        "response": {
            "code": "50010",
            "message": "学校数据:获取学校参与竞赛数据 失败",
        }
    }
    ```

## 平台数据接口

### 10.获取平台历年数据

<img src="https://s1.ax1x.com/2020/06/19/NuxGF0.png"/>

接口地址：`http://hostname/user/platform/info`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/platform/info/year/2020
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   year   |   string  |    y      |  平台记录的数据的年份       |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   平台信息相关数组    |
|   num_competition        |   int  |   平台总竞赛活动数   |
|   num_students       |   int   |   平台总参赛学生人数   |
|   num_school        |   int    |   平台总参与学校数量    |
|   num_male        |  int   |   平台总男生数    |
|   num_female       |   int   |   平台总女生数    |
|   num_award_male       |  int   |   平台总获奖男生数    |
|   num_award_female        |  int    |   平台总获奖女生数    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response": {
            "code": "20000",
            "message": "平台数据：获取平台历年数据 成功",
            "data": {
                "num_competition": 20,
                "num_students": 22,
                "num_school": 23,
                "num_male": 15,
                "num_female": 25,
                "num_award_male": 46,
                "num_award_female": 54
            }
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response": {
            "code": "50011",
            "message": "平台数据：获取平台历年数据 失败",
        }
    }

### 11.获取年度对比数据

接口地址：`http://hostname/user/platform/compare`  
支持格式：`json`  
请求方法：*`GET`*  
请求示例：

```url
http://hostname/user/platform/compare/year/2020/to/2019
```

- 请求参数：

|  参数名称     |   类型     |    必填    |  说明            |
|   ----       |  :----:   |  :----:   |  :----:          |
|   origin_year  |   string  |    N      |  年份       |
|   reference_year    |  string   |    N      |  被对比年份      |

- 响应内容：

|   参数名称        |   类型      | 说明  |
|   ----           |   :----:   | ----  |
|   coede          |   string   |   返回码    |
|   message        |   string   |   提示信息    |
|   data       |   array  |   信息相关数组    |
|   year      |   string   |   要进行对比的年份    |
|   num_comp       |   int   |   当年总竞赛活动数量    |
|   num_student       |   int   |   当年总参赛学生人数   |
|   num_school       |   int   |   当年总参与学校数量    |

- JSON响应示例：
  - 正确示例：

    ```json
    {
        "response": {
            "code": "20000",
            "message": "平台数据：获取年度对比数据 成功",
            "data": [
                {
                    "year": "",
                    "num_comp": 201,
                    "num_student": 1011,
                    "num_school": 701
                },
                {
                "year": "",
                    "num_comp": 689,
                    "num_student": 520,
                    "num_school": 510
                }
            ]
        }
    }
    ```

  - 错误示例：

    ```json
    {
        "response": {
            "code": "50013",
            "message": "平台数据：获取年度对比数据 失败",
        }
    }
    ```

## API 错误码

|   error_code      |   msg      | 来源接口  |
|   ----           |   :----:   | ----  |
|   50001        |   用户名不存在    |  用户登录    |
|   50002        |   密码错误  |   用户登录   |
|   50003       |    旧密码错误  |   用户修改密码    |
|   50004      |    文件导入失败  |  导入竞赛信息    |
|   50005       |    按年搜活动失败 |    按年份获取竞赛信息    |
|   50006       |     查所有学生参赛统计信息失败  |   获取学生参赛统计信息    |
|   50007       |    查学生个人竞赛信息失败   |   获取学生个人竞赛信息    |
|   50008      |     Illegal token |       |
|   50009        |    学生数据可视化失败   |   获取学生竞赛/获奖视图    |
|   50010      |    获取学校竞赛数据失败  |   获取学校参与竞赛的数据|
|   50011      |    获取平台历年数据失败 |    获取平台历年数据    |
|   50012       |    Other clients logged in  |      |
|   50013       |    获取年度对比数据失败 |   获取平台年度对比数据    |
|   50014       |    Token expired |      |
|   50015      |   管理员退出登录失败|    用户退出登录  |