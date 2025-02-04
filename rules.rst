============================================
工作守则速查
============================================

本节列举了一些在我的团队中工作默认遵守的原则（强制要求）。
绝大部分原则是不区分实习生（intern）和正式员工（staff）以及具有自治和指挥权的领主（lord）的。

我所组建和管理的团队，一般采用精英自治模式。
这要求每一位成员都具有高度的自主性、高度的技术能力和自我管理意识，同时能够同团队其他成员、以及整个团队实际要达到的目标出发进行事态分析和预测执行。

对于实习生而言，我内心并不想要降低要求。我相信优秀的人不是顿悟然后战斗力爆炸的，是通过长年累月的积累形成的。
注意，请注意，这里有一个误区。或者换个说法，现在我要开始揭示一个你可能从未认识到的事实：
这些我很珍视的品质，这种在劳动力市场上难能可贵的能力，并不需要任何超过平均值的智商、情商、数学功底、计算机功底、抑或其他任何需要痛苦自律才达到。
相反的，完全相反的，这些珍贵的品质，是需要对接下来我列出来的这些看起来微不足道的原则的遵守。

成为我的团队的一员，长期的那种，一个必须的前提是 **Be Humble**，谦卑。毕竟，
要相信只要遵守这些看起来是鸡毛蒜皮的守则就可以成为我刚才提到的顶级优秀的人才，并不是很容易。

原则 01 任何会议均要有纪要
================================================

没有会议纪要的会议或谈话，不曾发生过。

原则 02 任何任务均要有计划和记录
================================================

内部系统没有记录的任务，没有发生过。


原则 03 Learning By Teaching
================================================

以下原则是对所有成员（实习生、学生和员工）普遍适用的：

1. 任何学习过程本身不是目标，也不能作为交付内容。（不然就应该是反过来我来收培训费啦😄）
2. 未能讲授分享的知识，未能掌握。也就是说，没学会。

原则 04 没有版本控制的代码皆为尸体
================================================

任何离开 git repo 的代码，都是尸体（corpus）。

原则 05 任何非官方下载的软件二进制都有后门
================================================

是真的。严谨百度网盘或者X网盘下载。如果下载速度慢或者被墙，找mentor。

原则 06 严格遵守开源代码版权和LICENSE
================================================

做学生的时候，一般的工作流程是，有一个问题，分析，Google下代码，复制粘贴，修改。 It works，交作业。

但是做项目的时候是严格禁止直接复制粘贴的：没有标注引用出处的代码复制会被看成抄袭行为，
这在商业软件开发中是很严重的。这点尤其需要引起重视。

一般性的原则是，如果引用了他人的代码，首先需要检查是否LICENSE是跟你正在做的项目的LICENSE是相容的。

如果相容，那么引用的时候，需要注意保留作者的CREDITS。也就是说，如果是文件使用，本身有文件头声明，
那么要保留；如果是引用很少的片段，那么在注释中指出URL。如果是软件包使用，需要在CREDITS中进行致谢。

一般而言，模块级别的使用，放在 third_party 目录下，同时在CREDITS中致谢。而小的代码改动，则通常是自己理解了之后重写。

Jay Michaelson 的这篇文章是所有员工和实习生的必读：

There's no such thing as a free (software) lunch
What every developer should know about open source licensing

`<https://queue.acm.org/detail.cfm?id=1005066>`_

原则 07 只使用、无改动的工具不要放在 git repo 中
================================================

对于不修改只是用的软件，使用脚本自动下载和解压缩而不是放在 git repo。

例如交叉编译，要使用到 arm-linux-gcc-8 的某一版本的编译器。只是使用，不进行修改。这种情形是跟代码LICENSE没关系的，最好是按照脚本下载压缩文件，然后解压缩的形式。

这样【仓库中只有你写的下载-解压缩脚本，是没有这个编译器tar包的】。

.. code:: bash

    if 本地没有tar名字
        从URL下载
    # 保证有了
    if 有目标目录了
        删除这个目录
    tar tar文件 to 目标目录


一个有用的链接：
`<https://tinylab.org/prebuilt-cross-toolchains/>`_

（FIXME：原则07的交叉编译器的内容或许可以放在tips）

原则 08 避免「这个、那个、上次、昨天」等模糊指代
================================================

模糊指代也是歧义指代，是指说的代词可以指向一个客体集合而不是唯一的客体对象。

一个检测方法是将提到了指代的话单独拎出来读一遍，看看是否可以脱离聊天上下文成立。

提到软件，最好有具体的版本号，或者tag，或者 commit id；

提到任务，最好有 issue number 或者 T id；

讨论问题，先在GitHub或y站进行记录，然后贴url，再开口讨论。

原则 09 避免使用「你」在对话中
================================================

不管是中文语言还是英语还是日语，直接使用「你/you/あなた」都是带有隐含的对抗性质的。同时，「你」也会导致文字内容复制转发的时候会需要重新编辑。
改写的方式有很多种，要看具体的上下文。一般是有意识的规避几次就好了。一个通用做法是直接写名字，「我（名字）这边」怎么怎么样，「X这边负责」怎么怎么样，类似。


原则 10 禁止在项目开始的时候就用话语给自己寻找退路
============================================================

语言能够塑造人的行为，并在思维上给自己预期的失败寻找理由。

在项目的开始的时候，即使你的内心是这么想的，有些话也是不可以说出来的。以下是一些在PLCT被要求禁止说出来的话。

**例子1: 隐式推卸责任**

（当接到一个新任务和交付时间节点的时候）

「这个事情我之前没有接触过。我先看一看。」

实际上表达的潜台词：

「我不想对能否按时交付负责。我也不对结果负责。如果到了交货日期我交付不了，那要怪mentor自己。因为，我已经一开始就告诉mentor了。」

**例子2: 隐藏现状的说话方式**

当对一个事情进行解释的时候，使用了 「现状是A，因为B」的句式。在说出了A之后，非常快速的说「因为」。

这种情况，一定是在隐藏自己对A的陈述。

作为 mentor，应该立刻打断陈述，要求重复陈述A句，并仔细分析现状。不要分析原因。先确定现状。当出现这种情况的时候，就说明 **一定是出现了坏消息** 。
mentor/lord 是对项目交付最终负责的人，而不是 intern。 所以，身为 mentor 需要有这个能力。

**例子3: 模糊进展的说话方式**

在对工作进展进行描述的时候，采用大量的好像、可能、大概、应该是的说法去描述细节，不明确的表明进展情况。

这种情况是潜意识的逃避对目前的进展做说明，将进展掩盖在大量模棱两可的细节之中，会给合作伙伴和主管造成极大的困扰，造成实际进展不可见。
这种情况之下，通常进展已经不可控。

作为 intern 和 staff，以此为镜子自我观察。这几条例子都是非常、非常常见的，而且多数人已经形成了（很难改掉的）习惯。

在PLCT，不承担责任或者隐含的隐瞒坏消息是会被 wuwei 立刻抓住的。

要么改掉，要么离开PLCT。

原则 11 及时响应同事的ping，邮件每日查看
================================================

我们多数都是远程工作。远程工作的重要前提之一是及时响应。

不能在工作时间及时响应同事的成员，会拖累同事和项目。

如果做不到，要么调整成为 solo 工作方式，要么离职，不管是员工、兼职还是实习生。
