<!DOCTYPE html>
<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hệ thống bị xâm nhập!</title>
    <style>
        body { background: #000; color: #0f0; font-family: 'Courier New', monospace; padding: 20px; line-height: 1.6; overflow: hidden; }
        .cursor { display: inline-block; width: 10px; height: 1.2em; background: #0f0; animation: blink 0.7s infinite; }
        @keyframes blink { 50% { opacity: 0; } }
        .warning { color: #f00; font-weight: bold; text-transform: uppercase; }
    </style>
</head>
<body>
    <div id="console"></div><span class="cursor"></span>
    <script>
        const el = document.getElementById('console');
        const content = [
            "> Đang thiết lập kết nối từ xa...",
            "> Truy cập thành công IP: 113.161.x.x",
            "> Đang quét dữ liệu cá nhân...",
            "> [CẢNH BÁO] Hệ thống đã bị chiếm quyền!",
            "> Đang mở tin nhắn bí mật...",
            "------------------------------------",
            "THÔNG BÁO TỪ CẬU CHỦ TÂN:",
            "Tối nay đi ăn với anh nhé? ❤️",
            "------------------------------------"
        ];
        let line = 0;
        function type() {
            if (line < content.length) {
                let p = document.createElement('p');
                if (content[line].includes("CẢNH BÁO")) p.className = "warning";
                el.appendChild(p);
                let char = 0;
                let interval = setInterval(() => {
                    if (char < content[line].length) { p.textContent += content[line][char++]; }
                    else { clearInterval(interval); line++; setTimeout(type, 500); }
                }, 40);
            }
        }
        type();
    </script>
</body>
</html>
