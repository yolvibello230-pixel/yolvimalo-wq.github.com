<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>🎯 Sensibilidad Yolvi_King</title>
<style>
body {
    margin: 0;
    font-family: Arial;
    background: #0f172a;
    color: white;
    text-align: center;
}

.titulo {
    font-size: 30px;
    color: #22c55e;
    text-shadow: 0 0 15px #22c55e;
    margin: 20px;
}

.boton {
    background: #1e293b;
    margin: 10px auto;
    padding: 15px;
    width: 260px;
    border-radius: 10px;
    cursor: pointer;
}

.boton:hover {
    background: #22c55e;
}

.marca {
    display: none;
}

.card {
    background: #1e293b;
    padding: 20px;
    border-radius: 15px;
    width: 300px;
    margin: auto;
    margin-top: 20px;
}
</style>
</head>
<body>

<h1 class="titulo">🎯 Sensibilidad Yolvi_King 👑</h1>

<!-- MENU -->
<div id="menu">
    <div class="boton" onclick="abrir('iphone')">📱 iPhone</div>
    <div class="boton" onclick="abrir('xiaomi')">📱 Xiaomi</div>
    <div class="boton" onclick="abrir('samsung')">📱 Samsung</div>
    <div class="boton" onclick="abrir('motorola')">📱 Motorola</div>
    <div class="boton" onclick="abrir('huawei')">📱 Huawei</div>
    <div class="boton" onclick="abrir('tecno')">📱 Tecno</div>
</div>

<!-- iPhone -->
<div id="iphone" class="marca">
    <h2>📱 iPhone</h2>
    <div class="card">
        <p>🎯 General: 100</p>
        <p>🔴 Punto Rojo: 95</p>
        <p>🔍 Mira 2x: 90</p>
        <p>🔭 Mira 4x: 80</p>
        <p>🎯 AWM: 55</p>
        <p>🎮 DPI: 300</p>
    </div>
    <div class="boton" onclick="volver('iphone')">⬅ Volver</div>
</div>

<!-- Xiaomi -->
<div id="xiaomi" class="marca">
    <h2>📱 Xiaomi</h2>
    <div class="card">
        <p>🎯 General: 95</p>
        <p>🔴 Punto Rojo: 90</p>
        <p>🔍 Mira 2x: 85</p>
        <p>🔭 Mira 4x: 75</p>
        <p>🎯 AWM: 50</p>
        <p>🎮 DPI: 400</p>
    </div>
    <div class="boton" onclick="volver('xiaomi')">⬅ Volver</div>
</div>

<!-- Samsung -->
<div id="samsung" class="marca">
    <h2>📱 Samsung</h2>
    <div class="card">
        <p>🎯 General: 90</p>
        <p>🔴 Punto Rojo: 88</p>
        <p>🔍 Mira 2x: 80</p>
        <p>🔭 Mira 4x: 70</p>
        <p>🎯 AWM: 48</p>
        <p>🎮 DPI: 350</p>
    </div>
    <div class="boton" onclick="volver('samsung')">⬅ Volver</div>
</div>

<!-- Motorola -->
<div id="motorola" class="marca">
    <h2>📱 Motorola</h2>
    <div class="card">
        <p>🎯 General: 92</p>
        <p>🔴 Punto Rojo: 87</p>
        <p>🔍 Mira 2x: 82</p>
        <p>🔭 Mira 4x: 72</p>
        <p>🎯 AWM: 45</p>
        <p>🎮 DPI: 360</p>
    </div>
    <div class="boton" onclick="volver('motorola')">⬅ Volver</div>
</div>

<!-- Huawei -->
<div id="huawei" class="marca">
    <h2>📱 Huawei</h2>
    <div class="card">
        <p>🎯 General: 93</p>
        <p>🔴 Punto Rojo: 89</p>
        <p>🔍 Mira 2x: 83</p>
        <p>🔭 Mira 4x: 73</p>
        <p>🎯 AWM: 47</p>
        <p>🎮 DPI: 370</p>
    </div>
    <div class="boton" onclick="volver('huawei')">⬅ Volver</div>
</div>

<!-- Tecno -->
<div id="tecno" class="marca">
    <h2>📱 Tecno</h2>
    <div class="card">
        <p>🎯 General: 97</p>
        <p>🔴 Punto Rojo: 92</p>
        <p>🔍 Mira 2x: 86</p>
        <p>🔭 Mira 4x: 76</p>
        <p>🎯 AWM: 52</p>
        <p>🎮 DPI: 420</p>
    </div>
    <div class="boton" onclick="volver('tecno')">⬅ Volver</div>
</div>

<script>
function abrir(id) {
    document.getElementById("menu").style.display = "none";
    document.getElementById(id).style.display = "block";
}

function volver(id) {
    document.getElementById(id).style.display = "none";
    document.getElementById("menu").style.display = "block";
}
</script>

</body>
</html>
