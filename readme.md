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

   ![image-20221109144736725](res\image-20221109144736725.png)

9. 滚回原来版本后发现又想新版本挺好 想挽回就输入下面代码：

   ```shell
   #首先我们用 git log命令找不到最新版怎么办
   #就用以下命令查看版本切换记录
   git reflog
   #然后从中找出新版本输入滚回代码
   git reset --hard xxx	#xxx是新版本仓库的版本号
   #详细如下图：
   ```

   ![image-20221109150713305](res\image-20221109150713305.png)

10. git仓库分支概念：（开发新功能分支是需要紧急修复bug解决方案）

       ```shell
    git branch		#查看当前分支  主分支为master
    git branch dev 	#创建新分支 dev为
    #新建分支修复bag
    git branch dev 	#创建新分支 dev为新分支名
    git checkout dev#切换当前分支到dev分支继续开发新功能
    #原版本出现bug要得回到原版本创建新分支修复bug
    git branch bug	#创建新分支
    git checkout bug#修复bug
    #修复完bug提交
    #然后回到原分支
    git checkout master
    #合并修复的bug分支
    git merge bug
    #合并完删除不必要的分支
    git branch -d bug#删除gug分支
    #合并完bug分支后继续开发新功能dev分支
    #开发完新功能后又回到主分支合并新功能
    git checkout master	#切换到主分支
    git merge dev	#合并到主分支
    #手都修改冲突部分后提交代码到仓库
       ```

11. 把本地仓库推从到github仓库中

    ```shell
    #如果是空项目用以下命令
    #…或者在命令行上创建一个新的存储库
    echo "#TestOne" >> README.md 
    git init 
    git add README.md 
    git commit -m "first commit" 
    git branch -M main 
    git remote add origin https://github.com/AbrMain/TestOne.git
     git push -你原产地主要
    ```

    ```shell
    #但是我们现在要本地仓库文件推从到github所以用以下代码：
    #…或从命令行推送现有存储库
    git remote add origin https://github.com/AbrMain/TestOne.git #给仓库取别名为origin
    # git branch -M main #这部分是新规定主要是禁止使用master这个词
    #git push -u origin main	##这部分是新规定主要是禁止使用master这个词
    #老规矩是
    git push -u origin master
    #把dev分支也要上传
    git push -u origin dev
    ```

12. 从github仓库中拉下来

    ```shell
    #下载到本地有两种方法
    #第一种是本地还没有项目 就直接克隆
    git clone https://github.com/AbrMain/TestOne.git
    #第二种情况是 本地已经有旧项目 那就更新一下就可以
    git remote add origin https://github.com/AbrMain/TestOne.git #给仓库取别名为origin
    git pull origin dev	#(更新dev或者master分支)
    ```

    
