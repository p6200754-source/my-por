<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Work - Hollywood Portfolio</title>
    <style>
        /* 全局重置 + 老电影基础风格 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            /* 复古胶片背景色 */
            background-color: #f8f5f0;
            min-height: 100vh;
            /* 垂直居中布局 */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 5vh 5vw;
            /* 隐藏横向滚动条 */
            overflow-x: hidden;
        }

        /* ==================== 标题样式（老电影片头花体） ==================== */
        .portfolio-title {
            /* 核心：匹配Vivaldi/Snell Roundhand老电影字体 */
            font-family: "Snell Roundhand", "Vivaldi", "Script MT Bold", cursive;
            font-size: clamp(3rem, 8vw, 6rem);
            color: #2c2c2c;
            font-weight: 500;
            letter-spacing: 2px;
            /* 超大留白，呼吸感 */
            margin-bottom: 8vh;
            /* 页面入场动画 */
            opacity: 0;
            animation: fadeInUp 1.2s ease forwards 0.3s;
        }

        /* ==================== 水平滑动容器 ==================== */
        .slider-container {
            width: 100%;
            max-width: 1400px;
            height: 500px;
            /* 水平滚动核心 */
            overflow-x: auto;
            overflow-y: hidden;
            /* 流畅滚动吸附 */
            scroll-snap-type: x mandatory;
            /* 隐藏滚动条（复古简约） */
            scrollbar-width: none;
            padding: 20px 0;
            /* 入场动画延迟 */
            opacity: 0;
            animation: fadeInUp 1.2s ease forwards 0.6s;
        }

        /* 隐藏滚动条（Chrome/Safari） */
        .slider-container::-webkit-scrollbar {
            display: none;
        }

        /* 滑动卡片轨道 */
        .slider-track {
            width: max-content;
            height: 100%;
            display: flex;
            gap: 40px; /* 卡片间距 */
            padding: 0 5vw; /* 左右留白 */
        }

        /* ==================== 视差卡片样式 ==================== */
        .card {
            width: 380px;
            height: 100%;
            /* 滚动吸附居中 */
            scroll-snap-align: center;
            border-radius: 8px;
            /* 老电影胶片轻微阴影 */
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
            overflow: hidden;
            position: relative;
            cursor: grab;
            transition: transform 0.3s ease;
        }

        .card:active {
            cursor: grabbing;
        }

        /* 卡片悬浮微效果 */
        .card:hover {
            transform: translateY(-8px);
        }

        /* 卡片图片（视差核心） */
        .card img {
            width: 120%; /* 预留视差偏移空间 */
            height: 100%;
            object-fit: cover;
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            transition: transform 0.2s ease-out;
        }

        /* ==================== 页面入场动画 ==================== */
        @keyframes fadeInUp {
            0% {
                opacity: 0;
                transform: translateY(30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* ==================== 移动端适配 ==================== */
        @media (max-width: 768px) {
            .card {
                width: 280px;
            }
            .slider-container {
                height: 400px;
            }
        }
    </style>
</head>
<body>
    <!-- 第一部分：老电影标题 -->
    <h1 class="portfolio-title">My Work</h1>

    <!-- 第二部分：水平视差滑动卡片 -->
    <div class="slider-container">
        <div class="slider-track">
            <!-- 5张作品集卡片（替换src为你的作品图） -->
            <div class="card">
                <img src="https://picsum.photos/id/29/800/1000" alt="作品1">
            </div>
            <div class="card">
                <img src="https://picsum.photos/id/36/800/1000" alt="作品2">
            </div>
            <div class="card">
                <img src="https://picsum.photos/id/45/800/1000" alt="作品3">
            </div>
            <div class="card">
                <img src="https://picsum.photos/id/65/800/1000" alt="作品4">
            </div>
            <div class="card">
                <img src="https://picsum.photos/id/76/800/1000" alt="作品5">
            </div>
        </div>
    </div>

    <script>
        // 水平滑动视差效果 JS
        const slider = document.querySelector('.slider-container');
        const cards = document.querySelectorAll('.card img');

        slider.addEventListener('scroll', () => {
            // 滚动距离
            const scrollLeft = slider.scrollLeft;
            
            // 每张图片反向偏移，实现视差纵深
            cards.forEach((img, index) => {
                // 视差强度（数值越小越柔和）
                const parallax = scrollLeft * 0.15;
                img.style.transform = `translate(calc(-50% + ${-parallax}px), -50%)`;
            });
        });
    </script>
</body>
</html>
