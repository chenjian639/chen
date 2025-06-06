<!DOCTYPE html>
<html lang="zh-CN">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>中国历史人物分类系统</title>
    <style>
        body {
            font-family: 'Microsoft YaHei', sans-serif;
            margin: 20px;
            background-color: #f5f5f5;
        }

       .search-container {
            margin-bottom: 20px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

       .search-input {
            padding: 8px 12px;
            border: 1px solid #ccc;
            border-radius: 4px;
            flex: 1;
            font-size: 16px;
        }

       .search-button {
            padding: 8px 16px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }

       .search-button:hover {
            background-color: #45a049;
        }

       .container {
            display: flex;
            gap: 20px;
        }

       .filter-panel {
            width: 250px;
            background: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

       .results-panel {
            flex: 1;
            background: white;
            padding: 15px;
            border-radius: 8px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

       .filter-group {
            margin-bottom: 20px;
        }

       .filter-title {
            font-weight: bold;
            margin-bottom: 10px;
            color: #333;
        }

       .filter-option {
            display: flex;
            align-items: center;
            margin: 5px 0;
            cursor: pointer;
        }

       .checkbox {
            width: 16px;
            height: 16px;
            border: 1px solid #999;
            border-radius: 3px;
            margin-right: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

       .checkbox.checked {
            background-color: #4CAF50;
            border-color: #4CAF50;
            color: white;
        }

       .person-card {
            padding: 10px;
            border-bottom: 1px solid #eee;
            cursor: pointer;
        }

       .person-card:hover {
            background-color: #f0f0f0;
        }

       .detail-panel {
            display: none;
            margin-top: 20px;
            padding: 15px;
            background: #f9f9f9;
            border-radius: 8px;
        }

       .back-btn {
            margin-top: 10px;
            padding: 5px 10px;
            background: #4CAF50;
            color: white;
            border: none;
            border-radius: 3px;
            cursor: pointer;
        }
    </style>
</head>

<body>
    <h1>中国历史人物分类系统</h1>
    <div class="search-container">
        <input type="text" id="search-input" class="search-input" placeholder="输入人名进行搜索">
        <button class="search-button" onclick="searchPeople()">搜索</button>
    </div>
    <div class="container">
        <!-- 筛选面板 -->
        <div class="filter-panel">
            <div class="filter-group">
                <div class="filter-title">性别</div>
                <div class="filter-option" onclick="toggleFilter('gender', '男')">
                    <div class="checkbox" id="gender-男"></div>
                    <span>男</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('gender', '女')">
                    <div class="checkbox" id="gender-女"></div>
                    <span>女</span>
                </div>
            </div>
            <div class="filter-group">
                <div class="filter-title">地域</div>
                <div class="filter-option" onclick="toggleFilter('region', '北京')">
                    <div class="checkbox" id="region-北京"></div>
                    <span>北京</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '天津')">
                    <div class="checkbox" id="region-天津"></div>
                    <span>天津</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '河北')">
                    <div class="checkbox" id="region-河北"></div>
                    <span>河北</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '山西')">
                    <div class="checkbox" id="region-山西"></div>
                    <span>山西</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '内蒙古')">
                    <div class="checkbox" id="region-内蒙古"></div>
                    <span>内蒙古</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '辽宁')">
                    <div class="checkbox" id="region-辽宁"></div>
                    <span>辽宁</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '吉林')">
                    <div class="checkbox" id="region-吉林"></div>
                    <span>吉林</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '黑龙江')">
                    <div class="checkbox" id="region-黑龙江"></div>
                    <span>黑龙江</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '上海')">
                    <div class="checkbox" id="region-上海"></div>
                    <span>上海</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '江苏')">
                    <div class="checkbox" id="region-江苏"></div>
                    <span>江苏</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '浙江')">
                    <div class="checkbox" id="region-浙江"></div>
                    <span>浙江</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '安徽')">
                    <div class="checkbox" id="region-安徽"></div>
                    <span>安徽</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '福建')">
                    <div class="checkbox" id="region-福建"></div>
                    <span>福建</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '江西')">
                    <div class="checkbox" id="region-江西"></div>
                    <span>江西</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '山东')">
                    <div class="checkbox" id="region-山东"></div>
                    <span>山东</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '河南')">
                    <div class="checkbox" id="region-河南"></div>
                    <span>河南</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '湖北')">
                    <div class="checkbox" id="region-湖北"></div>
                    <span>湖北</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '湖南')">
                    <div class="checkbox" id="region-湖南"></div>
                    <span>湖南</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '广东')">
                    <div class="checkbox" id="region-广东"></div>
                    <span>广东</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '海南')">
                    <div class="checkbox" id="region-海南"></div>
                    <span>海南</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '四川')">
                    <div class="checkbox" id="region-四川"></div>
                    <span>四川</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '贵州')">
                    <div class="checkbox" id="region-贵州"></div>
                    <span>贵州</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '云南')">
                    <div class="checkbox" id="region-云南"></div>
                    <span>云南</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '西藏')">
                    <div class="checkbox" id="region-西藏"></div>
                    <span>西藏</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '陕西')">
                    <div class="checkbox" id="region-陕西"></div>
                    <span>陕西</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '甘肃')">
                    <div class="checkbox" id="region-甘肃"></div>
                    <span>甘肃</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '青海')">
                    <div class="checkbox" id="region-青海"></div>
                    <span>青海</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '宁夏')">
                    <div class="checkbox" id="region-宁夏"></div>
                    <span>宁夏</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '新疆')">
                    <div class="checkbox" id="region-新疆"></div>
                    <span>新疆</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '香港')">
                    <div class="checkbox" id="region-香港"></div>
                    <span>香港</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '澳门')">
                    <div class="checkbox" id="region-澳门"></div>
                    <span>澳门</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '台湾')">
                    <div class="checkbox" id="region-台湾"></div>
                    <span>台湾</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('region', '其他')">
                    <div class="checkbox" id="region-其他"></div>
                    <span>其他</span>
                </div>
            </div>
            <div class="filter-group">
                <div class="filter-title">民族</div>
                <div class="filter-option" onclick="toggleFilter('ethnicity', '汉族')">
                    <div class="checkbox" id="ethnicity-汉族"></div>
                    <span>汉族</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('ethnicity', '少数民族')">
                    <div class="checkbox" id="ethnicity-少数民族"></div>
                    <span>少数民族</span>
                </div>
            </div>
            <div class="filter-group">
                <div class="filter-title">朝代</div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '上古')">
                    <div class="checkbox" id="dynasty-上古"></div>
                    <span>上古（前3000年及更早 - 前2070年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '夏商西周')">
                    <div class="checkbox" id="dynasty-夏商西周"></div>
                    <span>夏商西周（前2070年 - 前771年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '春秋战国')">
                    <div class="checkbox" id="dynasty-春秋战国"></div>
                    <span>春秋战国（前770年 - 前221年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '秦')">
                    <div class="checkbox" id="dynasty-秦"></div>
                    <span>秦（前221年 - 前206年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '汉')">
                    <div class="checkbox" id="dynasty-汉"></div>
                    <span>汉（前202年 - 220年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '三国')">
                    <div class="checkbox" id="dynasty-三国"></div>
                    <span>三国（220年 - 280年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '两晋')">
                    <div class="checkbox" id="dynasty-两晋"></div>
                    <span>两晋（266年 - 420年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '南北朝')">
                    <div class="checkbox" id="dynasty-南北朝"></div>
                    <span>南北朝（420年 - 589年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '隋')">
                    <div class="checkbox" id="dynasty-隋"></div>
                    <span>隋（581年 - 618年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '唐')">
                    <div class="checkbox" id="dynasty-唐"></div>
                    <span>唐（618年 - 907年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '五代十国')">
                    <div class="checkbox" id="dynasty-五代十国"></div>
                    <span>五代十国（907年 - 979年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '宋')">
                    <div class="checkbox" id="dynasty-宋"></div>
                    <span>宋（960年 - 1279年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '元')">
                    <div class="checkbox" id="dynasty-元"></div>
                    <span>元（1271年 - 1368年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '明')">
                    <div class="checkbox" id="dynasty-明"></div>
                    <span>明（1368年 - 1644年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '清')">
                    <div class="checkbox" id="dynasty-清"></div>
                    <span>清（1644年 - 1912年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '民国')">
                    <div class="checkbox" id="dynasty-民国"></div>
                    <span>民国（1912年 - 1949年）</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('dynasty', '新中国')">
                    <div class="checkbox" id="dynasty-新中国"></div>
                    <span>新中国（1949年 - 至今）</span>
                </div>
            </div>
            <div class="filter-group">
                <div class="filter-title">领域</div>
                <div class="filter-option" onclick="toggleFilter('field', '政治')">
                    <div class="checkbox" id="field-政治"></div>
                    <span>政治</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '军事')">
                    <div class="checkbox" id="field-军事"></div>
                    <span>军事</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '文学')">
                    <div class="checkbox" id="field-文学"></div>
                    <span>文学</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '艺术')">
                    <div class="checkbox" id="field-艺术"></div>
                    <span>艺术</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '科学')">
                    <div class="checkbox" id="field-科学"></div>
                    <span>科学</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '宗教')">
                    <div class="checkbox" id="field-宗教"></div>
                    <span>宗教</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '思想')">
                    <div class="checkbox" id="field-思想"></div>
                    <span>思想</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '经济')">
                    <div class="checkbox" id="field-经济"></div>
                    <span>经济</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('field', '其他')">
                    <div class="checkbox" id="field-其他"></div>
                    <span>其他</span>
                </div>
            </div>
            <div class="filter-group">
                <div class="filter-title">历史评价</div>
                <div class="filter-option" onclick="toggleFilter('evaluation', '褒')">
                    <div class="checkbox" id="evaluation-褒"></div>
                    <span>褒</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('evaluation', '贬')">
                    <div class="checkbox" id="evaluation-贬"></div>
                    <span>贬</span>
                </div>
                <div class="filter-option" onclick="toggleFilter('evaluation', '中')">
                    <div class="checkbox" id="evaluation-中"></div>
                    <span>中</span>
                </div>
            </div>
        </div>
        <!-- 结果面板 -->
        <div class="results-panel">
            <h2>筛选结果</h2>
            <div id="results-container">
                <!-- 结果将通过JavaScript动态生成 -->
            </div>
            <div id="detail-container" class="detail-panel">
                <h2 id="detail-title">人物详情</h2>
                <div id="detail-content"></div>
                <button class="back-btn" onclick="backToList()">返回列表</button>
            </div>
        </div>
    </div>
	<script>
        // 人物数据库
        const peopleData = [
            { id: 1, name: "黄帝", gender: "男", region: "其他", ethnicity: "汉族", dynasty: "上古", field: "政治、军事", evaluation: "褒",
                detail: "黄帝是中国远古时期部落联盟首领，被尊为中华“人文初祖”。他联合炎帝打败蚩尤，统一中原部落，促进了华夏民族的形成，对中国文化、政治等方面的发展有着深远影响。" },
            { id: 2, name: "大禹", gender: "男", region: "其他", ethnicity: "汉族", dynasty: "夏商西周", field: "政治、水利", evaluation: "褒",
                detail: "大禹治水有功，受舜禅让而继承帝位，建立夏朝。他治理洪水，划定九州，推动了社会的发展和国家的形成。" },
            { id: 3, name: "孔子", gender: "男", region: "山东", ethnicity: "汉族", dynasty: "春秋战国", field: "思想、教育", evaluation: "褒",
                detail: "孔子是儒家学派创始人，其思想核心是仁和礼，主张有教无类，打破了贵族对教育的垄断。他的学说对中国和世界文化都产生了极为深远的影响。" },
            { id: 4, name: "司马迁", gender: "男", region: "陕西", ethnicity: "汉族", dynasty: "汉", field: "文学", evaluation: "褒",
                detail: "司马迁撰写了中国第一部纪传体通史《史记》，记载了从上古传说到汉武帝时期的历史，对后世史学和文学的发展影响巨大。" },
            { id: 5, name: "秦始皇", gender: "男", region: "陕西", ethnicity: "汉族", dynasty: "秦", field: "政治", evaluation: "中",
                detail: "秦始皇统一六国，建立了中国历史上第一个大一统王朝。他推行郡县制、统一度量衡和文字等措施，对中国历史发展影响深远，但在位期间也有暴政之举。" },
            { id: 6, name: "屈原", gender: "男", region: "湖北", ethnicity: "汉族", dynasty: "春秋战国", field: "文学、政治", evaluation: "褒",
                detail: "屈原是中国浪漫主义文学的奠基人，他的作品充满爱国情怀，代表作《离骚》是中国古代最长的抒情诗。他在政治上主张举贤任能、修明法度。" },
            { id: 7, name: "赵括", gender: "男", region: "河北", ethnicity: "汉族", dynasty: "春秋战国", field: "军事", evaluation: "贬",
                detail: "赵括熟读兵书，但缺乏实战经验，在长平之战中指挥不力，致使赵军大败，自己也战死沙场，“纸上谈兵”的典故就源自于他。" },
            { id: 8, name: "蔺相如", gender: "男", region: "河北", ethnicity: "汉族", dynasty: "春秋战国", field: "政治", evaluation: "褒",
                detail: "蔺相如凭借智慧和勇气，完璧归赵、渑池之会中维护了赵国的尊严和利益，后官拜上卿，与廉颇上演“将相和”的佳话。" },
            { id: 9, name: "张衡", gender: "男", region: "河南", ethnicity: "汉族", dynasty: "汉", field: "科学、文学", evaluation: "褒",
                detail: "张衡发明了地动仪和浑天仪，在天文学、地震学等领域成就卓越，同时他在文学方面也有很高造诣，代表作有《二京赋》等。" },
            { id: 10, name: "班昭", gender: "女", region: "陕西", ethnicity: "汉族", dynasty: "汉", field: "文学", evaluation: "褒",
                detail: "班昭博学高才，续写《汉书》，是中国第一位女史学家，还著有《女诫》等作品，对后世影响较大。" },
            { id: 11, name: "华佗", gender: "男", region: "安徽", ethnicity: "汉族", dynasty: "汉", field: "科学", evaluation: "褒",
                detail: "华佗是东汉末年著名医学家，发明麻沸散，擅长外科手术，被后人称为“外科圣手”“外科鼻祖”。" },
            { id: 12, name: "貂蝉", gender: "女", region: "山西", ethnicity: "汉族", dynasty: "三国", field: "其他", evaluation: "中",
                detail: "貂蝉是中国古代四大美女之一，在民间传说中她参与了王允的连环计，周旋于董卓与吕布之间，影响了当时的政治格局。" },
            { id: 13, name: "张辽", gender: "男", region: "山西", ethnicity: "汉族", dynasty: "三国", field: "军事", evaluation: "褒",
                detail: "张辽是曹魏名将，作战勇猛且富有谋略，多次立下战功，在合肥之战中以少胜多，威震江东。" },
            { id: 14, name: "陶渊明", gender: "男", region: "江西", ethnicity: "汉族", dynasty: "两晋", field: "文学", evaluation: "褒",
                detail: "陶渊明是田园诗派创始人，其作品风格清新自然，表达对田园生活的热爱和对官场的厌弃，代表作有《桃花源记》《饮酒》等。" },
            { id: 15, name: "拓跋宏", gender: "男", region: "山西", ethnicity: "鲜卑族", dynasty: "南北朝", field: "政治", evaluation: "褒",
                detail: "拓跋宏即北魏孝文帝，他推行汉化改革，促进了民族融合，推动了北魏社会的发展和鲜卑族的封建化进程。" },
            { id: 16, name: "祖冲之", gender: "男", region: "河北", ethnicity: "汉族", dynasty: "南北朝", field: "科学", evaluation: "褒",
                detail: "祖冲之是南北朝时期杰出的数学家、天文学家，他首次将“圆周率”精算到小数第七位，对数学和天文学的发展做出了重大贡献。" },
            { id: 17, name: "谢道韫", gender: "女", region: "浙江", ethnicity: "汉族", dynasty: "两晋", field: "文学", evaluation: "褒",
                detail: "谢道韫是东晋才女，聪慧有才辩，以“未若柳絮因风起”形容雪花而闻名，在文学方面有一定成就。" },
            { id: 18, name: "杨广", gender: "男", region: "陕西", ethnicity: "汉族", dynasty: "隋", field: "政治", evaluation: "贬",
                detail: "杨广即隋炀帝，在位期间修建大运河、开创科举制，对后世影响深远，但他滥用民力，穷奢极欲，导致民怨沸腾，隋朝二世而亡。" },
            { id: 19, name: "李白", gender: "男", region: "四川", ethnicity: "汉族", dynasty: "唐", field: "文学", evaluation: "褒",
                detail: "李白被誉为“诗仙”，其诗歌风格豪放飘逸、意境奇妙，是唐代浪漫主义诗人的代表，代表作有《将进酒》《望庐山瀑布》等。" },
            { id: 20, name: "武则天", gender: "女", region: "山西", ethnicity: "汉族", dynasty: "唐", field: "政治", evaluation: "中",
                detail: "武则天是中国历史上唯一的正统女皇帝，她在位期间重视人才选拔，推行了一些促进经济发展的政策，但也重用酷吏，晚年生活较为奢靡。" },
            { id: 21, name: "玄奘", gender: "男", region: "河南", ethnicity: "汉族", dynasty: "唐", field: "宗教", evaluation: "褒",
                detail: "玄奘西行天竺取经，带回大量佛经并翻译，为佛教在中国的传播和发展做出重要贡献，其经历被写成《大唐西域记》。" },
            { id: 22, name: "安禄山", gender: "男", region: "辽宁", ethnicity: "胡人（少数民族）", dynasty: "唐", field: "军事、政治", evaluation: "贬",
                detail: "安禄山是唐朝藩镇节度使，发动安史之乱，给社会经济和人民生活带来了巨大灾难，使唐朝由盛转衰。" },
            { id: 23, name: "郭子仪", gender: "男", region: "陕西", ethnicity: "汉族", dynasty: "唐", field: "军事", evaluation: "褒",
                detail: "郭子仪是唐朝名将，在安史之乱中平定叛乱，收复失地，为唐朝的稳定和延续立下赫赫战功，历仕四朝，德高望重。" },
            { id: 24, name: "李清照", gender: "女", region: "山东", ethnicity: "汉族", dynasty: "宋", field: "文学", evaluation: "褒",
                detail: "李清照是宋代著名女词人，婉约派代表，有“千古第一才女”之称。她的词作情感细腻，语言清新自然，代表作有《如梦令·常记溪亭日暮》《声声慢·寻寻觅觅》等。" },
            { id: 25, name: "岳飞", gender: "男", region: "河南", ethnicity: "汉族", dynasty: "宋", field: "军事", evaluation: "褒",
                detail: "岳飞是南宋抗金名将，他精忠报国，率领岳家军同金军进行了大小数百次战斗，保卫了南宋的半壁江山，但最终被秦桧以“莫须有”的罪名陷害。" },
            { id: 26, name: "秦桧", gender: "男", region: "江苏", ethnicity: "汉族", dynasty: "宋", field: "政治", evaluation: "贬",
                detail: "秦桧是南宋奸臣，以“莫须有”的罪名陷害岳飞，主张对金求和，出卖国家利益，遭到后世唾弃。" },
            { id: 27, name: "李时珍", gender: "男", region: "湖北", ethnicity: "汉族", dynasty: "明", field: "科学", evaluation: "褒",
                detail: "李时珍是明代著名医药学家，他历时二十七年编成《本草纲目》，对中国和世界医药学的发展做出了卓越贡献。" },
            { id: 28, name: "沈括", gender: "男", region: "浙江", ethnicity: "汉族", dynasty: "宋", field: "科学", evaluation: "褒",
                detail: "沈括是北宋科学家、政治家，他精通天文、数学、物理学、化学、地质学等多门学科，著有《梦溪笔谈》，被称为“中国整部科学史中最卓越的人物”。" },
            { id: 29, name: "成吉思汗", gender: "男", region: "蒙古", ethnicity: "蒙古族（少数民族）", dynasty: "元", field: "军事、政治", evaluation: "褒",
                detail: "成吉思汗即铁木真，他统一蒙古各部，建立大蒙古国，多次发动对外征服战争，疆域横跨欧亚大陆，对世界历史产生了深远影响。" },
            { id: 30, name: "关汉卿", gender: "男", region: "河北", ethnicity: "汉族", dynasty: "元", field: "文学", evaluation: "褒",
                detail: "关汉卿是元杂剧奠基人，他的作品具有强烈的现实批判性，代表作有《窦娥冤》等，对元杂剧和后来戏曲的发展产生了重要影响。" },
            { id: 31, name: "郑和", gender: "男", region: "云南", ethnicity: "回族（少数民族）", dynasty: "明", field: "军事、外交", evaluation: "褒",
                detail: "郑和是明朝太监、航海家，他率领船队七下西洋，加强了中国与亚非各国的友好往来和经济文化交流，展示了明朝的国力和威望。" },
            { id: 32, name: "张角", gender: "男", region: "河北", ethnicity: "汉族", dynasty: "汉", field: "宗教、军事", evaluation: "中",
                detail: "张角是东汉末年黄巾起义领袖，他以太平道为组织形式，发动起义，沉重打击了东汉王朝的统治，但也给社会带来了动荡。" },
            { id: 33, name: "沈万三", gender: "男", region: "江苏", ethnicity: "汉族", dynasty: "明", field: "商业", evaluation: "中",
                detail: "沈万三是元末明初商人，他富可敌国，曾资助朱元璋修建南京城，但后来因富而招祸，被朱元璋流放。" },
            { id: 34, name: "张三丰", gender: "男", region: "辽宁", ethnicity: "汉族", dynasty: "明", field: "武术、道教", evaluation: "褒",
                detail: "张三丰是武当派开山祖师，他创立了太极拳等武术流派，对中国武术和道教的发展做出了重要贡献。" },
            { id: 35, name: "戚继光", gender: "男", region: "山东", ethnicity: "汉族", dynasty: "明", field: "军事", evaluation: "褒",
                detail: "戚继光是明朝抗倭名将，他组建戚家军，在东南沿海抗击倭寇十余年，扫平了多年为虐沿海的倭患，确保了沿海人民的生命财产安全。" },
            { id: 36, name: "慈禧太后", gender: "女", region: "北京", ethnicity: "满族（少数民族）", dynasty: "清", field: "政治", evaluation: "贬",
                detail: "慈禧太后是晚清重要政治人物，她掌握清朝最高权力长达半个世纪，实行了一系列保守政策，签订了许多不平等条约，使中国逐渐沦为半殖民地半封建社会。" },
            { id: 37, name: "林则徐", gender: "男", region: "福建", ethnicity: "汉族", dynasty: "清", field: "政治", evaluation: "褒",
                detail: "林则徐是清朝时期的政治家、思想家和诗人，他虎门销烟，打击了外国鸦片贩子的嚣张气焰，彰显了中国人民反抗外来侵略的决心。" },
            { id: 38, name: "李鸿章", gender: "男", region: "安徽", ethnicity: "汉族", dynasty: "清", field: "政治", evaluation: "中",
                detail: "李鸿章是晚清重要大臣，他创办洋务运动，试图挽救清朝统治，但也代表清政府签订了一系列不平等条约，其功过是非存在较大争议。" },
            { id: 39, name: "洪秀全", gender: "男", region: "广东", ethnicity: "汉族", dynasty: "清", field: "政治、宗教", evaluation: "中",
                detail: "洪秀全是太平天国运动领袖，他领导的太平天国运动是中国近代史上规模巨大的农民运动，对清朝统治造成了沉重打击，但后期也暴露出一些局限性。" },
            { id: 40, name: "曹雪芹", gender: "男", region: "辽宁", ethnicity: "汉族", dynasty: "清", field: "文学", evaluation: "褒",
                detail: "曹雪芹是清代文学家，他创作的《红楼梦》是中国古典小说的巅峰之作，以贾、史、王、薛四大家族的兴衰为背景，描绘了18世纪上半叶中国封建社会的生活百态。" },
            { id: 41, name: "孙中山", gender: "男", region: "广东", ethnicity: "汉族", dynasty: "民国", field: "政治", evaluation: "褒",
                detail: "孙中山是中国近代民族民主主义革命的开拓者，中华民国和中国国民党的缔造者，他领导辛亥革命，推翻了清王朝的统治，结束了中国两千多年的封建君主专制制度。" },
            { id: 42, name: "袁世凯", gender: "男", region: "河南", ethnicity: "汉族", dynasty: "民国", field: "政治", evaluation: "中",
                detail: "袁世凯是中国近代史上著名政治家、军事家，他在辛亥革命后窃取革命果实，复辟帝制，但也在一定程度上推动了中国近代化进程。" },
            { id: 43, name: "鲁迅", gender: "男", region: "浙江", ethnicity: "汉族", dynasty: "民国", field: "文学、思想", evaluation: "褒",
                detail: "鲁迅是中国现代文学的奠基人，他的作品具有深刻的思想内涵和强烈的批判精神，代表作有《狂人日记》《阿Q正传》等，对中国社会和文化的变革产生了深远影响。" },
            { id: 44, name: "梅兰芳", gender: "男", region: "江苏", ethnicity: "汉族", dynasty: "民国", field: "艺术", evaluation: "褒",
                detail: "梅兰芳是京剧大师，他在京剧表演艺术上造诣深厚，形成了独特的艺术风格“梅派”，为京剧的传播和发展做出了重要贡献。" },
            { id: 45, name: "林徽因", gender: "女", region: "福建", ethnicity: "汉族", dynasty: "民国", field: "文学、建筑", evaluation: "褒",
                detail: "林徽因是中国近现代著名建筑师、诗人、作家，她参与了国徽和人民英雄纪念碑的设计，文学作品也具有较高的艺术价值。" },
            { id: 46, name: "毛泽东", gender: "男", region: "湖南", ethnicity: "汉族", dynasty: "新中国", field: "政治、军事、思想", evaluation: "褒",
                detail: "毛泽东是中国共产党第一代中央领导集体的核心，他带领中国人民经过长期的革命斗争，赢得民族独立和人民解放，创建了新中国，并对社会主义建设进行了积极探索。" },
            { id: 47, name: "杨振宁", gender: "男", region: "安徽", ethnicity: "汉族", dynasty: "新中国", field: "科学", evaluation: "褒",
                detail: "杨振宁是世界著名理论物理学家，他在粒子物理学、统计力学和凝聚态物理等领域取得了多项重要成果，获得诺贝尔物理学奖。" },
            { id: 48, name: "江青", gender: "女", region: "山东", ethnicity: "汉族", dynasty: "新中国", field: "政治", evaluation: "贬",
                detail: "江青是林彪、江青反革命集团的首要分子，她在“文化大革命”中与反革命集团勾结，给党、国家和各族人民带来严重灾难的内乱。" },
            { id: 49, name: "马英九", gender: "男", region: "湖南", ethnicity: "汉族", dynasty: "近现代", field: "政治", evaluation: "中",
                detail: "马英九曾任中国国民党主席、台湾地区领导人，在任期间推动两岸关系和平发展，促进了两岸经济文化交流。" },
            { id: 50, name: "莫言", gender: "男", region: "山东", ethnicity: "汉族", dynasty: "新中国", field: "文学", evaluation: "褒",
                detail: "莫言是中国当代著名作家，他的作品融合了民间故事、历史和现代元素，具有独特的艺术风格，2012年获得诺贝尔文学奖。" }
        ];

        // 当前筛选条件
        let filters = {
            gender: [],
            region: [],
            ethnicity: [],
            dynasty: [],
            field: [],
            evaluation: []
        };

        // 切换筛选条件
        function toggleFilter(type, value) {
            const checkbox = document.getElementById(`${type}-${value}`);
            const index = filters[type].indexOf(value);

            if (index === -1) {
                filters[type].push(value);
                checkbox.classList.add('checked');
            } else {
                filters[type].splice(index, 1);
                checkbox.classList.remove('checked');
            }

            updateResults();
        }

        // 更新结果列表
        function updateResults() {
            const resultsContainer = document.getElementById('results-container');
            resultsContainer.innerHTML = '';

            // 应用筛选条件
            const filteredPeople = peopleData.filter(person => {
                return (filters.gender.length === 0 || filters.gender.includes(person.gender)) &&
                    (filters.region.length === 0 || filters.region.some(reg => person.region.includes(reg))) &&
                    (filters.ethnicity.length === 0 || (filters.ethnicity.includes('汉族') && person.ethnicity === '汉族') || (filters.ethnicity.includes('少数民族') && person.ethnicity!== '汉族')) &&
                    (filters.dynasty.length === 0 || filters.dynasty.includes(person.dynasty)) &&
                    (filters.field.length === 0 || filters.field.some(f => person.field.includes(f))) &&
                    (filters.evaluation.length === 0 || filters.evaluation.includes(person.evaluation));
            });

            if (filteredPeople.length === 0) {
                resultsContainer.innerHTML = '<p>没有找到匹配的人物</p>';
                return;
            }

            filteredPeople.forEach(person => {
                const card = document.createElement('div');
                card.className = 'person-card';
                card.innerHTML = `
                    <h3>${person.name}</h3>
                    <p>朝代：${person.dynasty} | 领域：${person.field}</p>
                `;
                card.onclick = () => showDetail(person.id);
                resultsContainer.appendChild(card);
            });
        }

        // 显示详情
        function showDetail(personId) {
            const person = peopleData.find(p => p.id === personId);
            document.getElementById('results-container').style.display = 'none';
            document.getElementById('detail-container').style.display = 'block';
            document.getElementById('detail-title').textContent = person.name;
            document.getElementById('detail-content').innerHTML = `
                <p><strong>性别：</strong>${person.gender}</p>
                <p><strong>地域：</strong>${person.region}</p>
                <p><strong>民族：</strong>${person.ethnicity}</p>
                <p><strong>朝代：</strong>${person.dynasty}</p>
                <p><strong>领域：</strong>${person.field}</p>
                <p><strong>历史评价：</strong>${person.evaluation}</p>
                <p><strong>生平：</strong>${person.detail}</p>
            `;
        }

        // 返回列表
        function backToList() {
            document.getElementById('results-container').style.display = 'block';
            document.getElementById('detail-container').style.display = 'none';
        }

        // 搜索人物
        function searchPeople() {
            const searchInput = document.getElementById('search-input').value.trim();
            const resultsContainer = document.getElementById('results-container');
            resultsContainer.innerHTML = '';

            if (searchInput === '') {
                updateResults();
                return;
            }

            const foundPeople = peopleData.filter(person => person.name === searchInput);

            if (foundPeople.length === 0) {
                resultsContainer.innerHTML = '<p>没有找到匹配的人物</p>';
            } else {
                foundPeople.forEach(person => {
                    const card = document.createElement('div');
                    card.className = 'person-card';
                    card.innerHTML = `
                        <h3>${person.name}</h3>
                        <p>朝代：${person.dynasty} | 领域：${person.field}</p>
                    `;
                    card.onclick = () => showDetail(person.id);
                    resultsContainer.appendChild(card);
                });
            }
        }

        // 初始化
        updateResults();
    </script>
</body>

</html>
