# 介绍
miniob 是 OceanBase 与华中科技大学联合开发的、面向"零"基础同学的数据库入门实践工具。
miniob 设计的目标是让同学们快速了解数据库并深入学习数据库内核，期望通过相关训练之后，能够对数据库内核各个模块的功能及其关联有所了解，并能够在
使用数据库时，设计出高效的 SQL 。miniob 面向的对象主要是在校学生，并且诸多模块都做了简化，比如不考虑并发操作。

(注意：此代码仅供学习使用，不考虑任何安全特性。)

[GitHub 首页](https://github.com/oceanbase/miniob)

# 1. 题目说明
[miniob 题目描述](docs/miniob_topics.md) 

# 2. 开发指南
## 搭建开发环境
1. [本地配置gcc环境](docs/how_to_build.md)。
2. [使用Docker开发](docs/how-to-dev-using-docker.md)。
3. [在Windows上使用Docker](docs/how_to_dev_miniob_by_docker_on_windows.md)。

## 词法、语法解析
请参考 [miniob 词法语法解析开发与测试](docs/miniob-sql-parser.md)。

# 3. 提交测试
题目完成并通过自测后，大家可以在 [miniob 训练营](https://open.oceanbase.com/train?questionId=200001) 上提交代码进行测试。

客户端输出需要满足一定要求，如果你的测试结果不符合预期，请参考 [miniob 输出约定](docs/miniob-output-convention.md)。

# 4. 数据库管理系统实现基础讲义
由华中科技大学谢美意和左琼老师联合编撰的数据库管理系统实现教材：[《数据库管理系统实现基础讲义》](docs/lectures/index.md)

# 5. miniob 介绍
[miniob 源码解析视频](https://open.oceanbase.com/activities/4921877)

[miniob 源码解析文档](https://www.oceanbase.com/docs/community-developer-quickstart-10000000000627363)

# 以下作者为lcy

在miniob/build目录下键入进行编译
cmake .. -DDEBUG=ON
make

相同目录下
在后台启动服务端程序
./bin/observer -s minion.sock -f ../etc/observer.ini &
运行客户端
./bin/obclient -s minion.sock

# 提测流程(在miniob目录下):

rm -rf .git
git init
git add .
git commit -m 'init'  

git remote add origin https://gitee.com/zhang-zhilin-xishan/MiniOB.git
# 或者
git remote add origin https://github.com/KeplerFlow/miniob-2023.git

git branch -M main

git push -u origin main
# 或者使用-f强制覆盖
git push -f origin main

# 如果push后无响应:打开VScode的设置界面。方法即：“Code > Preferences > Settings”（我是Mac系统，Windows下应该是File > Preferences > Settings）
# 搜索“git.terminalAuthentication”，并将该复选框前的对钩取消掉

# 而后使用命令
git log
# 查看commit id


（资料持续整理中，请大家自行查阅标题为“MiniOB...”的视频或文档）
