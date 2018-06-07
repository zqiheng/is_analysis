# 接口：getTeachers  [返回](../README.md)
用例： [老师排课](../用例/老师排课.md)   [老师列表](../用例/老师列表.md)

- 权限： 管理员：必须先登录。

- 功能：返回所有老师的列表。

- API请求地址：
   - 接口基本地址/v1/api/getTeachers

- 请求方式 ：GET

- 请求参数说明:
无

- 返回实例：

<pre>
        {
            "status": true,
            "info": null,
            "total": 120,
            "data": [
                {"user_id": "1234",
                "teacher_id": "201300000000",
                "name": "张三",
                "github_username": "zhangsan",
                "department": "信息科学与工程学院",
                "disable": "否"
                {
                ...其他老师
                }
            ]
        }
</pre>

- 返回参数说明：

  |参数名称|说明|
  |:--|:--|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回老师人数|
  |data|所有老师的数组|
  |user_id|用户ID|
  |teacher_id|老师工号|
  |name|用户真实姓名|
  |github_username|GItHub账号|
  |department|老师所属部门|
  |disable|用户是否禁用|