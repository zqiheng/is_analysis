# 接口：getCourses  [返回](../README.md)
用例： [课程列表](../用例/课程列表.md)  [老师排课](../用例/老师排课.md)

- 权限：
    - 管理员：可以看到所有表(Courses)信息，增删改操作(暂未写)
    - 老师：可以看到老师自己教授课程列表信息(ArrangeInfo)。
    - 学生：可以看到自己上的课程信息（CourseInfo）以及授课老师信息(Teachers)。

- 功能：查看课程列表信息。

- API请求地址：
   - 1.管理员接口基本地址/v1/api/getStudents
   - 2.老师接口基本地址/v1/api/getStudents?teacher_id=?
   - 3.学生接口基本地址/v1/api/getStudents?student_id=?

- 请求方式 ：GET

- 请求参数说明:管理员不需要请求参数，老师和学生需要请求参数

  |参数名称|说明|
  |:--:|:--:|
  |teacher_id|老师工号|
  |student_id|学生学号|

- 返回实例：
    - 管理员和老师返回参数实例（返回内容一致，total不一样）
    <pre>
            {
                "status": true,
                "info": null,
                "total": 10,
                "data": [
                    {"course_id": "201800000000",
                    "course_name": "信息系统分析与设计",
                    "date": "2017-2018",
                    "term": "2",
                    "college": "信工学院",
                    "credit": "5"},
                    {
                    ...其他课程
                    }
                ]
            }
    </pre>
    - 学生返回参数实例
    <pre>
            {
                "status": true,
                "info": null,
                "total": 1,
                "data": [
                    {"course_id": "201800000000",
                    "course_name": "信息系统分析与设计",
                    "date": "2017-2018",
                    "term": "2",
                    "college": "信工学院",
                    "credit": "5",
                    "teacher_id":"201300000000",
                    "name":"张三",
                    "github_username":"zwdbox"},
                    {
                    ...其他课程
                    }
                ]
            }
    </pre>

- 返回参数说明：

  |参数名称|说明|
  |:--|:--|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回课程个数|
  |data|所有课程的数组|
  |course_id|课程号|
  |course_name|课程名|
  |date|开课学年|
  |term|开课学期|
  |college|开课学院|
  |credit|学分|
  |teacher_id|授课老师Id|
  |teacher_name|授课老师姓名|
  |github_username|授课老师GItHub账号|
