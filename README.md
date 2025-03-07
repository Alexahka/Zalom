<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CSS Анимация</title>
    <style>
        /* Общие стили */
        body {
            font-family: Arial, sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f9;
        }

        .wrapper {
            position: relative;
            width: 300px;
            padding: 20px;
            border: 1px solid #ccc;
            background: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        .form-box {
            position: relative;
        }

        .animation {
            font-size: 18px;
            font-weight: bold;
            color: #333;
            transform: translateX(0);
            transition: all 0.7s ease;
            opacity: 1;
            filter: blur(0);
            transition-delay: calc(0.1s * var(--j));
        }

        .wrapper.active .animation {
            transform: translateX(-120%);
            opacity: 0;
            filter: blur(10px);
            transition-delay: calc(0.1s * var(--i));
        }

        button {
            margin-top: 20px;
            padding: 10px 20px;
            font-size: 16px;
            color: #fff;
            background-color: #007bff;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        button:hover {
            background-color: #0056b3;
        }

        /* Стили для ссылки */
        .linkTxt a {
            color: blue;
            text-decoration: none;
            font-weight: 600;
        }

        .linkTxt a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>

    <!-- Контейнер с анимацией -->
    <div class="wrapper">
        <div class="form-box login">
            <p class="animation" style="--j: 1; --i: 2;">Текст 1</p>
            <p class="animation" style="--j: 2; --i: 3;">Текст 2</p>
            <p class="animation" style="--j: 3; --i: 4;">Текст 3</p>
        </div>
        <button onclick="toggleAnimation()">Переключить анимацию</button>
    </div>

    <!-- Пример ссылки -->
    <p class="linkTxt" style="margin-top: 20px;">
        <a href="#">Ссылка на пример</a>
    </p>

    <script>
        // Функция для переключения анимации
        function toggleAnimation() {
            document.querySelector('.wrapper').classList.toggle('active');
        }
    </script>

</body>
</html>
