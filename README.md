# bday-invitation[ritas_birthday_invitation_animate.html](https://github.com/user-attachments/files/34872718/ritas_birthday_invitation_animate.html)
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rita's Birthday Invitation</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            min-height: 100vh;
            background: #1a1423;
            display: flex;
            align-items: center;
            justify-content: center;
            font-family: "Georgia", serif;
            overflow: hidden;
        }
        /* 信封容器 */
        .envelope-wrap {
            position: relative;
            width: 420px;
            height: 300px;
            cursor: pointer;
            transition: transform 0.6s ease;
        }
        .envelope {
            width: 100%;
            height: 100%;
            position: relative;
            background: #f4e9d8;
            border-radius: 0 0 12px 12px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.35);
        }
        /* 信封上盖 */
        .envelope-flap {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 160px;
            background: #e8d9c4;
            clip-path: polygon(0 0, 50% 65%, 100% 0);
            transform-origin: top center;
            transition: transform 1.2s cubic-bezier(0.65, 0, 0.35, 1);
            z-index: 3;
        }
        .envelope-wrap.open .envelope-flap {
            transform: rotateX(180deg);
        }
        /* 信封左右翼 */
        .envelope-left, .envelope-right {
            position: absolute;
            bottom: 0;
            width: 50%;
            height: 140px;
            background: #e0d0ba;
            z-index: 2;
        }
        .envelope-left {
            left: 0;
            clip-path: polygon(0 0, 100% 100%, 0 100%);
        }
        .envelope-right {
            right: 0;
            clip-path: polygon(100% 0, 0 100%, 100% 100%);
        }
        /* 邀请函卡片 */
        .card {
            position: absolute;
            width: 340px;
            height: 220px;
            background: #fffbf5;
            border-radius: 8px;
            box-shadow: 0 4px 16px rgba(0,0,0,0.15);
            top: 50%;
            left: 50%;
            transform: translate(-50%, 0);
            padding: 32px 24px;
            text-align: center;
            z-index: 1;
            opacity: 0;
            transition: all 1.2s cubic-bezier(0.65, 0, 0.35, 1);
        }
        .envelope-wrap.open .card {
            opacity: 1;
            transform: translate(-50%, -140px);
        }
        .card h2 {
            color: #723b48;
            font-size: 26px;
            margin-bottom: 16px;
            letter-spacing: 2px;
        }
        .card p {
            color: #443338;
            font-size: 15px;
            line-height: 1.7;
        }
        .tip {
            position: absolute;
            bottom: -40px;
            left: 50%;
            transform: translateX(-50%);
            color: #c9b8a2;
            font-size: 14px;
            white-space: nowrap;
        }
        .envelope-wrap.open .tip {
            opacity: 0;
            transition: opacity 0.5s;
        }
        /* 星星点缀 */
        .star {
            position: absolute;
            color: #ffd8a8;
            animation: twinkle 2.5s infinite ease-in-out;
        }
        @keyframes twinkle {
            0%,100% { opacity: 0.3; }
            50% { opacity: 1; }
        }
    </style>
</head>
<body>
    <div class="envelope-wrap" id="env">
        <div class="envelope-flap"></div>
        <div class="envelope">
            <div class="envelope-left"></div>
            <div class="envelope-right"></div>
        </div>
        <div class="card">
            <h2>You’re Invited</h2>
            <p>
                Rita’s Birthday<br>
                —— Celebration ——<br>
                Date: Dec 6th, 2026<br>
                Time: 6:00 PM<br>
                Location: NYU Shanghai North Gate<br>
                Dress Code: Light Colors
            </p>
        </div>
        <div class="tip">✨ Click to open the invitation ✨</div>
    </div>

    <script>
        const env = document.getElementById('env');
        env.onclick = () => {
            env.classList.add('open');
        }
    </script>
</body>
</html>
