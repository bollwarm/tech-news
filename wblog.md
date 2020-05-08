论文：《Breaking RSA Security With A Low Noise D-Wave 2000Q Quantum Annealer:Computational Times, Limitations And Prospects》（运用低噪声D-Wave 2000Q量子退火机破解RSA：计算时间，局限性和前景）
运行Shor的归一化算法的大型通用量子计算机是将来有望破解RSA密码系统的可能方法。但是量子计算机和算法目前仍处于处于起步阶段，用于整数分解的量子退火方法是目前业界关注的热点。该论文研究使用低噪声D-Wave 2000Q量子退火机为基础对当前硬件条件的局限性以及未来发展的挑战进行了广泛的研究，分析了通过量子退火破解RSA最有希望的策略。

https://arxiv.org/pdf/2005.02268.pdf
=====================================
微软发布20w美刀的赏金计划，破解Azure Sphere操作系统

Azure Sphere操作系统是基于Linux自定义高级紧凑的操作系统，并对应用程序进行了安全加强，用于集成整合硬件，软件和云端，藉此提供微软IoT端到端安全平台。此次赏金计划，包括两部分：

在Pluton上执行代码，赏金$100,000

AbSecure World执行代码，赏金$100,000

计划从6月1日开始，持续三个月。要申请加入黑客赏金计划，需要在5月15日之前提交其申请。

https://www.microsoft.com/en-us/msrc/azure-security-lab
========================================

由于新冠疫情大英博物馆线上免费开放190万张藏品图片

新冠疫情严重，许多人被困在家中，只能通过网络在线参观，大英博物馆新版本的在线数据库日前提前发布。
大英博物馆在线收藏包括很多著名的藏品的图像，比如罗塞塔石碑，萨顿胡的艺术品，赛勒斯圆柱，帕台农神庙雕塑和贝宁青铜器。记录包括物理描述，材料信息，相关的历史记录，尺寸，历史持有者和策展人评论。
一项重要的新功能是可以超近距离浏览藏品图像，可以在很多关键藏品使用该功能，包括Rapa Nui雕塑Hoa Hakananai'a和1600年前在中国制造的告诫卷轴。

此次，还新发布了280,000张新藏品的照片和85,000张新藏品记录，其中很多是博物馆近年来的收购，包括达米安·赫斯特（Damian Hirst）的73幅肖像画，罗塞蒂（Rossetti）先前遗失的水彩画，以及3,000张青铜时代吊坠。

大英博物馆根据知识共享4.0的许可协议免费公开了其190万藏品图片，用户无需要注册即可在线浏览和下载。

此次更新是自2007年首次创建以来，其线收藏的最大的一次更新。

https://www.britishmuseum.org/collection

====================================
BASH常见问题列表（FAQ）119例

囊括了常见的bash问题，支持多格式输出（纯文本，打印版以及Docbook），也可以添加修改（wiki），建议大家收藏学习。

https://mywiki.wooledge.org/BashFAQ/

==========================
论文：《Achieving reliable UDP transmission at 10 Gb/s using BSD socket for data acquisition systems》（《利用BSD soket实现数据采集系统可靠的10Gb/s的UDP传输》）

用户数据报协议（UDP）是小型嵌入式系统中数据传输的常用协议。UDP协议的不可靠的，可能会发生数据包丢失。如果不使用最佳数据包大小，可达的数据速率也可能会受到影响。业界更好多的选择是，传输控制协议（TCP），可以保证数据的有序交付，并自动调整传输以匹配传输链路的功能。但是，由于UDP的简单，占用内存小，指令控件小，通常比UDP更受UDP的青睐。比如即将到来的HTTP 2，就是基于底层的UDP协议的改进。
UDP和TCP都在所有较大的操作系统和商业嵌入式框架中被实现。另外，UDP还支持各种小型硬件平台，例如数字信号处理器（DSP）现场可编程门阵列（FPGA）。而TCP协议却没有。本文中介绍了如何以极低的丢包率实现基于UDP的高速数据传输。几乎可靠的通信链路用于下一代超高强度中子源欧洲散裂源的数据采集（DAQ）系统中。本文介绍了采用几种优化方法解决UDP性能和可靠性问题。在基于Xeon E5的CentOS（Linux）服务器上执行，传输速率可达到近10Gb/s，整改过程中零丢包。项目中通过使用单个处理器内核作为发送器和单个内核作为接收器来获得性能。结果表明，支持传输大数据包是实现良好性能的关键参数。 吞吐量的优化包括：MTU，数据包大小，调整Linux内核参数，线程亲和力，核心位置和高效的计时器。


论文下载地址：

https://arxiv.org/pdf/1706.00333.pdf

==========================

邮件中如何拒绝？How to say no.

三十一个Gmail模版帮你搞定一切情形下的拒绝需求（客户需求，约会，VC投资人等等）：分类不同情况，Pigeon制作可以一键导入Gmail

https://www.starterstory.com/how-to-say-no
==============
在繁忙的开发工作中，分支拉太多，是不是会忘记各个分支情况？

为了解决这个烦恼，我们提供一个命令：
```
git log -g --abbrev-commit --pretty=format:"%gs ~ %gd"  --date=relative| grep 'checkout:' | grep -oE '[^ ]+ ~ .*' | awk -F~ '!seen[$1]++' | head -n 10 | awk   -F' ~ HEAD@{' '{printf(" \\033[33m%s: \\033[37m %s\\033[0m \n", substr($2, 1, length($2)-1), $1)
```

`git log -g --abbrev-commit --pretty=format:"%gs ~ %gd"  --date=relative `获取原始的reflog数据，并对其格式化，数据显示为距今日期。
`grep 'checkout:' `过滤掉多余日志，只想是checkou的行。
`grep -oE '[^ ]+ ~ .*' ` 仅保留（-o）我们关心的行的一部分。
`awk -F~ '!seen[$1]++' `用~为分割符号字段。用数组seen每个字段增加计数，对大于则跳过，相当于取唯一（sort|uniq）
`head -n 10：`显示最先top 10。
`awk -F' ~ HEAD@{' '{printf(\"  \\033[33m%s: \\033[37m %s\\033[0m\\n\", substr($2, 1, length($2)-1), $1)}'`：用ANSI颜色颜渲染色重新格式化彩色显示。

为了方便使用，可以该命令加入别名
vim `〜/.gitconfig` 增加
```
[alias]
    binfo = !git reflog show --pretty=format:'%gs ~ %gd' --date=relative | grep 'checkout:' | grep -oE '[^ ]+ ~ .*' | awk -F~ '!seen[$1]++' | head -n 10 | awk -F' ~ HEAD@{' '{printf(\"  \\033[33m%s: \\033[37m %s\\033[0m\\n\", substr($2, 1, length($2)-1), $1)}'
```

然后就可以用`git binfo` 即可
===========
pgsync——#postgresql# 数据库数据同步工具。优势为：

速度-比4核计算机上的传统工具快4倍。
安全性-防止敏感数据离开服务器的内置方法。
便利性-同步部分表，表组和相关记录。

具体操作：

git clone https://github.com/ankane/pgsync.git
cd pgsync
bundle install

createdb pgsync_test1
createdb pgsync_test2
createdb pgsync_test3

bundle exec rake test

==================
WEB技能树，一栈工程师必备，前端大神秘籍，
https://andreasbm.github.io/web-skills/
=================
Visual Studio Code 1.43（2020二月版）发布，大量亮点：

搜索编辑器：在全尺寸编辑器中搜索并保存全局搜索结果。
可拖动的窗框角：拖动窗框角可轻松更改编辑器布局。
Linux屏幕阅读器支持：VS Code现在支持Orca屏幕阅读器。
小地图尺寸调整选项：可以适合或填充小地图垂直布局的新选项。
列选择模式：列模式切换可让我们快速选择文本块。
选择时显示空白：仅在所选文本中显示空白字符。
转换为模板字符串：将串联转换为JavaScript/TypeScript模板字符串。
JS/TS呼叫层次结构视图：查看到某个功能或从该功能发出的所有调用，并深入到回调者的调用。
设置同步预览：设置同步可让我们在计算机之间共享设置和按键绑定。

https://code.visualstudio.com/updates/v1_43
=======================
旧书插图（Old Book Illustrations）：在线数据库可以下载19世纪和20世纪的数千个插图。插图黄金时代通常可追溯至1880年至20世纪初期。这是书籍和杂志插图史无前例的卓越时期，这时期创作了大量的插图艺术品。在线数据库“Old Book Illustrations”已经对这成千上万个这类插图进行了分类，插图都是取自原始图书内容，并且可以通过艺术家姓名，来源，日期，书名，技术，格式，出版商，主题等进行搜索和浏览。

https://www.oldbookillustrations.com/
=========================
苹果Mac Pro技术白皮书

https://www.apple.com/mac-pro/pdf/Mac_Pro_White_Paper_Feb_2020.pdf

==========================
网友分享谷歌开发面试经历，主要是在线算法题，三面后最后还是挂了。[允悲]

https://habr.com/en/post/489698/
==========================================
//grep.app :Github项目搜索神器，支持对对50万Github仓库全文代码搜索，支持正则表达式！

https://grep.app/

============================================

Mozilla基于HTTPs上的DNS（DoH）
不安全的DNS系统导致的DNS劫持使全世界数十亿人容易受到攻击。2017年，Mozilla开始研究DNS-over-HTTPS（DoH）协议，用来实现网络基础架构中的安全。目前，Firefox在美国默认启用基于HTTPS的加密DNS。Mozilla关于 DoH一些常识：

=========================================
福利：BHL免费开放15万张自然世界精美插图下载：

生物多样性遗产图书馆（BHL）开放了其馆藏的与植物，野生动植物和生物多样性有关的图像和文件，收集的插图使用水彩画，石版画和黑墨线条，展示了数百年来观察到的地球野生动植物的多样性。BHL最早的文字可以追溯到1400年代中期，其数字收藏包括1900年代初最新创作的插图。

BHL在线地址：

https://www.biodiversitylibrary.org/
=====================================
《The Economics of Maps (地图经济学)》

几个世纪以来，人类在地图中编纂了地理知识。在中世纪，制图是一项重大的且具有经济意义的活动，而新地图是大发现时代使用的主要工具。现在，世界数字地图（例如Google Maps）已经成为数字技术的重要应用之一。数字地图不仅使人们能够访问实时交通和交通信息，而且还支持基于位置的创新，例如拼车应用，房地产门户和本地搜索引擎，并且是具有340-4000亿美元的核心投入的地理空间技术和位置情报行业...

https://pubs.aeaweb.org/doi/pdfplus/10.1257/jep.34.1.196

===============================
Nature Methods (2020)论文: 《SciPy 1.0: fundamental algorithms for scientific computing in Python.(SciPy 1.0：Python科学计算的基础)》


SciPy是Python开源科学计算库。自2001年首次发布以来，SciPy已成为Python的科学算法的事实标准，每年有600多个独特的代码贡献者，数千个依赖它程序包，超过100,000个依赖存储库和数百万次下载。本论文介绍了SciPy 1.0的功能和开发实践的概述，并重点介绍了一些最新的技术发展。

https://www.nature.com/articles/s41592-019-0686-2
=====================
Say Goodbye to CoreOS

CoreOS将于2020年5月26日停止维护。Redhat将采用Fedora CoreOS作为其官方替代，主要区别

Fedora CoreOS，没有Azure，Digital Ocean，GCE，Vagrant等原生支持或Container Linux社区支持。
CoreOS开发的rkt运行时不再支持。

https://thenewstack.io/say-goodbye-to-coreos/
================================
进化上保守的铁硫簇是叶绿体传感器激酶的氧化还原感觉功能的基础



Communications Biology第3卷，文章编号：13（2020）引用本文


光合效率取决于两个光谱不同的串联光系统的相等光能转换。位于两个光系统之间的质体醌库的氧化还原状态是​​启动光系统相对丰度变化的关键调节信号。叶绿体传感器激酶（CSK）将质体醌氧化还原信号与光系统基因表达联系起来，但其监测质体醌氧化还原状态的机制尚不清楚。在这里，我们显示纯化的拟南芥和拟杆菌CSK和蓝细菌CSK同源物，组氨酸激酶2（Hik2），是铁硫蛋白。 CSK的Fe-S团簇进一步显示是高电位的氧化还原响应[3Fe-4S]中心。 CSK响应氧化还原剂减少的塑料醌抑制其自身激酶活性。 CSK铁-硫簇内的氧化还原变化转化为蛋白质折叠的构象变化。这些结果为基于CSK的叶绿体两组分系统对氧化还原信号的感知和传播提供了重要的见识。

Communications Biology volume 3

https://www.nature.com/articles/s42003-019-0728-4
=============================
Herbert Wolverson的游戏编程教学，使用Rust开发Roguelike游戏之全程教学，从Rust 0开始上手游戏开发


http://bfnightly.bracketproductions.com/rustbook/chapter_0.html

=============================

科学家通过模仿自然机制发现可持续生产化学物质的新方法

由伦敦帝国理工学院的科学家首创的这项新技术可以减少使用化石燃料生产化学药品，塑料，纤维和燃料的需求。当前，许多有用的化学物质是由化石燃料生产的，需要开采，供应有限，并且破坏了碳循环。一种替代方法是工程改造诸如大肠杆菌（E. coli）和蓝细菌的微生物，以更可持续地直接从大气二氧化碳中生产化学品。但是，可以通过这种方式生产的许多化学药品对微生物有毒，从而降低了其以低成本方式大量生产的能力。现在，研究人员复制了自然有机体处理其自身有毒化学物质的方式，通过对细菌进行编程，使其产生化学物质而又不损害其生长。该概念可用于生产有用的化学药品，塑料甚至燃料，从而可以进一步减少对化石燃料的需求，并最大程度地减少气候变化。这项新技术和概念性验证在《美国国家科学院院刊》上发表。
植物和酵母之类的生物有时会产生对它们有毒的化学物质，为了安全地存储，它们会对化学物质进行少量改动以使其无害。生成的化学物质称为“衍生物”，可以通过相对简单的化学反应恢复为原始的有毒形式。该团队采用模拟这个处理过程，并利用基因工程技术对大肠杆菌和蓝细菌进行编程，生产1-辛醇，该化学物质对细菌有毒。然后，他们在大肠杆菌中添加了机制，将产生两种危害较小的1-辛醇衍生物。研究人员说，如果将其扩大到工业系统，工程菌将产生1-辛醇的无毒衍生物，然后将其回收并化学转化回1-辛醇，以备使用。
该团队已经展示了使用程序化微生物创建衍生物的概念，他们想要建立一个完整的系统，从衍生物的生产到所需化学物质的回收。

==========================================================
老论文：《Qmail的安全体系架构》

Qmail是Linux下最知名的邮件系统内核，大量著名的商业邮件系统都是在Qmail内核下开发，比如Hotmail、Qmail等。

Qmail安装方便、安全性高、邮件结构合理、支持SMTP服务、队列管理、邮件反弹、基于域名的邮件路由、SMTP传输、转发和邮件列表、本地(邮件)传送、POP3 服务等强大的功能。Qmail是面向安全而设计的，作者曾经悬赏500美元来找出Qmail的安全漏洞，但是直到2006年，还是没有人能领取这笔奖金。

Qmail的体系结构经过精心设计，可以克服Sendmail的安全性问题。Qmail不仅比Sendmail更安全，而且效率更高，更易于理解。Qmail的安全性基于几种模式，了解qmail的体系结构可以确保其他应用程序的安全。

本论文是介绍了Qmail的安全体系架构，是值得学习的文档之一。当然Qmail的源码也是学习编程的好材料，可以自己学习。

http://hillside.net/plop/2004/papers/mhafiz1/PLoP2004_mhafiz1_0.pdf
===============
俄罗斯国家断网测试成功，世界最大的私有网络RuNet可以在断开互联网（不访问全球DNS系统和外部互联网）后成功运作。

根据俄罗斯“互联网主权”法，俄罗斯政府可以“国家安全”为由，无理由可断开互联网访问。

https://www.zdnet.com/article/russia-successfully-disconnected-from-the-internet/
========================
Awesome圣诞树源码：

function u(t) {
for(i=c.width|=0;i--;x.fillRect(S(a=i+t)*r+960,i/2,C(a)>0&&C(a)*r/2,19))s=i<1500,r=s?i/3:99,x.fillStyle=`hsl(${s*88} 33%${i%S(i)*77}%`


}// 134/140

https://www.dwitter.net/d/11650       



=============
为什么你总是失败，而别人却总会成功？关键看如何面对失败处理！

Nature论文：《Quantifying dynamics of failure across science, startups, and security》（《基于科学课题申报、创业和恐怖数据库的失败的动力学机制研究》）
美国西北大学凯洛格商学院、复杂系统研究中心副教授王大顺等人发表。

在获取成就之前，人们通常会反复尝试失败，但对于控制失败动态的机制知之甚少。在先前关于创新，人类动力学和学习的研究的基础上，本论文开发了一个简单的单参数模型来模仿成功和失败尝试的关系。经过模型分析表明，失败的动力分为进展或停滞区域，并预测在临界阈值附近，具有相似特征和学习策略的特征在失败后可能会遇到根本不同的结果。在临界点之上，代理人利用渐进式细化来系统地取得成功，而在临界点之下，他们会探索没有任何机会的改进模式。该模型做出了一些可以通过经验检验的预测，表明那些最终成功的人和失败的人可能起点都相似，但是在与每次失败后尝试相关的效率和质量方面，具有根本不同的特征征。从三个不同的领域收集的大规模数据，并追踪了调查人员的反复尝试，以获取美国国立卫生研究院（NIH）的课题资助，创新者成功退出了创业公司，恐怖组织声称在暴力袭击中造成了人员伤亡。在所有三个领域中发现了广泛一致的经验支持，从而系统地验证了模型预测。总之，论文揭示了可检测但先前未知的早期信号，可使用模型能够确定将导致最终成功或失败的失败动力学特态。

论文地址：
https://arxiv.org/abs/1903.07562v1

研究的数据和模型代码：

https://yian-yin.github.io/quantifyFailure.

========================

机器学习论文：《Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model》（通过学习模型规划掌握雅达利游戏，围棋，国际象棋和将棋）

长期以来，构建具有计划能力的代理一直是追求人工智能的主要挑战之一。基于树的计划方法在具有挑战性的领域中取得了巨大的成功，例如国际象棋和围棋，构造了完美的模拟器。但是，在实际问题中，控制环境的动力学通常是复杂且未知的。在这项工作中，论文介绍了MuZero算法，该算法通过将基于树的搜索与学习的模型相结合，可以在一系列具有挑战性和视觉复杂的领域中实现超人的性能，而无需了解其基本动态。 MuZero学习了一个模型，该模型在进行迭代应用时可以预测与计划最直接相关的数量：奖励，行动选择策略和价值函数。当在57种不同的达利游戏（用于测试AI技术的规范视频游戏环境）上进行评估时，我们的新算法达到了最新水平。在不了解游戏规则的情况下在围棋，国际象棋和将棋上进行评估时，MuZero匹配了游戏规则附带的AlphaZero算法的超人性能。

https://arxiv.org/pdf/1911.08265.pdf
============================
科学家开发出超快充电大容量钾电池

Skoltech研究人员与RAS化学物理问题研究所和乌拉尔联邦大学的科学家合作表明，高容量，高功率的电池可以由不含锂或其他稀有元素的有机材料制成。此外，他们还展示了具有相当稳定新的正极材料，并开发除了高能量密度可快速充电/放电钾基电池。他们的研究结果发表在《材料化学杂志》和《物理化学快报和化学通讯》上。


https://phys.org/news/2019-11-scientists-superfast-charging-high-capacity-potassium-batteries.html

https://pubs.rsc.org/en/content/articlelanding/2019/CC/C9CC05745E#!divAbstract

https://phys.org/news/2019-11-high-energy-density-polymeric-cathode-fast-charge-sodium-.html



============
Let's Encrypt论文《Let’s Encrypt: An Automated CertificateAuthority to Encrypt the Entire Web》

Let's Encrypt是一个免费，开放和自动的HTTPS证书颁发机构(CA)，旨在全网推广普及HTTPS。自2015年推出以来，Let's Encrypt已成长为世界上最大的HTTPS CA机构，比所有其他浏览器信任的CA颁发的证书合计还多。。截止2019年10年，
Let's Encrypt累计为2.23亿个域名颁发了超过5.38亿份证书。本文描述了Let's Encrypt是如何构建的，包括CA软件系统（Boulder）的体系结构和其运维运营体系（ISRG），运营实践经验等。论文中还描述了自设计的IETF标准协议ACME，用来自动执行CA-服务器交互和证书颁发，并对各种生态系统ACME客户进行调查统计。还有广大用户熟识的自动化HTTPS部署签证软件Certbot。最后，通过统计数据，说明了Let's Encrypt
对Web和CA生态系统的影响。

http://delivery.acm.org/10.1145/3370000/3363192/p2473-aas.pdf?ip=203.86.67.130&id=3363192&acc=OA&key=4D4702B0C3E38B35%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35%2E2DBADA94993EBE7C&__acm__=1573696650_a52e4d02942eada45b3340a0669dfe14

================
Let's Encrypt论文《Let’s Encrypt: An Automated CertificateAuthority to Encrypt the Entire Web》

Let's Encrypt是一个免费，开放和自动的HTTPS证书颁发机构(CA)，旨在全网推广普及HTTPS。自2015年推出以来，Let's Encrypt已成长为世界上最大的HTTPS CA机构，比所有其他浏览器信任的CA颁发的证书合计还多。。截止2019年10年，
Let's Encrypt累计为2.23亿个域名颁发了超过5.38亿份证书。本文描述了Let's Encrypt是如何构建的，包括CA软件系统（Boulder）的体系结构和其运维运营体系（ISRG），运营实践经验等。论文中还描述了自设计的IETF标准协议ACME，用来自动执行CA-服务器交互和证书颁发，并对各种生态系统ACME客户进行调查统计。还有广大用户熟识的自动化HTTPS部署签证软件Certbot。最后，通过统计数据，说明了Let's Encrypt
对Web和CA生态系统的影响。

http://delivery.acm.org/10.1145/3370000/3363192/p2473-aas.pdf?ip=203.86.67.130&id=3363192&acc=OA&key=4D4702B0C3E38B35%2E4D4702B0C3E38B35%2E4D4702B0C3E38B35%2E2DBADA94993EBE7C&__acm__=1573696650_a52e4d02942eada45b3340a0669dfe14

=======================
Nature论文：《Light-Induced Charge Density Wave in LaTe3》（三碲化镧中的光诱导电荷密度波）

向任何材料添加能量（例如通过加热）几乎总是会破坏其分子间结构规则。例如，具有晶体结构的冰融化成液态水，会破坏分子结构变得无序。
麻省理工学院和其他地方的物理学家进行的新实验中，发现一种于此相反的现象：当某种材料中的一种称为电荷密度波的图案被快速的激光脉冲撞击时，就会产生一个全新的电荷密度波，这种新产生的波态是一种高度有序的状态，而非预期的无序态。该发现可能有助于揭示各种材料中看不见的特性。实验中使用了一种称为三碲化镧的材料，该材料自然状况下自身形成层状结构。在这种材料中，高密度和低密度区域中的电子呈波状图案自发形成，但仅限于材料内的单个方向。但是，当受到超快的激光脉冲，不到皮秒长（万亿分之一秒）的冲击时，该模式（称为电荷密度波或CDW）将被消除，而新的CDW与原始激光束成直角。。。

http://news.mit.edu/2019/light-orders-exotic-material-1111

https://www.nature.com/articles/s41567-019-0705-3

https://www.researchgate.net/publication/332463073_Light-Induced_Charge_Density_Wave_in_LaTe3

Nature论文：《Light-Induced Charge Density Wave in LaTe3》（三碲化镧中的光诱导电荷密度波）

向任何材料添加能量（例如通过加热）几乎总是会破坏其分子间结构规则。例如，具有晶体结构的冰融化成液态水，会破坏分子结构变得无序。
麻省理工学院和其他地方的物理学家进行的新实验中，发现一种于此相反的现象：当某种材料中的一种称为电荷密度波的图案被快速的激光脉冲撞击时，就会产生一个全新的电荷密度波，这种新产生的波态是一种高度有序的状态，而非预期的无序态。该发现可能有助于揭示各种材料中看不见的特性。实验中使用了一种称为三碲化镧的材料，该材料自然状况下自身形成层状结构。在这种材料中，高密度和低密度区域中的电子呈波状图案自发形成，但仅限于材料内的单个方向。但是，当受到超快的激光脉冲，不到皮秒长（万亿分之一秒）的冲击时，该模式（称为电荷密度波或CDW）将被消除，而新的CDW与原始激光束成直角。。。


https://www.nature.com/articles/s41567-019-0705-3

https://www.researchgate.net/publication/332463073_Light-Induced_Charge_Density_Wave_in_LaTe3

===============
NIH：小鼠研究解释了大脑如何使疼痛信号加强和减弱的机理

一项针对老鼠的新研究发现了中央杏仁核在提升或降低大脑回路疼痛信号中所起的未知作用。
这项研究发表在《细胞报告》上，由美国国立卫生研究院补充与综合健康中心（NCCIH）内研究部门的研究人员进行。

https://www.nih.gov/news-events/news-releases/nih-study-mice-explains-how-brain-can-turn-pain-signals-or-down


=============

Nature论文：《Search-and-replace genome editing without double-strand breaks or donor DNA》（无需双链断裂或供体的DNA基因组搜索和替换编辑）

大多数导致疾病的遗传变异很难有效纠正，而且过程中会有过多的副产物。该论文描述了“prime editing”方法，这是一种通用且精确的基因组编辑方法，它使用融合了工程逆转录酶的催化受损的Cas9将新的遗传信息直接写入指定的DNA位点，并使用主prime editing指导RNA（pegRNA）进行编程，两者均指定了目标站点并编码所需的编辑。
通过对人细胞中进行的175次以上的编辑，包括靶向插入，缺失和所有12种类型的点突变，编辑过程无需双链断裂或供体DNA模板。对人类细胞的“prime editing”可以有效地纠正镰状细胞疾病（要求HBB发生转化）和Tay-Sachs病（要求HEXA发生缺失）的主要遗传原因，并利用少量副产物在PRNP中安装保护性转化，并将各种标签和表位精确插入目标基因座。四个人类细胞系和有丝分裂后的小鼠皮层神经元原代以不同的效率支持“prime editing”。与基础编辑相比，优质编辑提供了效率和产品纯度方面的优势，与碱基编辑相比，具有互补的优势和劣势，并且在已知Cas9脱靶位点处的脱靶编辑比Cas9核酸酶低得多。原始编辑大大扩展了基因组编辑的范围和能力，并且原则上可以纠正约89%的已知致病性人类遗传变异。 

https://www.nature.com/articles/s41586-019-1711-4

===============================

3D打印技术新突破，可打印包括血管的活体皮肤：

纽约州特洛伊市伦斯勒理工学院的研究人员已经开发出一种3D打印具有血管的活体皮肤的方法，该研究论文在 Tissue Engineering Part A。 

该研究中他们使用3D生物打印技术制造可植入多层血管化生物工程皮肤移植物的过程。移植物是使用一种生物墨水形成的，该墨水包含人包皮真皮成纤维细胞（FBs），源自脐带血人内皮集落形成细胞（HECFC）的人内皮细胞（EC）和悬浮在大鼠尾巴I型胶原中的人胎盘周细胞（PC），形成真皮，然后用包含人包皮角质形成细胞（KC）的第二种生物墨水进行印刷以形成表皮。在体外，KC复制并成熟以形成多层屏障，而EC和PC自组装成相互连接的微血管网络。真皮生物墨水中的PC与EC内衬的血管结构相关可以改善KC成熟。当将这些3D打印的移植物植入免疫缺陷小鼠的背部时，人类EC内衬结构会与伤口床产生的小鼠微血管相结合，并在植入后4周内被灌注。3d打印的真皮中PC的存在增强了宿主微血管对移植物的侵袭，并增强了表皮网状组织的形成。

https://www.liebertpub.com/doi/pdf/10.1089/ten.TEA.2019.0201

========================

NASA论文：旅行者2号在星际空间发现了一个奇怪的，无法解释的边界

旅行者2号在太阳系边界（heliopause）以外发现了一个前所未知未知的边界。研究人员将该阈值称为“宇宙射线边界层”，因为它发出信号，表明探针经历了宇宙射线梯度的偏移，该梯度发生了来自太阳周围熟悉环境的典型的大范围外能量和低能粒子的移动。有证据表明旅行者1号也层遇到类似的宇宙射线边界层之一，但有趣的是，它位于太阳系边界内部。

https://www.nature.com/articles/s41550-019-0928-3.epdf?referrer_access_token=jJ600BccLuSWcJjJaELO2dRgN0jAjWel9jnR3ZoTv0OtRzPnygf9JV_qX0mcYV-YKYknNh3Simtn7Vee9moyywE6c9qRqB4MOnBbd8ZvfSOqNpyc9i9J38UOHF-mg-7iS0n9d24Z_u2XhapJ0QtkpRq1f3SyJb4s5tKz7YsD22DpqEOWzqloVy55RNC0p_XdkpGd_8AFvPfRPBB1nC1DmXxfWnkIotWDPRp6G_ZOPn93z93z1YBRKDQruqXr_3ufhs7Z_5StUDc4ubJTPX6O6tHIRTRzEZ6ZV7wcB-kIfwYDwrvL4lrVhrj2BTNwxkvt

==================

美帝加州森林大火在线地图

https://ucanr.edu/sites/fire/Wildfire_Health_-_Safety/Current/

==============

CEO生命周期：2019百强CEO，腾讯Pony ma 上榜

https://hbr.org/2019/11/the-ceo-100-2019-edition#the-ceo-life-cycle

=================

Science论文：麻疹感染可使之前打的疫苗实效：消灭免疫系统对其他疾病

根据Science论文 《Measles virus infection diminishes preexisting antibodies that offer protection from other pathogens》和Science Immunology论文《Incomplete genetic reconstitution of B cell pools contributes to prolonged immunosuppression after measles》

最新研究揭示儿童的麻疹感染可消灭免疫系统对其他疾病（如流感）的记忆。 这回到麻疹恢复后孩子容易感染其他病原体，而这些病原体原本通过疫苗或者感染病毒已经产生了抗体保护。


https://www.nature.com/articles/d41586-019-03324-7

https://immunology.sciencemag.org/content/4/41/eaay6125

================
