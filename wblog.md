《五眼联盟国家发布联合网络安全咨询》

“五眼”情报联盟中的各国网络安全机构发布了联合网络安全公告，用于针对网络安全事故调查和对恶意活动的技术应对手册。

目的：增强合作伙伴和网络之间的事件响应管理员以及事件的指导。

第一步部分，调查：

重要要点：解决潜在事件并使用最佳事件响应流程。

首先，收集并移走相关资料以便更进行进一步分析，包括相关应用，日志和数据。

其次，实施缓解步骤，避免事故夸大，以及被对手发现。

最后，考虑寻求专门IT安全组织的事件响应支持：

提供主题专业知识和技术的事件响应支持

....

https://us-cert.cisa.gov/sites/default/files/publications/AA20-245A-Joint_CSA-Technical_Approaches_to_Uncovering_Malicious_Activity_508.pdf
==================
一个虚拟的操作系统，桌面和应用集合，囊括了我们历史上出现过的所有操作系统及其桌面应用的，可以作为研究也可以用来怀旧。

https://simone.computer/#/webdesktops
=========================================================
Rust语言之旅，在线学习，在线build和执行，一边学习，一边就可以执行，查看结果。
支持多种语言，其中也包括中文，是Rust语言初学者的良师益友！

https://tourofrust.com/TOC_zh-cn.html


========================================================

《Concentrating Solar Power Best Practices Study》 （聚光太阳能最佳实践研究）

聚光太阳能（CSP）行业的根源是1980年代开始在加利福尼亚州的LUZ抛物线槽式开发。
LUZ建造了九座工厂，这些工厂展示了CSP技术的早期商业应用，为将来的CSP系统开发提供了重要的知识来源。
在过去的15年中，CSP行业已经出现并发展成为全球性行业和供应链。
CSP工厂已在12个不同的国家/地区建立，目前该行业（截止2020年）将有在全美将有100座工厂投入商业运营。
许多公司，实验室，机构和个人在这种可再生电源的发展和增长中发挥了重要作用。


本文提供了大量实践范例，可用于以更低的项目成本和改善的长期工厂运营来开发更强大的CSP项目。


https://www.solarpaces.org/wp-content/uploads/Concentrating-Solar-Power-Best-Practices-Study.pdf
======================
Uber开源工具可自动清理过时的代码的工具食人鱼（Piranha）

Uber开源了其内部使用的自动化清理工具食人鱼（Piranha），他可以在管道中运行，以不断寻找要删除的过时代码。目前，Piranha支持Java，Swift和Objective-C项目。有一些开放性问题需要增加对其他语言（如Kotlin，.NET和JavaScript）的支持。
使用静态分析，Piranha执行三个关键任务：

删除功能标记API周围的代码；
删除由于上一步而变得不可访问的代码；
最后删除与该标记相关的所有测试。


要执行食人鱼，需要三个输入：

正在考虑的标志，处理行为以及标志的所有者。

例如，考虑以下包含功能部件标志的Java代码段：

public class MyClass {
  private XPTest expt;
  ...
  public void foo() {
    if(expt.flagEnabled(TestExperimentName.SAMPLE_STALE_FLAG)) {
        System.out.println("Hello World");
    }
  }

  public void bar() {
    if(expt.flagDisabled(TestExperimentName.SAMPLE_STALE_FLAG)) {
        System.out.println("Hi World");
    }
  }
}

可以使用下面参数调用食人鱼：

options.errorprone.errorproneArgs << "-XepOpt:Piranha:FlagName=SAMPLE_STALE_FLAG"
options.errorprone.errorproneArgs << "-XepOpt:Piranha:IsTreated=true"
options.errorprone.errorproneArgs << "-XepOpt:Piranha:Config=config/piranha.properties"


结果如下所示：

public class MyClass {
  private XPTest expt;
  ...
  public void foo() {
     System.out.println("Hello World");
  }


  public void bar() {
  }
}

项目Github地址为，开源协议为Apache 2.0.

https://github.com/uber/piranha/

有关项目的论文也公开了

https://github.com/uber/piranha/blob/master/report.pdf

===========================
[安全论文]2500例Docker Hub镜像安全漏洞态势分析

在过去的几年中，以Docker为领先的容器平台、容器技术的被广泛地采纳和使用。Docker用于公共可用容器镜像的在线存储库称为Docker Hub，目前Docker Hub中托管超过350万个的镜像，是世界上最大的容器镜像服务站点。

本研究对Docker Hub中广泛使用的2500个Docker映像进行漏洞分析。
漏洞态势是一个快速变化的类别，漏洞扫描程序正在不断开发、更新、发现新漏洞，Docker Hub上的映像量每天都在增加。

本研究的主要发现表明：

（1）Docker Hub上新引入的漏洞数量正在迅速增加；
（2）认证的镜像最容易受到攻击；
（3）官方镜像最不容易受到攻击；
（4）漏洞数量与镜像特征之间没有关联（即，pull数，start数和最后更新的天数）；
（5）最严重的漏洞来自于两种最流行的脚本语言JavaScript和Python；
（6）Python 2.x程序包和jackson-databind程序包包含了最多的严重漏洞。

该研究是最近几年公开文献中发布的最广泛的漏洞分析。


https://arxiv.org/pdf/2006.02932.pdf


========================================

逆向工程任天堂游戏机Game Boy和Game Boy Color的电路，并比较其音频放大器芯片

Game Boy（1989）和Game Boy Color（1998）使用定制放大器芯片。通过对两者电路进行反向工程，两者音频芯片在两个主要方面与普通放大器芯片不同。首先，每个芯片具有三个放大器：两个用于耳机通道，一个用于扬声器。其次，为了节省功率，该芯片具有根据是否插入耳机来关闭未使用的放大器的电路。对芯片进行反向工程也可以解释Game Boy和Game Boy Color之间的声音差异。Game Boy Color的芯片实现了高通滤波器，因此声音很细，没有Game Boy的低音。

http://www.righto.com/2020/06/reverse-engineering-and-comparing-two.html

===========================
破解了元素周期表中的难题，科学家发现氮的同位素black nitrogen （黑氮）

元素周期表以重复的周期排列，其中每一列均由具有相似属性的化学元素组成（比如氮族，惰性气体）。其中最顶部的元素那些具有最小的质子数和原子量。

在高压条件下，顶层的化学元素通常存在元素相同但是结构不同的同素异形体，比如臭氧是氧气的同素异形体，而石墨和金刚石都是碳的同素异形体。根据元素周期表一直有一个困惑的问题：未能找到氮的同素异形体。

氮没有类似的元素，只有一种同素异形体，即二氮形态的氮气。氮气（红色）被认为没有同素异形体，其结构与该族中较重的元素（磷，砷，锑和铋（绿色））相似。

新研究破解了这个一直以来的困惑——发现了氮同素异形体。背景中的蓝色图表示这种新的同素异形体的结构，称为黑氮。
为了创造新的形式，研究小组将氮气暴露在极高的热量和压力下。它被压在两颗钻石之间，压力达到140万大气压，温度超过4,000°C（7,232°F）。在这些极端条件下，氮气呈现出前所未有的结构，但看起来仍然很熟悉。
当使用X射线成像时，氮原子形成结晶的二维层，以锯齿形交联。它似乎具有良好的导电性，就像石墨烯一样，可以使其在未来的电子设备中有用。


由于其与黑磷（相关元素磷的同素异形体）的相似性，研究小组将这种新材料称为“黑氮”。该研究的主要作者多米尼克·兰尼尔（Do​​minique Laniel）说：“测量数据突然为我们提供了黑磷的结构特征，我们对此感到惊讶和好奇。
此后的进一步实验和计算证实了这一发现。这意味着毫无疑问它：实际上，氮不是一种例外的元素，但遵循与碳和氧相同的元素周期表的黄金定律。”

黑氮对于电子产品可能具有很大的潜力，但是也不要期望很快在智能手机中找到它。由于上述那些极端条件，不仅很难生产，而且材料本身仍然不稳定，并且在放热和加压时会迅速溶解。兰尼尔说：“由于这种不稳定性，目前工业应用尚不可行。” 
“尽管如此，氮气仍然是材料研究中非常有趣的元素。我们的研究以举例的方式表明，高压和高温会产生研究人员以前不知道的材料结构和特性。”

该研究近日发表在《Physical Review Letters》（物理评论快报）上。

=========================

Postgres发展史：约瑟夫.海勒斯坦的《Looking Back at Postgres》(回顾Postgres)

论文回顾了UC Berkeley Postgres项目的发展历史，Postgres数据库由Mike Stonebraker在1980年代中期到1990年代中期领导开发。这篇文章是为Mike Stonebraker的图灵奖书而征集的，论文结合了多人/历史回忆。 因此，它专注于Stonebraker的设计思想和领导才能。但是由于Stonebraker不是开发人员。 Postgres代码库是一个由一群才华横溢的学生和少数职业码农组成的团队的工作，他们的经验（仅略多于学生）多于学生。


https://arxiv.org/pdf/1901.01973.pdf

===========================

免费的reCAPTCHA数据集资源下载

最新有为国外的开发小哥在Github上公开了自己的大量reCAPTCHA图片数据集。

数据集由最受欢迎的3×3 reCAPTCHA组成。例如，自行车，桥梁，公共汽车，汽车，人行横道（或英国人的行人过路处），消防栓，山地或丘陵，棕榈等。数据集包含“其他”文件夹，该文件夹包含未分类的图像，或随机对象。

由于数据集较大，可以先先下载样本图像，看数据情况再斟酌下载。

数据集有11774张图片，大小400 MB

https://github.com/deathlyface/recaptcha-dataset


如果github下载满，又过路群众提供了磁力链：

magnet:?xt=urn:btih:a514f6cd6b71ba97905f2334ea158a130e972697&dn=reCAPTCHA+Dataset.zip

========================

Gaia-X技术架构白皮书发布（BMWi），干货满满！
Gaia-X项目是——有德法等欧洲国家发起的泛欧洲市场的云计划——旨在建立一个安全的数据基础架构，以减少欧州国家对AWS、微软和谷歌等美国云厂商的依赖。项目由非盈利的成立在比利时的GAIA-X基金会（GAIA-X Foundation）管理和推进，计划将采用开放架构，邀请所有欧洲的国家一同参与，以支持欧洲数字生态体系的开发，推动以资料驱动的各式创新服务与应用，最终目标是创建具备交互及可携能力的架构、资料与服务，且奠基在高度的用户信赖上。

https://www.heise.de/downloads/18/2/9/0/6/1/1/7/gaia-x-technical-architecture.pdf

=====================

二战期间，雷达还未发明之前，为了定位战机，军方采用一些奇形怪状的貌似乐器的工具来进行战机声音定位探测来袭提防战机。这些雷达先驱，被称为"战争塔布"或"声音喇叭"，在一战期间首次被法国和英国用来发现德国泽佩林飞艇。

日本声学定位器，也称为"战争图塔斯"。该设备的常见配置垂直排列了三个喇叭，另一个在侧面加上一个。三组中央一架和横向的一架用于获取飞机的轴承，其余两架用于估计飞机的高度。操作员会通过听诊器收听和倾斜喇叭，直到他们得到最响亮的声音。
贾德金斯说："这样，你就会给出方向，只需进行一点三角测量，就会给你飞机的高度。
 
声音定位器在前线附近与高射炮一起使用，但其射程仅限于几英里。这样敌机实际被击落的次数都很少。

声镜：为了获得更好的范围，英国人还试验了一种静态的声音定位器，由混凝土制成，形状像盘子或弧形墙，被称为"声镜"。这些试验在第一次世界大战期间首先在英国南部和东部海岸试用，然后在整个20世纪20年代和30年代在十几个地点建造。它们直径高达30英尺（9米），但位于伦敦东南60英里的肯特郡，一面墙形的墙形，长200英尺（61米）。包括德国、日本和美国在内的许多其他国家也在开发声音定位器。

   https://edition.cnn.com/style/article/war-sound-locators-before-radar/index.html


=============

自己玩着写一个JVM，实例：

https://zserge.com/posts/jvm/


====================

#HackerOne# 宣布累计向白帽子支付1亿美刀的赏金

Bug赏金平台HackerOne日前宣布，它已向全球白帽黑客支付了1亿美元的奖励。据平台开放以来，累积发现了17 万个多安全漏洞。平台注册有超过70万名的白帽子，有1900多HackerOne客户为bug买单。累计由此挽回数百亿美刀的损失。

根据统计HackerOne赏金数目逐年翻倍上升，从2014到2016有1000万美刀，2017年至2019年的3000万美刀。而从19年第二季度至2020年第二季度达到了5000万美元，一年内超过了历史总和。
HackerOne每年有12%白帽子赏金超过20,000美刀，有3%的白帽子赏金超过100,000美元，有1.1%的白帽子赏金高达350,000美元。
2019年8月，HackerOne还宣布，使用其平台的八名黑客已成为百万富翁，其中19岁的Santiago Lopez是2019年3月第一位收入超过100万美元的黑客。

======================

在线学基因  世界知名大学美国犹他大学 utah.edu的在线开放网站，基因学习learn.genetics 提供了大量高品质的学习材料，值得生物，医学，植物类同学学习。


    https://learn.genetics.utah.edu/
    

=====================

盲人福音 CELL 最新论文《Dynamic Stimulation of Visual Cortex Produces
Form Vision in Sighted and Blind Humans》（《视觉皮层的动态刺激产生有视力和盲人的视觉形态》）表明，可以用现代技术产生电脉冲模式传递到大脑设计视觉处理的部分后，就可以“阅读”字母

盲人失明通常是由于眼睛或视神经收损伤，通常大脑视皮层（处理视觉信息的大脑区域）是完好的。对这类盲人，通过电刺激视觉皮层的不同部分会触发闪光，就使大脑能够创建可识别的图像。但是图像通常是无形的。

得克萨斯州休斯敦贝勒医学院的丹尼尔.约索尔（Daniel Yoshor）和他的同事们发明了一种类似于在手掌上描绘对象轮廓的方法。该技术以模拟字母“ N”或“ Z”形状的顺序发射短脉冲。在试验中，有2位失明的人正确地识别出80%的“显示”字母。研究人员说，同样的方法也可以用来追踪房屋和汽车等常见物体的轮廓。

https://www.cell.com/cell/pdf/S0092-8674(20)30496-7.pdf
=============
论文：《Adversarial Light Projection Attacks on Face Recognition Systems:A Feasibility Study》（脸部识别系统的对抗性光投射攻击：一项可行性研究）

研究表明，基于深度学习的系统在数字和物理领域都容易受到对抗性攻击。尽管可行，但数字攻击在攻击已部署的系统（包括面部识别系统）中的适用性有限，在这类系统中，攻击者通常需要输入而不是传输通道。在这种情况下，直接通过输入通道提供恶意输入的物理攻击会带来更大的威胁。
本论文研究了使用对抗性光投射对面部识别系统进行实时物理攻击的可行性。攻击者使用包含市售网络摄像头和投影仪的装置进行攻击。通过使用变换不变的敌方模式生成方法，使用敌方可用的目标的一个或多个图像来生成数字对抗模式。然后，将数字对抗模式投射到物理领域中对手的脸上，以模仿目标（假冒）或逃避识别（迷惑）。
在50个主题上使用两个开源和一个商业人脸识别系统进行了初步实验。实验结果证明了人脸识别系统在白盒和黑盒场景中容易受到光线投射攻击。

https://arxiv.org/pdf/2003.11145.pdf
================
Rust语言是未来趋势，Rust改造世界，除了Linux内核和Windows内核都提供Rust的原原生开发接口外,Rust社区也正在推出大量的优质工具轮子。下面给大家推荐一些常见的符合 POSIX的命令工具的Rust替代者:

cat ➞ bat
https://github.com/sharkdp/bat

du ➞ dust
https://github.com/bootandy/dust

find ➞ fd
https://github.com/sharkdp/fd

find ➞ skim
https://github.com/lotabout/skim

grep ➞ ripgrep
https://github.com/BurntSushi/ripgrep

ls ➞ exa
https://the.exa.website

ps ➞ procs
https://github.com/dalance/procs

sed ➞ sd
https://github.com/chmln/sd

time ➞ hyperfine
https://github.com/sharkdp/hyperfine

top ➞ zenith
https://github.com/bvaisvil/zenith

wc -l ➞ tokei
https://github.com/XAMPPRocky/tokei

也许还有很多，大家可以回复大家比较中意用Rust编写的工具。


==========================
Turning Noise Into Signal: Using AI to Gain Context for Scientific Research （将噪声转化为信号：使用人工智能获取科研背景）

Josh Nicholson是scite（www.scite.ai）的联合创始人兼首席执行
