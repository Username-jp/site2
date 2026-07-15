<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aki's Portfolio (Not Responding)</title>
    <!-- ここにCSS（見た目）をあとで追加します -->
</head>
<body>

    <!-- 1. デスクトップ画面（背景） -->
    <div class="desktop">
        
        <!-- デスクトップのアイコンたち -->
        <div class="icon-container">
            <div class="icon">
                <img src="computer-icon.png" alt="My Computer">
                <span>マイ コンピュータ</span>
            </div>
            <div class="icon">
                <img src="folder-icon.png" alt="Works">
                <span>作品集</span>
            </div>
        </div>

        <!-- 2. ポップアップ風のウィンドウ -->
        <div class="window">
            <!-- ウィンドウのタイトルバー -->
            <div class="window-header">
                <span class="window-title">Aki's Digital Creations - portfolio.exe</span>
                <div class="window-buttons">
                    <button class="win-btn">_</button>
                    <button class="win-btn">[]</button>
                    <button class="win-btn">X</button>
                </div>
            </div>
            
            <!-- ウィンドウのメニューバー -->
            <div class="menu-bar">
                <span>ファイル(F)</span>
                <span>編集(E)</span>
                <span>表示(V)</span>
                <span>ヘルプ(H)</span>
            </div>

            <!-- ウィンドウの中身（メインコンテンツ） -->
            <div class="window-body">
                <h1>WELCOME TO AKI'S PORTFOLIO</h1>
                <p>ここにあなたのプロフィールや、イラストなどを掲載します。</p>
                <!-- イラストを並べるエリア -->
                <div class="gallery">
                    <div class="work-item">
                        <img src="your-art1.png" alt="作品1">
                        <p>Project Pixel</p>
                    </div>
                </div>
            </div>
        </div>

    </div>

    <!-- 3. 画面最下部のタスクバー -->
    <div class="taskbar">
        <button class="start-button">
            <img src="windows-logo.png" alt="" width="16"> スタート
        </button>
        <div class="active-tasks">
            <div class="task-tab pressed">portfolio.exe</div>
        </div>
        <div class="system-tray">
            <span class="time">14:30</span>
        </div>
    </div>

</body>
</html>
