# 实验六：基于GitHub的实验管理平台的分析与设计
### 成都大学信息科学与工程学院
|学号|班级|姓名|照片|
|:--:|:--: | :--:|:--:|
|201510414427|软件(本)15-4|张启恒|![MYSELF](src/myself.png)|

## 1.概述
- 基于GitHub的实验管理平台的作用是在线管理实验成绩的Web应用系统。
- 系统流程描述：管理员首先录入课程信息（Courses）、老师信息（Teachers）、学生信息（Students），然后给老师排课（arrangeInfo），根据排课表（arrangeInfo）再给学生排课（CourseInfo），老师在GItHub上发布试验内容，学生根据老师的链接地址查看试验要求并在自己的GItHub上提交试验，老师根据学生GItHub账号在给学生评定成绩，学生在查看试验成绩。
- 管理员的主要功能有：1、信息录入；2、给老师排课；3、给学生排课。
- 老师的功能主要有：1、根据自己教授的课程在GitHub上发布实验内容并指定GItHub库；2、批改学生的实验成绩；3、查看学生的实验成绩；4、设置自己的GitHub信息。
- 学生的功能主要有：1、设置自己的用户信息（GItHub账号、密码等）；2、根据所上的课程查看老师在GItHUb上发布的试验内容；3、根据实验内容提交试验（每门课程GitHub库不一样）；4、查询自己的实验成绩。
- 老师和学生都能通过本系统的链接方便地跳转到学生的每个GitHUB实验目录，以便批改实验或者查看实验情况。
- 实验成绩按数字分数计算，每项实验的满分为100分，最低为0分。
- 系统自动计算每个学生的所有实验的平均分。
- <b>说明：</b>由于时间问题，本系统暂时未实现应用到各学院（目前仅针对一个学院）甚至推广到全国。我的大概思路是数据库表一定要设计好（比如新增学校表（Universities）、学院表（Colleges）、专业表（Majors）、学生自主选课表（Electives）等等），其中的重难点是表之间的关系设计，它是复杂的，庞大的。

## 2.系统总体设计
![系统总体结构设计](src/系统总体结构.png)
<br>
说明：根据角色不同，部分列表显示的内容可能不同，详见<b>界面设计</b>和<b>用列</b>。

<b>界面设计：https://zqiheng.github.io/is_analysis/test6/ui/index.html</b>

<br><br><br>
## 3.用例图设计 [源码](src/UseCase.puml)
![用例图](src/UseCase.png)

<br><br><br>
## 4.类图设计 [源码](src/Class.puml)
![类图](src/Class.png)

<br><br><br>
## 5.数据库设计
- ### [参见数据库设计](数据库设计/sql.md)

## 6.用例及界面详细设计

- ### [“登录”用例](用例/登录.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/登录.html)
- ### [“查看用户信息”用例](用例/查看用户信息.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“修改用户信息”用例](用例/修改用户信息.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“修改密码”用例](用例/修改密码.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“登出”用例](用例/登出.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/顶部菜单.html)
- ### [“课程列表”用例](用例/课程列表.md)
    - #### [管理员和老师的界面](https://zqiheng.github.io/is_analysis/test6/ui/课程列表.html)
    - #### [学生的课程列表界面](https://zqiheng.github.io/is_analysis/test6/ui/学生的课程列表.html)
- ### [“老师排课”用例](用例/老师排课.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/老师排课.html)
- ### [“学生排课”用例](用例/学生排课.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/学生排课.html)
- ### [“教师列表”用例](用例/教师列表.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/教师列表.html)
- ### [“学生列表”用例](用例/学生列表.md)
    - #### [老师的学生列表界面](https://zqiheng.github.io/is_analysis/test6/ui/老师的学生列表.html)
    - #### [管理员的学生列表界面](https://zqiheng.github.io/is_analysis/test6/ui/管理员的学生列表.html)
- ### [“成绩列表”用例](用例/成绩列表.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/成绩列表.html)
- ### [“评定成绩”用例](用例/评定成绩.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/实验成绩评定页面.html)
- ### [“查看成绩”用例](用例/查看成绩.md)，   [界面](https://zqiheng.github.io/is_analysis/test6/ui/实验成绩详情页面.html)

