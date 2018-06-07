# 接口：getArrangeInfo  [返回](../README.md)
用例： [学生排课](../用例/学生排课.md)

- 功能：获取老师排课列表信息。

- 权限：管理员，必须先登录。

- API请求地址：接口基本地址/v1/api/getArrangeInfo

- 请求方式 ：GET

- 请求参数说明:
无

- 返回实例：

        {
            "status": true,
            "info": null,
            "total": 10,
            "data": [
                {"arrangeInfo_id": "2018100000000",
                "course_id": "201800000000",
                "course_name": "信息系统分析与设计",
                "teacher_id": "201300000000",
                "name": "张三",
                "place": "10502",
                "num": "90"
                 },
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
  |total|返回课程数|
  |data|所有课程的数组|
  |arrangeInfo_id|老师排课号|
  |course_id|课程号|
  |course_name|课程名|
  |teacher_id|授课老师工号|
  |name|授课老师名|
  |place|上课地点|
  |num|上课人数|
