# Hayali-telefon-olu-tur
Kendi hayalinizdeki telefonu oluşturun
<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <title>Kendi Telefonunu Tasarla</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

<h1>📱 Kendi Telefonunu Tasarla</h1>

<div class="container">

  <div class="section">
    <h2>İşlemci</h2>
    <select id="cpu">
      <option value="300">Snapdragon 8 Elite</option>
      <option value="250">Snapdragon 8 Gen 3</option>
      <option value="220">Snapdragon 8 Gen 2</option>
    </select>
  </div>

  <div class="section">
    <h2>Kamera</h2>
    <select id="camera">
      <option value="200">200 MP (1 inch)</option>
      <option value="150">108 MP</option>
      <option value="100">64 MP</option>
    </select>
  </div>

  <div class="section">
    <h2>Pil</h2>
    <select id="battery">
      <option value="120">7500 mAh</option>
      <option value="100">6500 mAh</option>
      <option value="80">5000 mAh</option>
    </select>
  </div>

  <div class="section">
    <h2>Ekran</h2>
    <select id="screen">
      <option value="180">6.9” LTPO AMOLED 144Hz</option>
      <option value="140">6.7” AMOLED 120Hz</option>
      <option value="100">OLED 90Hz</option>
    </select>
  </div>

  <button onclick="hesapla()">📊 Telefonu Oluştur</button>

  <div id="result"></div>

</div>

<script src="script.js"></script>
</body>
</html>
body {
  font-family: Arial, sans-serif;
  background: #0f172a;
  color: #fff;
  text-align: center;
}

.container {
  width: 400px;
  margin: auto;
  background: #020617;
  padding: 20px;
  border-radius: 10px;
}

.section {
  margin-bottom: 15px;
}

select, button {
  width: 100%;
  padding: 10px;
  border-radius: 5px;
  border: none;
}

button {
  background: #22c55e;
  color: black;
  font-weight: bold;
  cursor: pointer;
}

#result {
  margin-top: 20px;
  font-size: 18px;
}
function hesapla() {
  const cpu = Number(document.getElementById("cpu").value);
  const camera = Number(document.getElementById("camera").value);
  const battery = Number(document.getElementById("battery").value);
  const screen = Number(document.getElementById("screen").value);

  const toplam = cpu + camera + battery + screen;

  let seviye = "";
  if (toplam > 750) seviye = "🔥 ULTRA AMİRAL GEMİSİ";
  else if (toplam > 600) seviye = "⚡ AMİRAL GEMİSİ";
  else seviye = "📱 ORTA SEVİYE";

  document.getElementById("result").innerHTML = `
    <p><strong>Telefon Seviyesi:</strong> ${seviye}</p>
    <p><strong>Tahmini Parça Maliyeti:</strong> $${toplam}</p>
  `;
}
