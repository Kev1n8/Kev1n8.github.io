Tencent Diary

**Apr 11, Fri**

这是实习的最后一天。

### Week 20

**Apr 1, Tue**

下午弄好了。离职申请提交了。

**Mar 31, Mon**

没想到居然来了需求大晚上的。

## Month 5

### Week 19

**Mar 28, Fri**
**Mar 27, Thr**

没事做，这两天把rust-wasm过了一遍。

**Mar 26, Wed**

今天谈了薪， 大白菜，还算满意。

**Mar 25, Tue**

昨天做的被说有很多无效CPU，现在改了。

今天和terrence，wenzhi说了准备离职，估计清明前后吧。

**Mar 24, Mon**

今天一来就是把之前的一个ignore*的需求改成黑白名单。

### Week 18

**Mar 21, Fri**
**Mar 20, Thr**

没事做。

**Mar 19, Mar**

回学校交中期报告了这天。

**Mar 18, Tue**
**Mar 17, Mon**

布置了一个多租户相关的任务，监控定制格式的解析。说是ddl这周五，周二搞完了。

### Week 17

**Mar 14, Fri**
**Mar 13, Thr**
**Mar 12, Wed**
**Mar 11, Tue**
**Mar 10, Mon**

没事做。

### Week 16

## Month 4

**Mar 7, Fri**

没事做，总监面。

**Mar 6, Thr**

没事做。

突然来需求，加一个uptime指标。

**Mar 5, Wed**

没事做。

下午的面试体验比较糟糕，面试官很老派，我自认为我以一种更开放和探索性的回答去回应他的一些问题，但是他却十分执着于八股性质一样的关键词答案。咄咄逼人，令人不适。

**Mar 4, Tue**

没事做。

晚上面试聊了快一个小时，效果不错。

**Mar 3, Mon**

没事做。

下午ld叫去4210和存储二组的组长碰面，DBA还有hc，明天面试。

### Week 15

**Feb 28, Fri**
**Feb 27, Thr**
**Feb 26, Wed**

上午突然有新的优先级更高的需求，上午弄完了。

接下来几天把大需求弄好了。

值得一提的是新建资源以后因为没有设置对应的runner卡了很久。

**Feb 25, Tue**

晚上mt叫我去会议室单独布置了一个大需求，大致就是要往项目里加两个资源：Role和RoleBinding。还说周三到周五都不在

**Feb 24, Mon**

没事做。

### Week 14

**Feb 21, Fri**

没事做。

**Feb 20, Thr**

最后放save里了，构造了一个测试，但是有问题。

症状：
- master分支正常
- init_sqlite的时候如果不创建表，则create出错（没有对应表）
- 如果创建了表，则创建data_id一直pending

服了，因为data_id对应的kafka_channel没有ready，因为我根本没有创建！

突然有个bug找来，之前那个version kafka的需求，没有做好旧版本兼容。

**Feb 19, Wed**

今天没事做。

然后看我没事做给了个新活，现在功能代码已经写了，明天看看到底放哪里（save里面还是外面）。

**Feb 18, Tue**

没事做。

**Feb 17, Mon**

今天下午mt终于review了conditionalsink的代码。

因此晚上到八点才走。

### Week 13

**Feb 14, Fri**

没事做，下午五点半第一个走了。

**Feb 13, Thr**

今天有个cli，做完了。

今天还去办了passport。

**Feb 12, Wed**

今天没事做，有点发烧。下午五点半直接走了。

**Feb 11, Tue**

我把集成测试写出来，发现这个功能(kafka_inner sink to es)貌似是本来就可以的。

问mt，mt说那把测试提一个PR上去。

**Feb 10, Mon**

今天一来就有大活。理解了一天，终于大概知道需求是要做什么了。现在的问题是，是入库的时候要将bkbase-avro的格式转换成什么格式存到es里吗？

### Week 12

## Month 3

**Feb 7, Fri**

今天mt休假，但是给了个活。很简单，但是有一点不知道怎么做卡住了，问shunjie他也想不到，问mt没回。

晚上吃完直接润。

**Feb 6, Thr**

今天没事做。

**Feb 5, Wed**

假期过得好快啊，开工第一天。火焰图的压缩去掉。

没事做，把stringview的事再推进了一下。

### Week 11

**Jan 25, Sat**

今剧居然小改了一下代码，要放假喽。

**Jan 24, Fri**

今天居然有个小活。29行代码三十分钟搞定。

**Jan 23, Thr**

今天没事做。

也不知道晚上要不要开会（大概率是不开），但是mt老是拖到18:50分才通知，烦死，不能直接走。

不开会，我19点走了。

**Jan 22, Wed**

今天上来电梯里只有两个人……

又是没事做的一天了。

**Jan 21, Tue**

mt今天稍微review了一下很久以前一个PR，然后没事做。

能不能直接算我签到，让我回家了放假了……

**Jan 20, Mon**

没事做。

### Week 10

**Jan 17, Fri**

今天又是没事做，mt中午走了。

下午有下午茶。

**Jan 16, Thr**

提交了代码之后没有反馈，今天没事做。

晚上开会的时候对好几个需求的时候都是已经提交PR但是没有还反馈的。。。

**Jan 15, Wed**

今天一上来就有活干了，还是鉴权的，wuhu！

但其实只是往request里insert一个新的header而已。。。

设计的代码范围很广，感觉一不小心就会出错。

**Jan 14, Tue**

今天有两个问题，一个是为什么子Span没有父Span的field；另一个问题是我用参数一路传到最下面的Inner到底是不是一个好的实践？

不管怎样，这个需求算是按要求做好了，坐等review了。

**Jan 13, Mon**

今天一来就有任务，是给databus的某个指标新增两个维度。

终于涉及到telemetry了，然后还被迫要强制学习databus的运行时结构（准确来说仅仅是任务是如何被调度和传送的）。

### Week 9

**Jan 10, Fri**
**Jan 9, Thr**

忘记了，这两天好像都没什么事做。

**Jan 8, Wed**

今天又是没事情做。

**Jan 7, Tue**

今天mt说集成测试里添加校验，验证我的维度发现功能。半天死循环，结果发现是我本地的环境变量没更新，服了。

**Jan 6, Mon**

今天上午没事做，很困，看了点ddia。

### Week 8

## Month 2

**Jan 3, Fri**

今天没开会，因为他们只上了两天班。

上午给了个需求，理解需要点时间，下午弄完了。

**Jan 2, Thr**

到了下午终于来活了，又是命令行，20min搞定了。

**Dec 31, Tue**

今天还是没什么事，11点的时候组长回来了，我：回来啦？他：对。我：这么快（太蠢了，现在想想应该说：自驾确实灵活很多啊）

下午两点他们回到，有的还上来一趟有的直接走了。groobyming问对面实习生怎么还在这，下午不是放假吗？就很奇怪的安排。

总之下午挑了一会KTV，四点的时候和华本去健身房带他入门，五点半正好去刷面包回家吃了。第一次太阳下山之前下班。

**Dec 30, Mon**

整层楼都去年会了，突然发现之前那个女的工位在外包对面，她可能也是外包（or 实习生？），没去年会。

今天把微积分和概率论又看了一遍，重新做了一次4号的题，发现不止分部积分和命题，读代码的也写错了，这也让我进面试了。

还做了很多贝叶斯的概率题。

### Week 7

**Dec 27, Fri**

略。

**Dec 26, Thr**

今日没什么特别的。

**Dec 25, Wed**

今天mt来了，等他有空review代码再看PR怎么修改了。

mt过来问我做完了吗，我说提了PR了，他说好。然后过了一会在企微上问我如果申请成功or不成功的情况下我能实习多久，他好安排25年的工作。我和tj聊了下，最后回复的是至少四月底和三月中旬。mt说好，并祝我成功。

原来今天发版本，mt才一直不在座位上。四点的时候突然发个cli需求过来，好像很急，PR提了才几分钟就合并了。

**Dec 24, Tue**

过来搞半天单元测试，consumer一直报错，最后发现是groupid没有设置...服了

下午弄完，单测通过。需要留意的是，目前的实现仅适用于只有一个partition的情况。

**Dec 23, Mon**

来了把集成测试弄完，然后mt开完会过来问我是不是没事做了，我说是，他说那给我下个单子。看样子是要休假。

需求时写一个接口，获取kafka topic中后N条数据。

问题是partition不止一个的时候怎么做？碰巧mt走了，没得问，华本说他之前做过一个一模一样的cli，当时是默认partition为0。

### Week 6

**Dec 20, Fri**

下午给了集成测试的需求，说可以做了。

下班回家之后爸妈说要回来了，幸好没在我之前，东西还没藏好。

**Dec 19, Thr**

今天还是没什么事，上午临饭点丢了个小需求，20min搞定。

记 Rust 的 dot operator，一个变量调用函数的时候编译器尝试了下面的事情：
1. 直接匹配符号
2. 转化为引用（`&self` 或 `&mut self`）后匹配
3. 应用 `Deref trait` 后匹配；或者对于 `Sized` 的类型，尝试 unsizing 后匹配，比如 `[u8; 3]` 变为 `[u8]`

下午shunjie的集成测试合并了，我可以开始我的了。

**Dec 18, Wed**

今天一来没什么事，mt好像在忙别的，我感觉今天可能都没什么事了。

晚上打算直接回去了，不去健身房了，感冒还没好彻底不图这一下。

蛋白粉放了好久了，考虑要不要直接丢了。

**Dec 17, Tue**

今天写一个Cli，然后再改一点代码。之后等shunjie完成一个集成测试之后我可能就要参考他那个来写一个针对 `ConditionalSink` 的测试。

下午PolyU IT也出结果了，不出意外，Not Successful。

得找个机会和王先生说说了。

**Dec 16, Mon**

今天有点感冒，不是很舒服。早上一来改代码。

### Week 5

**Dec 13, Fri**

今早过来开会，估计又没什么事做了。
下午，貌似他们集体出去玩了。

**Dec 12, Thr**

今天早上一来mt就布置了一个任务要求上午完成。我一个小时不到弄完了，mt说你这么屌吗？然后又给我布置一个。shunjie也被布置了一个，还说你隔壁“大哥”都弄出来了。

mt管我叫大哥有点难绷，不是说我感觉很自豪什么，是我觉得年龄上有点奇怪。

晚上问mt关于年会的问题，mt在某个群里问，结果被人家线下过来说不要在群里问，怕实习生看到

**Dec 11, Wed**

今天一来把测试样例弄好了，跑通。下午继续研究了一下这个基于kube的运行时，Runner和Scheduler不太好懂，画了个图。

**Dec 10, Tue**

今天开干，上午搞通redis，下午进一步，提PR。晚上说缺少测试。

今天一看区块链给我拒了，气死了。

**Dec 9, Mon**

一来就找mt，但是也还是没回。准备线下过去问了。
他说他没空，晚点有空找我。
晚上结束前大致说了下（也只达到了让我理解的程度）

### Week 4

## Month 1

**Dec 6, Fri**

今天开会前派了两个需求，但是详情没写完。下午问了也不回，不管了。

**Dec 5, Thr**

今天还算不错，一大早就安排了一个bug fix。上午修改完，再写了一百行三个单元测试，完事。

中午发了工资，4090hh。我还以为会再多一丢丢。

下午又没事做了，看看ddia吧。

**Dec 4, Wed**

> 今日请假。

**Dec 3, Tue**

早上小江说我的开题和任务书没问题，搞定！
今天还是没什么事，抽空看看知识点吧。

**Dec 2, Mon**

今天一来就和华本和一个正职被抓去警告说迟到的问题。
上午照旧没有事做，下午照旧催mt，问关于dataid安全防御，说暂时没有设计，先忽略。
所以看来今天是没有事情做了。（看看ddia，写了个声明宏文档，早点回去搞完开题报告）

### Week 3

**Nov 29, Fri**

开会、睡觉。
叫mt review居然秒回，虽然只是回晚点看看。
今天把 CMU 的 Datafusion 讲座看完了，然后还看了一点DDIA。
申请了实习证明，瞬间就下来了文件，然后直接找翻译。估计明天就能出吧？然后今晚再让tj拍奖学金的奖状证明，不过不知道奖学金有没有必要放上去，我看都没有设置奖项的位置，要不把实习更新一下就行了吧？

计划修改PS的描述思路：
- 之前：缺乏工作经验，但是近期开始在qpt实习，相信能积累工作经验；简历无提及
- 改为：工作经验不多，但是自11/7开始在tx实习，负责xxx，短短时间已经xxx，相信未来能积攒更多经验；简历提及已经做的两个需求？撤销qpt

**Nov 28, Thr**

今天上午没事做，看了一会ddia。下午问mt在哪部署，说他自己部署，然后给我派了两个需求。
- 添加两行代码
- 写一个宏简化apply

好巧不巧，前几天才看的macro现在就用上了，当晚就搞定了。

**Nov 27, Wed**

mt一早reiview了代码，居然只有配置信息（统一函数）和逻辑（有无鉴权判断）的地方要改。
五点把代码push了，亮哥说差不多了，明天试着部署到准生产环境。

**Nov 26, Tue**

今天把代码移植为一个测试，比较麻烦的是前期的数据库和Kafka配置工作。
晚上培训的时候mt说shunjie和...（想不起我的名字）不用写他布置的作业。

**Nov 25, Mon**

今天跑通了写入和消费kafka的测试main.rs，还学了一下flamegraph怎么生成的。
一般来说，是通过perf命令（或者其他类似的）录制CPU的运行情况，然后生成的信息转换成svg图像，但是不知道为什么我录制某个特定PID也好或者是全局录制也罢，找不到我自己的程序，不是很会用。后面看到有更适合Rust的flamegraph工具，甚至加入了cargo工具里，很方便。

### Week 2

**Nov 22, Fri**

例行周会，似乎说到这个需求并不着急。
下午把集成测试写一下。
集成测试写出来了，但是非常依赖我自己的测试环境，不知道要不要整合到项目中。

**Nov 21, Thr**

今天上午把mt做完留的review做完，又开始waiting。随着时间流逝，越来越焦虑港校的情况啊。
继续看Macro，今天下午能把Declarative的看完？

**Nov 20, Wed**

今天带了一床啦夏，中午不怕冷了。
下雨，下次下雨出门穿洞洞鞋不能穿袜子。原本很自信不会被淋湿的，毕竟穿了雨衣，结果水直接蓄满了流进洞里。

**Nov 19, Tue**

今天一来就把代码修改push了。waiting...
自己学习Rust Macro中...
晚上参加了培训，讲了项目组织结构、一些常用集合和错误处理。

**Nov 18, Mon**

今天上午把上周的代码完善了一下然后告知mt做好了，并问他关于数据库和Kafka的配置能不能复用之前InitConfig里的，但是我看这个代码似乎不是这么设计的。到目前为止（15:28）他还没答复。
刚刚mt交代shunjie看我的代码，然后开完会给他提个需求，但是没来和我说。总之我先学习下宏定义吧，之前没有认真学过。
晚上mt review了我的代码，指出了一些问题，主要是一些注释和println没删掉、还有一个Kafka逻辑没完全落实、commit信息不符合规范。

### Week 1

**Nov 15, Fri**

今天开会，但是总监不在，估计上次是月会。上午没做什么就去吃饭了。下午落实了一下SeaORM部分的代码，在测试环境里插了一条数据试了一下，发现可以通了，结束。

**Nov 14, Thr**

今天把`Kafka`弄通了，使用`rdkafka`这个工具，也学习`SeaORM`的基础概念。

**Nov 13, Wed**

今天熟悉了项目的代码，api server什么的，搞通了axum路由。令人无语的是我在终端手动`curl`一直404，原来是因为路径最后没有加一个`/`……

今天是第一个健康日，所以借此机会和jp去了健身房。感觉五点半就跑过来，然后六点半去吃饭是最好的。但是因为是健康日，大家一般都到了快六点才走。要赶在七点晚饭停止供应前就比较紧张。

**Nov 12, Tue**

今日任务：下午两点半MT要我和他说说我对计算平台的理解。
口头稍微讲了一下理解之后就安排了一个接口需求，内容大致是对一个接口进行POST，将请求的body发送的对应的Kafka中。

**Nov 11, Mon**

今天MT拉我进一个测试环境群，可以体验项目（计算平台）。我大致操作了下、把上周的脚本都跑完以及开始了解OpenTelemetry的一些概念。

**Nov 8, Fri**

今天把隔壁实习生的之前的活给我做一遍，主要是跑一些脚本，让k8s集群能够运行起来。

**Nov 7, Thr**

第一天入职，没什么事做，MT单独交流问了我的情况和交代了一些注意事项；组长召集了实习生开会讲了部门结构等等和一些注意事项。今日MT吩咐的就是把代码clone下来然后成功编译。

### Week 0

## Month 0