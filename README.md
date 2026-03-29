# spine-health
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover, user-scalable=yes">
    <title>脊柱健康 · 知脊课堂 | 问答+图解放松 | 计算机设计大赛</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            background: linear-gradient(145deg, #eef5f0 0%, #d9e8de 100%);
            font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, Helvetica, sans-serif;
            color: #1e2f2b;
            padding: 1rem;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
        }

        /* 头部 (手机优化) */
        .hero {
            background: linear-gradient(135deg, #ffffff 0%, #f8fbf7 100%);
            border-radius: 2rem;
            padding: 1.5rem;
            margin-bottom: 1.8rem;
            box-shadow: 0 12px 24px -12px rgba(0, 32, 16, 0.1);
            border: 1px solid rgba(80, 120, 100, 0.2);
        }

        .hero h1 {
            font-size: 1.8rem;
            font-weight: 700;
            background: linear-gradient(120deg, #1c6e43, #2b8c5c);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            display: inline-flex;
            align-items: center;
            gap: 10px;
        }

        .hero h1 i {
            font-size: 1.8rem;
            color: #2b8c5c;
        }

        .sub {
            margin-top: 0.8rem;
            font-size: 0.9rem;
            border-left: 4px solid #3cac74;
            padding-left: 0.8rem;
            background: #eaf7ef70;
            border-radius: 0 0.8rem 0.8rem 0;
        }

        .badge-group {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
            margin-top: 1rem;
        }

        .badge {
            background: #eef3ec;
            padding: 0.2rem 0.8rem;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: 500;
            color: #1f6e46;
            border: 1px solid #cae3d4;
        }

        .stats {
            background: #fefce8;
            border-radius: 1.5rem;
            padding: 0.6rem 1rem;
            margin-bottom: 1.5rem;
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 0.5rem;
            font-size: 0.8rem;
        }

        /* 问答卡片 */
        .questions-grid {
            display: flex;
            flex-direction: column;
            gap: 1.2rem;
            margin-bottom: 2rem;
        }

        .card {
            background: white;
            border-radius: 1.5rem;
            box-shadow: 0 6px 14px -8px rgba(0,0,0,0.08);
            border: 1px solid #ddebe2;
        }

        .card-header {
            background: #f9fdfb;
            padding: 0.9rem 1.2rem;
            border-bottom: 2px solid #e2f0e8;
            display: flex;
            flex-wrap: wrap;
            gap: 0.4rem;
        }

        .q-num {
            background: #d4f0e2;
            padding: 0.2rem 0.7rem;
            border-radius: 40px;
            font-size: 0.75rem;
        }

        .q-type {
            font-size: 0.7rem;
            background: #eef2f0;
            padding: 0.2rem 0.7rem;
            border-radius: 30px;
        }

        .question-text {
            font-size: 1rem;
            font-weight: 600;
            padding: 0.8rem 1.2rem 0.2rem;
        }

        .options {
            padding: 0 1.2rem 0.6rem;
            display: flex;
            flex-direction: column;
            gap: 0.6rem;
        }

        .option-item {
            display: flex;
            align-items: center;
            gap: 10px;
            background: #fafefb;
            padding: 0.5rem 0.8rem;
            border-radius: 1rem;
            border: 1px solid #e0f0e6;
            cursor: pointer;
        }

        input[type="radio"] {
            width: 1.1rem;
            height: 1.1rem;
        }

        .option-text {
            font-size: 0.85rem;
            font-weight: 500;
        }

        .action-area {
            padding: 0.2rem 1.2rem 0.8rem;
        }

        .check-btn {
            background: #eef2ef;
            padding: 0.4rem 1rem;
            border-radius: 2rem;
            font-size: 0.75rem;
            font-weight: 600;
            color: #2c6e49;
            border: 1px solid #cde0d6;
            cursor: pointer;
        }

        .explanation-area {
            margin: 0 1.2rem 1rem;
            background: #f7fbf5;
            border-radius: 1rem;
            padding: 0.8rem;
            border-left: 4px solid #4cae7c;
            font-size: 0.85rem;
        }

        /* 放松模块 - 手机优先，图片大幅放大 */
        .relax-section {
            background: white;
            border-radius: 1.5rem;
            padding: 1.2rem;
            margin: 1rem 0 2rem;
            box-shadow: 0 8px 20px -12px rgba(0,0,0,0.08);
        }

        .section-title {
            font-size: 1.5rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 0.6rem;
            color: #1c6e43;
        }

        .relax-desc {
            font-size: 0.85rem;
            margin-bottom: 1.2rem;
            border-left: 3px solid #7bcfa3;
            padding-left: 0.8rem;
        }

        .relax-grid {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .relax-card {
            background: #fafef9;
            border-radius: 1.2rem;
            padding: 1rem;
            border: 1px solid #e2f0e8;
            transition: 0.2s;
        }

        /* 单张图片：宽度100%，高度自动，最大高度增加 */
        .relax-img {
            width: 100%;
            height: auto;
            max-height: 340px;
            object-fit: cover;
            border-radius: 1rem;
            margin-bottom: 0.8rem;
            border: 2px solid #cae3d4;
            box-shadow: 0 6px 12px -8px rgba(0,0,0,0.1);
            cursor: pointer;
            transition: 0.2s;
        }

        /* 双图并排容器 */
        .img-pair {
            display: flex;
            gap: 12px;
            justify-content: space-between;
            margin-bottom: 0.8rem;
        }
        .img-pair .relax-img {
            width: calc(50% - 6px);
            max-height: 240px;
            margin: 0;
        }

        .relax-card h4 {
            font-size: 1.1rem;
            font-weight: 700;
            margin: 0.3rem 0;
        }
        .relax-card p {
            font-size: 0.8rem;
            color: #4f6a5c;
            margin-bottom: 0.5rem;
        }
        .relax-steps {
            font-size: 0.75rem;
            background: #eef5f0;
            padding: 0.5rem;
            border-radius: 0.8rem;
        }

        .tips-box {
            background: #eef5ea;
            border-radius: 1rem;
            padding: 0.8rem;
            margin-top: 1.2rem;
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            gap: 0.5rem;
            font-size: 0.8rem;
        }
        .tips-btn {
            background: #2c8c5c;
            padding: 0.3rem 1rem;
            border-radius: 30px;
            color: white;
            border: none;
            font-size: 0.7rem;
        }

        /* 放大模态框 */
        .lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.9);
            z-index: 2000;
            justify-content: center;
            align-items: center;
            cursor: pointer;
        }
        .lightbox img {
            max-width: 92vw;
            max-height: 92vh;
            object-fit: contain;
            border-radius: 12px;
            border: 2px solid white;
        }
        .footer {
            font-size: 0.7rem;
            text-align: center;
            color: #587c68;
            border-top: 1px solid #cde0d4;
            padding-top: 1rem;
            margin-top: 1rem;
        }

        @media (min-width: 700px) {
            .relax-grid {
                flex-direction: row;
                flex-wrap: wrap;
                justify-content: space-between;
            }
            .relax-card {
                flex: 1 1 280px;
                max-width: 32%;
            }
            .relax-img {
                max-height: 280px;
            }
            .img-pair .relax-img {
                max-height: 200px;
            }
            body {
                padding: 2rem;
            }
        }
    </style>
</head>
<body>
<div class="container">
    <div class="hero">
        <h1><i class="fas fa-spine"></i> 脊柱健康 · 知脊课堂</h1>
        <div class="sub">📖 沉浸式问答 + 图解放松练习 | 剧本+医学双解析<br></div>
        <div class="badge-group">
            <span class="badge">10道硬核问答</span>
            <span class="badge">5个配图放松动作</span>
            <span class="badge">预防伤痛 · 主动养护</span>
        </div>
    </div>

    <div class="stats">
        <span><i class="fas fa-database"></i> 总题数: <strong id="totalCount">0</strong></span>
        <span><i class="fas fa-check-circle"></i> 点击「检查答案」</span>
        <span><i class="fas fa-heartbeat"></i> 科学护脊</span>
    </div>

    <div class="questions-grid" id="questionsContainer"></div>

    <!-- 放松模块 (图片大幅放大) -->
    <div class="relax-section">
        <div class="section-title">
            <i class="fas fa-hand-holding-heart"></i>
            <span>脊柱放松 · 每日护脊小练习</span>
        </div>
        <div class="relax-desc">
            <i class="fas fa-leaf"></i> 劳累之后，花5分钟给脊柱做个“温柔SPA”。<br>
            <span style="font-size:0.7rem;">※ 点击图片可放大查看。图片已按规范命名，如需单文件分享请将图片转为Base64嵌入（见代码注释）。</span>
        </div>
        <div class="relax-grid">
            <!-- 收下巴 -->
            <div class="relax-card">
                <img class="relax-img" src="收下巴式1.jpg" alt="收下巴" onerror="this.onerror=null; this.src='https://picsum.photos/id/20/400/350'; this.alt='示例图片'">
                <h4>收下巴 · 解压颈椎</h4>
                <p>改善头前倾，即刻减轻颈部压力</p>
                <div class="relax-steps">✓ 坐直，水平后收下巴，像挤出双下巴<br>✓ 保持3秒，重复10次</div>
            </div>
            <!-- 猫牛式 (放大) -->
            <div class="relax-card">
                <img class="relax-img" src="猫牛式1.jpg" alt="猫牛式" onerror="this.onerror=null; this.src='https://picsum.photos/id/21/400/350'; this.alt='示例图片'">
                <h4>猫牛式 · 灵动脊柱</h4>
                <p>活动每一节椎骨，为椎间盘“补水”</p>
                <div class="relax-steps">✓ 四肢跪姿，吸气塌腰抬头<br>✓ 呼气拱背低头，缓慢重复8次</div>
            </div>
            <!-- 婴儿式 双图 -->
            <div class="relax-card">
                <div class="img-pair">
                    <img class="relax-img" src="婴儿式1.jpg" alt="婴儿式1" onerror="this.onerror=null; this.src='https://picsum.photos/id/22/300/240'; this.alt='示例'">
                    <img class="relax-img" src="婴儿式2.jpg" alt="婴儿式2" onerror="this.onerror=null; this.src='https://picsum.photos/id/22/300/240'; this.alt='示例'">
                </div>
                <h4>婴儿式 · 放松腰背</h4>
                <p>温和拉伸腰椎，舒缓下背紧张</p>
                <div class="relax-steps">✓ 跪姿，臀部坐脚跟，身体前屈<br>✓ 双臂前伸，保持30秒深呼吸</div>
            </div>
            <!-- 靠墙站立 (放大) -->
            <div class="relax-card">
                <img class="relax-img" src="靠墙站立式1.jpg" alt="靠墙站立" onerror="this.onerror=null; this.src='https://picsum.photos/id/23/400/350'; this.alt='示例图片'">
                <h4>靠墙站立 · 重塑姿态</h4>
                <p>矫正驼背，恢复脊柱生理曲度</p>
                <div class="relax-steps">✓ 后脑、肩、臀、脚跟贴墙<br>✓ 收下巴，保持3-5分钟</div>
            </div>
            <!-- 仰卧抱膝 双图 -->
            <div class="relax-card">
                <div class="img-pair">
                    <img class="relax-img" src="仰卧抱膝式1.jpg" alt="仰卧抱膝1" onerror="this.onerror=null; this.src='https://picsum.photos/id/24/300/240'; this.alt='示例'">
                    <img class="relax-img" src="仰卧抱膝式2.jpg" alt="仰卧抱膝2" onerror="this.onerror=null; this.src='https://picsum.photos/id/24/300/240'; this.alt='示例'">
                </div>
                <h4>仰卧抱膝 · 舒缓骨盆</h4>
                <p>牵拉腰骶部，减轻腰椎压力</p>
                <div class="relax-steps">✓ 仰卧，双手抱膝靠近胸口<br>✓ 自然呼吸，保持20秒，重复3次</div>
            </div>
        </div>
        <div class="tips-box">
            <span><i class="fas fa-lightbulb"></i> 💡 护脊小锦囊：</span>
            <span id="randomTip">久坐时屁股坐满椅面，腰后加靠枕，腰椎压力下降30%！</span>
            <button class="tips-btn" id="refreshTipBtn"><i class="fas fa-sync-alt"></i> 换一条</button>
        </div>
        <div style="font-size:0.7rem; text-align:center; margin-top:0.8rem;">
            <i class="fas fa-clock"></i> 每工作45分钟，起身活动2分钟 + 一组放松动作
        </div>
    </div>

    <div class="footer">
        <i class="fas fa-leaf"></i> 解析融合剧本趣味与骨科医学共识 <br>
 
    </div>
</div>

<!-- 放大图片模态框 -->
<div id="lightbox" class="lightbox" style="display: none;">
    <img id="lightbox-img" src="" alt="放大图片">
</div>

<script>
    // ---------- 题目数据库：已删除原第二题（低头60度），恢复原第十一题（成年人椎骨数量） ----------
    const questionsData = [
        { id: 2, text: "以下哪一部分椎骨被描述为“被肋骨焊死了，动不了”？", options: ["颈椎", "胸椎", "腰椎", "尾椎"], correct: "B", 
          explanation: `📖 剧本还原：介绍胸椎时说：“中间12个，叫胸椎。这几位兄弟比较惨，被肋骨焊死了，动不了，只能老老实实当‘保护壳’。”<br><br>
          🔬 科学拓展：胸椎与肋骨、胸骨形成胸廓，活动度较小，主要功能是保护心、肺等重要器官。这种“半刚性”结构既保证了稳定性，又允许一定范围的旋转运动，但屈伸幅度远小于颈椎和腰椎。`, type: "基础" },
        { id: 5, text: "以下哪项不是剧本中提到的“工伤”？", options: ["久坐+瘫坐", "直腿弯腰搬东西", "长时间站立不动", "低头看手机"], correct: "C", 
          explanation: `📖 剧本还原：明确列出的“工伤”包括低头看手机、久坐+瘫坐、直腿弯腰搬东西，未提及长时间站立。<br><br>
          🔬 科学拓展：虽然长时间站立（>2小时）也会增加腰椎负荷，但剧本未将其归入“工伤”。不过科学建议：久站应交替重心、使用脚踏板，避免腰部肌肉持续紧张。`, type: "基础" },
        { id: 7, text: "以下哪个动作被推荐用来缓解颈椎压力？", options: ["抬头看天", "左右快速转头", "收下巴", "用力耸肩"], correct: "C", 
          explanation: `📖 剧本还原：“这个动作叫‘收下巴’......能让我颈椎的压力瞬间小很多。”要点是下巴水平后收，拉长脖子后侧。<br><br>
          🔬 科学拓展：“收下巴”（Chin Tuck）能激活颈深屈肌，恢复颈椎生理曲度，减轻椎间关节压力。研究表明，每天多次收下巴训练可有效改善头前倾姿势，是颈椎康复的核心基础动作。`, type: "基础" },
        { id: 8, text: "剧本中推荐的“猫牛式”主要作用是什么？", options: ["锻炼手臂力量", "活动椎骨，帮助椎间盘恢复弹性", "增强心肺功能", "放松腿部肌肉"], correct: "B", 
          explanation: `📖 剧本还原：“这个动作能让我的每一节椎骨都活动开，椎间盘也能‘吸吸水分’，重新变得饱满有弹性。”<br><br>
          🔬 科学拓展：猫牛式通过脊柱节段性屈伸，促进椎间盘营养交换（类似“泵送”机制），增加椎间盘含水量，改善灵活性，缓解腰背僵硬，是脊柱健康推荐的温和动态活动。`, type: "基础" },
        { id: 9, text: "坐姿时为了给腰椎支撑，应该怎么做？", options: ["坐一半椅子，身体前倾", "屁股坐满椅面，后背靠椅背", "只靠一边坐，身体倾斜", "双脚离地，身体后仰"], correct: "B", 
          explanation: `📖 剧本还原：“你坐的时候，能不能把屁股坐满整个椅面，后背靠着椅背？如果腰后面空空的，就塞个靠枕。”<br><br>
          🔬 科学拓展：臀部坐满椅面能利用椅背分担上半身重量，维持腰椎生理前凸。腰靠可填补空隙，避免腰部悬空，降低椎间盘压力30%以上，是久坐人群必备防护措施。`, type: "基础" },
        { id: 10, text: "以下哪项是剧本结尾对“我”提出的核心建议？", options: ["每天做一小时剧烈运动", "购买昂贵的按摩设备", "看手机举高、坐久站起来、搬东西蹲下", "多躺着休息，少活动"], correct: "C", 
          explanation: `📖 剧本还原：“我只需要你——看手机的时候举高一点，坐久了站起来走一走，搬东西的时候蹲下去。”<br><br>
          🔬 科学拓展：这三点直击脊柱三大杀手：①低头（举高手机保持视线平齐）②久坐（每40分钟起身活动，促进椎间盘营养）③错误搬物（下蹲替代弯腰）。坚持这三个习惯，可预防80%的脊柱劳损问题。`, type: "基础" },
        { id: 12, text: "日常中哪种习惯最容易加速腰椎间盘退变、引发突出风险？", options: ["久坐且瘫坐于软沙发", "每隔40分钟起身活动", "平躺硬板床休息", "游泳锻炼"], correct: "A", 
          explanation: `📖 剧本呼应：瘫坐是腰椎大敌，加上久坐更是雪上加霜。<br><br>
          🔬 科学拓展：瘫坐时腰椎后凸，椎间盘压力向后分布，纤维环后方承受最大剪切力，同时缺乏肌肉动态保护，极易导致髓核突出。软沙发进一步加剧骨盆后倾，风险倍增。`, type: "拓展" },
        { id: 13, text: "想要科学保护颈椎，以下哪一项是骨科医生最推荐的习惯？", options: ["使用高枕让颈部悬空", "长时间低头玩手机", "经常做“收下巴”后缩训练", "快速猛烈转动脖子"], correct: "C", 
          explanation: `📖 剧本推荐：收下巴动作能快速缓解颈椎压力。<br><br>
          🔬 科学拓展：高枕或低头都会破坏颈椎曲度，而“收下巴”能主动强化颈深屈肌，稳定颈椎节段。每天3组，每组10次，坚持4周可显著改善颈痛和头前倾姿势，是颈椎康复的金牌动作。`, type: "拓展" },
        { id: 14, text: "关于“搬重物不伤腰”的生物力学原则，下列描述正确的是？", options: ["直腿弯腰，利用背部肌肉拉起", "扭转身体借力快速提起", "下蹲保持脊柱中立，靠大腿力量站起", "重物远离身体，用腰力猛拉"], correct: "C", 
          explanation: `📖 剧本强调：蹲下、背挺直、重物贴近身体、大腿发力。<br><br>
          🔬 科学拓展：此原则基于“髋关节替代腰椎”的生物力学策略，使重物重心靠近身体重力线，减少腰椎力臂，将负荷转移至臀腿大肌群。研究证实正确搬运可降低腰椎受伤风险达70%以上。`, type: "拓展" },
        // 恢复的原第11题（成年人脊柱椎骨数量）
        { id: 11, text: "成年人脊柱中，椎骨的数量通常为多少块？（融合后）", options: ["33块", "26块", "24块", "30块"], correct: "B", 
          explanation: `📖 拓展知识点：成人脊柱由26块骨组成：7颈椎、12胸椎、5腰椎、1骶骨（由5块骶椎融合）、1尾骨（由4块尾椎融合）。<br><br>
          🔬 科学拓展：骶尾椎的融合增加了骨盆稳定性，适应直立行走。了解这一数字变化有助于理解脊柱发育及影像学阅片基础。`, type: "拓展" }
    ];

    function renderQuestions() {
        const container = document.getElementById('questionsContainer');
        document.getElementById('totalCount').innerText = questionsData.length;
        let html = '';
        questionsData.forEach((q, idx) => {
            const letters = ['A','B','C','D'];
            let opts = '';
            q.options.forEach((opt, i) => {
                opts += `
                    <label class="option-item">
                        <input type="radio" name="q_${q.id}" value="${letters[i]}">
                        <span class="option-text"><strong>${letters[i]}.</strong> ${escapeHtml(opt)}</span>
                    </label>
                `;
            });
            html += `
                <div class="card" id="card-${q.id}">
                    <div class="card-header">
                        <span class="q-num">第${idx+1}题</span>
                        <span class="q-type">${q.type === '基础' ? '剧本核心' : '健康拓展'}</span>
                    </div>
                    <div class="question-text">${escapeHtml(q.text)}</div>
                    <div class="options">${opts}</div>
                    <div class="action-area">
                        <button class="check-btn" data-id="${q.id}"><i class="fas fa-search"></i> 检查答案</button>
                    </div>
                    <div class="explanation-area" id="explain-${q.id}" style="display: none;"></div>
                </div>
            `;
        });
        container.innerHTML = html;
        document.querySelectorAll('.check-btn').forEach(btn => {
            btn.addEventListener('click', (e) => {
                const qid = parseInt(btn.dataset.id);
                handleCheckAnswer(qid);
            });
        });
    }

    function handleCheckAnswer(qid) {
        const q = questionsData.find(qq => qq.id === qid);
        if (!q) return;
        const selected = document.querySelector(`input[name="q_${qid}"]:checked`);
        const expDiv = document.getElementById(`explain-${qid}`);
        if (!selected) {
            expDiv.style.display = 'block';
            expDiv.innerHTML = `<i class="fas fa-exclamation-triangle"></i> 请先选择一个答案。`;
            return;
        }
        const isCorrect = (selected.value === q.correct);
        const correctLetter = q.correct;
        const correctText = q.options[['A','B','C','D'].indexOf(q.correct)];
        let result = isCorrect ? '<span class="correct-badge">✅ 回答正确</span>' : '<span class="correct-badge wrong-badge">❌ 回答错误</span>';
        result += `<div><strong>正确答案：${correctLetter}. ${escapeHtml(correctText)}</strong></div>`;
        result += `<div style="margin-top:6px;">${q.explanation}</div>`;
        expDiv.innerHTML = result;
        expDiv.style.display = 'block';
        // 高亮正确选项
        document.querySelectorAll(`#card-${qid} .option-item`).forEach(label => {
            const radio = label.querySelector('input');
            if (radio && radio.value === q.correct) label.style.backgroundColor = '#e2f7ea';
            else label.style.backgroundColor = '';
        });
    }

    function escapeHtml(str) {
        if (!str) return '';
        return str.replace(/[&<>]/g, m => ({'&':'&amp;','<':'&lt;','>':'&gt;'}[m]));
    }

    // 小锦囊
    const tips = ["久坐时屁股坐满椅面，腰后加靠枕，腰椎压力下降30%！","看手机举到与视线平齐，颈椎压力减半。","每45分钟站起来走动2分钟。","睡前猫牛式+婴儿式，放松脊柱。","搬重物先蹲下，大腿发力。","选枕头支撑颈部曲度，一拳高。","收下巴每天3组，颈椎维他命。","平躺膝下垫枕减轻腰椎压力。","核心训练是天然腰带。"];
    function refreshTip() {
        const tipSpan = document.getElementById('randomTip');
        if (tipSpan) tipSpan.innerText = tips[Math.floor(Math.random() * tips.length)];
    }

    // 图片点击放大
    function initLightbox() {
        const lb = document.getElementById('lightbox');
        const lbImg = document.getElementById('lightbox-img');
        document.querySelectorAll('.relax-img').forEach(img => {
            img.addEventListener('click', (e) => {
                e.stopPropagation();
                lbImg.src = img.src;
                lb.style.display = 'flex';
            });
        });
        lb.addEventListener('click', () => { lb.style.display = 'none'; lbImg.src = ''; });
    }

    window.addEventListener('DOMContentLoaded', () => {
        renderQuestions();
        initLightbox();
        refreshTip();
        document.getElementById('refreshTipBtn')?.addEventListener('click', refreshTip);
    });
</script>


</body>
</html>
