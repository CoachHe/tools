# 先创建一个记事本文件readme.txt
内容为：This is my first git file.  
![image](005C5028E48A45789BBCCC7DB946927E)
		
# 第一步（将文件添加到git中）
使用命令git add readme.txt添加到暂存区里面去，如下：
![image](317D42106CC54C4F86F47925EA969D00)  
没有任何提示说明添加成功
# 第二步（将文件提交）
用命令git commit告诉Git，把文件提交到仓库  
![image](F7048205171B46A9A65244A0F6E80092)  
后面双引号内的内容为提交的注释  
目前已经提交了一个readme.txt文件了，下面可以通过命令git.ststus来查看是否还有文件未提交，如下：
![image](D7EC5488AA0E4B8F91456AAF6109E94B)
说明没有任何文件未提交

# 第三步（修改并提交修改文件）
## 1. 修改文件
现在继续修改readme.txt的内容，例如添加"This is the change I made"   
![image](655B3B4E0C6F48C19591BAA6CA32952B)
## 2. 查看修改
如下，然后再用git status来查看结果。  
![image](0B591BA1C2BF454FB36FE250FCF15194)    
这里说明readme.txt已经被修改，但是还没提交。
### 注意：
- 对文本进行更改后，restore是回到没修改之前的版本，commit是提交还没提交过的文件。
- git status能查看出文件被修改了看，但是不能查询被提交的修改。所有的版本控制系统，只能跟踪文件文本的改动，比如txt文件，程序代码等，git也不例外，版本控制系统可以告诉你每次的改动，但是图片、视频这些二进制文件，虽然可以通过版本控制系统管理，但没法跟踪文件的变化，也就是改了什么不知道。需要查询更改，可以使用以下命令：  
```shell
git diff xxx.xxx
```
## 3. 修改后add需要被提交的部分来更新  
![image](31C3EC2BD4DB408F878D30AA7BDD3684)	

## 4. 最后提交更改
![image](0A2CB3B989584B1AB93EBA6454382EDC)	
	
# 第四步（回退版本）
## 1. 再次进行修改
![image](681221315A7D45EBBCF0CFD655D0748B)		

## 2. 查看历史记录
使用命令git log
![image](4FED07BE492E434C9D922136DF2FC02D)  
如果觉得显示的信息太多，那么可以使用命令
```shell
git log --pretty=oneline
```	
## 3. 版本回退
有两种命令：
```shell
git reset --hard HEAD^
```
若是要恢复之前几个版本，那么可以多使用几个^（例如，HEAD^^）
### 注意：
回退版本之后git log也会相应减少
```shell
git reset --hard 版本号
```  
首先通过git reflog得到版本号  
![image](3514DCDA2CF14CE3947AC1573561621B)	
然后通过
```shell
git reset --hard 版本号
```
恢复到对应的版本
				
				
