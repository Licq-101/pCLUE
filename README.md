# PromptCLUE
pCLUE: Large-scale Prompt-based Dataset for Multi-task and Zero-shot Learning in Chinese

pCLUE：基于提示的大规模预训练数据集，用于多任务学习和零样本学习

### 已转化数据集
    
    数据量： 120万训练数据，73个Prompt
    1. 训练集 train.json: 1,200,705
    2. 验证集 dev.json: 100,000
    3. 公开测试集 test_public.json: 129,556
    4. 测试集 test.json: 250,461
    
    具体数据，见：./datasets

### 目前已经有包含9个数据集：

    1.单分类tnews 
    2.单分类iflytek 
    3.自然语言推理ocnli 
    4.语义匹配afqmc 
    5.指代消解-cluewsc2020 
    6.关键词识别-csl 
    7.阅读理解-自由式c3 
    8.阅读理解-抽取式cmrc2018 
    9.阅读理解-成语填空chid 
    
### 字段说明及评价标准：
    input:模型的输入
    target:模型的输出
    type:任务类型，阅读理解(mrc),分类(classify)，生成(generate)，自然语言推理(nli)
    评价标准：阅读理解(em),分类(acc)，生成(em)，自然语言推理(acc)
    answer_choices:选项（只有分类、推理类任务有）

### 提交样例：
    见resources/promptclue_submit_examples。只需提交一个文件，每行是一个json，如：{"target": "2000万元"}
    
### 示例：
    {"input": "哪个类别最好的描述了这篇新闻？扣篮王拉文：精彩暴扣表演！炸\n选项：故事，文化，娱乐，体育，财经，房产，汽车，教育，科技，军事，旅游，国际，股票，农业，游戏\n答案：", "target": "电竞", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "你会把这个描述推荐给哪方面的人？银行，社区，电商，支付，经营，卡牌，借贷，驾校，理财，职考，新闻，旅游，交通，魔幻，医疗，影像，动作，工具，体育，小说，运动，相机，工具，快递，教育，股票，菜谱，行车，仙侠，亲子，购物，射击，漫画，小学，同城，成人，求职，电子，艺术，赚钱，约会，经营，兼职，视频，音乐，英语，棋牌，摄影，养生，办公，政务，视频，论坛，彩票，直播，其他，休闲，策略，通讯，买车，违章，地图，民航，电台，语言，搞笑，婚恋，超市，养车，杂志，在线，家政，影视，装修，资讯，社交，餐饮，美颜，挂号，飞行，预定，票务，笔记，买房，外卖，母婴，打车，情侣，日程，租车，博客，百科，绘画，铁路，生活，租房，酒店，保险，问答，收款，竞技，唱歌，技术，减肥，工作，团购，记账，女性，公务，二手，美妆，汽车，行程，免费，教辅，两性，出国，婚庆，民宿快来施放属于你的寒冰魔法吧特殊效果雪花缓缓从上方飘落，手指触碰之处有冰魔法出现爱莎女王脱掉了封印魔法她的手套，在冰雪天地中建造了属于她一个人的辉煌宫殿。安娜中了冰魔法需要真爱之吻才能获救，最终姐妹二人齐心揭穿了异国王子的阴谋拯救了阿伦戴尔。解锁方法随意滑动屏幕一定距离后解锁要是觉得好玩，记得推荐给好朋友哦,,1.新增多张精美冰雪奇缘壁纸2.增加冰雪图钉，锁定当前壁纸功能3.内存，减小电量消耗\n答案：", "target": "休闲益智", "answer_choices": ["银行", "社区", "电商", "支付", "经营", "卡牌", "借贷", "驾校", "理财", "职考", "新闻", "旅游", "交通", "魔幻", "医疗", "影像", "动作", "工具", "体育", "小说", "运动", "相机", "工具", "快递", "教育", "股票", "菜谱", "行车", "仙侠", "亲子", "购物", "射击", "漫画", "小学", "同城", "成人", "求职", "电子", "艺术", "赚钱", "约会", "经营", "兼职", "视频", "音乐", "英语", "棋牌", "摄影", "养生", "办公", "政务", "视频", "论坛", "彩票", "直播", "其他", "休闲", "策略", "通讯", "买车", "违章", "地图", "民航", "电台", "语言", "搞笑", "婚恋", "超市", "养车", "杂志", "在线", "家政", "影视", "装修", "资讯", "社交", "餐饮", "美颜", "挂号", "飞行", "预定", "票务", "笔记", "买房", "外卖", "母婴", "打车", "情侣", "日程", "租车", "博客", "百科", "绘画", "铁路", "生活", "租房", "酒店", "保险", "问答", "收款", "竞技", "唱歌", "技术", "减肥", "工作", "团购", "记账", "女性", "公务", "二手", "美妆", "汽车", "行程", "免费", "教辅", "两性", "出国", "婚庆", "民宿"], "type": "classify"}
    {"input": "阅读以下文章，并选择一个合适的成语。文章：\n赵宝刚导演表示，当看到温家宝总理在灾区安慰失去亲人__的孩子时，他再也控制不住自己的感情，不禁潸然泪下。他非常关心灾区的孤儿，目前正计划为孩子们做一些更有意义的事情。当记者问到是否会考虑日后拍一部地震题材的影片时，赵宝刚导演则明确表示自己更愿意为灾区做一些实事，目前正在积极了解灾区儿童的需要，为下一步援助工作做准备。\n 候选成语：忧心忡忡，提心吊胆，后顾之忧，土豪劣绅，叫苦不迭，用武之地，无计可施，明眸皓齿，孤立无援，步步为营。答案是：", "target": "孤立无援", "answer_choices": ["忧心忡忡", "提心吊胆", "后顾之忧", "土豪劣绅", "叫苦不迭", "用武之地", "无计可施", "明眸皓齿", "孤立无援", "步步为营"], "type": "mrc"}
    {"input": "这是关于哪方面的新闻？黄埔军校老师有哪些？\n选项：故事，文化，娱乐，体育，财经，房产，汽车，教育，科技，军事，旅游，国际，股票，农业，游戏\n答案：", "target": "军事", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "这个是关于哪方面的App应用程序的描述？银行，社区，电商，支付，经营，卡牌，借贷，驾校，理财，职考，新闻，旅游，交通，魔幻，医疗，影像，动作，工具，体育，小说，运动，相机，工具，快递，教育，股票，菜谱，行车，仙侠，亲子，购物，射击，漫画，小学，同城，成人，求职，电子，艺术，赚钱，约会，经营，兼职，视频，音乐，英语，棋牌，摄影，养生，办公，政务，视频，论坛，彩票，直播，其他，休闲，策略，通讯，买车，违章，地图，民航，电台，语言，搞笑，婚恋，超市，养车，杂志，在线，家政，影视，装修，资讯，社交，餐饮，美颜，挂号，飞行，预定，票务，笔记，买房，外卖，母婴，打车，情侣，日程，租车，博客，百科，绘画，铁路，生活，租房，酒店，保险，问答，收款，竞技，唱歌，技术，减肥，工作，团购，记账，女性，公务，二手，美妆，汽车，行程，免费，教辅，两性，出国，婚庆，民宿“魅爱同城美女主动视频陪聊神器，女神绝密私照，一对一视频畅聊，保护你的私密。清纯的萌妹子、火辣的舞女郎，惊艳的时装秀，浪漫的午夜邂逅，伴你告别寂寞和美女主播视频聊天、交友、热舞零距离互动。让你随时随地享受偶遇的激情与惊喜与网红视频网红主播与你在线视频交友，浪漫邂逅。生活动态圈高颜值女神用短视频和照片与你分享生活中的点滴。\n答案：", "target": "约会社交", "answer_choices": ["银行", "社区", "电商", "支付", "经营", "卡牌", "借贷", "驾校", "理财", "职考", "新闻", "旅游", "交通", "魔幻", "医疗", "影像", "动作", "工具", "体育", "小说", "运动", "相机", "工具", "快递", "教育", "股票", "菜谱", "行车", "仙侠", "亲子", "购物", "射击", "漫画", "小学", "同城", "成人", "求职", "电子", "艺术", "赚钱", "约会", "经营", "兼职", "视频", "音乐", "英语", "棋牌", "摄影", "养生", "办公", "政务", "视频", "论坛", "彩票", "直播", "其他", "休闲", "策略", "通讯", "买车", "违章", "地图", "民航", "电台", "语言", "搞笑", "婚恋", "超市", "养车", "杂志", "在线", "家政", "影视", "装修", "资讯", "社交", "餐饮", "美颜", "挂号", "飞行", "预定", "票务", "笔记", "买房", "外卖", "母婴", "打车", "情侣", "日程", "租车", "博客", "百科", "绘画", "铁路", "生活", "租房", "酒店", "保险", "问答", "收款", "竞技", "唱歌", "技术", "减肥", "工作", "团购", "记账", "女性", "公务", "二手", "美妆", "汽车", "行程", "免费", "教辅", "两性", "出国", "婚庆", "民宿"], "type": "classify"}
    {"input": "阅读理解：\n有一次，有人问马克·吐温是否记得他第一次是怎样挣到钱的。他想了很久，然后说：“对，我还记得很清楚，那是我在小学读书的时候。那时，小学生们都不尊重自己的老师，而且不爱惜学校的财产，经常弄坏桌椅。所以我们学校就定了一条规则，哪个学生用铅笔或小刀弄坏了桌椅，他就得在全校学生面前挨老师的打，或者交五元罚款。有一天，我弄坏了我的书桌，只好回家对父亲说，我违反了学校的规定，要么罚五元，要么在全校学生面前受到挨打的处分。父亲说当着全校学生的面挨打真是太丢脸了，他答应给我五块钱，让我交给学校。但是在给我这五块钱之前，他把我带到楼上，狠狠地打了我一顿。我想，既然我已经挨过一顿打了，那就干脆当着全校学生的面再挨一顿，这样就可以把那五块钱留下来。我真的这样做了，那就是我第一次挣到的钱。” \n问：父亲为什么给马克·吐温钱? 选项：喜欢他，奖励他，怕丢脸，感谢他\n答案：", "target": "怕丢脸", "type": "mrc", "answer_choices": ["喜欢他", "奖励他", "怕丢脸", "感谢他"]}
    {"input": "“全面加强教师特别是农村教师培训,鼓励大学生、师范生到基层、农村任教”根据前面的段落，以下是否是真的“农村教师的培训需要特别重视”？是的,不是,或也许？\n答案：", "target": "是的", "answer_choices": ["是的", "不是", "也许"], "type": "nli"}
    {"input": "给定“国民经济保持较快增长”我们应该假定“国民经济一个月内还会保持快速增长”是真的吗？是的,不是,或也许？\n答案：", "target": "也许", "answer_choices": ["是的", "不是", "也许"], "type": "nli"}
    {"input": "这个是关于哪方面的App应用程序的描述？银行，社区，电商，支付，经营，卡牌，借贷，驾校，理财，职考，新闻，旅游，交通，魔幻，医疗，影像，动作，工具，体育，小说，运动，相机，工具，快递，教育，股票，菜谱，行车，仙侠，亲子，购物，射击，漫画，小学，同城，成人，求职，电子，艺术，赚钱，约会，经营，兼职，视频，音乐，英语，棋牌，摄影，养生，办公，政务，视频，论坛，彩票，直播，其他，休闲，策略，通讯，买车，违章，地图，民航，电台，语言，搞笑，婚恋，超市，养车，杂志，在线，家政，影视，装修，资讯，社交，餐饮，美颜，挂号，飞行，预定，票务，笔记，买房，外卖，母婴，打车，情侣，日程，租车，博客，百科，绘画，铁路，生活，租房，酒店，保险，问答，收款，竞技，唱歌，技术，减肥，工作，团购，记账，女性，公务，二手，美妆，汽车，行程，免费，教辅，两性，出国，婚庆，民宿移动吧是移动官方面向青海移动用户推出的移动智能终端网上营业厅。新版的移动吧为用户提供方便快捷的账单查询、业务办理、积分查询、通讯录等功能。随时随地尽享青海移动的贴心服务，方便触手可及。查询更丰富直观准确、消费透明充值更优惠专享优惠、充值赠费办理更便捷套餐流量、随时办理好友更亲密相互关注、贴心关怀活动更精彩活动不停、优惠不断更新内容1修复已知Bug；2优化客户端访问速度；3提升活动体验，丰富奖励资源。\n答案：", "target": "工具", "answer_choices": ["银行", "社区", "电商", "支付", "经营", "卡牌", "借贷", "驾校", "理财", "职考", "新闻", "旅游", "交通", "魔幻", "医疗", "影像", "动作", "工具", "体育", "小说", "运动", "相机", "工具", "快递", "教育", "股票", "菜谱", "行车", "仙侠", "亲子", "购物", "射击", "漫画", "小学", "同城", "成人", "求职", "电子", "艺术", "赚钱", "约会", "经营", "兼职", "视频", "音乐", "英语", "棋牌", "摄影", "养生", "办公", "政务", "视频", "论坛", "彩票", "直播", "其他", "休闲", "策略", "通讯", "买车", "违章", "地图", "民航", "电台", "语言", "搞笑", "婚恋", "超市", "养车", "杂志", "在线", "家政", "影视", "装修", "资讯", "社交", "餐饮", "美颜", "挂号", "飞行", "预定", "票务", "笔记", "买房", "外卖", "母婴", "打车", "情侣", "日程", "租车", "博客", "百科", "绘画", "铁路", "生活", "租房", "酒店", "保险", "问答", "收款", "竞技", "唱歌", "技术", "减肥", "工作", "团购", "记账", "女性", "公务", "二手", "美妆", "汽车", "行程", "免费", "教辅", "两性", "出国", "婚庆", "民宿"], "type": "classify"}
    {"input": "足三两（）是麦当劳推出的一种汉堡包，为继巨无霸后的另一招牌食品。英文名称的意思是「四分之一磅」，因为牛肉重量大约等如四分之一磅（烹调前计），而四分之一磅大约等于三两重，故在香港被称为「足-{}-三两」。在麦当劳于1975年进入香港市场时，Quarter Pounder曾被命名为「大汉-{}-堡」，而Quarter Pounder with Cheese则被命名为「大芝-{}-士汉-{}-堡」，但于1980年代后停售。2000年代初，曾经作为推广产品重新命名为「足-{}-三两」（或写作足-{}-三両），但推广期后便继续停售。直至2007年起，麦当劳在香港推出「Double足-{}-三两」（Double Quarter Pounder，即是双重份量的足-{}-三两）作为MacTonight套餐，于香港时间每晚21:00至翌日凌晨04:00间供应。由于反应理想，香港麦当劳于2009年将其发售时段提早至上午11时开始，并重新引入常规版的「足-{}-三两」作为长期发售的项目。Double足-{}-三两已于2017年初停售，常规版足-{}-三两亦于同年3月9日起停售。事实上，在香港售卖的「足-{}-三两」实际重量只有100克。香港麦当劳的餐牌上足-{}-三两及Double足-{}-三两都会以小字体加上「烹调前」标签，以符合香港海关《商品说明条例》的规定。一个正常的足三两，包括有四分之一磅（113.4克）牛肉（烹调前计）、两块芝麻面包、酸瓜、茄酱及生洋葱，而很多时候足三两也会有一块芝士。\n 从上面的段落中，根据一个合理的答案：麦当劳\n那么问题可能是：", "target": "足三两是哪个品牌的招牌食品之一？", "type": "mrc"}
    {"input": "“切实转变工作作风”根据前面的段落，以下是否是真的“这是公文话语”？是的,不是,或也许？\n答案：", "target": "是的", "answer_choices": ["是的", "不是", "也许"], "type": "nli"}
    {"input": "“逐步实行中等职业教育免费,今年先从农村家庭经济困难学生和涉农专业做起”记住上面的文字,考虑:“后年就能够全面实现中等职业教育免费”这是总是,绝不,或有时正确的？\n答案：", "target": "有时", "answer_choices": ["总是", "绝不", "有时"], "type": "nli"}
    {"input": "阅读下列论文的摘要，然后生成这篇摘要的多个关键词。摘要：通过对泥河湾盆地43条剖面和6个钻孔晚新生代地层和微体古生物(介形类和有孔虫)的调查研究,发现非常丰富的介形类,计26属70余种,有孔虫4属4种,其中介形类自下而上可明显地划分为5个组合带:(1)Potamocyprisplana-Candoniella-Ilyocypris组合带;(2)Leucocythere-Ilyocypris-Candoniella组合带;(3)Leucocythere-Cytherissa-Limnocythere组合带;(4)Ilyocypris-Limnocythereflexa-Limnocytheredubiosa组合带;(5)Limnocytheredubiosa-Limnocytheresancti-Patricii-Ilyocypris组合带.按以上5个介形类组合带的分布,第1组合带及所含地层红崖村组和石匣组的时代为上新世;第2～4组合带及所含地层泥河湾组的时代为早更新世;第5组合带为中-晚更新世,分布于虎头梁组和许家窑组,虎头梁组置中更新世为宜,许家窑组为晚更新世.根据5个介形类组合带和有孔虫的分布及介形类的始现、繁盛、兴衰的演替特征,对泥河湾古湖和盆地的形成经历了上新世的起始,早更新世早期的扩展,中、晚期稳定、发展、湖面最大,中更新世向西部退缩和晚更新世消亡、桑干河水系形成五个发展阶段的演化进行了探讨.。摘要的关键词有这些：\n答案：", "target": "介形类，晚新生代，环境演化，生物地层", "answer_choices": "", "type": "generate"}
    {"input": "这个App应用程序的描述会出现在哪个栏目？•只需随身携带手机即可随时了解您步行、跑步和骑车的运动情况。达成健身目标•设定时长或步数目标，并了解自己的进度。•获得根据健身效果提供的运动目标建议。全面掌握健身情况•将第三方设备和应用与Google健身关联后，您就可以在一个地方集中查看您的所有健身数据。随时随地使用•兼容所有AndroidWer设备。•还可以通过浏览器www.google.com/fit和平板电脑使用Google健身。更新内容提升体验，修复部分问题。\n选项：银行，社区，电商，支付，经营，卡牌，借贷，驾校，理财，职考，新闻，旅游，交通，魔幻，医疗，影像，动作，工具，体育，小说，运动，相机，工具，快递，教育，股票，菜谱，行车，仙侠，亲子，购物，射击，漫画，小学，同城，成人，求职，电子，艺术，赚钱，约会，经营，兼职，视频，音乐，英语，棋牌，摄影，养生，办公，政务，视频，论坛，彩票，直播，其他，休闲，策略，通讯，买车，违章，地图，民航，电台，语言，搞笑，婚恋，超市，养车，杂志，在线，家政，影视，装修，资讯，社交，餐饮，美颜，挂号，飞行，预定，票务，笔记，买房，外卖，母婴，打车，情侣，日程，租车，博客，百科，绘画，铁路，生活，租房，酒店，保险，问答，收款，竞技，唱歌，技术，减肥，工作，团购，记账，女性，公务，二手，美妆，汽车，行程，免费，教辅，两性，出国，婚庆，民宿\n答案：", "target": "运动健身", "answer_choices": ["银行", "社区", "电商", "支付", "经营", "卡牌", "借贷", "驾校", "理财", "职考", "新闻", "旅游", "交通", "魔幻", "医疗", "影像", "动作", "工具", "体育", "小说", "运动", "相机", "工具", "快递", "教育", "股票", "菜谱", "行车", "仙侠", "亲子", "购物", "射击", "漫画", "小学", "同城", "成人", "求职", "电子", "艺术", "赚钱", "约会", "经营", "兼职", "视频", "音乐", "英语", "棋牌", "摄影", "养生", "办公", "政务", "视频", "论坛", "彩票", "直播", "其他", "休闲", "策略", "通讯", "买车", "违章", "地图", "民航", "电台", "语言", "搞笑", "婚恋", "超市", "养车", "杂志", "在线", "家政", "影视", "装修", "资讯", "社交", "餐饮", "美颜", "挂号", "飞行", "预定", "票务", "笔记", "买房", "外卖", "母婴", "打车", "情侣", "日程", "租车", "博客", "百科", "绘画", "铁路", "生活", "租房", "酒店", "保险", "问答", "收款", "竞技", "唱歌", "技术", "减肥", "工作", "团购", "记账", "女性", "公务", "二手", "美妆", "汽车", "行程", "免费", "教辅", "两性", "出国", "婚庆", "民宿"], "type": "classify"}
    {"input": "这个是关于哪方面的App应用程序的描述？银行，社区，电商，支付，经营，卡牌，借贷，驾校，理财，职考，新闻，旅游，交通，魔幻，医疗，影像，动作，工具，体育，小说，运动，相机，工具，快递，教育，股票，菜谱，行车，仙侠，亲子，购物，射击，漫画，小学，同城，成人，求职，电子，艺术，赚钱，约会，经营，兼职，视频，音乐，英语，棋牌，摄影，养生，办公，政务，视频，论坛，彩票，直播，其他，休闲，策略，通讯，买车，违章，地图，民航，电台，语言，搞笑，婚恋，超市，养车，杂志，在线，家政，影视，装修，资讯，社交，餐饮，美颜，挂号，飞行，预定，票务，笔记，买房，外卖，母婴，打车，情侣，日程，租车，博客，百科，绘画，铁路，生活，租房，酒店，保险，问答，收款，竞技，唱歌，技术，减肥，工作，团购，记账，女性，公务，二手，美妆，汽车，行程，免费，教辅，两性，出国，婚庆，民宿神秘又惊喜的万圣节到啦快来宝宝超市挑选你最爱的南瓜灯和面具吧还可以挑个礼服画个妆，打造超炫的万圣节造型呢和奇奇一起学会在超市购物，成为妈妈购物的好帮手吧丰富商品水果，蔬菜，玩具，零食&hellip;各种商品一应俱全模拟真实超市购物的场景，让宝宝体验超市购物的乐趣。根据清单购物你能帮妈妈买到清单上的东西吗对照清单购买需要的东西，让孩子有目的性的逛超市，帮宝宝树立正确的消费观。模拟结账别忘记结账哟~所有商品一共8元，付了10元，该找回多少钱呢，你能帮奇奇算一算吗丰富小游戏鱼缸捞鱼、搭配你喜欢的蛋糕、帮试妆员化上美丽的妆&hellip;丰富趣味小游戏，乐趣无穷宝宝巴士以孩子的兴趣启蒙为出发点，从健康、语言、社会、科学、艺术五大领域关注幼儿成长，吸取蒙氏教育精髓，根据幼儿不同年龄段左右脑发育、敏感期特点和学习重点来设计产品，打造&ldquo;年龄+能力&rdquo;的多元化产品体系。让孩子在游戏中独立思考，自由学习，享受探索世界的乐趣。宝宝巴士儿童早教pp，众多儿童早教产品的一致选择，孩子从小学宝宝巴士儿歌，贝瓦儿歌，儿歌点点，宝宝树，小伴龙，贝乐虎儿歌，咔哒故事，伴鱼绘本，宝宝手工零食，宝宝时尚设计师等使用者的一致推荐。设计理念宝宝巴士BbyBus,专注启蒙，而不仅仅是教育。我们专注于启发，而不只是学习。我们专注于能力培养，而不只是单一认知。我们专注于寓教于乐，而不是填鸭式教学。宝宝巴士，快乐启蒙全球3.5亿家庭用户的早教首选，您身边的幼儿教育专家搜索宝宝巴士，就可以下载宝宝巴士的所有早教APP了哦~欢迎联系微信宝宝巴士微博@宝宝巴士官网http//www.bbybus.com邮箱cn@bbybus.com更新内容不放过任何可以提升体验的地方，优化细节，让游戏体验更上一层楼贴心的小bug修复，提升稳定性和流畅度，畅玩无压力搜索宝宝巴士，就可以下载宝宝巴士的所有早教APP了哦~欢迎加入宝宝巴士官方Q群288190979，一起为孩子做更多更好的产品。\n答案：", "target": "亲子儿童", "answer_choices": ["银行", "社区", "电商", "支付", "经营", "卡牌", "借贷", "驾校", "理财", "职考", "新闻", "旅游", "交通", "魔幻", "医疗", "影像", "动作", "工具", "体育", "小说", "运动", "相机", "工具", "快递", "教育", "股票", "菜谱", "行车", "仙侠", "亲子", "购物", "射击", "漫画", "小学", "同城", "成人", "求职", "电子", "艺术", "赚钱", "约会", "经营", "兼职", "视频", "音乐", "英语", "棋牌", "摄影", "养生", "办公", "政务", "视频", "论坛", "彩票", "直播", "其他", "休闲", "策略", "通讯", "买车", "违章", "地图", "民航", "电台", "语言", "搞笑", "婚恋", "超市", "养车", "杂志", "在线", "家政", "影视", "装修", "资讯", "社交", "餐饮", "美颜", "挂号", "飞行", "预定", "票务", "笔记", "买房", "外卖", "母婴", "打车", "情侣", "日程", "租车", "博客", "百科", "绘画", "铁路", "生活", "租房", "酒店", "保险", "问答", "收款", "竞技", "唱歌", "技术", "减肥", "工作", "团购", "记账", "女性", "公务", "二手", "美妆", "汽车", "行程", "免费", "教辅", "两性", "出国", "婚庆", "民宿"], "type": "classify"}
    {"input": "参考下面的段落，回答下列问题：\n段落：因吊钟的花朵通常在农历新年前后开花，故英文又名为Chinese New Year Flower，意即中国新年花。在清代中叶开始已有吊钟作为年花的习俗，取其「金钟一响，黄金万两」的吉兆，同时吊钟花的花朵都是生长在枝顶上，亦有高中科举之寓意，古时百姓因希望子弟能高中科举，就砍伐吊钟花带回家作为年花。不过近年因人们觉“吊钟”和“吊终”谐音，不吉利，所以较少人以吊钟作为年花。吊钟是一种落叶或半常绿灌木，可高约7米，但常高3米。树皮呈灰黄色，多分枝，小枝呈淡褐色。叶长圆形或倒卵状长圆形，先端渐尖，基部渐狭而成短柄，常密集生于枝顶，互生，革质，表面绿色而背面淡绿色，长5－10厘米，阔2－4厘米，全缘或顶部疏生细齿，叶两面无毛，侧脉6－7对，中脉两面清晰呈羽状伸出，网脉两面清晰，叶短柄长约5－20厘米，灰黄色呈圆柱状无毛。花为伞房花序顶生，花粉红色或红色，常5－8朵，下垂呈钟型，从枝顶覆瓦状排列的红色大苞片内生出，苞片长圆形或长方形，膜质，花梗绿色无毛，长约1.5－2厘米，花萼5裂，披针形先端披纤毛，长约2－4厘米，花冠呈宽钟状，口部5裂，裂片长约1－1.2厘米，裂片钝圆，轻微反卷白色，雄蕊8枚，雌蕊1枚，雌蕊较雄蕊长。果为蒴果，椭圆形无毛，淡黄色，具5梭，长约8－12厘米，果柄直立粗壮，长约3－5厘米。种子有3－5角或翅。喜温暖湿润，日光充足，土壤肥沃含腐殖质及排水良好的土壤。可以使用播种、扦插法及压条法繁殖。\n问题：吊钟花如何进行繁殖？\n答案：", "target": "播种、扦插法及压条法", "type": "mrc"}
    {"input": "从医院打完针、开了药回来。母亲就赶到单位去上班了。走前，她把我托付给禾寡妇（候选词），请她(代词)关照我。。上面的句子中，代词“她”指代的是“禾寡妇”吗？选项：是的，不是。答案：", "target": "是的", "type": "anaphora_resolution", "answer_choices": ["是的", "不是"]}
    {"input": "《1997年郡尉职权法案》（）于1997年生效，是一项英国国会法案，来厘订大不列颠委任的郡尉（Lord Lieutenant）所管辖的地区。根据《1888年地方政府法案》，郡尉是被委派到每一个郡。可是，这个法案所定义的区域混杂了新的行政郡及郡的自治区。实际上，影响很微小，因为只有少数行政郡的边界跟原来的不一样。直到1965年大伦敦及亨廷登-彼得伯勒郡的成立，导致米德尔塞克斯郡尉办公室、伦敦郡郡尉办公室、亨廷登郡郡尉办公室被废除，取而代之就是大伦敦郡尉及亨廷登-彼得伯勒郡尉。1974年，英格兰及威尔斯内的行政郡及郡自治区被废除。一项大型改革也同时推行。所有郡尉辖区都被划分为都会郡和非都会郡。而1973年《苏格兰地方政府法案》则不跟从新的苏格兰地区来厘订郡尉辖区，反而从传统郡中拼合起来。因此，两者结合导致产生出来的郡尉辖区完全不跟从原有的郡。大部分这些郡尉辖区都没有留下来。在1990年代中期的英国地方政府改革中，很多非都会郡都开始重组成为单一管理区。苏格兰及威尔斯的地方政府过渡成为只由单一管理区所组成。这个时候开始草拟这个法案的计划，把郡尉辖区从地方政府再次分出来。虽然法案没有使用这个计划，但这些地方成了英格兰的名誉郡。\n 参考上述上下文，改革推行后，所有郡尉辖区被划分为什么？\n答案：", "target": "都会郡和非都会郡", "type": "mrc"}
    {"input": "香港2004年继去年七一游行后再次经历了巨大政治争议，4月全国人民代表大会常务委员会第二次行使权力解释基本法，并否决了0708年双普选。5月，商业电台多名著名节目主持人指受到压力相继暂停节目，发生了「商台名嘴封咪事件」。7月1日，仍有数以十万计市民参与七一游行表达争取民主诉求。9月，第三届立法会选举刷新了历届投票纪录，有178万多人投票（投票率55.64%）。经济方面，去年发生沙士事件后情况逐渐改善，失业率下跌至2004年第四季的6.5%，是近三年以来的低位，年内本地生产总值增长8.1%，是自1987年以来的第二快增长，历时68个月的通缩终于结束，经济复苏主要受惠于东亚、欧美国等主要市场的强劲需求，以及中国内地对外贸易畅旺和内部需求殷切所带动。然而去年沙士期间，带来经济下滑以及增加开支，政府账目录得赤字401亿。下列节庆，如无注明，均是香港的公众假期，同时亦是法定假日（俗称劳工假期）。有 # 号者，不是公众假期或法定假日（除非适逢星期日或其它假期），但在商业炒作下，市面上有一定节庆气氛，传媒亦对其活动有所报导。详情可参看香港节日与公众假期。\n 从上面的段落中，根据一个合理的答案：受惠于东亚、欧美国等主要市场的强劲需求，以及中国内地对外贸易畅旺和内部需求殷切所带动。\n那么问题可能是：", "target": "香港2004年经济复苏的原因是什么？", "type": "mrc"}
    {"input": "这是关于哪方面的新闻： 故事,文化,娱乐,体育,财经,房产,汽车,教育,科技,军事,旅游,国际,股票,农业,游戏？首次承认落后，美媒披露中国高超音速导弹技术领先美国\n答案：", "target": "军事", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "这是关于哪方面的新闻： 故事,文化,娱乐,体育,财经,房产,汽车,教育,科技,军事,旅游,国际,股票,农业,游戏？未来5年，教师会成为高收入人群吗？\n答案：", "target": "国际", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "阅读下面短文，从短文后给出的候选项中选出最佳选项。\n 新浪体育讯叠泉自开业以来，以其球场精良的设计、球会周到的服务，在业界的影响力不断提高，吸引了大批高尔夫爱好者慕名来到球会，这其中包括大家__的各界知名人士，政界、财经、实业、演艺界等有社会公众影响力的人物#idiom593805#。然而他们却拥有着很多共同点：他们都是社会各界的领袖精英；他们都在各自的领域颇有建树；他们都在接触叠泉后被其美丽而又富有挑战的场地所折服，#idiom593806#。 \n 候选项:神龙见首，各式各样，耳熟能详，不一而足，一应俱全，流连忘反，不胜枚举，沾沾自喜，一无所有，衣食住行。最佳选项是：", "target": "耳熟能详", "answer_choices": ["神龙见首", "各式各样", "耳熟能详", "不一而足", "一应俱全", "流连忘反", "不胜枚举", "沾沾自喜", "一无所有", "衣食住行"], "type": "mrc"}
    {"input": "唐音是日本汉字音（音读）的一类。广义的「唐音」（唐宋音）指镰仓时代以后直至近代传入日本的汉字音，也就是明清时期的南方标准语「南京官话」。包含室町时代传入的「宋音」与狭义的「唐音」，即江户时代（明清）传入的汉字音。「唐音」的「唐」与「吴音」的「吴」和「汉音」的「汉」一样，并非指朝代，而是对中国的泛称。本文以论述狭义的唐音为主。江户时代传入的「唐音」与之前的「宋音」一样，主要限于佛典诵读及学问研究等，对一般用语的影响很小，仅限于特定的词语。唐音内部尚有不同的系统。就来源而言，大体分为以下三系。第一是隐元隆琦（福州府福清县人）于承应三年（1654）渡日后建立的黄檗宗所传承的用于诵读清规的明代音。第二是延宝五年（1677）渡日的曹洞宗心越派开祖心越兴俦（杭州人）所传的清规和琴谱（明乐）的诵读音。第三是江户时代的汉语学者（1674-1728）及韵镜学者文雄（1700-1763）等研究者通过长崎的通事（翻译官）等所学的中国音。有坂秀世氏将此三类分别称为黄檗唐音、心越系唐音和译官系唐音。这些音皆主要源于明末清初的南京官话音。相比于镰仓时代的宋音反映出更新的音韵变化。唐音由于母胎音的关系，带有明显的类似于现代官话和吴语发音的特色。甚至宕摄入声字也有的以エツ表示，如 阁ケツ。反映这些韵的韵腹为中母音。唐音的例词如下列举（此处一并列举可能为宋音的词）。椅子（イス） 蒲団（フトン） 行灯（アンドン） 行脚（アンギャ） 馅（アン）明（ミン） 清（シン） 普请（フシン） 白汤（パイタン） 石灰（シックイ） 馒头（マンジュウ）\n 从上面的段落中产生一个问题：", "target": "「唐音」的「唐」与「吴音」的「吴」和「汉音」的「汉」都指什么", "type": "mrc"}
    {"input": "“还还没有,没有回来呢.”仅使用以上描述和你对世界所了解的,“有人还没有回来”是正确,错误,或未知？\n答案：", "target": "正确", "answer_choices": ["正确", "错误", "未知"], "type": "nli"}
    {"input": "这些关键词“通用航空，导航系统，航图管理，航空器”代表了这篇论文的摘要：“为满足通用航空器对结构简单、价格低廉的导航系统的需求，提出一种机载便携式导航系统方案。系统以航路图作为背景，通过标定技术实现航图像素坐标与经纬度坐标的配准，并通过对航图的分割与四叉树管理，降低了对设备内存的需求，随着航空器位置更新，系统通过平移、旋转航图实现对航空器的导航。仿真实验结果表明，航空器在航图上定位精确，系统对于航图的平移、旋转响应准确，便携式导航系统可以满足通用航空器导航的需求，对通航飞行安全提供了一定的技术支持。”。这是正确的吗？\n选项：是的，不是\n答案：", "target": "不是", "answer_choices": ["是的", "不是"], "type": "classify"}
    {"input": "根据短文内容，选出缺少的成语填在下划线处。\n 梅柏肯__。“你未经我的许可就擅自结婚，对我而言，要废除这个婚姻#idiom588293#。”他的眼睛闪着微光。“事实上，我相信你会发现登记你们结婚的记录员已经神秘失踪，而替你们主持婚礼的牧师已搬到法国。你想要证明自己结了婚恐怕是难上加难。” \n 候选成语：借花献佛，嗤之以鼻，易如反掌，投桃报李，求之不得，大失所望，虚位以待，无人之境，喜出望外，落井下石。 正确答案是：", "target": "嗤之以鼻", "answer_choices": ["借花献佛", "嗤之以鼻", "易如反掌", "投桃报李", "求之不得", "大失所望", "虚位以待", "无人之境", "喜出望外", "落井下石"], "type": "mrc"}
    {"input": "这是关于哪方面的新闻？买家付了款却没有购房资格，卖家能解除房屋买卖合同吗？\n选项：故事，文化，娱乐，体育，财经，房产，汽车，教育，科技，军事，旅游，国际，股票，农业，游戏\n答案：", "target": "房产", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "阅读短文：\n 方宏进在与律师商量后决定于今日将__于天下。方宏进昨日接受了个别媒体的电话采访，并不避讳自己现在很麻烦。据悉，方宏进身上牵扯的官司不止此次今麦郎这一起，之前还和多家企业发生矛盾，精通金融知识的他一直希望在商业场上大展拳脚，加之其之前央视名嘴的身份，他一直坚信自己能成功。不过，成立了北京澳卫时代广告公司(简称澳卫)的他生意方面却不顺利，记者昨日得悉，该公司已被吊销了营业执照，公司原址也已易主。记者从方宏进一位朋友那边了解到，方宏进经常用酒精麻痹自己，日前接受记者电话采访，还用一起喝酒来“打掩护”，拒绝回应实质性内容。 \n 从候选成语“扫地出门，一网打尽，顺藤摸瓜，狗血喷头，真相大白，走投无路，逍遥法外，治病救人，东窗事发，名正言顺”中选出最适合填在下划线处的成语。正确答案是：", "target": "真相大白", "answer_choices": ["扫地出门", "一网打尽", "顺藤摸瓜", "狗血喷头", "真相大白", "走投无路", "逍遥法外", "治病救人", "东窗事发", "名正言顺"], "type": "mrc"}
    {"input": "“也是作践你自己,好歹我总是你的女儿”我们这样说有道理吗“我是你的女儿改变不了”？是的,不是,或也许？\n答案：", "target": "是的", "answer_choices": ["是的", "不是", "也许"], "type": "nli"}
    {"input": "阅读以下文章，并选择一个合适的成语。文章：\n新浪娱乐讯一向在银幕上保持文艺、内敛气质的黄璐，近日在最新写真中彰显出自身阳光、青春的一面，粉色系运动装扮搭配__的绿茵场背景，如夏日般朝气蓬勃的年轻气息扑面而来，吸引众人目光。\n 候选成语：郁郁葱葱，万家灯火，高楼大厦，车水马龙，欣欣向荣，浮光掠影，东西南北，乔装打扮，下里巴人，四通八达。答案是：", "target": "郁郁葱葱", "answer_choices": ["郁郁葱葱", "万家灯火", "高楼大厦", "车水马龙", "欣欣向荣", "浮光掠影", "东西南北", "乔装打扮", "下里巴人", "四通八达"], "type": "mrc"}
    {"input": "阅读以下对话并回答问题。\n女：今天已经三月十五号了，那个调研报告什么时候可以完成？男：下个月中旬应该可以。问题：男的打算什么时候完成报告？选项：3月初,3月15号,4月中旬,4月底\n答案：", "target": "4月中旬", "answer_choices": ["3月初", "3月15号", "4月中旬", "4月底"], "type": "mrc"}
    {"input": "阅读下列论文摘要，然后判断下面的这些关键词是否都是论文摘要合适的关键词？\n摘要：集成多跳中继技术的WiMAXMesh网络中,当发送功率和信道数目一定时,用户接入链路的传输速率直接取决于用户到中继的距离.在满足用户到中继距离要求的条件下,研究最少中继部署问题具有保证网络性能、降低组网成本的意义.文中将该问题转化为最少团划分问题,基于用户邻居信息提出启发式算法MAXDCP,基于用户位置信息提出启发式算法GEOCP.模拟结果表明:与该问题的最新算法MIS相比,在相同时间复杂度下,MAXDCP部署中继的个数平均减少23.8％,GEOCP平均减少35％；与已有PTAS算法HS相比,GEOCP部署中继个数平均减少18.5％,且时间复杂度更低.MAXDCP和GEOCP很好地保证了网络性能、降低了组网成本.\n关键词：问题，信息，中继，组网。答案是：\n选项：是的，不是\n答案：", "target": "不是", "answer_choices": ["是的", "不是"], "type": "classify"}
    {"input": "哪个类别最好的描述了这篇新闻？芦淞区档案史志局指导档案规范化管理工作\n选项：故事，文化，娱乐，体育，财经，房产，汽车，教育，科技，军事，旅游，国际，股票，农业，游戏\n答案：", "target": "财经", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "根据短文内容，选出缺少的成语填在下划线处。\n 慢慢地，“朝圣”变成对亚洲无法满足的好奇，而不是倒拨世纪之钟的时针，寻觅历史的源头。于是，他想到哪儿就到哪儿，不管亚历山大大帝是不是到过那个地方。他骑马翻过东土耳其的__，看见积雪覆盖着山坡，从撒哈拉大沙漠#idiom598242#吹来的黄沙，又将那山坡变成粉红色。现在，让他#idiom598243#的是，大自然神奇的力量和人类如何面对大自然、改造大自然。 \n 候选成语：崇山峻岭，冰天雪地，肃然起敬，一望无际，翻山越岭，各抒己见，一马平川，玄之又玄，开诚布公，成年累月。 正确答案是：", "target": "崇山峻岭", "answer_choices": ["崇山峻岭", "冰天雪地", "肃然起敬", "一望无际", "翻山越岭", "各抒己见", "一马平川", "玄之又玄", "开诚布公", "成年累月"], "type": "mrc"}
    {"input": "摘要：为了解汉族民间童帽所隐含的民俗审美及民俗文化,以江南大学民间服饰传习馆藏品为研究对象,通过实物归纳法对其装饰用色、图案、配件,以及装饰元素的布局特点、装饰纹样造型特点进行分析研究.结果表明:近代汉族民间童帽装饰元素丰富,充满童趣,形成了自己的装饰规范,较其他类服饰更具特色;童帽装饰元素与民间生活密切相关,并非偶然形成.其丰富的文化内涵为研究与儿童相关的民俗风俗提供参考,为儿童服饰设计提供了丰富的素材.\n 以下的关键词都是这篇摘要合适的关键词吗？关键词：童帽，图案，装饰。答案是：\n选项：是的，不是\n答案：", "target": "不是", "answer_choices": ["是的", "不是"], "type": "classify"}
    {"input": "给定“王琦瑶嘴里说抱歉的话,心里却想:严师母的意思其实是说她不识抬举”保证是真实的吗“王琦瑶在心里反思以后该怎么做的更好”？是的,不是,或也许？\n答案：", "target": "不是", "answer_choices": ["是的", "不是", "也许"], "type": "nli"}
    {"input": "给定“当然了,当然我这身材等于男模横着放,所以我不走秀,我坐秀”保证是真实的吗““我”喜欢坐着不爱动”？是的,不是,或也许？\n答案：", "target": "也许", "answer_choices": ["是的", "不是", "也许"], "type": "nli"}
    {"input": "哪个类别最好的描述了这篇新闻？魅力乡村｜忻州岢岚宋家沟村新貌\n选项：故事，文化，娱乐，体育，财经，房产，汽车，教育，科技，军事，旅游，国际，股票，农业，游戏\n答案：", "target": "旅游", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "\n段落：日本传统歌舞剧场有一条奇特的规定：观众即使看到入迷处，也只能心领神会，而不准喝彩，否则会被他人侧目而视。而台下寥寥无几的喝彩者则是剧院特邀的职业喝彩师，受过专门的喝彩训练，熟谙什么时候用什么方式喝彩，以便同台上的演员上下呼应，使演出更加趣味盎然。这些职业喝彩师多为男性，社会地位颇高，著名的喝彩大师甚至同演员齐名。他们可以自由出入剧场，坐特等包厢，有的剧团和剧院还特邀大名鼎鼎的喝彩大师光临以抬高身价。自然，喝彩大师领取的报酬也很高。不过，现在日本的喝彩师已越来越少，因而培养职业喝彩师已成为日本传统歌舞的当务之急。  \n问：目前急需解决的是什么?  选项：邀请喝彩大师，抬高喝彩大师身份，喝彩大师能自由出入，尽快培养职业喝彩师 \n答案：", "target": "尽快培养职业喝彩师", "type": "mrc", "answer_choices": ["邀请喝彩大师", "抬高喝彩大师身份", "喝彩大师能自由出入", "尽快培养职业喝彩师"]}
    {"input": "摘要：针对采用一次二阶矩法计算复杂、高度非线性功能函数的可靠指标时,求解功能函数对随机变量的偏导数极其困难,并且偏导数形式非常复杂等问题,提出用响应面函数代替原功能函数的方法,使其求导过程方便,并且使偏导数形式转化为随机变量的线性表达式,便于程序化求解.然后以计算三维Hoek-Brown强度准则的可靠度为例,确认响应面法在复杂、高度非线性功能函数可靠度计算中的可行性,并与变量代换法和复合函数求导法则的计算结果进行比较,说明利用响应面法计算的结果具有较高的精度.最后,用响应面法分析强度准则参数分布类型和岩体参数之间的相关性对三维Hoek-Brown准则可靠度的影响规律.研究结果表明:该方法具有较高精度;强度准则参数分布类型对可靠指标的敏感性较弱;岩体参数的负相关系数与可靠指标线性相关,对可靠指标的影响不大.\n 以下的关键词都是这篇摘要合适的关键词吗？关键词：Hoek-Brown准则，功能，响应面法。答案是：\n选项：是的，不是\n答案：", "target": "不是", "answer_choices": ["是的", "不是"], "type": "classify"}
    {"input": "以下两句话的意思相同的吗？“怎么我的蚂蚁借呗不能用了”，“怎么我不能使用蚂蚁借呗”。选项：是的，不是。答案：", "target": "是的", "answer_choices": ["是的", "不是"], "type": "classify"}
    {"input": "“现在婴儿的健康状况仍很严重”记住上面的文字,考虑:“婴儿已经完全康复了。”这是总是,绝不,或有时正确的？\n答案：", "target": "绝不", "answer_choices": ["总是", "绝不", "有时"], "type": "nli"}
    {"input": "这是一个成语填空任务。上文是：早上锻炼还可以提高你一天的。 \n下文是:，所以调整一下作息时间，早起30分钟，锻炼一下吧。导语：如果你2011年的计划之一是减肥，希望你在1号的时候没有满脑子想着“从明天开始”减肥没有捷径，但是可以有“jumpstart”，就是一个见效快的开始。那些“常年”减肥的女性朋友们，都应当知道减肥最难得是后期的坚持和养成一个健康的生活方式。\n候选的成语：安然无恙，误打误撞，起死回生，新陈代谢，故态复萌，自食其力，死里逃生，因祸得福，返老还童，开山祖师。请问：我们应该填写哪个成语？\n答案：", "target": "新陈代谢", "answer_choices": ["安然无恙", "误打误撞", "起死回生", "新陈代谢", "故态复萌", "自食其力", "死里逃生", "因祸得福", "返老还童", "开山祖师"], "type": "mrc"}
    {"input": "阅读以下段落：\n我想找个演外国旧片的影院，走了两家都满座。走到一家剧场，有人迎上来问我要不要退票。我只肯出一张电影票的价，那人踌躇一下，索性把票子白送给我，我进剧场时不禁有些怀疑。剧场里只有稀稀拉拉儿个观众，台上一个古装少女在跳着徐缓但十分舒展的中国古典舞。水袖在淡蓝的光中拖来曳去，腰肢婀娜地扭动，筝和琵琶流水般地倾泻，天幕一片辽远清丽的冷调子。曲终舞罢，灯光暗下来。尽管我很入迷，也没鼓掌。舞台再次亮起来时，这个姑娘穿得很少地跳出来。跳了一会儿我才明白，她跳的是一个神话中的女英雄。在共工那个倒霉蛋头触不周山、造成__的严重后果后，这个女人像瓦匠一样把天重新砌好，使我们人类得以继续繁衍。据说，也是这个女人，同她的同胞交尾产卵，提供了第一批人种。值得欣慰的是编导没让这个女孩子裹上一层蛇皮，否则，她就不能向我们展现她那双极富表现力、#idiom598598#的腿。最后，我还是觉得扫兴。我以为不该让一个女孩子向成年人表现雄壮、慈悲，即使她是好心眼。我对这个女孩子印象深刻，因为她表现#idiom598599#后接踵而来的死亡很传神，简直可以说死得#idiom598600#。\n其中下划线处需要填写成语，有以下候选项：生气勃勃，洋洋得意，明媒正娶，怨气冲天，内忧外患，阒其无人，功成名遂，祸从天降，祸不单行，天塌地陷。下划线处合适的成语是：", "target": "天塌地陷", "answer_choices": ["生气勃勃", "洋洋得意", "明媒正娶", "怨气冲天", "内忧外患", "阒其无人", "功成名遂", "祸从天降", "祸不单行", "天塌地陷"], "type": "mrc"}
    {"input": "这个是关于哪方面的App应用程序的描述？银行，社区，电商，支付，经营，卡牌，借贷，驾校，理财，职考，新闻，旅游，交通，魔幻，医疗，影像，动作，工具，体育，小说，运动，相机，工具，快递，教育，股票，菜谱，行车，仙侠，亲子，购物，射击，漫画，小学，同城，成人，求职，电子，艺术，赚钱，约会，经营，兼职，视频，音乐，英语，棋牌，摄影，养生，办公，政务，视频，论坛，彩票，直播，其他，休闲，策略，通讯，买车，违章，地图，民航，电台，语言，搞笑，婚恋，超市，养车，杂志，在线，家政，影视，装修，资讯，社交，餐饮，美颜，挂号，飞行，预定，票务，笔记，买房，外卖，母婴，打车，情侣，日程，租车，博客，百科，绘画，铁路，生活，租房，酒店，保险，问答，收款，竞技，唱歌，技术，减肥，工作，团购，记账，女性，公务，二手，美妆，汽车，行程，免费，教辅，两性，出国，婚庆，民宿界面简洁清晰，没有多余的装饰，方便您更加直观的查阅分析各彩种信息动态。主推时下热门彩种的开奖信息、历史开奖、走势分析、预测选号、彩种排行等。是您分析走势的必备工具。,,提升体验，修复部分问题。\n答案：", "target": "彩票", "answer_choices": ["银行", "社区", "电商", "支付", "经营", "卡牌", "借贷", "驾校", "理财", "职考", "新闻", "旅游", "交通", "魔幻", "医疗", "影像", "动作", "工具", "体育", "小说", "运动", "相机", "工具", "快递", "教育", "股票", "菜谱", "行车", "仙侠", "亲子", "购物", "射击", "漫画", "小学", "同城", "成人", "求职", "电子", "艺术", "赚钱", "约会", "经营", "兼职", "视频", "音乐", "英语", "棋牌", "摄影", "养生", "办公", "政务", "视频", "论坛", "彩票", "直播", "其他", "休闲", "策略", "通讯", "买车", "违章", "地图", "民航", "电台", "语言", "搞笑", "婚恋", "超市", "养车", "杂志", "在线", "家政", "影视", "装修", "资讯", "社交", "餐饮", "美颜", "挂号", "飞行", "预定", "票务", "笔记", "买房", "外卖", "母婴", "打车", "情侣", "日程", "租车", "博客", "百科", "绘画", "铁路", "生活", "租房", "酒店", "保险", "问答", "收款", "竞技", "唱歌", "技术", "减肥", "工作", "团购", "记账", "女性", "公务", "二手", "美妆", "汽车", "行程", "免费", "教辅", "两性", "出国", "婚庆", "民宿"], "type": "classify"}
    {"input": "带着问题来阅读文章并回答问题：\n问：教授想说明什么道理?  \n选项：装满杯子可以有多种方式，如何去解决生活中的问题，人生必须要实现一些目标，别让烦恼和忧郁占据生活 \n段落：一位教授在一个空杯子里装满大石块，又倒进一些小石子，并轻轻摇动杯子，让小石子滚进石块之间的空隙；然后教授拿出一些沙子倒进杯子，摇动杯子，把小石子间的空隙都填满；最后他又往杯子里倒水，把杯子所有的空间都填满。做完这些，教授对学生们说：“现在，我想让大家把这个杯子理解为生活。里面的大石块代表生命中最珍贵的东西，比如说家庭、伴侣、健康、孩子等等，所有这些对我们来说都极为重要，一旦失去将永远无法弥补；小石子代表生命中较为重要的东西，如工作、房子、车子等等；沙子代表生命中的日常小事；水代表烦恼、忧郁。请记住，如果我们先把水和沙子装进杯子，那就没有空间去装大石块和小石子了。”\n答案：", "target": "别让烦恼和忧郁占据生活", "type": "mrc", "answer_choices": ["装满杯子可以有多种方式", "如何去解决生活中的问题", "人生必须要实现一些目标", "别让烦恼和忧郁占据生活"]}
    {"input": "对话：男：欢迎你，刘经理，好久不见了。女：是啊，如果不是因为工作，我们还真是难得见一次面。男：这次我要好好儿请你吃个饭，上次你走得太急了。女：那就太谢谢你了。问题：他们可能是什么关系？选项：夫妻,朋友,师生\n答案：", "target": "朋友", "answer_choices": ["夫妻", "朋友", "师生"], "type": "mrc"}
    {"input": "阅读文章：\n“没关系，”他尽量__地说，“我也迟到了。杰克和米莉。布坎南打架了，我正要走的时候他来到我家。我给他吃了一杯酒，打发他上床了。”他为她倒了一杯酒，可她没有接杯子。“他就是你办公室的那位吗？我是说，在卡尔参议员办公室工作的那位吗？”她虽然没见过他的同事，但是他们的\n其中下划线的地方需要填写成语，有以下候选的成语：心平气和，以理服人，认祖归宗，开诚布公，依然故我，生吞活剥，和颜悦色，将心比心，不动声色，一本正经。正确的成语是：", "target": "心平气和", "answer_choices": ["心平气和", "以理服人", "认祖归宗", "开诚布公", "依然故我", "生吞活剥", "和颜悦色", "将心比心", "不动声色", "一本正经"], "type": "mrc"}
    {"input": "这是关于哪方面的新闻？有哪些娱乐圈里面的明星追星？\n选项：故事，文化，娱乐，体育，财经，房产，汽车，教育，科技，军事，旅游，国际，股票，农业，游戏\n答案：", "target": "娱乐", "answer_choices": ["故事", "文化", "娱乐", "体育", "财经", "房产", "汽车", "教育", "科技", "军事", "旅游", "国际", "股票", "农业", "游戏"], "type": "classify"}
    {"input": "摘要：提应用常规观测资料、NCEP再分析资料，对比分析了山东两次春季黄淮气旋暴雨落区异同点。发现春季影响山东的黄淮气旋暴雨区集中出现在气旋中心北侧的偏东风中，且主要位于东北气流中。暴雨区偏北的程度，与影响系统的后倾程度及我国东北地区是否存在高压有关。当系统明显后倾时，锋面坡度小，暖湿气流沿锋面向北爬升的更远，暴雨区更偏北；当我国东北地区存在高压时，其南侧东北气流经渤海侵入850hPa低涡后部，与低涡前东南气流在风向上渐近辐合，在低涡北侧产生辐合中心，从而产生暴雨区。此外，地面东北风形成的冷垫，有利于南方暖湿气流向北爬升。实际暴雨落区预报中，需综合分析系统的空间结构、周围系统的影响及温度场的配置等。 \n关键词：hPa低涡，5，暴雨落区，系统空间结构。请问：上面的关键词都是这篇摘要合适的关键词吗？\n选项：是的，不是\n答案：", "target": "是的", "answer_choices": ["是的", "不是"], "type": "classify"}

### 基线效果
 
    十一期间，添加中。。。

### 技术交流和问题反馈
<p float="left">
   <img src="https://github.com/CLUEbenchmark/pCLUE/blob/main/resources/imgs/pCLUE.jpeg"  width="29%" height="29%" />   
   <img src="https://github.com/CLUEbenchmark/pCLUE/blob/main/resources/imgs/brightmart.jpeg"  width="29%" height="29%" /> 
</p> 
       
          
