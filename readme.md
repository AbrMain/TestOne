# git版本控制器使用说明

## 1.安装教程

TODO:今天暂不介绍安装过程

## 2.版本控制

1. 在git Bash中进入项目文件目录或者新建目录

   ```shell
   mkdir $		#$是要新建的文件目录名
   ```

2. 初始化当前目录

   ```shell
   git init	#初始化当前项目目录
   ```

3. 分析当前项目目录命令：

   ```shell
   git status 	#标红色文件名都是还未被管理的文件
   ```

4. 把文件添加到git管理列表中的代码：

   ```shell
   git add $.$ #添加指定文件$.$为你要添加的文件名
   git add .	#添加所有没有被管理的文件到git管理列表
   ```

5. 生成版本新的版本代码：

   ```shell
   git commit -m 'V1'	#生成新的版本'V1'可以写自己的版本描述
   ```

6. 查看现有版本

   ```shell
   git log		#查看现有版本
   ```

7. 创建文件命令：

   ```shell
   touch $.$	#创建新文件 文件名为$.$
   ```

8. 滚回某个版本代码：

   ```shell
   #首先输入下面命令查看本地git仓库版本信息
   git log
   #然后输入以下代码来滚回指定版本
   git reset --hard xxx	#xxx是本地仓库版本号
   #详细如下图：
   ```

   ![image-20221109144736725](C:\Users\小白兔\AppData\Roaming\Typora\typora-user-images\image-20221109144736725.png)

9. 滚回原来版本后发现又想新版本挺好 想挽回就输入下面代码：

   ```shell
   #首先我们用 git log命令找不到最新版怎么办
   #就用以下命令查看版本切换记录
   git reflog
   #然后从中找出新版本输入滚回代码
   git reset --hard xxx	#xxx是新版本仓库的版本号
   #详细如下图：
   ```

   ![image-20221109150713305](C:\Users\小白兔\AppData\Roaming\Typora\typora-user-images\image-20221109150713305.png)

10. git仓库分支概念：

   ```
   git branch		#查看当前分支  主分支为master
   git branch dev 	#创建新分支 dev为
   #新建分支修复bag
   ```

  
