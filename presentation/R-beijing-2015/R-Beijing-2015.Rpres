Rabix: 基于docker的可重复流程解决方案
========================================================
author: 殷腾飞@第八届R会议@北京
date: 2015-06-07


梗概
===
- 生物信息数据分析流程面临的5大难题
- Docker 简介
- Common Workflow Language 简介
- Rabix: Portable Bioinformatics Pipeline
- 实例






源码分享是大势所趋
===
- 把代码放在github，ftp
- 作为文章发表的附件
- 藏在不知道什么鬼地方。。。
![](./figure/sharing.png)



难题1：神烦的系统依赖
========================================================
<center><img src="./figure/dephell.png" style = "width:50%"></center>

难题2：分析流程复杂不利于开发和分发
===
<center><img src="./figure/pipeline.png" alt="Drawing" style="width: 100%; height: 100%"/></center>

难题3：流程不易重复
===
<center><img src="./figure/nuuh.jpg" alt="Drawing" style="width: 80%"/></center>

难题4：文章审阅困难
===
<center><img src="./figure/cartoon_mini.jpg" alt="Drawing" style="width: 80%"/></center>

难题5：缺乏成熟的国际标准
=== 
<center><img src="./figure/standard.png" style="width: 80%"/></center>

Nature: 科学软件可重复的重要性
===
<center><img src="./figure/nature1.png"  style="width: 60%"/></center>
- 4月7日起同行审稿杂志要求评估计算分析中的算法和文档
- 探索是否可以通过使用类似Docker的服务来测试复杂代码
- 高质量审稿人难觅，需要跨领域知识背景
- 社交尴尬：大部分作者会觉得代码被人查出错会很尴尬
- open sciense + open research： 不仅仅是“获得”，更重要是可重复和可扩展性


Nature: 精准医疗需透明化计算方法
===
<center><img src="./figure/nature2.png"  style="width: 60%"/></center>
- 精准医疗大热，数据易得，可分析并不简单
- 基因组虽然不大，但0.1%的不同就是几百万的变异
- 商业公司不大愿意公开方法，测试数据和性能评估细节
- 所谓精准医疗必需“证据为王”
- 需要benchmark系统既保证商业利益，又可以进行有效评估



肿么办？
===
<center><img src="./figure/how.jpg"  style="width: 80%"/></center>


应用带到数据端
===
<center><img src="./figure/alg2data.png"  style="width: 100%"/></center>
- 数据在云端，应用轻量围绕在数据周围
- 灵活，便捷，易重复


容器化你的工具：使用Docker
===
<center><img src="./figure/docker.png" style = "width = 80%" ></center>
> 关于Docker你只知道两件事情。首先，它使用linux容器；第二，互联网会一直对它喋喋不休。
>
> ---Solomon Hykes, Docker CEO

Docker风暴
===
<center><img src="./figure/docker-thankyou.jpg" style = "width = 100%" ></center>


Docker简介
===
- 2013年3月：Docker 0.1发布
- Docker 是 Docker.Inc 公司开源的一个基于 LXC技术之上构建的Container容器引擎， 源代码托管在 GitHub 上, 基于Go语言并遵从Apache2.0协议开源。
- 轻量，快速，便捷
- Dockfile可手动构建容器，便于分享
- 记录容器快照历史版本
- 特性：文件系统隔离, 资源隔离, 网络隔离, 写时复制, 日志记录, 变更管理, 交互式Shell


Docker原理
===
<center><img src="./figure/docker_layer.png" style = "width = 100%" ></center>


Docker vs 虚拟机
===
<center><img src="./figure/dockervsvm.png" style="width: 80%" ></center>

Dockerfile示例: "编译"出你的容器， rocker/r-base
===
<center><img src="./figure/dockerfile.png" style="width: 80%" ></center>


Rocker: 使用Docker容器运行R
===
- R的[官方](http://www.r-bloggers.com/rocker-is-now-the-official-r-image-for-docker/)Docker镜像管理
- [Gihub](https://github.com/rocker-org/rocker)上有用来建立容器的Dockerfile
<center><img src="./figure/rocker_container.png" style="width: 80%" ></center>

===
<center><img src="./figure/logo_bioconductor.jpg" style="width: 100%" ></center>
- 项目起始于2001， 由Robert Gentleman领导创立
- 专门的生物信息R软件库, 截止目前1024个软件包
- 包括各种注释数据。
- 每年两次更新
- AMI和Docker镜像可用



Bioconductor容器列表
===
- Bioconductor的Docker镜像存储在[Docker Hub](https://registry.hub.docker.com/repos/bioconductor/)
- 原始Dockerfiles存储在 [Github](https://github.com/Bioconductor/bioc_docker).
- 稳定版基于 [rocker/rstudio](https://github.com/rocker-org/rocker/tree/master/rstudio)；开发版本基于 [rocker/rstudio-daily](https://github.com/rocker-org/rstudio-daily).
<center><img src="./figure/bioc_list.png" ></center>

标准化：Common Workflow Language 
========================================================
- 多家机构参与开发和定制包括： Seven Bridges Genomics （发起和主要参与者），Curoverse，Galaxy，Institut Pasteur，BioDatomics，Michigan State University，Broad Institute 等等
- google group已有100+人
- 请访问[github官网](https://github.com/common-workflow-language/common-workflow-language)

<center><img src="./figure/cwl_org.png" style = "width:60%" ></center>

CWL: 为数据科学而生
===
- CWL用来描述数据科学所使用的流程， 包括生物信息，化学，物理，宇航等等。
- 针对命令行工具(Command Line Tools) 和流程（Workflow）定义了数据和流程执行模型，从而可以移植在不同的计算平台上，从个人工作站到cluster，grid，云和高性能运算平台。
- 提高了流程的可移植性和可重复性。
- JSON, YML描述性的语言（数据，工具，流程，参数等）
- 使用向图（directed graph)来描述一系列将输入数据转化为输出数据的的操作。
- 包含了命令行工具（command line) 和表达工具（使用ECMAScript）。


Rabix: 可轻松移植的流程开发系统
====
<center><img src="./figure/rabix-web.png" style = "width:100%" ></center>

功能概况
===
- 任何linux系统上运行，只需指定JSON的URL
- 描述任何有命令行接口linux工具
- 使用docker进行工具以及系统依赖快照
- 灵活，可移植，迅速
- 指定运行所需资源需求（CPU，内存）优化执行
- javascript表达式
- 类型声明从而支持输入输出严格校验和图形界面映射
- 由SBG开发，请访问官方网站 [rabix.org](https://www.rabix.org)或者[rabix.io](https://www.rabix.io)

一个简单的流程
===
<center><img src="./figure/pipeline1.png" ></center>

定义工具
=== 
<center><img src="./figure/pipeline_tool.png" ></center>

定义输入
===
<center><img src="./figure/pipeline_input.png" ></center>

定义参数
===
<center><img src="./figure/pipeline_param.png" ></center>

定义输出
=== 
<center><img src="./figure/pipeline_output.png" ></center>

定义流程
===
<center><img src="./figure/pipeline_workflow.png" ></center>



实例
===
我希望执行一个命令
```
samtools view -bS in.sam > out.bam
```
- 命令行 `samtools view`
- 输入文件 Sam
- 输出文件 Bam
- Adaptor -bS

安装base镜像创建新的容器
===
进入ubuntu镜像
``` 
docker run -ti ubuntu bash
```
在虚拟机里安装samtools（注：先进行update）
```
apt-get update
apt-get install samtools
```


封装推送容器
===
```
docker commit -m "add samtools 0.1.19 to ubuntu base" \
-a "Tengfei Yin" 0d1ff3541700 tengfei/samtools:0.1.19

docker push tengfei/samtools
```

Rabix: 用户界面直接描述工具和流程
===
<center><img src="./figure/rabix_ui2.png" ></center>

Rabix: 可视化可拖拽的流程编辑器
===
<center><img src="./figure/rabix_ui1.png" ></center>



Rabix: roadmap
===
<center><img src="./figure/rabix-roadmap.png" ></center>

Seven Bridges Genomics: 整合Rabix
===
- 原生支持rabix
- 完美整合SBG官方平台
- 简易开发，云端运行
<center><img src="./figure/cwl-sbg.png" style = "width:60%"></center>


Seven Bridges Genomics: Rabix支持
===
<center><img src="./figure/cwl-sbg-rabix.png" style = "width:100%"></center>

致谢
===
<center><img src="./figure/developer.png" ></center>
- Nebojsa Tijanic
- Sinisa Ivkovic 
- Milica Kadic 
- Luka Stojanovic 



====
<center><img src="./figure/sbg_logo.png" style="width: 100%" ></center>
- 全球最领先的生物信息云计算平台， 提供最丰富的软件库和最完整安全的生态系统
- 成立于2011， 总部位于美国波士顿，全球三个办公室，截止目前100+员工
- 全球唯一一家给美国政府和英国政府项目同时提供生物信息大数据方案的公司
- 欢迎访问 [sbgenomics.com](https://www.sbgenomics.com)

平台简介
===
<center><img src="./figure/platform.png" style="width: 80%" ></center>
<center><img src="./figure/platform2.png" style="width: 80%" ></center>




