# 接口：getGardes  [返回](../README.md)
用例： [成绩列表](../用例/成绩列表.md)

- 权限：
    - 老师：可以看到老师自己教授课程的成绩列表信息。
    - 学生：可以看到自己上的课程信息的成绩列表信息。

- 功能：查看成绩信息。

- API请求地址：
   - 1.老师接口基本地址/v1/api/getGardes?teacher_id=?
   - 2.学生接口基本地址/v1/api/getStudents?student_id=?

- 请求方式 ：GET

- 请求参数说明:老师和学生需要请求参数

  |参数名称|说明|
  |:--:|:--:|
  |teacher_id|老师的工号|
  |student_id|学生的学号|

- 返回实例：
    - 学生和老师返回参数实例（返回内容一致，total不一样）
    <pre>
        {
            "status": true,
            "info": null,
            "total": 120,
            "data": [
                {
                "student_id": "20151041427",
                "name": "张启恒",
                "course_name":"信息系统分析与设计",
                "result_sum": "90.90,90,90,90,N",
                "github_username": "zhangqiheng",
                "class": "软件(本)15-4"
                {
                ...其他成绩
                }
            ]
        }

    </pre>

- 返回参数说明：

  |参数名称|说明|
  |:--|:--|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回成绩个数|
  |data|所有成绩的数组|
  |student_id|学号|
  |name|学生姓名|
  |course_name|课程名|
  |result_sum|成绩汇总|
  |github_username|GItHub账号|
  |class|班级|
