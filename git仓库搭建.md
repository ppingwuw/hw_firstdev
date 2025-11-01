# git仓库搭建以及管理
## 一、搭建git仓库的步骤
1. 安装git
2. 配置git
3. 创建git仓库
   ```
   git init                      # 初始化一个新的git仓库
   git add .                     # 添加所有文件到暂存区
   git commit -m "dev1"          # 提交暂存区的文件到仓库
   git branch -m main            # 重命名默认分支为main
   ```

## 二、上传git仓库至github的步骤
1. 注册github账号

   略
2. 在github上创建一个新的仓库
   
   截图举例：
   ![创建github仓库](./img/create_github_repo.png)
3. 初始化本地仓库
   
   在 （一、搭建git仓库的步骤） 中已经完成
4. 添加远程仓库（首次推送会要求登录GitHub，输入账号密码登入即可。）
   
   添加远程仓库的URL，其中`<remote-name>`是自定义名称（作用是存储remote-url，方便后续使用，即可以直接使用`<remote-name>`来代替`<remote-url>`），`<remote-url>`是远程仓库的URL：
   ```
   git remote add <remote-name> <remote-url>
   git remote add origin https://github.com/yourusername/yourrepository.git
   ```


5. 推送本地仓库至远程仓库
   
   推送本地仓库的`<branch-name>`分支到远程仓库的`<remote-name>`分支，其中`<remote-name>`是远程仓库的名称，`<branch-name>`是本地仓库的分支名称。
   ```
   git push -u <remote-name> <branch-name>
   git push -u origin main
   ```