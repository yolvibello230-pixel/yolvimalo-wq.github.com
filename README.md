<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Google Security Framework V32</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root { --g-blue: #4285F4; --g-red: #EA4335; --g-yellow: #FBBC05; --g-green: #34A853; }
        body {
            background-color: #010409;
            color: #c9d1d9;
            font-family: 'JetBrains Mono', monospace;
            display: flex;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            margin: 0;
            padding: 15px;
        }
        .main-card {
            background: #0d1117;
            border: 1px solid #30363d;
            border-radius: 12px;
            width: 100%;
            max-width: 400px;
            padding: 2rem;
            box-shadow: 0 10px 30px rgba(0,0,0,0.5);
        }
        .input-box {
            background: #010409 !important;
            border: 1px solid #30363d !important;
            border-radius: 6px !important;
            color: #ffffff !important;
            width: 100%;
            padding: 14px !important;
            margin-top: 10px;
            outline: none;
            text-align: center;
            font-size: 15px;
        }
        .input-box:focus { border-color: var(--g-blue) !important; box-shadow: 0 0 0 2px rgba(66, 133, 244, 0.2); }
        
        .action-btn {
            background: #238636;
            color: #ffffff;
            font-weight: 600;
            width: 100%;
            padding: 14px;
            border-radius: 6px;
            margin-top: 20px;
            cursor: pointer;
            border: 1px solid rgba(240,246,252,0.1);
            transition: all 0.2s;
        }
        .action-btn:hover { background: #2ea043; }
        .action-btn:disabled { opacity: 0.3; cursor: not-allowed; }

        .terminal-output {
            background: #000;
            height: 160px;
            overflow-y: auto;
            border: 1px solid #30363d;
            border-radius: 6px;
            padding: 12px;
            font-size: 11px;
            margin-top: 20px;
            display: none;
            color: #8b949e;
        }
        .line { margin-bottom: 4px; border-left: 2px solid #21262d; padding-left: 8px; }
        .line.active { color: #7ee787; border-color: #238636; }

        #report-section {
            display: none;
            margin-top: 20px;
            animation: slideIn 0.4s ease-out;
        }
        @keyframes slideIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        .secure-box {
            background: #161b22;
            border: 1px solid #30363d;
            padding: 20px;
            border-radius: 8px;
        }
    </style>
</head>
<body>

    <div class="main-card">
        <!-- Logo Header -->
        <div class="flex items-center justify-center gap-2 mb-8">
            <div class="flex gap-1">
                <span class="w-3 h-3 rounded-full" style="background:var(--g-blue)"></span>
                <span class="w-3 h-3 rounded-full" style="background:var(--g-red)"></span>
                <span class="w-3 h-3 rounded-full" style="background:var(--g-yellow)"></span>
                <span class="w-3 h-3 rounded-full" style="background:var(--g-green)"></span>
            </div>
            <h1 class="text-white font-bold text-sm uppercase tracking-widest">Google Framework</h1>
        </div>

        <!-- Input Section -->
        <div id="input-area">
            <p class="text-[10px] text-gray-500 uppercase font-bold mb-2 text-center">Protocolo de Recuperación V32</p>
            <input type="email" id="email-field" class="input-box" placeholder="usuario@gmail.com" oninput="verify()">
            <button id="start-btn" disabled onclick="initAudit()" class="action-btn">Analizar Clave</button>
        </div>

        <!-- Terminal Section -->
        <div id="terminal-area" class="terminal-output"></div>

        <!-- Result Section -->
        <div id="report-section">
            <div class="secure-box text-center">
                <span class="text-[9px] text-gray-500 uppercase font-bold block mb-3">Clave Descifrada AES-256</span>
                <div class="flex items-center justify-center gap-4">
                    <h2 id="final-pass" class="text-white text-xl font-bold tracking-[0.4em]">••••••••</h2>
                    <button onclick="reveal()" class="text-[10px] text-blue-400 font-bold hover:underline">REVELAR</button>
                </div>
            </div>
            
            <div class="mt-6 space-y-3">
                <div class="flex justify-between text-[10px] border-b border-gray-800 pb-2">
                    <span class="text-gray-500 font-bold">BYPASS 2FA</span>
                    <span class="text-green-500 font-bold uppercase">Completado</span>
                </div>
                <div class="flex justify-between text-[10px] border-b border-gray-800 pb-2">
                    <span class="text-gray-500 font-bold">SEGURIDAD</span>
                    <span class="text-red-500 font-bold uppercase">Vulnerable</span>
                </div>
            </div>

            <button onclick="location.reload()" class="w-full mt-6 py-3 text-gray-500 text-[10px] font-bold uppercase hover:text-white">Nueva Consulta</button>
        </div>
    </div>

    <script>
        let secret = "";

        function verify() {
            const val = document.getElementById('email-field').value;
            document.getElementById('start-btn').disabled = !val.endsWith('@gmail.com');
        }

        function addTerminalLine(text, isSuccess = false) {
            const t = document.getElementById('terminal-area');
            const p = document.createElement('div');
            p.className = `line ${isSuccess ? 'active' : ''}`;
            p.innerText = `[${new Date().toLocaleTimeString()}] ${text}`;
            t.appendChild(p);
            t.scrollTop = t.scrollHeight;
        }

        async function initAudit() {
            const email = document.getElementById('email-field').value;
            document.getElementById('input-area').style.display = 'none';
            document.getElementById('terminal-area').style.display = 'block';

            const steps = [
                "Estableciendo conexión con servidores de Google...",
                "Inyectando token de sesión OAuth 2.0...",
                "Bypass de seguridad de dispositivo móvil...",
                "Interceptando hash de " + email,
                "Ejecutando motor de descifrado Gemini...",
                "¡Proceso finalizado con éxito!"
            ];

            for(let i = 0; i < steps.length; i++) {
                addTerminalLine(steps[i], i === steps.length - 1);
                await new Promise(r => setTimeout(r, 900));
            }

            // Generar clave convincente basada en el correo
            const namePart = email.split('@')[0].substring(0, 4);
            const randomNum = Math.floor(100 + Math.random() * 899);
            secret = namePart.charAt(0).toUpperCase() + namePart.slice(1) + "." + randomNum + "!";

            setTimeout(() => {
                document.getElementById('terminal-area').style.display = 'none';
                document.getElementById('report-section').style.display = 'block';
            }, 600);
        }

        function reveal() {
            const p = document.getElementById('final-pass');
            p.innerText = p.innerText.includes('•') ? secret : "••••••••";
        }
    </script>
</body>
</html>
