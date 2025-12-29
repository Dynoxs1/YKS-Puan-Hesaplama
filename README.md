
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>YKS Net ve Puan Hesaplama | TYT AYT 2026</title>
  <meta name="description" content="YKS 2026 TYT ve AYT net ve puan hesaplama aracı. Ücretsiz, mobil uyumlu ve hızlı.">
  <meta name="keywords" content="YKS puan hesaplama, TYT net hesaplama, AYT net hesaplama">

  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
</head>

<body class="bg-gray-100 p-4">

<div class="max-w-3xl mx-auto bg-white p-6 rounded-2xl shadow">

  <!-- BAŞLIK -->
  <h1 class="text-2xl md:text-3xl font-bold text-center mb-4">
    YKS Net & Puan Hesaplama
  </h1>

  <!-- BANNER -->
  <img src="images/banner.jpg"
       alt="YKS Net ve Puan Hesaplama"
       class="w-full rounded-xl mb-6">

  <!-- TYT TABLO -->
  <h2 class="text-xl font-semibold mb-2">TYT</h2>
  <div class="grid grid-cols-3 gap-2 text-sm md:text-base mb-6">
    <span class="font-semibold">Ders</span>
    <span class="font-semibold">Doğru</span>
    <span class="font-semibold">Yanlış</span>

    <span>Türkçe</span>
    <input id="t_d" type="number" min="0" max="40" class="border p-2 rounded">
    <input id="t_y" type="number" min="0" max="40" class="border p-2 rounded">

    <span>Matematik</span>
    <input id="m_d" type="number" min="0" max="40" class="border p-2 rounded">
    <input id="m_y" type="number" min="0" max="40" class="border p-2 rounded">

    <span>Sosyal</span>
    <input id="s_d" type="number" min="0" max="20" class="border p-2 rounded">
    <input id="s_y" type="number" min="0" max="20" class="border p-2 rounded">

    <span>Fen</span>
    <input id="f_d" type="number" min="0" max="20" class="border p-2 rounded">
    <input id="f_y" type="number" min="0" max="20" class="border p-2 rounded">
  </div>

  <!-- AYT TABLO -->
  <h2 class="text-xl font-semibold mb-2">AYT</h2>
  <div class="grid grid-cols-3 gap-2 text-sm md:text-base mb-6">
    <span>Matematik</span>
    <input id="ayt_m_d" type="number" min="0" max="40" class="border p-2 rounded">
    <input id="ayt_m_y" type="number" min="0" max="40" class="border p-2 rounded">

    <span>Edebiyat</span>
    <input id="ayt_e_d" type="number" min="0" max="24" class="border p-2 rounded">
    <input id="ayt_e_y" type="number" min="0" max="24" class="border p-2 rounded">

    <span>Sosyal</span>
    <input id="ayt_s_d" type="number" min="0" max="16" class="border p-2 rounded">
    <input id="ayt_s_y" type="number" min="0" max="16" class="border p-2 rounded">

    <span>Fen</span>
    <input id="ayt_f_d" type="number" min="0" max="24" class="border p-2 rounded">
    <input id="ayt_f_y" type="number" min="0" max="24" class="border p-2 rounded">
  </div>

  <!-- DİPLOMA -->
  <label class="block mb-4 font-semibold">
    Diploma Notu (30 - 100)
    <input id="diploma" type="number" min="30" max="100"
           class="border p-2 rounded w-full mt-1">
  </label>

  <!-- HATA -->
  <p id="hata" class="text-red-600 font-semibold text-center mb-4 hidden"></p>

  <!-- BUTON -->
  <button onclick="hesapla()"
          class="w-full bg-blue-600 text-white py-3 rounded-xl font-semibold hover:bg-blue-700 transition">
    Hesapla
  </button>

  <!-- SONUÇ -->
  <div id="sonuc" class="mt-6 text-center font-semibold"></div>

  <canvas id="grafik" class="mt-6"></canvas>

</div>

<script>
function net(d, y) {
  return d - (y / 4);
}

function hesapla() {
  const hata = document.getElementById("hata");
  hata.classList.add("hidden");

  const diploma = Number(diploma.value);

  if (diploma < 30 || diploma > 100 || isNaN(diploma)) {
    hata.innerText = "❌ Diploma notu 30 - 100 arasında olmalı";
    hata.classList.remove("hidden");
    return;
  }

  const tytNet =
    net(t_d.value, t_y.value) +
    net(m_d.value, m_y.value) +
    net(s_d.value, s_y.value) +
    net(f_d.value, f_y.value);

  const aytNet =
    net(ayt_m_d.value, ayt_m_y.value) +
    net(ayt_e_d.value, ayt_e_y.value) +
    net(ayt_s_d.value, ayt_s_y.value) +
    net(ayt_f_d.value, ayt_f_y.value);

  const tytPuan = 100 + tytNet * 4 + diploma * 0.12;
  const aytPuan = 100 + aytNet * 5 + diploma * 0.12;

  sonuc.innerHTML = `
    TYT Net: ${tytNet.toFixed(2)} <br>
    AYT Net: ${aytNet.toFixed(2)} <br><br>
    TYT Puan: ${tytPuan.toFixed(2)} <br>
    AYT Puan: ${aytPuan.toFixed(2)}
  `;

  if (window.chart) window.chart.destroy();
  window.chart = new Chart(grafik, {
    type: "bar",
    data: {
      labels: ["TYT", "AYT"],
      datasets: [{
        label: "Puan",
        data: [tytPuan, aytPuan]
      }]
    }
  });
}
</script>

<footer class="text-center mt-6 text-sm text-gray-600">
  <a href="hakkimizda.html">Hakkımızda</a> |
  <a href="gizlilik.html">Gizlilik Politikası</a> |
  <a href="iletisim.html">İletişim</a>
</footer>

</body>
</html>
