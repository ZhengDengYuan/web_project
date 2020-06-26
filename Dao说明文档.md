# Dao_User

## 用户登录界面

```php  

    /** 用户登录
    * @param  String  $username  用户名
    * @param  String  $pswd  密码
    * @return  返回ture或false
    */
    public function login($req){
        //$req->{"user_name":,"password":}
        //两个参数都是必须的
        //数据库工作：用户名密码匹配
    }

    /*
    数据库返回值包含字段:
    |  列名        |  数据类型  | 允许空 |主键   |  说明         |
    |   ----       |  :----:   | :----:|:----: | :----:        |
    |   user_name  |  string   |   否  | key   |管理员用户名   |
    |   password   |  string   |       |       |密码           |
    */

    //用户退出登录     待定

    // 根据用户名修改用户密码  
    // 返回ture|false
    public function update_password($req){
        //$req->{"user_name":,"password":}
        //两个参数都是必须的
    }

```

# Dao_Competition

## 活动竞赛界面

```php
    //按年份获取竞赛信息
    public function get_info_by_year($req){
        //$req->{"year":,"keyword":}
        //两个参数都是非必须的
    }

    /*
    数据库返回值包含字段:
|  列名            | 数据类型|允许空 |主键   |  说明   |
|   ----          |:----:   |:----: |:----:| :----:        |
|competition_id   | string  | 否    |  key |竞赛活动ID   |
|competition_name |  string | 否    |      |竞赛活动名称 |
|   year          |  string | 否    |      |活动举办年度|
| organizer       |  string |       |       |活动主办方 |
|hold_time        |  array  |      |    |[开始时间、结束时间]|
|status         |string |||活动进行状态（未开始、进行中、已结束|
|type         |  string  ||     |活动类别（线上、线下）      |
|event       |  array|||活动包含项目数组["铅球"、"跑步"……]  |
|description      |string  |      |    |活动描述       |
|num_total        |  int  |      |     |总参赛学生人数      |
|num_award        |  int  |      |     |总获奖学生人数       |
|num_male         |  int  |      |     |总参赛男生人数       |
|num_female       |  int  |      |     |总参赛女生人数      |
    */

    //获取指定竞赛信息，活动详情
    public function get_info_by_id($req){
        //$req->{"competition_id":}
        //必须的
    }
    /*
    数据库返回值包含字段:
|  列名            | 数据类型|允许空 |主键   |  说明   |
|   ----          |:----:   |:----: |:----:| :----:        |
|competition_id   | string  | 否    |  key |竞赛活动ID   |
|competition_name |  string | 否    |      |竞赛活动名称 |
|   year          |  string | 否    |      |活动举办年度|
| organizer       |  string |       |       |活动主办方 |
|hold_time        |  array  |      |    |[开始时间、结束时间]|
|status         |string |||活动进行状态（未开始、进行中、已结束|
|type         |  string  ||     |活动类别（线上、线下）      |
|event       |  array|||活动包含项目数组["铅球"、"跑步"……]  |
|description      |string  |      |    |活动描述       |
|num_total        |  int  |      |     |总参赛学生人数      |
|num_award        |  int  |      |     |总获奖学生人数       |
|num_male         |  int  |      |     |总参赛男生人数       |
|num_female       |  int  |      |     |总参赛女生人数      |
    */
```

# Dao_Student

## 学生数据界面

```php
    //获取学生竞赛信息
    //学生基础信息和student_base有关，参赛信息和competition有关
    public function get_info($req){
        //$req->{"student_id":,"year":,"keyword":}
        //三个参数都是非必须的

        /*
        数据库返回值包含字段:
|  列名            | 数据类型|允许空 |主键   |  说明   |
|   ----          |:----:   |:----: |:----:| :----:        |
|student_id       | string |   否 | key  | 学号 |
|student_name     | string |   否 |      | 姓名 |
|   sex           |  string|      |     |性别，男1、女0     |
| grade           |  string|      |     |年级，大二42、高二32 |
|school           |  string|      |      |学校名称       |

|year             | string |  否  |      | 学生的参赛年份     |
|num_attendance   | int    |      |      |该年参赛次数   |
|num_awards       | int    |      |      |该年获奖次数   |
|num_indi_awards  | int    |      |      |该年个人奖数量 |
|num_group_awards |  int   |      |      |该年团体奖数量 |
|attendance_detail|  array |      |      | 该年的参赛数组信息 |
|monthly_attendance | array|      |      | 月参赛次数数组[1,0,1……]|
|monthly_award      | array|      |      | 月获奖次数数组[1,0,1……]|

|attendance_detail内部|数据类型 |允许空 |主键  |  说明       |
|   ----          |  :----:|:----:|:----:| :----:        |
|competion_id     |  string |      |     | 参加的活动id  |
|event            |  array| | | 项目+奖项数组[["两人三足","团体一等奖"] ,["铅球"，"三等奖"]]|
         */
    }

    //获取学生个人竞赛信息
    public function get_info_by_student_id($req){
        //$req->{"student_id":,"year":,"award":,"keyword":} 
        //student_id必须的，其他参数不一定
    }

    //获取学生竞赛获奖视图
    public function get_student_view($req){
        //$req->{"student_id":,"year":}
        //两个参数都是必须的
    }

    /*
    数据库返回值包含字段:
|  列名            | 数据类型|允许空 |主键   |  说明   |
|   ----          |:----:   |:----: |:----:| :----:        |
|student_id       | string |   否 | key  | 学号 |
|year             | string |  否  |      | 学生的参赛年份     |
|monthly_attendance | array|      |      | 月参赛次数数组[1,0,1……]|
|monthly_award      | array|      |      | 月获奖次数数组[1,0,1……]|
    */






    //获取 指定竞赛的 参赛学生信息
    //待定
    public function get_student_info_by_competition_id($req){
        //$req->{"competition_id":,"student_keyword":}
        //competition_id必须的，student_keyword非必须的
    }
    /*
|  列名            | 数据类型|允许空 |主键   |  说明   |
|   ----          |:----:   |:----: |:----:| :----:        |
|student_id       | string |   否 | key  | 学号 |
|student_name     | string |   否 |      | 姓名 |
|   sex           |  string|      |     |性别，男1、女0     |
| grade           |  string|      |     |年级，大二42、高二32 |
|school           |  string|      |      |学校名称       |
|attendance_detail|  array |      |      | 该年的参赛数组信息 |

|attendance_detail内部|数据类型 |允许空 |主键  |  说明       |
|   ----          |  :----:|:----:|:----:| :----:        |
|competion_id     |  string |      |     | 参加的活动id  |
|event            |  array| | | 项目+奖项数组[["两人三足","团体一等奖"] ,["铅球"，"三等奖"]]|

    */
```

# Dao_School

```php

    //获取学校参与竞赛的数据
    /*
    获取学校的参赛数据，键是id但是接口里面用的参数是学校名。是改接口文档还是以校名为键值
    */
    public function get_info_by_name($req){
        //$req->{"school_name":}
        //非必须
    }

    /*
|  列名              | 数据类型 |允许空 |主键  |  说明         |
|   ----            |  :----:  |:----:|:----:| :----:        |
|school_name        |   string | 是 | |校名（冗余，方便插入数据时对照） |
|school_id          |  string  | 否 | key|学校id|
|year               |   string | 否 |    |学校参赛年度 |
|num_attendance        | int   | |    |学校年参赛次数|
|num_awards            | int   | |      |学校年获奖次数 |
|num_indi_awards       | int   | |      |学校年个人奖数量|
|num_group_awards      | int   | |      |学校年团体奖数量 |
|num_attendance_student| int   | |      |学校年总参赛人数|
|num_award_student     | int   | |      |学校年总获奖人数|
|num_male              | int   | |      |学校年参赛男生人数|
|num_female            |   int | |       |学校年参赛女生人数|
|monthly_attendance    | array | |   | 月参赛次数数组[1,0,1……]|
|monthly_award         |array  | |   |月获奖次数数组[1,0,1……]|

    */

    //获取学校的详细信息
    public function get_info_by_id($req){
        //$req->{"school_id":}
        //必须的
    }

    /*
|  列名              | 数据类型 |允许空 |主键  |  说明         |
|   ----            |  :----:  |:----:|:----:| :----:        |
|school_name        |   string |   否 |      |校名 |
|school_id          |  string  |   否 | key  |学校id|
| address           |  string  |      |      |学校地址    |
|school_introduction|  string  |      |      |学校简介 |
|region             |  string |       ||学校所属地区（朝阳区）|
|num_attendance_student| int   | |      |学校年总参赛人数|
|num_award_student     | int   | |      |学校年总获奖人数|
|num_male              | int   | |      |学校年参赛男生人数|
|num_female            |   int | |       |学校年参赛女生人数|
    */

    //获取学校的年度竞赛获奖视图
    public function get_school_view($req){
        //$req->{"school_id":,"year":}
        //两个参数是必须的
    }

    /*
|  列名              | 数据类型 |允许空 |主键  |  说明         |
|   ----            |  :----:  |:----:|:----:| :----:        |
|school_name        |   string |   否 |      |校名 |
|school_id          |  string  |   否 | key  |学校id|
|year               |   string | 否 |    |学校参赛年度 |
|monthly_attendance    | array | |   | 月参赛次数数组[1,0,1……]|
|monthly_award         |array  | |   |月获奖次数数组[1,0,1……]|
    */
```

# Dao_Platform 

```php

    //获取平台统计的历年数据
    public function get_info_by_competition_year($req){
        //$req->{"year":}
        //必须的
    }

    /*
|  列名         |数据类型|允许空 |主键  |  说明         |
|   ----        |:----: |:----:|:----:| :----:        |
|year           |string |   否 | key  |平台数据年份|
|num_competition|int    |      |      |平台合计比赛数量|
|num_students   |int    |      |      |平台合计参赛学生人数|
|num_school     | int   |      |      |平台合计参赛学校数量|
|num_male       | int   |      |      |平台合计参赛男生人数|
|num_female     |   int |      |      |平台合计参赛女生人数|
|num_award_male  |int   |      |      |平台合计获奖男生人数|
|num_award_female| int  |      |      |平台合计获奖女生人数|
    */

    //获取平台的年度对比数据
    public function get_comparation_between_year($req){
        //$req->{"first_year":,"second_year":}
        //两个参数是非必须的
    }
    
```
