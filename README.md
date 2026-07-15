<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <title>{Title}</title>
    <link rel="shortcut icon" href="{Favicon}">
    <link rel="alternate" type="application/rss+xml" href="{RSS}">
    
    <link rel="stylesheet" href="https://unpkg.com/98.css">

    <style type="text/css">
        /* デスクトップ（背景）の設定 */
        body {
            background-color: #008080 !important; /* あの懐かしい緑色 */
            margin: 0;
            padding: 20px;
            font-family: "MS UI Gothic", Tahoma, sans-serif;
            overflow-x: hidden;
        }

/* ウィンドウを並べるエリア */
        #desktop {
            /* 👇 ここを追加：左側にアイコン用のスペースを強制的に空けます */
            padding-left: 130px !important; 
            box-sizing: border-box !important;

            column-width: 320px; 
            column-gap: 20px; 
            max-width: 100%;
            margin: 0 auto;
        }

/* 1つのウィンドウ（投稿）のサイズ設定 */
        .window {
            zoom: 0.75; 
            margin-bottom: 20px; 
            box-shadow: inset -1px -1px #0a0a0a, inset 1px 1px #fff, inset -2px -2px #dfdfdf, inset 2px 2px #808080;
            transform-origin: top left; 
            height: max-content !important;
            
            /* 👇 分裂を絶対に防止するための強力な設定セット */
            display: inline-table !important; /* ブロックが泣き別れするのを防ぐ */
            break-inside: avoid-column !important; /* 列の途中での分裂を禁止 */
            column-break-inside: avoid !important; /* 古いブラウザ向けの分裂禁止 */
            
            width: 100% !important; 
        }

/* ウィンドウの中身（本文） */
        .window-body {
            background: #ffffff !important;
            padding: 12px;
            margin: 0;
            
            /* くぼみエフェクト（お好みでON/OFFしてください） */
            /* box-shadow: inset -1px -1px #fff, inset 1px 1px #0a0a0a, inset -2px -2px #dfdfdf, inset 2px 2px #808080; */
            
            font-size: 12px !important;    
            line-height: 1.6 !important;  
            
            /* 👇 無理な引き伸ばしを消して、中身のサイズ通りにさせます */
            height: auto !important; 
        }

        /* もしタイトル文字（h2）が大きすぎる場合、これも小さくします */
        .window-body h2 {
            font-size: 14px !important;    /* 見出しをほどよい大きさに */
            margin-top: 0;
            margin-bottom: 10px;
        }

        /* ページナビゲーション（前へ・次へ） */
        .navigation {
            width: 100%;
            display: flex;
            justify-content: center;
            margin-top: 30px;
        }
        
        .navigation .field-row {
            background: #c0c0c0;
            padding: 10px;
            box-shadow: inset -1px -1px #0a0a0a, inset 1px 1px #fff;
        }
    </style>
</head>
<body>

    <div id="desktop">
<div class="desktop-shortcuts">
    
    <a href="https://x.com/____mana" class="shortcut-item">
        <img src="https://win98icons.alexmeub.com/icons/png/notepad-5.png" alt="My Computer">
        <span>Twitter</span>
    </a>

    <a href="https://www.instagram.com/cha_n_ma_na" class="shortcut-item">
        <img src="https://win98icons.alexmeub.com/icons/png/cd_audio_cd_a-3.png" alt="Internet">
        <span>Instagram</span>
    </a>


</div>

<style type="text/css">
/* アイコン全体を左側に縦並びにする設定 */
    .desktop-shortcuts {
        display: flex;
        flex-direction: column; 
        gap: 20px;
        position: absolute;
        top: 20px;
        
        /* 👇 左側の余白（130px）の真ん中に来るように調整 */
        left: 25px; 
        width: 80px;
        
        /* 👇 ウィンドウより手前に配置して、クリックしやすくします */
        z-index: 999; 
        pointer-events: auto;
    }

    /* アイコン1つ1つの見た目と文字の設定 */
    .shortcut-item {
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
        text-decoration: none !important;
        color: #ffffff !important; /* 文字色はデスクトップに映える白 */
        font-family: "MS UI Gothic", sans-serif;
        font-size: 11px !important;
        cursor: pointer;
    }

    /* アイコン画像のデザイン */
    .shortcut-item img {
        width: 32px;
        height: 32px;
        margin-bottom: 4px;
        image-rendering: pixelated; /* ドット絵をクッキリさせる */
    }

    /* アイコンの文字が背景に溶けないように、ほんのり影をつける（あの頃風） */
    .shortcut-item span {
        padding: 2px 4px;
        text-shadow: 1px 1px 1px #000000;
        line-height: 1.2;
    }

    /* マウスを乗せたときに、Windows特有の「選択された青い状態」にする */
    .shortcut-item:hover span {
        background-color: #000080 !important; /* 懐かしの紺色 */
        outline: 1px dotted #ffffff;
    }
</style>        
        {block:Posts}
        <div class="window">
            <div class="title-bar">
                <div class="title-bar-text">
                    {block:Title}{Title}{/block:Title}
                    {block:NotTitle}Windows 98 Document{/block:NotTitle}
                </div>
                <div class="title-bar-controls">
                    <button aria-label="Minimize"></button>
                    <button aria-label="Maximize"></button>
                    <button aria-label="Close"></button>
                </div>
            </div>

            <div class="window-body">
                {block:Text}
                    {block:Title}<h2>{Title}</h2>{/block:Title}
                    {Body}
                {/block:Text}

                {block:Photo}
                    <img src="{PhotoURL-400}" alt="{PhotoAlt}"/>
                    {block:Caption}<div class="caption">{Caption}</div>{/block:Caption}
                {/block:Photo}

                {block:Link}
                    <a href="{URL}" class="link" {Target}>{Name}</a>
                    {block:Description}<div class="description">{Description}</div>{/block:Description}
                {/block:Link}
            </div>
        </div>
        {/block:Posts}

<div id="retro-statusbar">
    <div class="status-inset">
        <span class="visitor-text">WELCOME TO MY SITE</span>
        <div class="digital-counter" id="mock-counter">004521</div>
    </div>
</div>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap" rel="stylesheet">

<script type="text/javascript">
    /* ページを開くたびに、当時のキリ番っぽいリアルな数字を自動生成する可愛いお遊びスクリプト */
    window.addEventListener('DOMContentLoaded', () => {
        const counterEl = document.getElementById('mock-counter');
        // 10000〜99999の間のランダムな数字を作って、あの頃の個人サイトっぽさを演出します
        const randomNum = Math.floor(Math.random() * 90000) + 10000;
        counterEl.innerText = String(randomNum).padStart(6, '0');
    });
</script>

<style type="text/css">
    /* カウンターを画面最下部に固定するタスクバー風のCSS */
    #retro-statusbar {
        position: fixed;
        bottom: 0;
        left: 0;
        width: 100%;
        background: #c0c0c0 !important;
        padding: 4px;
        box-shadow: inset 1px 1px #fff;
        border-top: 2px solid #dfdfdf;
        z-index: 9999; 
        display: flex;
        justify-content: flex-end; 
        box-sizing: border-box;
    }

    /* Windows98特有の「くぼみ」を表現 */
    #retro-statusbar .status-inset {
        background: #c0c0c0;
        padding: 4px 10px;
        box-shadow: inset -1px -1px #fff, inset 1px 1px #0a0a0a, inset -2px -2px #dfdfdf, inset 2px 2px #808080;
        display: flex;
        align-items: center;
        gap: 8px;
        margin-right: 10px;
    }

    /* カウンターの横のキリ番風テキスト */
    .visitor-text {
        font-family: "MS UI Gothic", sans-serif;
        font-size: 11px !important;
        color: #000000;
        font-weight: bold;
    }

    /* 💡 あの頃の「黒背景に緑文字」のデジタルカウンターを完全再現 */
    .digital-counter {
        background-color: #000000 !important;
        color: #00ff00 !important;
        font-family: 'Share Tech Mono', monospace !important;
        font-size: 16px !important;
        padding: 1px 6px !important;
        letter-spacing: 2px !important;
        border: 1px solid #404040 !important;
        text-shadow: 0 0 4px #00ff00; /* ネオンっぽく光らせる */
        line-height: 1.2 !important;
    }
    
    /* デスクトップの最下部がタスクバーと被らないように余白を追加 */
    #desktop {
        margin-bottom: 60px !important;
    }
</style>
    </div>

<img src="https://64.media.tumblr.com/2b3341c0ffcfe90ca8e9e7f6473d64e1/3d9494a2c398f82a-9e/s640x960/4369536ae6e9050482510970838d98b3688c75d5.gif" id="floating-gif" alt="mascot">

<script type="text/javascript">
    /* GIF画像を画面内でバウンドさせるプログラム */
    window.addEventListener('DOMContentLoaded', () => {
        const img = document.getElementById('floating-gif');
        
        // 浮遊するスピード（数字を大きくすると速くなります）
        let speedX = 2;
        let speedY = 1.5;
        
        // 初期位置
        let posX = Math.random() * (window.innerWidth - 100);
        let posY = Math.random() * (window.innerHeight - 100);
        
        function moveGif() {
            // 画面の現在の縦横幅を取得
            const maxX = window.innerWidth - img.clientWidth;
            const maxY = window.innerHeight - img.clientHeight;
            
            // 位置を更新
            posX += speedX;
            posY += speedY;
            
            // 左右の壁にぶつかったら跳ね返る
            if (posX >= maxX || posX <= 0) {
                speedX = -speedX;
                // 壁にぶつかったときに画像を反転させる（お好みで）
                img.style.transform = speedX < 0 ? 'scaleX(-1)' : 'scaleX(1)';
            }
            // 上下の壁（またはタスクバー）にぶつかったら跳ね返る
            if (posY >= maxY - 40 || posY <= 0) {
                speedY = -speedY;
            }
            
            // 実際の画像の位置に反映
            img.style.left = posX + 'px';
            img.style.top = posY + 'px';
            
            requestAnimationFrame(moveGif);
        }
        
        // 動きを開始
        moveGif();
    });
</script>

<style type="text/css">
    /* 浮遊画像用のCSS設定 */
    #floating-gif {
        position: fixed;
        z-index: 9998; /* ウィンドウより手前、タスクバー（9999）より一歩奥に配置 */
        pointer-events: none; /* 💡 画像が邪魔で後ろのボタンがクリックできないのを防ぐ */
        
        /* 👇 ここで浮遊させたいGIF画像のサイズ（横幅）を指定 */
        width: 200px; 
        height: auto;
        
        /* 昔のドット絵GIFがぼやけないようにクッキリ表示する魔法 */
        image-rendering: pixelated; 
    }
</style>

</body>
</html>
