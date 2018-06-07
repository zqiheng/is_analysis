# 接口：getStudents  [返回](../README.md)
用例： [学生列表](../用例/学生列表.md) ，[学生排课](../用例/学生排课.md)

- 权限：
    - 管理员：不能看到试验列表和成绩列表，没有成绩评定操作
    - 老师：可以看到RESULT_SUM，WEB_SUM，有成绩评定操作。

- 功能：返回所有学生的列表。

- API请求地址：
   - 1.管理员接口基本地址/v1/api/getStudents
   - 2.老师接口基本地址/v1/api/getStudents=?

- 请求方式 ：GET

- 请求参数说明:管理员不需要请求参数，老师查询学生列表需要请求参数

  |参数名称|说明|
  |:--:|:--:|
  |id|老师的ID号。对应表Users.user_id的值|

- 返回实例：

        {
            "status": true,
            "info": null,
            "total": 120,
            "data": [
                {
                ...其他学生
                },
                {"web_sum": "Y,Y,Y,Y,Y,N",
                "result_sum": "90.90,90,90,90,N",
                "github_username": "zhangqiheng",
                "student_id": "20151041427",
                "class": "软件(本)15-4",
                "name": "张启恒",
                "update_date": "2018-04-10 13:48:01"},
                {
                ...其他学生
                }
            ]
        }

- 返回参数说明：

  |参数名称|说明|
  |:--|:--|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回学生人数|
  |data|所有学生的数组|
  |web_sum|网址是否正确的汇总|
  |result_sum|成绩的汇总|
  |github_username|GITHUB 用户名|
  |student_id|学号|
  |class|班级|
  |name|真实姓名|
  |update_date|GitHUB用户名修改日期|