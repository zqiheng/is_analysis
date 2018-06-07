# 接口：addArrangeInfo  [返回](../README.md)
用例： [老师排课](../用例/老师排课.md)

- 功能：管理员新增老师排课信息。

- 权限：理员，必须先登录。

- API请求地址： 接口基本地址/v1/api/addArrangeInfo?course_id=? and teacher_id=?

- 请求方式 ：POST

- 请求实例：

        {
            "course_id":"201800000000",
            "teacher_id":"201300000000"
        }

- 请求参数说明:

  |参数名称|说明|
  |:--:|:--|
  |course_id|课程号|
  |teacher_id|老师工号|

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
