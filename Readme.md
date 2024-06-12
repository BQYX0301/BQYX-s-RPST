# GitHub


## 关键字查询 
	awesome:在该标签类别中查询项目
	python tutorial:查询资料、书籍、文档
	socket sample:查询对应技术的代码样本

## GitHub三要素

### Repository 仓库:
	仓库是github项目管理存储基本单位
	一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库分为public,private
### Commit 提交:
	程序员在整个开发周期，有大量的对代码资源的选代和修改，都可以通过commit的方式进行记录,
	便于程序员回溯代码（即使这些代码被删除）
	提交便于使用者观察整个工程的开发流程以及设计流程

### Branch 分支
	在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，
	默认的仓库主分支为master/main
	*不仅可以管理代码存储，便于多人协作开发
[Branch分支](https://picture.gptkong.com/20240612/17298788b339f84da998281b654c727cb3.png)

## 仓库内容
	Code，资源存储，代码资源，二进制，项目管理脚本，许可证等等
	issues，使用时遇到的bug 或 进行提交，等待反馈
	README，使用markdown语言编写，工程自述文件，开发进度，，版本更新，使用介绍等等
	LICENSE 许可证:GPL2.0,3.0.Apahce 2.0，Mit，这些许可证，给使用者最大使用权限以及最少的限制


## Git软件，分布式版本控制系统
仓库管理软件，使用git管理私人代码或企业代码

[示例](https://picture.gptkong.com/20240612/173099f539bd5d4083aa9b18f7974a91e3.png)


# 设备认证
## 1.让网站的账户与设备绑定，后续完成代码的管理，上传下载
```bash
	git init  //创建本地仓库 *后续对仓库的操作，都要在仓库位置(master)

	git config -list  //查看git的配置文件
```
修改或添加config配置项
```bash
	git config --global user.name  //用户名
	git config --global user.email //注册邮箱
```
生成本机设备密文
```bash
	ssh-keygen -t rsa -C “注册邮箱’ //创建本地密文 *去对应的目录下查找密文文件
```

* 去对应的目录查找密文文件
	rsa.pub 复制密文，粘贴到 settings -> ssH key and
        GPG -> new ssh key ->粘贴
```bash
	ssh -T git@github.com //测试关联是否成功
```

## 2.为目标仓库起别名，定位目标仓库，后续上传
```bash
	git remote add orgin "SSH地址(云端仓库地址)" //为ssh擦那个库地址创建别名为origin
	git remote remove origin  //删除地址别名
```



# 本地设备与云端仓库的交互逻辑

[示例](https://picture.gptkong.com/20240612/1732d69c7dd06143a699c8689c36370e6d.png)

```bash
	git add code.c  #添加内容
	
	#将缓冲区数据提交到本地仓库
	git commit  #提交到本地仓库
	git commit -m "备注信息"  #生成提交记录
	git push origin(云端仓库地址) master  #将本地仓库内容推到云端仓库
	
	git status  #查看状态
	git rm code.c  #删除本地文件及仓库中文件
	git restore code.c  #复位误删除文件(在仓库存在的前提下)
```


# 代码更新的依赖关系被破坏
	本地内容要比云端新,完成更新替换， 但是如果直接修改云端内容,
	会导致本地内容无法再次提交
	*先拉取 git pull 云端内容,与本地内容合井或操作,而后再次推即可
```bash
	git pull --rebase origin master

	git rebase --skip      #忽略旧版，更新本地后可以上传
	git rebase --abort     #忽略新版，此时还不能上传
	git rebase --continue  #版本合并，解决冲突后可以直接上传

```

## 下载开源代码
```bash
	git clone "https仓库地址"  #下载开源项目code资源
```
## 分支Branch
	关于分支的相关命令，创建分支、选择分支、合并分支等等



# Markdown文本修饰语言
用特殊符号修饰正文效果<br>

## 标题修饰符(\#)
注：修饰符与正文之间要有空格
# 标题修饰符(一级标题)
## (二级标题)
### (三级标题)
#### (四级标题)
##### (五级标题)

## 正文内容
        输出正文内容 , 但是如果需要换行,用\<br\> 标签

## 修饰正文
  *一段测试文本*<br>
  **一段测试文本**<br>
 ***一段测试文本***

## 分割线(\-\-\-)
---

## 引用(\>)
>对于和死亡毗邻而居的人而言，比起生死的问题来，一朵花的微笑更能铭记于心
>>《潘多拉之匣》
>>>三级引用
>>>>四级引用

## 列表修饰符
### 无序列表(\*)
* RPG游戏
  * 生化危机
    * 里昂·肯尼迪
    * 伊森·温特斯
    * 艾达·王
    * 克里斯·雷德菲尔德
    * 克莱尔·雷德菲尔德
    * 瑞贝卡·查姆博斯
    * 吉尔·瓦伦丁

### 有序列表(1.)
1. 2013-2015年TGA年度最佳
   1. 巫师三
   2. 龙腾世纪：审判
   3. GTA5
2. 2016-2018年TGA年度最佳
   1. 守望先锋
   2. 塞尔达传说：旷野之息
   3. 战神4

## 表格<br>
### 2024年度书单
名称|作者|国籍
--|:--:|--:
《罗杰疑案》|阿加莎·克里斯蒂|英国
《解忧杂货店》|东野圭吾|日本
《围城》|钱锺书|中国
《追风筝的人》|卡勒德·胡塞尼|阿富汗

<br>

## 代码片段

```c
	#include <stdio.h>
```

```cpp
	#include <iostream>
```

```python
	import <os>
```

```bash
	echo "测试"
	pwd
	ps aux
```

## 超链接
[BZone-ZARD](https://WEZARD.net)

## 插入图片
[世纪会晤](https://picture.gptkong.com/20240612/17201cc2c5e3524e2c8e25a5eaf0345bf3.jpg)

