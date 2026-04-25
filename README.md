<!DOCTYPE html><html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Formulario Policía AsaltoRP</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #1a0000;
            color: white;
            margin: 0;
        }
        header {
            background: #330000;
            padding: 20px;
            text-align: center;
            border-bottom: 2px solid #ff0000;
        }
        h1 { color: #ff3b3b; margin: 0; }
        .container {
            max-width: 900px;
            margin: 20px auto;
            background: #260000;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 15px #ff000033;
        }
        h2 { margin-top: 25px; color: #ff4d4d; }
        label { display: block; margin-top: 10px; }
        input, textarea, select {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 5px;
            border: 1px solid #ff0000;
            background: #1a0000;
            color: white;
        }
        textarea { resize: vertical; }
        button {
            margin-top: 20px;
            padding: 12px;
            width: 100%;
            background: #ff0000;
            border: none;
            border-radius: 5px;
            color: white;
            font-weight: bold;
            cursor: pointer;
        }
        button:hover { background: #cc0000; }
        .msg { margin-top:10px; font-size:14px; }
    </style>
</head>
<body><header>
    <h1>🚔 Formulario de Ingreso – Policía AsaltoRP</h1>
</header><div class="container">
<form id="formPostulacion"><h2>📌 Información IC</h2>
<label>Nombre IC:</label><input name="nombre_ic" type="text" required>
<label>Edad IC:</label><input name="edad_ic" type="number" required>
<label>Nacionalidad IC:</label><input name="nacionalidad_ic" type="text">
<label>Teléfono IC:</label><input name="telefono_ic" type="text">
<label>Tiempo viviendo en la ciudad:</label><input name="tiempo_ciudad" type="text"><h2>📌 Información OOC</h2>
<label>Nombre:</label><input name="nombre_ooc" type="text" required>
<label>Edad:</label><input name="edad_ooc" type="number" required>
<label>País:</label><input name="pais" type="text">
<label>Horas diarias que juegas:</label><input name="horas" type="number">
<label>Experiencia en servidores RP:</label>
<textarea name="experiencia" rows="3"></textarea><h2>📌 Conocimientos de Rol</h2>
<label>PG:</label><textarea name="pg" rows="2"></textarea>
<label>MG:</label><textarea name="mg" rows="2"></textarea>
<label>RK:</label><textarea name="rk" rows="2"></textarea>
<label>CK:</label><textarea name="ck" rows="2"></textarea>
<label>FK:</label><textarea name="fk" rows="2"></textarea><h2>📌 Situaciones de Rol</h2>
<textarea name="situacion1" placeholder="1- Delincuente abatido..." rows="3"></textarea>
<textarea name="situacion2" placeholder="2- Robo con rehén..." rows="3"></textarea>
<textarea name="situacion3" placeholder="3- Sospechoso armado..." rows="3"></textarea>
<textarea name="situacion4" placeholder="4- Abuso policial..." rows="3"></textarea>
<textarea name="situacion5" placeholder="5- Persecución..." rows="3"></textarea><h2>📌 Compromiso</h2>
<textarea name="porque" placeholder="¿Por qué quieres ser policía?" rows="3"></textarea>
<textarea name="aporte" placeholder="¿Qué aportarías?" rows="3"></textarea><button type="submit">Enviar Postulación</button>

<div class="msg" id="msg"></div>
</form><script>
const webhookURL = "https://discord.com/api/webhooks/1497694131823185963/HBB77b2QSp2oioOvClCqcBuDtxt8xsBd7pi9p2ynnMGw5B8tjjJKuLD2_cDs_B_W4fkr";

const form = document.getElementById("formPostulacion");
const msg = document.getElementById("msg");

form.addEventListener("submit", async (e) => {
    e.preventDefault();

    const data = new FormData(form);

    let contenido = "🚔 **Nueva Postulación Policía**\n\n";

    data.forEach((valor, clave) => {
        if(valor) contenido += `**${clave.replace(/_/g," ")}**: ${valor}\n`;
    });

    try {
        await fetch(webhookURL, {
            method: "POST",
            headers: { "Content-Type": "application/json" },
            body: JSON.stringify({ content: contenido })
        });

        msg.innerHTML = "✅ Postulación enviada correctamente";
        msg.style.color = "#4ade80";
        form.reset();

    } catch (error) {
        msg.innerHTML = "❌ Error al enviar";
        msg.style.color = "red";
    }
});
</script></div></body>
</html>
