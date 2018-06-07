## GItHub试验管理平台数据库设计 [首页](../README.md)

<div id="Users"></div>

- ### Users表（用户表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |user_id|NUMBER(8,0)|主键|否| | | 用户ID|
    |name|VARCHAR2(50 BYTE)| |否| | | 用户真实姓名|
    |github_username|VARCHAR2(50 BYTE)| |是|空| | GitHUB用户名|
    |update_date|DATE| |是|空| | GitHUB用户名修改日期|
    |password|VARCHAR2(512 BYTE)| |是|空| | 加密存储密码，为空表示密码就是学号|
    |disable|VARCHAR2(20 BYTE)| |否| | |是否禁用,值为是表示禁用,其他表示正常.|

<div id="Managers"></div>

- ### Managers表（管理员表）
    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |manager_id|VARCHAR2(50 BYTE)|主键|否| | | 管理员工号|
    |user_id|NUMBER(8,0)|外键|是| | Users.user_id| 管理员的用户ID，Users表的外键,为空表示还没有建立该管理员|
    |department|VARCHAR2(20 BYTE)| |否| | | 管理员属于的部门|

<div id="Teachers"></div>

- ### Teachers表（老师表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |teacher_id|VARCHAR2(50 BYTE)|主键|否| | | 老师工号|
    |user_id|NUMBER(8,0)|外键|是| | Users.user_id| 老师的用户ID，Users表的外键，为空时表示还没有建立用户|
    |department|VARCHAR2(20 BYTE)| |否| | | 老师属于的部门|

<div id="Students"></div>

- ### Students表（学生表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |student_id|VARCHAR2(50 BYTE)|主键|否| | | 学号|
    |user_id|NUMBER(8,0)|外键|是| |Users.user_id| 学生的用户ID，Users表的外键，为空表示还没有建立用户|
    |class|VARCHAR2(20 BYTE)| |否| | | 学生班级|
    |result_sum|VARCHAR2(400 BYTE)|外键|是|空| | 成绩汇总（来自Grades表），以逗号分开，第一个成绩是平均成绩,后面是每次实验的成绩，N表示未批改，平均分只计算已批改的。比如：“81.25,70,80,85,90,N”表示一共批改了4次，第5次未批改，4次的成绩分别是81.25,70,80,85,90,N，4次的平均分是81.25|
    |web_sum|VARCHAR2(400 BYTE)| |是|空| | GitHub网址是否正确，用逗号分开，Y代表正确，N代表不正确。第1位代表总的GitHUB地址是否正确，第2位表示第1次实验的地址，第3位表示第2位实验地址，依此类推。比如：“Y,Y,Y,Y,Y,N”表示第5次实验地址不正确，其他地址正确|

<div id="Courses"></div>

- ### Courses表（课程表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |course_id|VARCHAR2(50 BYTE)|主键|否|||课程号|
    |course_name|VARCHAR2(50 BYTE)||否|||课程名|
    |date|DATE||否|||开课学年|
    |term|NUMBER(1,0)||否|||开课学期|
    |college|VARCHAR2(50 BYTE)||否|||开课学院|
    |credit|NUMBER(1,0)||否|||学分|

<div id="ArrangeInfo"></div>

- ### ArrangeInfo表（老师任课表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |arrangeInfo_id|VARCHAR2(50 BYTE)|主键|否|||老师任课编号|
    |course_id|VARCHAR2(50 BYTE)|外键|否||Courses.course_id|课程号|
    |teacher_id|VARCHAR2(50 BYTE)|外键|否||Teachers.teacher_id|授课老师工号|
    |place|VARCHAR2(5 BYTE)||否|||上课地点|
    |num|NUMBER(3,0)||否|||上课人数|

<div id="CourseInfo"></div>

- ### CourseInfo表（学生排课表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |courseInfo_id|VARCHAR2(50 BYTE)|主键|否|||学生排课编号|
    |arrangeInfo_id|VARCHAR2(50 BYTE)|外键|否||ArrangeInfo.arrangeInfo_id|老师任课编号|
    |student_id|VARCHAR2(50 BYTE)|外键|否||Students.student_id|学号|

<div id="Tests"></div>

- ### Tests表（实验项目表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |test_id|NUMBER(6,0)|主键|否| | | 实验编号|
    |arrangeInfo_id|VARCHAR2(50 BYTE)|外键|否||ArrangeInfo.arrangeInfo_id|老师任课编号|
    |TITLE|VARCHAR2(100 BYTE)| |否| | | 实验名称|

<div id="Grades"></div>

- ### Grades表（学生实验成绩表）

    |字段|类型|主键、外键|可以为空|默认值|约束|说明|
    |:--:|:--:|:--:|:--:|:--:|:--:|:--|
    |student_id|VARCHAR2(50 BYTE)|联合主键1，外键|否| | | 学生的学号，STUDENTS表外键|
    |test_id|NUMBER(6,0)|联合主键2，外键|否| | | 实验编号，TESTS表的外键|
    |reslut|NUMBER|主键|是|空| 取值0-100| 分数，这个值为空表示没有批改|
    |memo|VARCHAR2(400 BYTE)| |是|空| | 老师对实验的评语|
    |update_date|DATE| |是|空| |老师批改实验的日期，为空表示未批改|




