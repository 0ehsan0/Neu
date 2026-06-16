<!DOCTYPE html>
<html lang="fa">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Singularity | @phrazel</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        body {
            background: #000000;
            overflow: hidden;
            font-family: 'Courier New', Courier, monospace;
            position: relative;
        }
        /* افکت خطوط تلویزیونی برای حس سایبرپانک */
        body::before {
            content: " ";
            display: block;
            position: absolute;
            top: 0; left: 0; bottom: 0; right: 0;
            background: linear-gradient(rgba(18, 16, 16, 0) 50%, rgba(0, 0, 0, 0.4) 50%);
            z-index: 100;
            background-size: 100% 4px;
            pointer-events: none;
        }
        canvas {
            display: block;
            position: absolute;
            top: 0;
            left: 0;
            z-index: 1;
            /* انیمیشن لود ناگهانی پس‌زمینه */
            opacity: 0;
            animation: nasaIntroCanvas 2s cubic-bezier(0.25, 1, 0.5, 1) forwards;
            animation-delay: 0.5s;
        }
        /* 🌌 باکس هسته مرکزی با افکت لود ناگهانی ناسا */
        .singularity-core {
            position: absolute;
            top: 50%;
            left: 50%;
            z-index: 10;
            text-align: center;
            padding: 40px;
            border-radius: 50%;
            width: 280px;
            height: 280px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: rgba(0, 0, 0, 0.75);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(0, 255, 0, 0.2);
            
            /* وضعیت اولیه: مخفی و کوچک */
            opacity: 0;
            transform: translate(-50%, -50%) scale(0.7);
            filter: blur(10px);
            
            /* انیمیشن اصلی ورود */
            animation: nasaIntroCore 1.8s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
            animation-delay: 0.8s; /* کمی بعد از مشکی مطلق ظاهر می‌شود */
        }
        h1 {
