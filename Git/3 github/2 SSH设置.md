由于本地仓库和github仓库之间的传输是通过SSH加密的，所以需要一点设置：
# 1. 创建SSH Key
在用户主目录下，看看有没有.ssh目录，如果有，再看看有没有id_rsa和id_rsa.pub这两个文件，如果有，直接跳过此如下命令，如果没有，打开命令行输入：
```shell
ssh-keygen -t rsa -C "youremail@example.com"
```	
## 注意：
id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心告诉任何人。

# 2. 登录github
打开"settings"中的SSH Keys页面，然后点击"Add SSH Key"，填上任意title，在Key文本框中粘贴id_rsa.pub文件的内容，最后得到一个新的SSH Key
![image](B074BC6E871444008B1AEC5BB1157DBA)
	
