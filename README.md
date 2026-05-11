<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Work - Hollywood Portfolio</title>
    <style>
        /* 全局重置 + 复古蓝背景（完全保留） */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #1660AB;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 5vh 5vw;
            overflow-x: hidden;
        }

        /* 标题样式（完全保留：加粗+放大+居中+米白色） */
        .portfolio-title {
            font-family: "Snell Roundhand", "Vivaldi", "Script MT Bold", cursive;
            font-size: clamp(4rem, 10vw, 7rem);
            font-weight: 700;
            color: #F9F2E0;
            letter-spacing: 2px;
            margin-bottom: 10vh;
            text-align: center;
            opacity: 0;
            animation: fadeInUp 1.2s ease forwards 0.3s;
        }

        /* 水平滑动容器（完全保留） */
        .slider-container {
            width: 100%;
            max-width: 1400px;
            height: 500px;
            overflow-x: auto;
            overflow-y: hidden;
            scroll-snap-type: x mandatory;
            scrollbar-width: none;
            padding: 20px 0;
            opacity: 0;
            animation: fadeInUp 1.2s ease forwards 0.6s;
        }

        /* 隐藏滚动条（完全保留） */
        .slider-container::-webkit-scrollbar {
            display: none;
        }

        .slider-track {
            width: max-content;
            height: 100%;
            display: flex;
            gap: 40px;
            padding: 0 5vw;
        }

        /* 卡片样式（完全保留，支持a标签/div标签通用） */
        .card {
            width: 380px;
            height: 100%;
            scroll-snap-align: center;
            border-radius: 8px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            cursor: pointer;
            transition: transform 0.3s ease;
            /* 清除a标签默认样式 */
            text-decoration: none;
            display: block;
        }

        .card:active {
            cursor: grabbing;
        }

        .card:hover {
            transform: translateY(-8px);
        }

        /* 图片固定样式（完全保留） */
        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        /* 入场动画（完全保留） */
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

        /* 移动端适配（完全保留） */
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
    <!-- 老电影标题（完全保留） -->
    <h1 class="portfolio-title">My Work？</h1>

    <!-- 水平滑动卡片 → 已融合点击跳转功能（布局/动效无任何修改） -->
    <div class="slider-container">
        <div class="slider-track">
            <!-- 卡片1：替换href为你的作品链接，替换src为你的图片 -->
            <a href="work1.html" class="card" target="_blank">
                <img src="https://picsum.photos/id/29/800/1000" alt="作品1">
            </a>
            <!-- 卡片2 -->
            <a href="work2.html" class="card" target="_blank">
                <img src="https://picsum.photos/id/36/800/1000" alt="作品2">
            </a>
            <!-- 卡片3 -->
            <a href="work3.html" class="card" target="_blank">
                <img src="https://picsum.photos/id/45/800/1000" alt="作品3">
            </a>
            <!-- 卡片4 -->
            <a href="work4.html" class="card" target="_blank">
                <img src="https://picsum.photos/id/65/800/1000" alt="作品4">
            </a>
            <!-- 卡片5 -->
            <a href="work5.html" class="card" target="_blank">
                <img src="https://picsum.photos/id/76/800/1000" alt="作品5">
            </a>
        </div>
    </div>
</body>
</html>
