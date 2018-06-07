# 接口：addCourseInfo  [返回](../README.md)
用例： [学生排课](../用例/学生排课.md)

- 功能：管理员新增学生排课信息。

- 权限：理员，必须先登录。

- API请求地址： 接口基本地址/v1/api/addCourseInfo?arrange_id=? and student_id=?

- 请求方式 ：POST

- 请求实例：

        {
            "arrange_id":"201800000000",
            "student_id":"201510414427"
        }

- 请求参数说明:

  |参数名称|说明|
  |:--:|:--|
  |course_id|（ArrangeInfo）表排课号|
  |teacher_id|学生学号|

- 返回实例：

        {
            "status": true,
            "info": null
        }

- 返回参数说明：

  |参数名称|说明|
  |:--:|:--:|
  |status|bool类型，true表示正确的返回(操作成功)，false表示有错误|
  |info|返回结果说明信息|
