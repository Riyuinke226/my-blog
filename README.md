<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>炭水化合物</title>
    <meta name="description" content="炭水化合物 - 一个记录文字的地方">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body { font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; background: #fafafa; color: #1a1a1a; line-height: 1.7; padding: 20px; max-width: 700px; margin: 0 auto; word-break: break-word; }
        /* 密码层 */
        .password-overlay { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: #fafafa; display: flex; flex-direction: column; align-items: center; justify-content: center; z-index: 999; padding: 20px; }
        .password-box { background: white; border-radius: 16px; padding: 40px 30px; box-shadow: 0 8px 24px rgba(0,0,0,0.06); text-align: center; max-width: 320px; width: 100%; }
        .password-box h2 { font-size: 1.8rem; margin-bottom: 8px; letter-spacing: 2px; }
        .password-box p { color: #666; font-size: 0.9rem; margin-bottom: 24px; }
        .password-box input { width: 100%; padding: 12px 16px; font-size: 1.1rem; border: 1px solid #ddd; border-radius: 8px; text-align: center; letter-spacing: 4px; margin-bottom: 16px; outline: none; }
        .password-box button { width: 100%; padding: 12px; background: #1a1a1a; color: white; border: none; border-radius: 8px; font-size: 1rem; cursor: pointer; letter-spacing: 1px; }
        .error-msg { color: #d32f2f; font-size: 0.85rem; margin-top: 8px; display: none; }

        header { text-align: center; margin: 40px 0 30px; position: relative; }
        header h1 { font-size: 2.2rem; font-weight: 700; letter-spacing: 2px; color: #2c2c2c; }
        header p { font-size: 0.95rem; color: #5a5a5a; margin-top: 5px; }
        .new-post-btn { position: absolute; right: 0; top: 10px; background: #1a1a1a; color: white; border: none; border-radius: 8px; padding: 8px 16px; font-size: 0.9rem; cursor: pointer; display: none; }
        .back-link { display: inline-block; margin: 20px 0 10px; color: #3a3a3a; text-decoration: none; font-size: 0.95rem; border-bottom: 1px solid #ccc; cursor: pointer; }
        .article-list { list-style: none; margin-top: 20px; }
        .article-item { background: #ffffff; border-radius: 12px; padding: 20px 24px; margin-bottom: 16px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); cursor: pointer; transition: background 0.2s; }
        .article-item:hover { background: #f5f5f5; }
        .article-title { font-size: 1.25rem; font-weight: 600; margin-bottom: 6px; color: #1a1a1a; }
        .article-date { font-size: 0.8rem; color: #999; }
        .article-detail { background: #ffffff; border-radius: 12px; padding: 28px 24px; box-shadow: 0 2px 8px rgba(0,0,0,0.04); margin-top: 20px; }
        .article-detail h2 { font-size: 1.8rem; margin-bottom: 8px; }
        .article-detail .meta { font-size: 0.8rem; color: #999; margin-bottom: 24px; border-bottom: 1px solid #eee; padding-bottom: 12px; }
        .article-detail .content { font-size: 1.05rem; line-height: 1.8; color: #2c2c2c; }
        .article-detail .content p { margin-bottom: 1.2rem; }
        footer { text-align: center; margin-top: 50px; padding: 20px 0; color: #aaa; font-size: 0.8rem; }

        /* 写文章弹窗 */
        .editor-overlay { position: fixed; top: 0; left: 0; right: 0; bottom: 0; background: rgba(0,0,0,0.4); display: none; justify-content: center; align-items: center; z-index: 1000; padding: 20px; }
        .editor-box { background: white; border-radius: 16px; padding: 30px 24px; max-width: 500px; width: 100%; box-shadow: 0 8px 24px rgba(0,0,0,0.15); }
        .editor-box h3 { margin-bottom: 20px; font-size: 1.4rem; text-align: center; }
        .editor-box input, .editor-box textarea { width: 100%; padding: 12px; font-size: 1rem; border: 1px solid #ddd; border-radius: 8px; margin-bottom: 16px; outline: none; font-family: inherit; }
        .editor-box textarea { height: 200px; resize: vertical; }
        .editor-box .btn-group { display: flex; gap: 10px; }
        .editor-box button { flex: 1; padding: 12px; border: none; border-radius: 8px; font-size: 1rem; cursor: pointer; }
        .btn-publish { background: #1a1a1a; color: white; }
        .btn-cancel { background: #eee; color: #333; }

        @media (max-width: 500px) {
            body { padding: 12px; }
            header h1 { font-size: 1.8rem; }
            .article-item { padding: 16px 18px; }
            .new-post-btn { top: 5px; padding: 6px 12px; font-size: 0.8rem; }
            .password-box { padding: 30px 20px; }
        }
    </style>
</head>
<body>
    <!-- 密码验证 -->
    <div id="password-overlay" class="password-overlay">
        <div class="password-box">
            <h2>炭水化合物</h2>
            <p>请输入密码以继续阅读</p>
            <input type="password" id="password-input" placeholder="****" maxlength="20" inputmode="numeric">
            <button id="password-submit">进入</button>
            <div class="error-msg" id="error-msg">密码错误</div>
        </div>
    </div>

    <!-- 主内容 -->
    <div id="main-content" style="display: none;">
        <header>
            <h1>炭水化合物</h1>
            <p>吃进去的是碳水，写出来的是文字</p>
            <button class="new-post-btn" id="new-post-btn">✏️ 写文章</button>
        </header>

        <div id="app">
            <div id="list-view">
                <ul class="article-list" id="article-list"></ul>
                <p id="empty-msg" style="text-align:center; color:#999; margin-top:40px; display:none;">还没有文章，点击右上角“写文章”开始吧</p>
            </div>
            <div id="detail-view" style="display: none;">
                <a class="back-link" id="back-btn">← 回到列表</a>
                <div class="article-detail" id="article-detail"></div>
            </div>
        </div>
        <footer>© 炭水化合物 · 简单记录</footer>
    </div>

    <!-- 写文章弹窗 -->
    <div class="editor-overlay" id="editor-overlay">
        <div class="editor-box">
            <h3>写新文章</h3>
            <input type="text" id="post-title" placeholder="文章标题...">
            <textarea id="post-content" placeholder="正文内容...（段落用回车隔开）"></textarea>
            <div class="btn-group">
                <button class="btn-cancel" id="cancel-post">取消</button>
                <button class="btn-publish" id="publish-post">发布</button>
            </div>
        </div>
    </div>

    <script>
        // ========== 密码配置 ==========
        const CORRECT_PASSWORD = '1399';
        const STORAGE_KEY = 'tshhw_auth';
        const ARTICLES_KEY = 'tshhw_articles';

        // ========== 文章管理（本地存储） ==========
        function getArticles() {
            const stored = localStorage.getItem(ARTICLES_KEY);
            return stored ? JSON.parse(stored) : [];
        }

        function saveArticles(articles) {
            localStorage.setItem(ARTICLES_KEY, JSON.stringify(articles));
        }

        // ========== 密码逻辑 ==========
        const overlay = document.getElementById('password-overlay');
        const mainContent = document.getElementById('main-content');
        const pwInput = document.getElementById('password-input');
        const submitBtn = document.getElementById('password-submit');
        const errorMsg = document.getElementById('error-msg');

        function checkAuth() {
            if (localStorage.getItem(STORAGE_KEY) === CORRECT_PASSWORD) {
                overlay.style.display = 'none';
                mainContent.style.display = 'block';
                showAdmin();
                handleRoute();
            } else {
                overlay.style.display = 'flex';
                mainContent.style.display = 'none';
            }
        }

        function verify() {
            if (pwInput.value.trim() === CORRECT_PASSWORD) {
                localStorage.setItem(STORAGE_KEY, CORRECT_PASSWORD);
                overlay.style.display = 'none';
                mainContent.style.display = 'block';
                showAdmin();
                handleRoute();
            } else {
                errorMsg.style.display = 'block';
                pwInput.value = '';
            }
        }

        submitBtn.addEventListener('click', verify);
        pwInput.addEventListener('keypress', (e) => {
            if (e.key === 'Enter') verify();
        });

        // 显示管理员功能（写文章按钮）
        function showAdmin() {
            document.getElementById('new-post-btn').style.display = 'inline-block';
        }

        // ========== 文章列表与详情 ==========
        function getCurrentArticleId() {
            const hash = window.location.hash;
            if (hash.startsWith('#article-')) {
                return parseInt(hash.replace('#article-', ''), 10);
            }
            return null;
        }

        function renderList() {
            document.getElementById('list-view').style.display = 'block';
            document.getElementById('detail-view').style.display = 'none';
            const articles = getArticles();
            const listEl = document.getElementById('article-list');
            const emptyMsg = document.getElementById('empty-msg');
            listEl.innerHTML = '';

            if (articles.length === 0) {
                emptyMsg.style.display = 'block';
            } else {
                emptyMsg.style.display = 'none';
                articles.sort((a, b) => b.id - a.id).forEach(a => {
                    const li = document.createElement('li');
                    li.className = 'article-item';
                    li.innerHTML = `<div class="article-title">${a.title}</div><div class="article-date">${a.date}</div>`;
                    li.addEventListener('click', () => {
                        window.location.hash = '#article-' + a.id;
                    });
                    listEl.appendChild(li);
                });
            }
        }

        function renderDetail(id) {
            const articles = getArticles();
            const article = articles.find(a => a.id === id);
            if (!article) {
                window.location.hash = '';
                return;
            }
            document.getElementById('list-view').style.display = 'none';
            document.getElementById('detail-view').style.display = 'block';
            const detailEl = document.getElementById('article-detail');
            // 内容中的换行转为段落
            const formattedContent = article.content
                .split('\n')
                .filter(p => p.trim() !== '')
                .map(p => `<p>${p}</p>`)
                .join('');
            detailEl.innerHTML = `<h2>${article.title}</h2><div class="meta">${article.date}</div><div class="content">${formattedContent}</div>`;
            window.scrollTo(0, 0);
        }

        function handleRoute() {
            const articleId = getCurrentArticleId();
            if (articleId) {
                renderDetail(articleId);
            } else {
                renderList();
            }
        }

        window.addEventListener('hashchange', handleRoute);

        document.getElementById('back-btn').addEventListener('click', (e) => {
            e.preventDefault();
            window.location.hash = '';
        });

        // ========== 写文章功能 ==========
        const editorOverlay = document.getElementById('editor-overlay');
        const postTitle = document.getElementById('post-title');
        const postContent = document.getElementById('post-content');
        const publishBtn = document.getElementById('publish-post');
        const cancelBtn = document.getElementById('cancel-post');
        const newPostBtn = document.getElementById('new-post-btn');

        newPostBtn.addEventListener('click', () => {
            editorOverlay.style.display = 'flex';
            postTitle.value = '';
            postContent.value = '';
            postTitle.focus();
        });

        cancelBtn.addEventListener('click', () => {
            editorOverlay.style.display = 'none';
        });

        publishBtn.addEventListener('click', () => {
            const title = postTitle.value.trim();
            const content = postContent.value.trim();
            if (!title || !content) {
                alert('标题和正文都不能为空');
                return;
            }
            const articles = getArticles();
            const newId = articles.length > 0 ? Math.max(...articles.map(a => a.id)) + 1 : 1;
            const now = new Date();
            const dateStr = now.getFullYear() + '-' + 
                String(now.getMonth() + 1).padStart(2, '0') + '-' + 
                String(now.getDate()).padStart(2, '0');
            articles.push({
                id: newId,
                title: title,
                date: dateStr,
                content: content
            });
            saveArticles(articles);
            editorOverlay.style.display = 'none';
            window.location.hash = '';
            renderList();
        });

        // 初始加载
        checkAuth();
    </script>
</body>
</html>
