<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Work - Hollywood Portfolio</title>
    <style>
        /* 全局重置 + 复古蓝背景 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            /* 你要求的背景色：1660AB */
            background-color: #1660AB;
            min-height: 100vh;
            /* 全局垂直+水平居中 */
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 5vh 5vw;
            overflow-x: hidden;
        }

        /* ==================== 标题：加粗+放大+居中+米白色 ==================== */
        .portfolio-title {
            font-family: "Snell Roundhand", "Vivaldi", "Script MT Bold", cursive;
            /* 大幅放大字体 + 加粗 */
            font-size: clamp(4rem, 10vw, 7rem);
            font-weight: 700;
            /* 你要求的字体色：F9F2E0 */
            color: #F9F2E0;
            letter-spacing: 2px;
            /* 居中留白 */
            margin-bottom: 10vh;
            text-align: center;
            /* 入场动画 */
            opacity: 0;
            animation: fadeInUp 1.2s ease forwards 0.3s;
        }

        /* ==================== 水平滑动容器 ==================== */
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

        /* 隐藏滚动条 */
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

        /* ==================== 卡片样式 ==================== */
        .card {
            width: 380px;
            height: 100%;
            scroll-snap-align: center;
            border-radius: 8px;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            cursor: grab;
            transition: transform 0.3s ease;
        }

        .card:active {
            cursor: grabbing;
        }

        .card:hover {
            transform: translateY(-8px);
        }

        /* ==================== 图片固定：取消视差，完全贴合卡片 ==================== */
        .card img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            /* 图片固定在卡片内，不随滑动偏移 */
            display: block;
        }

        /* ==================== 入场动画 ==================== */
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
    <!-- 老电影标题 -->
    <h1 class="portfolio-title">My Work</h1>

    <!-- 水平滑动卡片 -->
    <div class="slider-container">
        <div class="slider-track">
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

    <!-- 已移除视差JS，图片完全固定 -->
</body>
</html>
