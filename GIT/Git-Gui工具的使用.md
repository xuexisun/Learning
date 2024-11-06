# Git-Gui 的使用

## 汉化

1. 下载汉化文件 https://files.cnblogs.com/files/chenghu/git-gui-zh-master.zip

2. 找到 git 安装路径 ( 我的安装位置在 D:\Program Files\Git\mingw64\share\git-gui\lib\msgs), msgs 可能不存在, 需要手动自己创建.

3. ![image-20241106012759543](Git-Gui工具的使用.assets/image-20241106012759543.png)

4. 解压下载的文件, 将名为 zh_cn.msg 的文件, 放进 msgs 中文件夹中

   ![image-20241106013130252](Git-Gui工具的使用.assets/image-20241106013130252.png)

5. 重新打开Git GUI 如下图: 

   ![image-20241106013358958](Git-Gui工具的使用.assets/image-20241106013358958.png)

![image-20241106013557648](Git-Gui工具的使用.assets/image-20241106013557648.png)

## 权限校验

生成公钥

1. 点击菜单栏 帮助 - 显示ssh密钥

   ![image-20241106014147006](Git-Gui工具的使用.assets/image-20241106014147006.png)

2. 然后再点击 生成密钥 然后 复制到粘贴板

![image-20241106014339687](Git-Gui工具的使用.assets/image-20241106014339687.png)

3. GitHud 与 Gitee 添加 SSH 密钥  ( 添加SSH公钥的页面都在设置里 ), 且保存后前都要输用户密码

   -  GitHud  的教程 [通过 SSH 连接到 GitHub - GitHub 文档](https://docs.github.com/zh/authentication/connecting-to-github-with-ssh)
   -  Gitee  的教程 [SSH 公钥设置 | Gitee 帮助中心](https://help.gitee.com/base/account/SSH公钥设置)

   ![image-20241106014732223](Git-Gui工具的使用.assets/image-20241106014732223.png)

   ![image-20241106015604615](Git-Gui工具的使用.assets/image-20241106015604615.png)

   ![image-20241106014922341](Git-Gui工具的使用.assets/image-20241106014922341.png)

4. 测试 SSH 连接 (第一次执行 ssh 的命令会有警告信息, 直接输入yes 按回车即可)

```sh
# Gitee
ssh -T git@gitee.com

# Github
ssh -T git@github.com
```

5. 输出 SSH Key 绑定的用户名 即对应 远程 git 的用户名 

![image-20241106010301412](Git-Gui工具的使用.assets/image-20241106010301412.png)

![image-20241106010346362](Git-Gui工具的使用.assets/image-20241106010346362.png)

## git Gui 的基础操作

1. 前提准备配置个人的用户名称和电子邮件地址，克隆/下载远程仓库

   ```shell
   git config --global user.name "xuexi"
   git config --global user.email 2161224007@QQ.COM
   
   git clone https://gitee.com/sunxuexi/learning.git
   ```

   ![image-20241106022742828](Git-Gui工具的使用.assets/image-20241106022742828.png)

2. 在有 .git 的目录右击 - Open Git GUI here 打开 Git GUI

   ![image-20241106023017853](Git-Gui工具的使用.assets/image-20241106023017853.png)

   ![image-20241106023147852](Git-Gui工具的使用.assets/image-20241106023147852.png)

3. 提交操作

   1. 点击 下方的重新扫描, 将会在 未缓存的改动 或 缓存的改动 信息显示文件信息

      ![image-20241106023725129](Git-Gui工具的使用.assets/image-20241106023725129.png)

   2. 点击 下方的缓存改动, 然后点确定, 

      ![image-20241106023852511](Git-Gui工具的使用.assets/image-20241106023852511.png) 

   3. 此时 未缓存的改动 将会被清空, 缓存的改动 就是将要提交的内容.填写提价描述, 然后点击提交

      ![image-20241106024414509](Git-Gui工具的使用.assets/image-20241106024414509.png)

   4. 最后点击上传 在弹窗选择分支,  在点击上传

      ![image-20241106024635411](Git-Gui工具的使用.assets/image-20241106024635411.png)

      ![image-20241106024726984](Git-Gui工具的使用.assets/image-20241106024726984.png)

   5.  下图就是上传成功, 以及Gitee 的信息

      ![image-20241106024905694](Git-Gui工具的使用.assets/image-20241106024905694.png)

      ![image-20241106025040342](Git-Gui工具的使用.assets/image-20241106025040342.png)

      字符乱码问题: 在缓存未提交的窗口上右击选择 编码 - Unicode(UTF 8)

      ![image-20241106030058367](Git-Gui工具的使用.assets/image-20241106030058367.png)

4. 同步远程代码

   1. 准备工作: 手动在远程 git 仓库创建文件夹 (机顶盒) 和文件 (机顶盒刷成 liunx系统-Armbian.md) 

      ![image-20241106144946566](Git-Gui工具的使用.assets/image-20241106144946566.png)

      添加文件夹 - 机顶盒

      ![image-20241106145023990](Git-Gui工具的使用.assets/image-20241106145023990.png)

      添加文件 - 机顶盒刷成 liunx系统-Armbian.md

      ![image-20241106145113669](Git-Gui工具的使用.assets/image-20241106145113669.png)

      在拓展信息内添加说明信息然后点击 提交

      ![image-20241106145217697](Git-Gui工具的使用.assets/image-20241106145217697.png)

   2. 点击菜单栏 远程库 - 从...项获取 - origin(  有可能不是这个名字 )

      ![image-20241106145707386](Git-Gui工具的使用.assets/image-20241106145707386.png)

   3. 如果远程仓库有东西 弹窗里面会显示一些信息

      ![image-20241106145959362](Git-Gui工具的使用.assets/image-20241106145959362.png)

   4. 再点击菜单栏 合并- 本地合并

      ![image-20241106150212984](Git-Gui工具的使用.assets/image-20241106150212984.png)

   5. 在空白的位置单击一下就能看到之前在的在远程仓库填写的说明信息

      ![image-20241106150542774](Git-Gui工具的使用.assets/image-20241106150542774.png)

   6. 然后点击合并即可

      ![image-20241106150635277](Git-Gui工具的使用.assets/image-20241106150635277.png)

   7. 看到提示信息 以及查看文件管理器的中的新内容

      ![image-20241106150906246](Git-Gui工具的使用.assets/image-20241106150906246.png)

      ![image-20241106151048600](Git-Gui工具的使用.assets/image-20241106151048600.png)

5. 冲突处理
   1. 准备工作: 手动在远程 git 仓库修改文件(README.md), 同时也在本地修改同名文件

      ![image-20241106153106676](Git-Gui工具的使用.assets/image-20241106153106676.png)
      
      ![image-20241106153131810](Git-Gui工具的使用.assets/image-20241106153131810.png)
      
      

参考来源：http://www.cnblogs.com/iruxu/p/gitgui.html