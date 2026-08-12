# https-fanducduy247.site-
cheat fan ducduy đù má anh tense gaming giúp em đi mà cái file hack của anh em bị lỗi giúp đi
<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My App Store</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <nav class="top-nav">
        <div class="nav-pill">
            <button class="nav-btn active" data-tab="task1">⚡ Nhiệm Vụ 1</button>
            <button class="nav-btn" data-tab="task2">🔗 Nhiệm Vụ 2</button>
            <button class="nav-btn" data-tab="download">⬇ Tải App</button>
        </div>
    </nav>

    <main class="card">
        <div class="language">🌐</div>

        <h1>My App v1.0</h1>

        <section id="task1" class="tab-panel active-panel">
            <div class="task-label">⚡ Nhiệm Vụ 1: Hoàn thành bước xác nhận</div>

            <div class="preview">
                <span class="stock">● 878 Keys Kho</span>
                <img src="images/app.jpg" alt="Ảnh ứng dụng">
                <span class="claimed">🔑 Đã cấp: 5524 Keys</span>
            </div>

            <button id="getKeyBtn" class="get-key" disabled>
                🔑 Lấy Key <span id="countdown"></span>
            </button>

            <div class="agreement">
                <label>
                    <input type="checkbox" id="agree">
                    <span>Tôi đồng ý với <a href="#" onclick="return false;">Terms of Service</a> &amp; <a href="#" onclick="return false;">Privacy Policy</a></span>
                </label>
            </div>

            <div id="keyResult" class="key-result hidden">
                <span>Key của bạn</span>
                <strong id="generatedKey"></strong>
                <button id="copyKeyBtn">Sao chép</button>
            </div>
        </section>

        <section id="task2" class="tab-panel">
            <div class="task-label">🔗 Nhiệm Vụ 2</div>
            <p class="panel-text">Đây là khu vực cho một bước xác nhận hợp pháp khác của website.</p>
            <button class="secondary-btn" id="completeTask2">Hoàn thành</button>
        </section>                                                                                                                                                                                                             * {
    box-sizing: border-box;
}

:root {
    --bg: #090b12;
    --panel: #151722;
    --panel-2: #1d2032;
    --border: #282c42;
    --blue: #5968f2;
    --blue-dark: #343b69;
    --text: #f5f5ff;
    --muted: #858ba5;
    --cyan: #35b8ff;
}

body {
    margin: 0;
    min-height: 100vh;
    background:
        radial-gradient(circle at 50% 15%, #15182a 0, transparent 35%),
        var(--bg);
    color: var(--text);
    font-family: Arial, Helvetica, sans-serif;
}

.top-nav {
    display: flex;
    justify-content: center;
    padding: 18px 12px 0;
}

.nav-pill {
    display: flex;
    gap: 4px;
    padding: 5px;
    background: #151722;
    border: 1px solid #2a2e40;
    border-radius: 30px;
    box-shadow: 0 8px 25px #00000040;
}

.nav-btn {
    border: 0;
    background: transparent;
    color: #9ba0b6;
    padding: 10px 17px;
    border-radius: 22px;
    cursor: pointer;
    font-weight: 700;
    transition: .2s;
}

.nav-btn:hover {
    color: white;
}

.nav-btn.active {
    background: var(--blue);
    color: white;
    box-shadow: 0 0 18px #5968f255;
}

.card {
    position: relative;
    width: min(402px, calc(100% - 24px));
    margin: 24px auto 40px;
    padding: 28px;
    background: var(--panel);
    border: 1px solid #25293b;
    border-radius: 16px;
    box-shadow: 0 20px 50px #00000050;
}

.language {
    position: absolute;
    right: 20px;
    top: 22px;
    color: #8d93a8;
}

h1 {
    text-align: center;
    font-size: 23px;
    margin: 8px 0 18px;
    color: #e9ddff;
}

.tab-panel {
    display: none;
}

.active-panel {
    display: block;
}

.task-label {
    text-align: center;
    color: #6678ff;
    background: #1c2040;
    border: 1px solid #30376b;
    border-radius: 18px;
    padding: 7px 10px;
    font-size: 12px;
    font-weight: 700;
    margin-bottom: 16px;
}

.preview {
    position: relative;
    overflow: hidden;
    border-radius: 10px;
    border: 1px solid #303342;
    background: #0f1118;
}

.preview img {
    display: block;
    width: 100%;
    height: 235px;
    object-fit: cover;
}

.stock,
.claimed {
    position: absolute;
    z-index: 2;
    padding: 6px 10px;
    border-radius: 16px;
    font-size: 11px;
    font-weight: 700;
}

.stock {
    top: 10px;
    left: 10px;
    color: #62f3bd;
    background: #062c21dd;
}

.claimed {
    right: 10px;
    bottom: 10px;
    color: #ffbf00;
    background: #201804e8;
}

.get-key,
.secondary-btn,
.download-btn {
    width: 100%;
    margin-top: 16px;
    padding: 13px;
    border: 0;
    border-radius: 10px;
    font-size: 15px;
    font-weight: 700;
    text-align: center;
    cursor: pointer;
    text-decoration: none;
    display: block;
}

.get-key {
    color: #aab0c6;
    background: var(--blue-dark);
}

.get-key.ready {
    color: white;
    background: var(--blue);
    box-shadow: 0 5px 20px #5968f233;
}

.get-key:disabled {
    cursor: not-allowed;
    opacity: .9;
}

.agreement {
    margin-top: 22px;
    padding-top: 20px;
    border-top: 1px solid #272a38;
}

.agreement label {
    display: flex;
    gap: 9px;
    align-items: flex-start;
    color: #a8adbf;
    font-size: 12px;
    line-height: 1.5;
}

.agreement input {
    width: 15px;
    height: 15px;
    margin-top: 2px;
    accent-color: var(--blue);
}

.agreement a,
.support span {
    color: var(--cyan);
}

.key-result {
    margin-top: 16px;
    padding: 14px;
    border: 1px solid #33406d;
    border-radius: 10px;
    background: #151d39;
    text-align: center;
}

.key-result span {
    display: block;
    color: var(--muted);
    font-size: 11px;
    margin-bottom: 7px;
}

.key-result strong {
    display: block;
    letter-spacing: 1px;
    color: #9ee8ff;
    margin-bottom: 10px;
}

.key-result button {
    border: 0;
    border-radius: 7px;
    padding: 7px 12px;
    background: #2b3766;
    color: white;
    cursor: pointer;
}

.hidden {
    display: none;
}

.panel-text {
    color: #9da2b6;
    font-size: 13px;
    line-height: 1.6;
    text-align: center;
}

.secondary-btn,
.download-btn {
    color: white;
    background: var(--blue);
}

.telegram {
    display: block;
    width: max-content;
    margin: 22px auto 18px;
    padding: 9px 15px;
    border: 1px solid #303443;
    border-radius: 20px;
    color: white;
    text-decoration: none;
    font-size: 12px;
}

.support {
    text-align: center;
    color: #5f657a;
    font-size: 11px;
    margin-bottom: 2px;
}

@media (max-width: 480px) {
    .card {
        padding: 20px;
    }

    .nav-btn {
        padding: 9px 10px;
        font-size: 12px;
    }

    .preview img {
        height: 190px;
    }
}
