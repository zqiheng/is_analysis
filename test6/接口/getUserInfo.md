# 接口：getUserInfo  [返回](../README.md)
用例： [查看用户信息](../用例/查看用户信息.md),[修改用户信息](../用例/修改用户信息.md)

- 功能：用户查看自己的信息。

- 权限：学生、老师、管理员，查看自己的信息，必须先登录，不能查看其他用户的信息。

- API请求地址：接口基本地址/v1/api/getUserInfo?user_id=?

- 请求方式 ：GET

- 请求参数说明:

  |参数名称|说明|
  |:--:|:--|
  |user_id|用户的ID号。对应表Users.user_id的值|

- 返回实例：

        {
            "status": true,
            "info": null,
            "id":"201510414427",
            "name":"张启恒",
            "class_dept":"软件(本)15-4"
            "github_username":"zhangqiheng",
            "type":"学生"
        }

- 返回参数说明：

  |参数名称|说明|
  |:--:|:--|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |id|学号或者工号|
  |name|用户的真实姓名|
  |class_dept|班级或者部门名称|
  |github_username|gitHub用户名|
  |type|用户类型：老师、学生或管理员|
