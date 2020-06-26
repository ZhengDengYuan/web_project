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

    //获取指定竞赛信息，活动详情
    public function get_info_by_id($req){
        //$req->{"competition_id":}
        //必须的
    }

    //获取学生个人竞赛信息
    public function get_info_by_student_id($req){
        //$req->{"student_id":,"year":,"award":,"keyword":} 
        //student_id必须的，其他参数不一定
    }

```

# Dao_Student

## 学生数据界面

```php
    //获取学生竞赛信息
    //学生基础信息和student_base有关，参赛信息和competition有关
    public function get_info($req){
        //$req->{"student_id":,"year":,"keyword":}
        //三个参数都是非必须的

    }



    //获取学生竞赛获奖视图
    public function get_student_view($req){
        //$req->{"student_id":,"year":}
        //两个参数都是必须的
    }






    //获取 指定竞赛的 参赛学生信息
    //待定
    public function get_student_info_by_competition_id($req){
        //$req->{"competition_id":,"student_keyword":}
        //competition_id必须的，student_keyword非必须的
    }
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

    //获取学校的详细信息
    public function get_info_by_id($req){
        //$req->{"school_id":}
        //必须的
    }

    //获取学校的年度竞赛获奖视图
    public function get_school_view($req){
        //$req->{"school_id":,"year":}
        //两个参数是必须的
    }

```

# Dao_Platform 

```php

    //获取平台统计的历年数据
    public function get_info_by_competition_year($req){
        //$req->{"year":}
        //必须的
    }


    //获取平台的年度对比数据
    public function get_comparation_between_year($req){
        //$req->{"first_year":,"second_year":}
        //两个参数是非必须的
    }
```
