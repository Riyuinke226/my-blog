炭水化合物网站
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name名称="viewport"“视口” content内容="width=device-width, initial-scale=1.0">元数据name="viewport" content="width=device-width, initial-scale=1.0">
    <title>炭水化合物</title><标题>碳水化合物</标题><标题>碳水化合物</标题><标题>碳水化合物</标题>
    <meta name名称名称名称名称名称名称名称名称名称名称="description"“描述”“描述” content内容="炭水化合物 - 一个记录文字的地方"><元数据name="description" content="炭水化合物 - 一个记录文字的地方"><元数据name="description" content="碳水化合物 - 一个记录文字的地方"><metaname="description" content="碳水化合物 - 一个记录文字的地方"><metaname="description" content="碳水化合物 - 一个记录文字的地方"><metaname="description" content="碳水化合物 - 一个记录文字的地方">
    <style><样式>
        * {
            margin: 0;边距: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", sans-serif;字体系列: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, "Noto Sans", 无衬线字体;字体系列:-apple-system,BlinkMacSystemFont"Segoe UI"Roboto"Helvetica Neue"Arial"Noto Sans"无衬线字体;字体系列:-apple-system,BlinkMacSystemFont"Segoe UI"Roboto"Helvetica Neue"Arial"Noto Sans"无衬线字体;字体系列:-apple-system,BlinkMacSystemFont"Segoe UI"Roboto"Helvetica Neue"Arial"Noto Sans"无衬线字体;字体系列:-apple-system,BlinkMacSystemFont"Segoe UI"Roboto"Helvetica Neue"Arial"Noto Sans"无衬线字体;
            background-color: #fafafa;背景颜色: #fafafa;背景颜色: #fafafa;背景颜色: #fafafa;背景颜色: #fafafa;背景颜色: #fafafa;背景颜色: #fafafa;背景颜色: #fafafa;
            color颜色颜色颜色颜色颜色: #1a1a1a;颜色: #1a1a1a;颜色颜色颜色颜色颜色颜色: #1a1a1a;颜色: #1a1a1a;
            line-height: 1.7;行高: 1.7;行高: 1.7;行高: 1.7;
            padding: 20px;内边距: 20像素;内边距: 20px;内边距: 20像素;
            max-width: 700px;最大宽度: 700像素;最大宽度: 700px;最大宽度: 700像素;
            margin边距: 0 auto自动;外边距: 0 自动;
            word-break: break-word;断字: 断字;换行: 断字;断字: 断字;
        }
        /* 密码弹层 */
        .password-overlay {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background: #fafafa;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 999;
            padding: 20px;内边距: 20像素;
        }
        .password-box {
            background: white;
            border-radius: 16px;
            padding: 40px 30px;
            box-shadow: 0 8px 24px rgba(0,0,0,0.06);
            text-align: center;
            max-width: 320px;
            width: 100%;
        }
        .password-box h2 {
            font-size: 1.8rem;
            margin-bottom: 8px;
            letter-spacing: 2px;
        }
        .password-box p {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 24px;
        }
        .password-box input {
            width: 100%;
            padding: 12px 16px;
            font-size: 1.1rem;
            border: 1px solid #ddd;
            border-radius: 8px;
            text-align: center;
            letter-spacing: 4px;
            margin-bottom: 16px;
            outline: none;
            transition: border 0.2s;
        }
        .password-box input:focus {
            border-color: #666;
        }
        .password-box button {
            width: 100%;
            padding: 12px;
            background: #1a1a1a;
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            cursor: pointer;
            letter-spacing: 1px;
            transition: background 0.2s;
        }
        .password-box button:active {
            background: #333;
        }
        .error-msg {
            color: #d32f2f;
            font-size: 0.85rem;
            margin-top: 8px;
            display: none;
        }
        /* 主体内容 */
        header {
            text-align: center;
            margin: 40px 0 30px;
        }
        header h1 {
            font-size: 2.2rem;
            font-weight: 700;
            letter-spacing: 2px;
            color: #2c2c2c;
        }
        header p {
            font-size: 0.95rem;
            color: #5a5a5a;
            margin-top: 5px;
        }
        .back-link {
            display: inline-block;
            margin: 20px 0 10px;
            color: #3a3a3a;
            text-decoration: none;
            font-size: 0.95rem;
            border-bottom: 1px solid #ccc;
            cursor: pointer;
        }
        .article-list {
            list-style: none;
            margin-top: 20px;
        }
        .article-item {
            background: #ffffff;
            border-radius: 12px;
            padding: 20px 24px;
            margin-bottom: 16px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.04);
            transition: background 0.2s;
            cursor: pointer;
        }
        .article-item:hover {
            background: #f5f5f5;
        }
        .article-title {
            font-size: 1.25rem;
            font-weight: 600;
            margin-bottom: 6px;
            color: #1a1a1a;
        }
        .article-date {
            font-size: 0.8rem;
            color: #999;
        }
        .article-detail {
            background: #ffffff;
            border-radius: 12px;
            padding: 28px 24px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.04);
            margin-top: 20px;
        }
        .article-detail h2 {
            font-size: 1.8rem;
            margin-bottom: 8px;
        }
        .article-detail .meta {
            font-size: 0.8rem;
            color: #999;
            margin-bottom: 24px;
            border-bottom: 1px solid #eee;
            padding-bottom: 12px;
        }
        .article-detail .content {
            font-size: 1.05rem;
            line-height: 1.8;
            color: #2c2c2c;
        }
        .article-detail .content p {
            margin-bottom: 1.2rem;
        }
        footer {
            text-align: center;
            margin-top: 50px;
            padding: 20px 0;
            color: #aaa;
            font-size: 0.8rem;
        }
        /* 适配小屏幕 */
        @media (max-width: 500px) {
            body {
                padding: 12px;
            }
            header h1 {
                font-size: 1.8rem;
            }
            .article-item {
                padding: 16px 18px;
            }
            .password-box {
                padding: 30px 20px;
            }
        }
    </style>
</head>
<body>
    <!-- 密码验证层 -->
    <div id="password-overlay" class="password-overlay">
        <div class="password-box">
            <h2>炭水化合物</h2>
            <p>请输入密码以继续阅读</p>
            <input type="password" id="password-input" placeholder="****" maxlength="20" inputmode="numeric">
            <button id="password-submit">进入</button>
            <div class="error-msg" id="error-msg">密码错误</div>
        </div>
    </div>
    <!-- 网站主体，初始隐藏 -->
    <div id="main-content" style="display: none;">
        <header>
            <h1>炭水化合物</h1>
            <p>吃进去的是碳水，写出来的是文字</p>
        </header>
        <div id="app">
            <!-- 文章列表视图 -->
            <div id="list-view">
                <ul class="article-list" id="article-list"></ul>
            </div>
            <!-- 文章详情视图 -->
            <div id="detail-view" style="display: none;">
                <a class="back-link" id="back-btn">← 回到列表</a>
                <div class="article-detail" id="article-detail"></div>
            </div>
        </div>
        <footer>
            &copy; 炭水化合物 · 简单记录
        </footer>
    </div>
    <script>
        // ========== 密码配置 ==========
        const CORRECT_PASSWORD = '1399';
        const STORAGE_KEY = 'tshhw_auth';
        // ========== 文章数据 ==========
        const articles = [
            {
                id: 1,
                title: "炭水化合物的自白",
                date: "2025-03-10",
                content: `内容: `
                    <p>大家好，我叫炭水化合物。不是你们常说的碳水化合物，我多了一点“炭”，多了几分深沉。</p>
                    <p>碳水化合物是能量，我炭水化合物是带着烟火气的能量。我诞生于烤焦的面包边、锅底的锅巴、还有烧烤架上那一层微焦的甜蜜。</p>
                    <p>如果你觉得生活太寡淡，就像白水煮鸡胸，那我建议你试试我——炭水化合物。一口下去，酥脆、微苦、回甘，像极了成年人的快乐。</p>
                `
            },
            {
                id: 2,
                title: "如何正确食用炭水化合物",
                date: "2025-03-18",日期: "2025-03-18",
                content: `内容: `
                    <p>很多人问我：炭水化合物怎么吃才健康？我笑了笑，健康这个词本身就不太适合我。</p>
                    <p>正确食用我的方式只有一种：在深夜，趁世界安静，趁理性松懈，拿出那袋藏了很久的炭烧饼干或者烤得微糊的红薯，配上一杯无糖豆浆，告诉自己“这只是碳水，不是罪恶”。</p>
                    <p>记得要小口咀嚼，让焦香在嘴里散开。那一刻，你摄入的不是热量，是一整天紧绷后的放松。</p>
                `
            },
            {
                id: 3,编号: 3,
                title: "一个炭水化合物爱好者的自我修养",
                date: "2025-04-22",
                content: `内容: `
                    <p>作为一个专业的炭水化合物爱好者，冰箱里没有蔬菜可以，但不能没有冷冻的烤馒头片。</p>
                    <p>我的烤箱常年设定在200度，不是为了烤肉，而是为了把吐司边缘烤成深棕色。朋友们说我这是美拉德反应上瘾，我觉得这是一种生活美学。</p>
                    <p>如果有一天你路过一家面包店，闻到微微的焦糊味，请想起我，一个平凡却坚定的炭水化合物信徒。</p>
                `
            }
        ];
        // ========== 密码验证逻辑 ==========
        const overlay = document.getElementById('password-overlay');
        const mainContent = document.getElementById('main-content');
        const passwordInput = document.getElementById('password-input');
        const submitBtn = document.getElementById('password-submit');
        const errorMsg = document.getElementById('error-msg');
        // 检查是否已登录（基于 localStorage）
        function checkAuth() {
            const stored = localStorage.getItem(STORAGE_KEY);
            if (stored === CORRECT_PASSWORD) {
                showContent();
            } else {
                showPasswordPrompt();
            }
        }
        function showContent() {
            overlay.style.display = 'none';
            mainContent.style.display = 'block';
            // 初始化文章路由
            handleRoute();
        }
        function showPasswordPrompt() {
            overlay.style.display = 'flex';
            mainContent.style.display = 'none';
            passwordInput.value = '';
            errorMsg.style.display = 'none';
        }
        // 验证密码
        function verifyPassword() {
            const input = passwordInput.value.trim();
            if (input === CORRECT_PASSWORD) {
                // 记住登录状态（可选）
                localStorage.setItem(STORAGE_KEY, CORRECT_PASSWORD);
                showContent();
            } else {
                errorMsg.style.display = 'block';
                passwordInput.value = '';
                passwordInput.focus();
            }
        }
        // 事件绑定
        submitBtn.addEventListener('click', verifyPassword);
        passwordInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') {
                verifyPassword();
            }
        });
        // ========== 文章路由（原逻辑） ==========
        function getCurrentArticleId() {
            const hash = window.location.hash;
            if (hash.startsWith('#article-')) {
                return parseInt(hash.replace('#article-', ''), 10);
            }
            return null;
        }
        function renderList() {
            const listView = document.getElementById('list-view');
            const detailView = document.getElementById('detail-view');
            listView.style.display = 'block';
            detailView.style.display = 'none';
            const listEl = document.getElementById('article-list');
            listEl.innerHTML = '';
            articles
                .sort((a, b) => (a.id < b.id ? 1 : -1))
                .forEach(article => {
                    const li = document.createElement('li');
                    li.className = 'article-item';
                    li.innerHTML = `
                        <div class="article-title">${article.title}</div>
                        <div class="article-date">${article.date}</div>
                    `;
                    li.addEventListener('click', () => {
                        window.location.hash = `#article-${article.id}`;
                    });
                    listEl.appendChild(li);
                });
        }
        function renderDetail(articleId) {
            const article = articles.find(a => a.id === articleId);
            if (!article) {
                window.location.hash = '';
                return;
            }
            const listView = document.getElementById('list-view');
            const detailView = document.getElementById('detail-view');
            listView.style.display = 'none';
            detailView.style.display = 'block';
            const detailEl = document.getElementById('article-detail');
            detailEl.innerHTML = `
                <h2>${article.title}</h2>
                <div class="meta">${article.date}</div>
                <div class="content">${article.content}</div>
            `;
            window.scrollTo(0, 0);
        }
        function handleRoute() {
            const articleId = getCurrentArticleId();
            if (articleId) {如果 (articleId) {
                renderDetail(articleId);
            } else {} 否则 {
                renderList();
            }
        }
        window.addEventListener('hashchange', handleRoute);
        document.getElementById('back-btn').addEventListener('click', (e) => {
            e.preventDefault();
            window.location.hash = '';
        });
        // 页面加载时先检查密码
        checkAuth();
    </script>
</body>
</html>
