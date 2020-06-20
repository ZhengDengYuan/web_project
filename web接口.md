
# 用户相关接口

## **1\. 管理员登录 login**

### 名称
> 管理员登录接口

### URL（只是个例子——路径的V1表示第一个版本）
> [http://api.local.com/v1/users/login](http://api.local.com/v1/users/login)


### 请求方式：`get`
### 支持格式:`json`

- ### 请求参数
	|  参数名称     |   类型     |    必填    |  说明     |
	|   ----       |  :----:   |  :----:   |  :----:     |
	|   user_name   |   string  |    N      |  用户名    |
	|   password    |  string   |    N      |  密码      |

- ### 响应内容：

	|   参数名称        |   类型      | 说明  |
	|   ----           |   :----:   | ----  |
	|   coede          |   string   |   返回码    |
	|   message        |   string   |   提示信息    |
	|   token          |   string   |   用户登录令牌，用于标识唯一登录者    |



- ### JSON响应示例：
	- #### 正确示例：
		```json
		{
			"response":{
       			"code":"20000",
				"token":"RVBNIOKJIHIIIJ",
				"message":"登录成功"
			}
		}
		```

	- #### 错误示例:
		```json
		{
			"response":{
				"code":"50001",
				"message":"用户名不存在"
			}
		}
		```

	- #### 错误示例
		```json
		{
			"response":{
				"code":"50002",
				"message":"用户名正确、密码错误"
			}
		}  
		```



## **2\. 管理员退出登录 logout**
### 名称
> 管理员退出登录

###  URL（只是个例子）
>[http://api.local.com/v1/users/logout](http://api.local.com/v1/users/logout)


### 请求方式：`post`
### 支持格式：·json·

- ### 请求参数

	|  参数名称     |   类型   |    必填    |  说明     |
	|   ----       |  :----:  |  :----:   |  :----:     |
	|   token   |   string  |   N    |  用户登录令牌，用于标识唯一登录者  |


- ### 响应内容：

	|   参数名称     |   类型     | 说明  |
	|   ----        |   :----:   | ----  |
	|   coede       |   string   |   返回码    |
	|   message     |   string   |   提示信息    |


- ### JSON响应示例：
	- #### 正确示例：

		```json
		{
			"response":{
			"code":"20000",
			"message":"成功退出"
		}
		```
	- #### 错误示例：
		```json
		{

		}
		```



## **3\. 获取管理员信息get_user_info(忽略,不是重点)**
### 名称
> 获取管理员信息

###  URL（只是个例子）
>[http://api.local.com/v1/users/get_user_info](http://api.local.com/v1/users/get_user_info)


### 支持格式:`json`
### 请求方法：`get`


- ### 请求参数
	|  参数名称 |   类型    |    必填    |  说明     |
	|   ----   |  :----:   |  :----:   |  :----:     |
	|   token  |   string  |    N      |   用户登录令牌，用于标识唯一登录者   |

- ### 响应内容：

	|   参数名称        |   类型      | 说明  |
	|   ----           |   :----:   | ----  |
	|   code            |   string   |  返回码   |
	|   message        |   string   |  提示信息   |



- ### JSON响应示例：
	- #### 正确示例：
		```json
		{
			"response":{
				"code":"20000",
				"message":"获取管理员信息成功"
			}
		}
		```



## **4\. 修改管理员密码change_password**
### 名称
> 修改管理员密码

###  URL（只是个例子）
> [http://api.local.com/v1/users/change_password](http://api.local.com/v1/users/change_password)





### 请求方式：`post`
### 支持格式:`json`

- ### 请求参数
	|  参数名称        |   类型     |    必填    |  说明     |
	|   ----          |  :----:   |  :----:   |  :----:     |
	|   old_password  |   string  |    y     |  旧密码    |
	|   new_password  |  string   |    y      |  新密码      |

- ### 响应内容：

	|   参数名称        |   类型      | 说明  |
	|   ----           |   :----:   | ----  |
	|   coede          |   string   |   返回码    |
	|   message        |   string   |   提示信息    |




- ### JSON响应示例：
	- #### 正确示例：
		```json
		{
			"response":{
				"code":"20000",
				"message":"旧密码正确，新密码修改成功"
			}
		}
		```
	- #### 错误示例：
		```json
		{
			"response":{
				"code":"50003",
				"message":"旧密码错误"
			}
		}
		```






## **5\. 检查账号是否登陆过check_login:(可以不急着做,这是容错的内容)**
### 名称
> 检查是否登录

###  内容略





# ***基础数据管理***

## **6\. 导入竞赛活动信息upload_excel（导入excel)**
### 名称
> 导入竞赛活动信息

###  URL（只是个例子）
>  [http://api.local.com/v1/upload/upload_excel](http://api.local.com/v1/upload/upload_excel)




###  请求方式
> post

### 支持格式
> json

### 请求参数

```
file
```

### 请求方式：`post`
### 支持格式:`json`

- ### 请求参数
	|  参数名称     |   类型     |    必填    |  说明     |
	|   ----       |  :----:   |  :----:   |  :----:     |
	|   file   		| 文件    |    N      |  用户名    |
	

- ### 响应内容：

	|   参数名称        |   类型      | 说明  |
	|   ----           |   :----:   | ----  |
	|   coede          |   string   |   返回码    |
	|   message        |   string   |   提示信息    |




- ### JSON响应示例：
	- #### 正确示例：
		```json
		{
			"response":{
				"code":"20000",
				"message":"文件导入成功"
			}
		}
		```

	- #### 错误示例：
		```json
		{
			"response":{
				"code":"50001",
				"message":"文件导入失败"
			}
		}
		```



# 活动数据详情页

<img src="https://s1.ax1x.com/2020/06/19/NumLzd.png" />

## **7\. 按年份搜索该年全部活动数据search_activities_by_year**
### 名称
> 按年份搜索活动数据

###  URL（只是个例子）
> [http://api.local.com/v1/activities/search_activities_by_year](http://api.local.com/v1/activities/search_activities_by_year)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"year":"2020"
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
        "activities_data":[
            {
                "activity_name":"中学线上运动会",
		        "year":"2020",
	    	    status":"进行中",
		        "held_time":[{
			        "start_time":"2020.06.03",
			        "end_time":"2020.06.03"
		    	}],
		        "activity_type":"线上比赛",
		        "project_content":[
			        "俯卧撑",
			        "仰卧起坐",
			        "引体向上"
			    ],
		        "total_people_num":"130",
	    	    "total_boys_num":"80",
		        "total_girls_num":"50"
            },
            {
                "activity_name":"中学生趣味运动会",
		        "year":"2020",
	    	    status":"进行中",
		        "held_time":[{
						"start_time":"2020.06.05",
						"end_time":"2020.06.05"
		    	}],
		        "activity_type":"线下比赛",
		        "project_content":[
			        "两人三足",
			        "接力运球",
			    	"跳长绳"
				],
		        "total_people_num":"186",
	    	    "total_boys_num":"100",
		        "total_girls_num":"86"
            }
    	],
		"message":"活动数据页面:按年份搜索该年全部活动数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"活动数据页面:按年份搜索该年全部活动数据 失败"
	}
} 
```

### 返回信息说明
```
{
	"activity_name":"活动名称"
	"year":"活动举办年份",
	status":"活动状态（进行中、已结束、未开始）",
	"held_time":
	[
		{
			"开始时间":"2020.06.03",
			"结束时间":"2020.06.03"
		}
	],
	"activity_type":"活动类别（线上比赛、线下比赛）",
	"project_content":"包含项目",
	"total_people_num":"总人数",
	"total_boys_num":"男生人数",
	"total_girls_num":"女生人数"
}
```



## **8\. 按全字段关键字搜索活动search_activities_by_keyword**
### 名称
> 按全字段关键字搜索活动

###  URL（只是个例子）
> [http://api.local.com/v1/activities/search_activities_by_keyword](http://api.local.com/v1/activities/search_activities_by_keyword)



###  请求方式
> post

### 支持格式
> json

### 请求参数
##### （关键字,可以是活动名称,状态,活动类别,比赛项目,举办时间  中任意一个 ）

```
{
	"keyword":"中学线上运动会"
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"activities_data":
		[
            {
                "activity_name":"中学线上运动会",
		        "year":"2020",
	    	    status":"进行中",
		        "held_time":[{
			        "start_time":"2020.06.03",
			        "end_time":"2020.06.03"
		    	}],
		        "activity_type":"线上比赛",
		        "project_content":[
			        "俯卧撑",
			        "仰卧起坐",
			        "引体向上"
			    ],
		        "total_people_num":"130",
	    	    "total_boys_num":"80",
		        "total_girls_num":"50"
            },
            {
                "activity_name":"中学生趣味运动会",
		        "year":"2020",
	    	    status":"进行中",
		        "held_time":[{
						"start_time":"2020.06.05",
						"end_time":"2020.06.05"
		    	}],
		        "activity_type":"线下比赛",
		        "project_content":[
			        "两人三足",
			        "接力运球",
			    	"跳长绳"
				],
		        "total_people_num":"186",
	    	    "total_boys_num":"100",
		        "total_girls_num":"86"
            }
    	],
		"message":"活动数据页面：按关键字搜索活动数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"活动数据页面：按关键字搜索相关信息 失败"
	}
}
```

### 返回信息说明
```
{
	"activity_name":"活动名称"
	"year":"年份",
	status":"活动状态（进行中、已结束、未开始）",
	"held_time":[{
		"开始时间":"2020.06.03",
		"结束时间":"2020.06.03"
	}],
	"activity_type":"活动类别（线上比赛、线下比赛）",
	"project_content":"包含项目",
	"total_people_num":"总人数",
	"total_boys_num":"男生人数",
	"total_girls_num":"女生人数"
}
```





# 学生数据页面_首页
<img src="https://s1.ax1x.com/2020/06/19/Nul4Ld.png"/>



## **9\. 查看所有学生参加比赛数据列表get_students_competitions_data_list**
### 名称
> 查看所有学生参加比赛数据列表

>  (所有学生参赛数据都展示出来、不分页)

###  URL（只是个例子）
> [http://api.local.com/v1/students/get_students_competitions_data_list](http://api.local.com/v1/users/get_student_competition_data_list)



###  请求方式
> get

### 支持格式
> json

### 请求参数
##### （无参数）

```
{
	"offset":""
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"data":
		[
			{
				"student_name":"艾秋富",
				"student_id":"201700001",
				"sex":"男",
				"grade":"大二",
				"school_name":"北京理工大学",
				"total_attendance":"3",
				"total_awards":"3"
			},
			{
				"student_name":"白锦如",
				"student_id":"201700002",
				"sex":"男",
				"grade":"大二",
				"school_name":"北京理工大学",
				"total_attendance":"6",
				"total_awards":"6"
			}
		],
		"message":"学生数据首页：查看所有学生参加比赛数据列表 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"学生数据首页：查看所有学生参加比赛数据列表 失败"
	}
}
```

### 返回信息说明
```
{
	"student_name":"学生姓名",
	"student_id":"学生学号",
	"sex":"学生性别",
	"grade":"学生年级",
	"school_name":"学校",
	"total_attendance":"历年总参加比赛次数"
	"num_awards":"历年总获奖次数"
}
```



## **10\. 按年份 搜索学生参加的活动 统计列表search_students_activities_statisticals_by_years**
### 名称
>  按年份 搜索学生参加的 活动统计列表

###  URL（只是个例子）
> [http://api.local.com/v1/students/search_students_activities_statisticals_by_years](http://api.local.com/v1/students/search_students_activities_statisticals_by_years)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"years":"2020"
}
```


### 正确返回格式

```
{
	"response":{
		"code":"20000",
		"data":
		[
			{
				"student_name":"艾秋富",
				"student_id":"201700001",
				"sex":"男",
				"grade":"大二",
				"school_name":"北京理工大学",
				"annual_total_attendance":"3",
				"annual_total_awards":"3"
			},
			{
				"student_name":"白锦如",
				"student_id":"201700002",
				"sex":"男",
				"grade":"大二",
				"school_name":"北京理工大学",
				"annual_total_attendance":"6",
				"annual_total_awards":"6"
			}
		],
		"message":"学生数据首页：按年份查询学生参加的活动统计列表 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50003",
		"message":"学生数据首页：按年份查询学生参加的活动统计列表 失败"
	}
} 
```

### 返回信息说明
```
	{
		"student_name":"姓名",
		"student_id":"学号",
		"sex":"性别",
		"grade":"年级",
		"school_name":"学校",
		"annual_total_attendance":"年参赛次数",
		"annual_total_awards":"年获奖次数",
	}
		
```






## **11\. 按全字段 搜索全体学生参加的历年累计总活动 信息统计列表search_students_activities_statisticals_by_keyword**
### 名称
>  按全字段 搜索全体学生参加的历年累计总活动 信息统计列表

###  URL（只是个例子）
> [http://api.local.com/v1/students/search_students_activities_statisticals_by_keyword](http://api.local.com/v1/students/search_students_activities_statisticals_by_keyword)



###  请求方式
> post

### 支持格式
> json

### 请求参数
##### （姓名、学号、性别、年级、学校中任意一个）

```
{
	"keyword":"北京理工大学"
}
```


### 正确返回格式

```
{
	"response":{
		"code":"20000",
		"data":
		[
			{
				"student_name":"艾秋富",
				"student_id":"201700001",
				"sex":"男",
				"grade":"大二",
				"school_name":"北京理工大学",
				"total_attendance":"3",
				"total_awards":"3"
			},
			{
				"student_name":"白锦如",
				"student_id":"201700002",
				"sex":"男",
				"grade":"大二",
				"school_name":"北京理工大学",
				"total_attendance":"6",
				"total_awards":"6"
			}
		],
		"message":"学生数据首页：按全字段查询学生参加的活动统计列表 成功"
	}
}
```


### 错误返回格式（关键字不存在）
```
{
	"response":{
		"code":"50003",
		"message":"学生数据首页：按全字段查询学生参加的活动统计列表 失败"
	}
} 
```

### 返回信息说明
```
		
{
	"student_name":"学生姓名",
	"student_id":"学号",
	"sex":"性别",
	"grade":"年级",
	"school_name":"学校",
	"total_attendance":"历年总参赛次数",
	"total_awards":"历年总获奖次数"
}
```







# 学生数据-个人数据详情页面

<img src="https://s1.ax1x.com/2020/06/19/NuNjZF.png"/>

## 学生数据页面第一板块——学生个人数据详情


## **12\. 查看学生个人详情数据search_student_personal_details_by_id**
### 名称
> 查看学生个人详情数据


###  URL（只是个例子）
> [http://api.local.com/v1/students/search_student_personal_details_by_id](http://api.local.com/v1/students/search_student_personal_details_by_id)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"student_id":"201700001"
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"student_name":"艾秋富",
		"student_id":"201700001",
		"sex":"男",
		"grade":"大二",
		"school_name":"北京理工大学",
		"total_attendance":"3"
		"total_awards":"3",
		"individual_awards":"2",
		"group_awards":"1",
		"message":"学生数据个人页：查看学生个人详情数据 成功"
	}
}

```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"学生数据个人页：查看学生个人详情数据 失败"
	}
}
```

### 返回信息说明
```
{
	"response":{
		"student_name":"姓名",
		"student_id":"学号",
		"sex":"性别",
		"grade":"年级",
		"school_name":"学校",
		"total_attendance":"历年总参赛次数"
		"total_awards":"历年总获奖次数",
		"individual_awards":"历年总个人奖数量",
		"group_awards":"历年总团体奖数量"
	}
}
```







# 数据统计可视化

## 学生数据第二板块——数据可视化-个人月参赛获奖折线图

<img src="https://s1.ax1x.com/2020/06/19/NuNjZF.png"/>

## **13\. 查看学生个人  参赛 月 数据search_student_competition_monthly_data**
### 名称
> 查看学生个人  参赛 月  数据


###  URL（只是个例子）
> [http://api.local.com/v1/students/search_students_competitions_monthly_data](http://api.local.com/v1/students/search_students_competitions_monthly_data)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{   
	"student_id":"201700001",
    "year":"2018",
    "keyword":"attendance"
}
```



### 正确返回格式（查看学生参加比赛数据成功）
```
{
	"response":{
		"code":"20000",
		"monthly_attendance":
		[
			"0",
			"0",
			"0",
			"0",
			"3",
			"0",
			"0",
			"0",
			"0",
			"0",
			"0",
			"0"
		],
		"message":"学生数据可视化：查看学生参赛月数据 成功"
	}
}
```


### 错误返回格式（该年份比赛不存在）
```
{
	"response":{
		"code":"50004",
		"message":"学生数据可视化：查看学生参赛月数据 失败"
	}
}
```

### 返回信息说明
```
{
	"monthly_attendance":
	[
		"jan":"一月参赛次数",
		"feb":"二月参赛次数",
		"mar":"三月参赛次数",
		"apr":"四月参赛次数",
		"may":"五月参赛次数",
		"june":"六月参赛次数",
		"jul":"七月参赛次数",
		"aug":"八月参赛次数",
		"sept":"九月参赛次数",
		"oct":"十月参赛次数",
		"nov":"十一月参赛次数",
		"dec":"十二月参赛次数"
	]
}
```





## **14\. 查看学生个人   获奖 月 数据search_student_awards_monthly_data**
### 名称
> 查看学生个人  获奖  月  数据

###  URL（只是个例子）
> [http://api.local.com/v1/students/search_student_awards_monthly_data](http://api.local.com/v1/students/search_student_awards_monthly_data)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"student_id":"201700001",
	"year":"2018",
	"keyword":"awards"
}
```



### 正确返回格式（查看学生参加比赛数据成功）
```
{
	"response":{
		"code":"20000",
		"monthly_awards":
		[
			"0",
			"0",
			"0",
			"0",
			"3",
			"0",
			"0",
			"0",
			"0",
			"0",
			"0",
			"0"
		],
		"message":"学生数据可视化：查看学生个人月获奖数据 成功"
	}
}
```


### 错误返回格式（该年份获奖信息不存在）
```
{
	"response":{
		"code":"50004",
		"message":"学生数据可视化：查看学生个人月获奖数据 失败"
	}
}
```

### 返回信息说明
```
{
	"monthly_awards":
	[{
		"jan":"一月获奖次数",
		"feb":"二月获奖次数",
		"mar":"三月获奖次数",
		"apr":"四月获奖次数",
		"may":"五月获奖次数",
		"june":"六月获奖次数",
		"jul":"七月获奖次数",
		"aug":"八月获奖次数",
		"sept":"九月获奖次数",
		"oct":"十月获奖次数",
		"nov":"十一月获奖次数",
		"dec":"十二月获奖次数"
	}]
}
		
```


## 学生数据页面第三板块——活动详情-列表

<img src="https://s1.ax1x.com/2020/06/19/NuNjZF.png"/>

## **15\. 按比赛年份 搜索学生A该年的活动数据search_student_activities_by_year**
### 名称
> 按比赛年份 搜索学生A该年的学生个人参加活动数据

###  URL（只是个例子）
> [http://api.local.com/v1/students/search_student_activities_by_year](http://api.local.com/v1/students/search_student_activities_by_year)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"student_id":"201700001"
	"year":"2020"
}
```



### 正确返回格式（按年份搜索成功、获奖）
```
{
	"response":{
		"code":"20000",
        "activities":
        [
            {
		        "activity_name":"中学线上运动会",
		        "year":"2020",
		         status":"进行中",
		        "held_time":
                [
                    {
			            "start_time":"2020.06.03",
			            "end_time":"2020.06.03"
			        }
                ],
		        "activity_type":"线上比赛",
		        "project_awards":
                [
                     {
			            "project":"俯卧撑",
			            "awards":"个人三等奖"
			        },
                    {
                        "project":"仰卧起坐",
			            "awards":"男子团体三等奖"
                    },
                    {
                        "project":"引体向上",
			            "awards":"初中团体三等奖"
                    }
                ],
            },
			{
		        "activity_name":"中学趣味运动会",
		        "year":"2020",
		         status":"进行中",
		        "held_time":
                [
                    {
			            "start_time":"2020.06.03",
			            "end_time":"2020.06.03"
			        }
                ],
		        "activity_type":"线下比赛",
		        "project_awards":
                [
                     {
			            "project":"两人三足",
			            "awards":"个人三等奖"
			        },
                    {
                        "project":"接力运球",
			            "awards":"男子团体三等奖"
                    },
                    {
                        "project":"跳长绳",
			            "awards":"初中团体三等奖"
                    }
                ],
            }
        ]
		"message":"学生数据活动详情：按年份搜索活动数据 成功"
	}
}
```


### 错误返回格式（该年份比赛不存在）
```
{
	"response":{
		"code":"50004",
		"message":"学生数据活动详情：按年份搜索活动数据 失败"
	}
}
```

### 返回信息说明
```
{
	"activity_name":"活动名称"
	"year":"活动举办年份",
	status":"活动状态（进行中、已结束、未开始）",
	"held_time":
    [
        {
			"开始时间":"2020.06.03",
			"结束时间":"2020.06.03"
		}
    ],
	"activity_type":"活动类别（线上比赛、线下比赛）",
	"project_awards":
    [
    	{
			"project":"项目1",
			"awards":"项目1获奖"
		},
        {
            "project":"项目2",
			"awards":"项目2获奖"
        }
    ]
}
		
```




## **16\. 按奖项搜索学生参加的活动search_students_activities_by_awards**

### 名称

>  按奖项搜索学生参加的活动


###  URL（只是个例子）
> [http://api.local.com/v1/students/search_student_activities_by_awards](http://api.local.com/v1/students/search_student_activities_by_awards)



###  请求方式
> post

### 支持格式
> json

### 请求参数
##### （一等奖,二等奖,三等奖、）

```
{
    "student_id":"201700001",
	"awards":"三等奖"
}
```



### 正确返回格式（按奖项搜索学生参加的活动成功）
```
{
	"response":{
		"code":"20000",
		"activities":
        [
            {
		        "activity_name":"中学线上运动会",
		        "year":"2020",
		         status":"进行中",
		        "held_time":
                [
                    {
			            "start_time":"2020.06.03",
			            "end_time":"2020.06.03"
			        }
                ],
		        "activity_type":"线上比赛",
		        "project_awards":
                [
                     {
			            "project":"俯卧撑",
			            "awards":"个人三等奖"
			        },
                    {
                        "project":"仰卧起坐",
			            "awards":"男子团体三等奖"
                    },
                    {
                        "project":"引体向上",
			            "awards":"初中团体三等奖"
                    }
                ],
            },
			{
		        "activity_name":"中学趣味运动会",
		        "year":"2020",
		         status":"进行中",
		        "held_time":
                [
                    {
			            "start_time":"2020.06.03",
			            "end_time":"2020.06.03"
			        }
                ],
		        "activity_type":"线下比赛",
		        "project_awards":
                [
                     {
			            "project":"两人三足",
			            "awards":"个人三等奖"
			        },
                    {
                        "project":"接力运球",
			            "awards":"男子团体三等奖"
                    },
                    {
                        "project":"跳长绳",
			            "awards":"初中团体三等奖"
                    }
                ],
            }
        ]
		"message":"学生数据活动详情：按奖项搜索学生参加的活动 成功"
	}
}
```


### 错误返回格式（奖项不存在）
```
{
	"response":{
		"code":"50004",
		"message":"学生数据活动详情：按奖项搜索学生参加的活动 失败"
	}
} 
```

### 返回信息说明
```
{
	"activity_name":"活动名称"
	"year":"活动举办年份",
	status":"活动状态（进行中、已结束、未开始）",
	"held_time":
    [
        {
			"开始时间":"2020.06.03",
			"结束时间":"2020.06.03"
		}
    ],
	"activity_type":"活动类别（线上比赛、线下比赛）",
	"project_awards":
    [
        {
			"project":"项目1",
			"awards":"项目1获奖"
		},
        {
            "project":"项目2",
			"awards":"项目2获奖"
        }
    ]
}
		
```



## **17\. 按全字段关键字搜索该学生参加的活动search_students_activities_by_keyword**
### 名称
> 按全字段关键字搜索该学生参加的活动

###  URL（只是个例子）
> [http://api.local.com/v1/students/search_students_activities_by_keyword](http://api.local.com/v1/students/search_students_activities_by_keyword)



###  请求方式
> post

### 支持格式
> json

### 请求参数
##### （关键字,可以是活动名称,状态,活动类别,比赛项目,获奖情况中任意一个）

```
{
	"keyword":"2018年全国大学联赛"
}
```



### 正确返回格式（按关键字搜索学生参加的活动成功）
```
{
	"response":{
		"code":"20000",
		"activities":
        [
            {
		        "activity_name":"中学线上运动会",
		        "year":"2020",
		         status":"进行中",
		        "held_time":
                [
                    {
			            "start_time":"2020.06.03",
			            "end_time":"2020.06.03"
			        }
                ],
		        "activity_type":"线上比赛",
		        "project_awards":
                [
                     {
			            "project":"俯卧撑",
			            "awards":"个人三等奖"
			        },
                    {
                        "project":"仰卧起坐",
			            "awards":"男子团体三等奖"
                    },
                    {
                        "project":"引体向上",
			            "awards":"初中团体三等奖"
                    }
                ],
            },
			{
		        "activity_name":"中学趣味运动会",
		        "year":"2020",
		         status":"进行中",
		        "held_time":
                [
                    {
			            "start_time":"2020.06.03",
			            "end_time":"2020.06.03"
			        }
                ],
		        "activity_type":"线下比赛",
		        "project_awards":
                [
                     {
			            "project":"两人三足",
			            "awards":"个人三等奖"
			        },
                    {
                        "project":"接力运球",
			            "awards":"男子团体三等奖"
                    },
                    {
                        "project":"跳长绳",
			            "awards":"初中团体三等奖"
                    }
                ],
            }
        ]
		"message":"学生数据活动详情：按关键字搜索学生参加的活动 成功"
	}
}
```


### 错误返回格式（关键字对应信息不存在）
```
{
	"response":{
		"code":"50004",
		"message":"学生数据活动详情：按关键字搜索学生参加的活动 成功"
	}
}
```

### 返回信息说明
```
{
	"activity_name":"活动名称",
	"held_time":"年份、举办时间",
	"status":"活动状态（进行中、已结束、未开始）",
	"activity_type":活动类别"",
	"project_awards":"比赛项目、获奖情况"
}
		
```






# 学校数据

<img src="https://s1.ax1x.com/2020/06/19/Nu2CA1.png"/>



## **18\. 查看 所有学校 历年累计比赛数据统计 get_schools_competition_data_list**
### 名称
>查看 所有学校 比赛数据统计

###  URL（只是个例子）
> [http://api.local.com/v1/schools/get_schools_competition_data_list](http://api.local.com/v1/schools/get_schools_competition_data_list)



###  请求方式
> get

### 支持格式
> json

### 请求参数
##### （无参数）
```
{
	"offset":""
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"data":
        [
			{
			    "school_name":"北京理工大学",
			    "school_total_attendance":"10",
			    "school_total_awards":"9",
			    "school_total_awards_student":"7",
			    "school_total_individual_awards":"5",
			    "school_total_group_awards":"4",
			},
			{
			    "school_name":"中国传媒大学",
			    "school_total_attendance":"15",
			    "school_total_awards":"14",
			    "school_total_awards_student":"10",
			    "school_total_individual_awards":"8",
			    "school_total_group_awards":"6",
			}
		],
		"message":"学校数据首页：查看所有学校历年累计总体比赛数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"学校数据首页：查看所有学校历年累计总体比赛数据 失败"
	}
}
```

### 返回信息说明
```
{
	"school_name":"学校名称",
	"school_total_attendance":"学校历年累计总参赛次数",
	"school_total_awards":"学校历年累计总获奖次数",
	"school_total_awards_student":"学校历年累计总个人获奖学生数量",
	"school_total_individual_awards":"学校历年累计总个人奖数量",
	"school_total_group_awards":"学校历年累计总团体奖数量"
}
		
```




## **19\. 查看单个学校总体 比赛数据get_school_competition_data**

## 名称
> 单个学校 总体比赛数据

###  URL（只是个例子）
> [http://api.local.com/v1/users/search_school_annual_competition_data](http://api.local.com/v1/users/search_school_annual_competition_data)


#### 请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"school_name":"北京理工大学"
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"school_name":"北京理工大学",
		"school_total_attendance":"10",
		"school_total_awards":"9",
		"school_total_awards_students":"7",
		"school_total_individual_awards":"5",
		"school_total_group_awards":"4",
		"message":"学校数据：查看单个学校总体比赛数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"学校数据：查看单个学校总体比赛数据 失败"
	}
}
```

### 返回信息说明
```
{
	"school_name":"学校名称",
	"school_total_attendance":"学校历年累计总参赛次数",
	"school_total_awards":"学校历年累计总获奖次数",
	"school_total_awards_students":"学校历年累计总获奖学生人数",
	"school_total_individual_awards:"学校历年累计总个人奖数量",
	"school_total_group_awards":"学校历年累计总团体奖数量"
}

		
```



## **20\. 查看 单个学校 年度总体 比赛数据get_school_annual_competition_data**

## 名称
> 单个学校 年度总体比赛数据

###  URL（只是个例子）
> [http://api.local.com/v1/users/search_school_annual_competition_data](http://api.local.com/v1/users/search_school_annual_competition_data)


#### 请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"school_name":"北京理工大学",
	"year":"2018"
}
```



### 正确返回格式（ 查看学校 每年 比赛数据成功）
```
{
	"response":{
		"code":"20000",
		"school_name":"北京理工大学",
		"school_annual_attendance":"10",
		"school_annual_awards":"9",
		"school_annual_awards_student":"7",
		"school_annual_individual_awards":"5",
		"school_annual_group_awards":"4",
		"message":"学校数据首页:查看单个学校年度总体比赛数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"学校数据首页:查看单个学校年度总体比赛数据 失败"
	}
}
```

### 返回信息说明
```
{
	"school_name":"学校名称",
	"school_annual_attendance":"学校年度参赛次数",
	"school_annual_awards":"学校年度获奖次数",
	"school_annual_awards_student":"学校年度获奖学生人数",
	"school_annual_individual_awards":"学校年度个人奖数量",
	"school_annual_group_awards":"学校年度团体奖数量"
}
		
```


# 平台数据— — — —第一版块

<img src="https://s1.ax1x.com/2020/06/19/NuxGF0.png"/>



## **21\. 查看 平台历年汇总数据get_platform_total_data**
### 名称

>  查看 平台 历年汇总数据

###  URL（只是个例子）
> [http://api.local.com/v1/users/get_platform_total_data](http://api.local.com/v1/users/get_platform_total_data)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"keyword":"platform"
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"platform_total_competition_num":"10",
		"platform_total_student_num":"56",
		"platform_total_school_num":"9",
		"platform_total_boys_num":"30",
		"platform_total_girls_num":"26",
		"platform_total_awards_boys_num":"28",
		"platform_total_awards_girls_num":"25",
		"message":"平台数据：查看平台历年汇总数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"平台数据：查看平台历年汇总数据 失败"
	}
}
```

### 返回信息说明
```
{
	"platform_total_competition_num":"平台历年总竞赛活动数量",
	"platform_total_student_num":"平台历年总参赛学生人数",
	"platform_total_school_num":"平台历年总参赛学校数量",
	"platform_total_boys_num":"平台历年总参赛男生数量",
	"platform_total_girls_num":"平台历年总参赛女生数量",
	"platform_total_awards_boys_num":"平台历年总获奖男生数量",
	"platform_total_awards_girls_num":"平台历年总获奖女生数量"
}
		
```



## **22\. 查看 平台 年度数据get_platform_annual_data**
### 名称

>  查看 平台 年度数据

###  URL（只是个例子）
> [http://api.local.com/v1/users/get_platform_annual_data](http://api.local.com/v1/users/get_platform_annual_data)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"year":"2018"
}
```



### 正确返回格式（ 查看 平台 年度比赛项目数据成功）
```
{
	"response":{
		"code":"20000",
		"platform_annual_competition_num":"10",
		"platform_annual_student_num":"56",
		"platform_annual_school_num":"9",
		"platform_annual_boys_num":"30",
		"platform_annual_girls_num":"26",
		"platform_annual_awards_boys_num":"28",
		"platform_annual_awards_girls_num":"25",
		"message":"平台数据：查看平台年度数据 成功"
	}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"平台数据：查看平台年度数据 失败"
	}
}
```

### 返回信息说明
```
		"platform_annual_competition_num":"平台年度竞赛活动数量",
		"platform_annual_student_num":"平台年度参赛学生人数",
		"platform_annual_school_num":"平台年度参赛学校数量",
		"platform_annual_boys_num":"平台年度参赛男生数量",
		"platform_annual_girls_num":"平台年度参赛女生数量",
		"platform_annual_awards_boys_num":"平台年度获奖男生数量",
		"platform_annual_awards_girls_num":"平台年度获奖女生数量"
```



## **23\. 查看 平台 两个年度   数据对比search_platform_data_between_years**
<img src="https://s1.ax1x.com/2020/06/19/NKpkw9.png">

## 名称


>  查看 平台 两个年度数据对比
>  (功能简化了,只展示2020年以及2019年的活动项目数、参赛人数和学校数。)

###  URL（只是个例子）
> [http://api.local.com/v1/platform/search_platform_data_between_years](http://api.local.com/v1/platform/search_platform_data_between_years)



###  请求方式
> post

### 支持格式
> json

### 请求参数

```
{
	"origin_year":"2020",
	"refernce_year":"2019"
}
```



### 正确返回格式
```
{
	"response":{
		"code":"20000",
		"comparison_between_years":
        [
			{
			    "origin_year_activities_num":"50",
			    "origin_year_people_num":"120",
			    "origin_year_schools_num":"6",
			},
			{
			    "reference_year_activities_num":"48",
			    "reference_year_people_num":"100",
			    "reference_year_schools_num":"4",
			}
		],
		"message":"平台数据对比:查看平台年度对比数据 成功"
		}
}
```


### 错误返回格式
```
{
	"response":{
		"code":"50004",
		"message":"平台数据对比:查看平台年度对比数据 失败"
	}
}
```

### 返回信息说明
```
{
	"comparison_between_years":
    [
		{
			"origin_year_activities_num":"平台第一年活动数量",
			"origin_year_people_num":"平台第一年参赛人数",
			"origin_year_schools_num":"平台第一年参赛学校数量",
		},
		{
			"reference_year_activities_num":"平台参考年活动数量",
			"reference_year_people_num":"平台参考参赛人数",
			"reference_year_schools_num":"平台参考年参赛学校人数",
		}
	]
}
```













