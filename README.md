<!DOCTYPE html>
<html>
<head>
  <title>NeuroDefender Test</title>
  <style>
    body {font-family: Arial; text-align: center; margin-top: 50px; background: #0f172a; color: #e2e8f0;}
    button {background: #1e40af; color: white; padding: 12px 24px; border: none; border-radius: 8px; margin: 10px; cursor: pointer;}
    input {padding: 10px; width: 300px; border-radius: 8px; border: 1px solid #475569;}
    #status {margin-top: 20px; color: #86efac;}
  </style>
</head>
<body>
  <h2 style="color:#60a5fa">NeuroDefender — Biometrik Test</h2>
  <p style="color:#94a3b8">Ismingiz: <input id="name" placeholder="Asilbek" /></p>
  
  <button onclick="recordVoice()">1. Ovoz yozish (5 soniya)</button><br><br>
  <button onclick="captureFace()">2. Yuz surati</button><br><br>
  <input id="text" placeholder="neurodefender yozing"><br><br>
  <button onclick="saveData()">SAQLASH → Keyingi odam</button>

  <div id="status"></div>

<script>
let data = {name: '', voice: null, face: null, keystroke: []};

document.getElementById('name').oninput = e => data.name = e.target.value;
document.getElementById('text').addEventListener('keydown', e => {
    data.keystroke.push({key: e.key, time: Date.now()});
});

async function recordVoice() {
    const stream = await navigator.media...
    // (oldingi kodning davomi — to'liq kod quyida)# neurodefender-uz
