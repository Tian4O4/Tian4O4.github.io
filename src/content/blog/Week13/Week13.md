---
title: 周记 Week13
description: 2025-12-29 ~ 2026-01-04.
publishDate: 2026-01-04
tags:
  - Weekly_Journal
  - Python
  - memoir
heroImage:
  src: ./Week13.jpg
  alt: an image targetting my article
  color: "#B4C6DA"
---
新年快乐！

## 近况
这一周没有课，主要精力都放在了复习上，可能也没有太多可以写的，但还是简单总结一下。

首先来看看上周定下目标的完成情况。复习方面，已经完成了有期末考试的四门课的课本内容复习和记忆唤醒，这部分的目标算是圆满完成了，接下来就是在每门考试的前几天尽可能多的做相关题目和总结了。Deep Learning学习方面，只完成了所有内容的25%左右。主要还是因为前段时间闲下来之后有一些躺平，这周不少时间用来逐渐找回状态。好消息是，目前的状态相较于一周之前，已经有了很大的改善。长跑运动，这周有一半多的时间在下雪，确实也没有办法完成。

在考试周之前，第八周结课的 *程序设计基础* 课程的成绩也出来了。整体上大家的成绩较往届有所上升，但自己的成绩只能说勉强说得过去。主要的原因在之前的周记里面也提到了，机试准备阶段忽视了一些细节问题，导致机试时候心态出了问题，没有做得太好。比较可惜的是距离90分差了一点点，至今还是没能收获进入西交后的第一个90+成绩。

以上就是最近一周能回忆起来的主要内容了，总体而言，一切都在往好的方向发展。

## ROT 13
ROT 13，全称rotate by 13 places，是凯撒密码的一种变体。提到这个主要是因为最近在无意中找到了 *The Zen of Python* 的源代码。与我所预想的简单的输出一段文字不同，该源代码使用了ROT-13进行加密，使我第一眼看到源码内容时还有些看不懂。后面进行了一些学习，发现ROT-13其实是一种凯撒密码的变体，他的基本加密思路是把大小写字母替换为他们在字母表上13位后的对应字母，超出26的范围则绕回开头的字母a/A继续计算即可。这个算法的巧妙之处在于由于13是26的一半，因而加密与解密使用的算法是一样的。

该加密方法以前主要是用于英文网络论坛来隐藏一些不便于直接展示的文字，比如脏话、妙语等，逃过管理员的简单审查。这样的历史还是挺有趣的。

后来也是突发奇想，直接采用了该源代码的内容，写了一段新年祝福发送给若干好友，这里将代码记录下来，留作纪念，也希望大家能够在新的一年里得偿所愿。值得一提的是，为了保持原有 *The Zen of Python* 的形式，这里采用模块化的思想，将代码分为了两个文件，并且最终通过类似于import this的方式执行代码。

加密和解密的思路大体上是先构建了明文和密文的对应关系的字典d，然后利用字典，对于密文进行翻译。

```python
# FileName: HappyNewYear.py
s = """Unccl Arj Lrne, ol Gvna

Vs lbh frr gurfr jbeqf fhpprffshyyl, pbatenghyngvbaf, jung lbh ner ivrjvat vf gur erfhyg bs EBG13 qrpelcgvba.
Un, vg vf whfg n yvggyr gevpx juvpu fvzcyl hfrf gur fnzr nytbevguz nf Clguba'f snzbhf guvf zbqhyr (Mra bs Clguba).
V ubcr lbh yvxr guvf gevpx.

Bbcf, V arneyl oynaxrq ba jung V jnf tbaan gb fnl bevtvanyyl.
Unccl Arj Lrne 2026!
Jvfuvat lbh tbbq urnygu naq qernzf shysvyyrq.
Nobir nyy, fgnl cher --- vg'f ernyyl vzcbegnag naq cerpvbhf.
Jung jr xabj nf TBNG ner nyjnlf crbcyr bs nofbyhgr chevgl.
Lbh pna frr guvf va fcbegf, yvxr fbppre, naq vg nccyvrf gb bgure svryqf, gbb.

Gurfr ner whfg fbzr gubhtugf V'ir unq erpragyl.
V qba'g jnag gb ynl ba gbb zhpu jvfqbz gbqnl.
Yrg'f jevgr qbja bhe jvfurf sbe 2026, naq purpx jurgure gurl'yy pbzr gehr va gur raq bs 2026.

Unccl Arj Lrne!"""

d = {}
for c in (65, 97):
    for i in range(26):
        d[chr(i+c)] = chr((i+13) % 26 + c)

print("".join([d.get(c, c) for c in s]))
```


```python
# FileName:2026.py
import HappyNewYear
```

以上是源代码，程序运行后的内容如下，也算是我的一些新年祝福了。

*Happy New Year, by Tian*

*If you see these words successfully, congratulations, what you are viewing is the result of ROT13 decryption.
Ha, it is just a little trick which simply uses the same algorithm as Python's famous this module (Zen of Python).
I hope you like this trick.*

*Oops, I nearly blanked on what I was gonna to say originally.
Happy New Year 2026!
Wishing you good health and dreams fulfilled.
Above all, stay pure --- it's really important and precious.
What we know as GOAT are always people of absolute purity.
You can see this in sports, like soccer, and it applies to other fields, too.*

*These are just some thoughts I've had recently.
I don't want to lay on too much wisdom today.
Let's write down our wishes for 2026, and check whether they'll come true in the end of 2026.*

*Happy New Year!*

## 关于2026
我预想中的2026年，还是会发生很多重要的事情的。不妨在一年刚开始的时候，写下一些希望达成的目标，一年之后，看看能否实现。
- 完成人工智能基本必要知识体系的自学
- 阅读50篇相关论文
- 加入浙大相关课题组，开始科研训练
- 每天学习非当前本科课程内容至少四小时 
- 坚持每周写周记
- 了解并参与更多开源项目，完善个人博客网站
- 综测成绩进入学院前20%，获得大学奖学金
- 每周跑步至少两次，单次距离大于一公里
- 交到大学阶段的第一个真正的朋友
- 做一个纯粹的人

以上大致就是能够想到的全部内容了，希望到了今年结束时，回过头看，能有一个好的结果。

总而言之，最近还是在慢慢调整状态的过程中。下周开始就是考试周了，愿一切顺利。祝大家新年快乐，身体健康，得偿所愿。[^1]

---

[^1]: Hero Image:https://www.pixiv.net/artworks/139487059