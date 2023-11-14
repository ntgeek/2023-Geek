#  Git学习时的想法

> 为什么不是笔记呢？因为我把笔记写[Github进阶学习笔记](https://github.com/chlorine22/Tasks/blob/main/阶段2学习笔记/Github进阶学习笔记.md)里了

学git不光让我更了解git的用法，而且也增长了别的知识，比如：

> Microsoft开发记事本的团队使用了一个非常弱智的行为来保存UTF-8编码的文件，他们自作聪明地在每个文件开头添加了0xefbbbf（十六进制）的字符，会导致各种不可思议的错误

(貌似有用的知识增加了！)



做一阶段任务时，第一次体验git，报一大堆错，给我整不会了

本来以为经过一段时间的学习~~（才2天）~~，我的git不会再出错了，结果刚刚上传二阶段笔记又出问题了:rage:

像什么“failed to push some refs...”、“src refspec master does not match any”、"your branch  is ahead of 'origin/main' by 2 commits"、“unable to access...”

好在在我坚持不懈的努力~~（上CSDN狂搜）~~下，这些问题都解决了（但是我还是不太清楚这些问题的原理）

记录下解决的方法

### “failed to push some refs...”

这是上传一阶段笔记时出现的

在CSDN上搜到两种方法：

1. 先`git clone`,然后再输入`git add .`、`git commit`、`git push`
2. 直接输入`git push origin main -f`

第一种方法当时试过，不管用，于是果断选择第二种，一次成功，但不知道`-f`是什么意思

（但是我上传二阶段笔记时不加`-f`也可以了,怪）

### “src refspec master does not match any”

也是上传一阶段笔记时出现的

CSDN上查到这个错误的原因是`push`后写的分支名在本地不存在，我分析了一下，问题应该是我当时敲`git push`时没加`origin main`，导致git不能识别分支

### "your branch  is ahead of 'origin/main' by 2 commits"

这是上传修改后的README时出现的

翻译过来是“你的本地分支超前远程仓库下main分支两次提交”，也就是我一不小心多`commit`了一次，导致无法`push`。解决方法很简单，`git  reset --hard HEAD~2`，回溯两个版本就行了（算是提前一个阶段接触了吧）

### “unable to access...”

敲完二阶段笔记`push`时出现的

初见很是迷惑，“不能链接”是什么鬼，我梯子挂着啊。搞得我又去检查我的网络设置，结果没问题，懵了都。在CSDN上查到要用git-cmd重新关联GitHub账号，`git config`就可以了



# 参考资料

* [创建版本库 - 廖雪峰的官方网站 (liaoxuefeng.com)](https://www.liaoxuefeng.com/wiki/896043488029600/896827951938304)
* [软件测试|解决 Git Push 出现 “error: failed to push some refs to“错误-CSDN博客](https://blog.csdn.net/Tester_muller/article/details/132837267)
* [git 报错 error: src refspec master does not match any-CSDN博客](https://blog.csdn.net/weixin_45319250/article/details/129981496)
* [Your branch is ahead of ‘origin/master‘ by 2 commits. (use “git push“ to publish your local commit_雪落无尘处的博客-CSDN博客](https://blog.csdn.net/qq_53873381/article/details/131362061)
* [git报错fatal: unable to access ‘XXX‘: SSL certificate problem: certificate has expired_今天不要写bug的博客-CSDN博客](https://blog.csdn.net/weixin_52443895/article/details/125722500)



