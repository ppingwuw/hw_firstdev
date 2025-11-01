# 初识终端以及了解ssh协议
## 初识终端（认识这几个名词）
<a name="CIL"></a>
### 命令行接口（Command Line Interface，CLI）
- 命令行接口是计算机操作系统或应用程序为用户提供的可视提示接口，使用CLI，可以在特定的行中输入命令，从操作系统接收回应等。
```
ls                      # 列出当前目录下的文件和文件夹。
cd                      # 切换当前工作目录。
mkdir                   # 创建新的目录。
rm                      # 删除文件或目录。
cp                      # 复制文件或目录。
mv                      # 移动文件或目录。
cat                     # 把文件的所有行打印到终端上
vim                     # Vim是从 vi 发展出来的一个文本编辑器
```
<a name="terminal"></a>
### 终端（terminal）
- Windows 终端是一个面向命令行工具和 shell（如命令提示符、PowerShell 和适用于 Linux 的 Windows 子系统 (WSL)）用户的新式终端应用程序。

即用于交互的gui界面


<a name="shell"></a>
### 命令解释器（shell）

- 运行在终端的程序，接受命令，解释并执行。
```
test.bat
bash qwen2.5_7b.sh
```

- bat脚本内容
```
for /r %%a in (*.bat) do ren "%%a" "%%~na.txt"
```
- bat脚本功能：实现更改文件名后缀

tips:       >%%~na：保留文件名信息       >%%a：文件完整信息

<a name="environment"></a>
### 环境变量（Environment Variables）(env)
- 一般是指在操作系统中用来指定操作系统运行环境的一些参数，如：临时文件夹位置和系统文件夹位置等。


路径例子：
![path](/path.png)

- 我的理解是：key = value 其中key就是变量，value就代表这个变量的值，而这个值一般是什么呢，就是哪些存储了操作指令文件（也就是可执行文件）的地址。我们每运行一个命令，他就会在变量里面去找到对应的操作文件位置，执行其中对应的代码。

```
conda activate
git clone web_url.git
pip install torch
```
以 git clone 为例，我们在终端输入 git clone web_url.git 时，终端会在变量里面去找到 git 这个变量，然后执行 git 这个变量对应的值（也就是 git 可执行文件的地址），从而实现克隆仓库的功能。
<a name="ssh"></a>
## ssh协议
SSH是一种网络协议，用于计算机之间的加密登录。如果一个用户从本地计算机，使用SSH协议登录另一台远程计算机，我们就可以认为，这种登录是安全的，即使被中途截获，密码也不会泄露。最早的时候，互联网通信都是明文通信，一旦被截获，内容就暴露无疑。
整个过程是这样的：
- （1）远程主机收到用户的登录请求，把自己的公钥发给用户。
- （2）用户使用这个公钥，将登录密码加密后，发送回来。
- （3）远程主机用自己的私钥，解密登录密码，如果密码正确，就同意用户登录。

## 参考文献
- 【[Warp]在学校没有人教你的终端基础知识】（[bilibili](https://www.bilibili.com/video/BV1rk4y1W7dZ)）
- 【[自制双语字幕] 计算机教育缺失的一课(2020) - 第1讲 - 课程概览与 shell】（[bilibili](https://www.bilibili.com/video/BV1uc411N7eK)）
- ❤️肝下25万字的《决战Linux到精通》笔记，你的Linux水平将从入门到入魔❤️【建议收藏】（[csdn](https://blog.csdn.net/as604049322/article/details/120446586)）
- 什么是SSH 以及常见的ssh 功能（[csdn](https://blog.csdn.net/u013452337/article/details/80847113)）



