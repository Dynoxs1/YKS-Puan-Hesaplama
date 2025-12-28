<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  
  <title>YKS Net ve Puan Hesaplama | TYT AYT Puan Hesaplama 2026</title>
  <meta name="description" content="YKS 2026 TYT ve AYT net hesaplama aracı. Doğru yanlış girerek netini ve tahmini puanını hemen öğren. Ücretsiz YKS puan hesaplama sitesi.">
  <meta name="keywords" content="YKS puan hesaplama, TYT net hesaplama, AYT net hesaplama, YKS 2026">

  <script src="https://cdn.tailwindcss.com"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
</head>
<body class="bg-gray-100 p-2 sm:p-6">

<div class="max-w-full sm:max-w-2xl mx-auto bg-white p-2 sm:p-6 rounded-xl shadow">

  <h1 class="text-2xl font-bold text-center mb-6">YKS Net & Puan Hesaplama</h1>

  <img src="images/banner.jpg" 
       alt="YKS Net ve Puan Hesaplama" 
       class="w-full h-auto max-h-80 sm:max-h-96 md:max-h-[400px] rounded-xl mb-6 object-cover">

  <!-- TYT -->
  <h2 class="text-xl font-semibold mb-2">TYT</h2>

  <div class="flex flex-wrap items-center gap-2 mb-2">
    <span class="w-1/3 font-semibold">Türkçe</span>
    <input id="t_dogru" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="t_yanlis" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <div class="flex flex-wrap items-center gap-2 mb-2">
    <span class="w-1/3 font-semibold">Matematik</span>
    <input id="m_dogru" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="m_yanlis" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <div class="flex flex-wrap items-center gap-2 mb-2">
    <span class="w-1/3 font-semibold">Sosyal</span>
    <input id="s_dogru" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="s_yanlis" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <div class="flex flex-wrap items-center gap-2 mb-4">
    <span class="w-1/3 font-semibold">Fen</span>
    <input id="f_dogru" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="f_yanlis" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <!-- AYT -->
  <h2 class="text-xl font-semibold mb-2">AYT</h2>

  <div class="flex flex-wrap items-center gap-2 mb-2">
    <span class="w-1/3 font-semibold">Matematik</span>
    <input id="ayt_m_d" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="ayt_m_y" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <div class="flex flex-wrap items-center gap-2 mb-2">
    <span class="w-1/3 font-semibold">Edebiyat</span>
    <input id="ayt_e_d" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="ayt_e_y" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <div class="flex flex-wrap items-center gap-2 mb-2">
    <span class="w-1/3 font-semibold">Sosyal</span>
    <input id="ayt_s_d" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="ayt_s_y" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <div class="flex flex-wrap items-center gap-2 mb-4">
    <span class="w-1/3 font-semibold">Fen</span>
    <input id="ayt_f_d" type="number" placeholder="Doğru" class="w-1/3 border p-1">
    <input id="ayt_f_y" type="number" placeholder="Yanlış" class="w-1/3 border p-1">
  </div>

  <label class="block mb-3">Diploma Notu:
    <input id="diploma" type="number" class="border p-1 w-full">
  </label>

  <button onclick="hesapla()" class="w-full bg-blue-600 text-white p-2 rounded">Hesapla</button>

  <div id="sonuc" class="mt-4 font-semibold text-center"></div>
  <canvas id="grafik" class="mt-6"></canvas>

</div>

<script>
function net(d, y) { return d - (y / 4); }

function hesapla() {
  const tytNet = net(t_dogru.value, t_yanlis.value) +
                 net(m_dogru.value, m_yanlis.value) +
                 net(s_dogru.value, s_yanlis.value) +
                 net(f_dogru.value, f_yanlis.value);

  const aytNet = net(ayt_m_d.value, ayt_m_y.value) +
                 net(ayt_e_d.value, ayt_e_y.value) +
                 net(ayt_s_d.value, ayt_s_y.value) +
                 net(ayt_f_d.value, ayt_f_y.value);

  const diploma = Number(document.getElementById("diploma").value) || 0;

  const tytPuan = 100 + tytNet * 4 + diploma * 0.12;
  const aytPuan = 100 + aytNet * 5 + diploma * 0.12;

  document.getElementById("sonuc").innerHTML = `
    TYT Net: ${tytNet.toFixed(2)} <br>
    AYT Net: ${aytNet.toFixed(2)} <br><br>
    TYT Puan: ${tytPuan.toFixed(2)} <br>
    AYT Puan: ${aytPuan.toFixed(2)}
  `;

  const ctx = document.getElementById("grafik");
  if (window.chart) window.chart.destroy();
  window.chart = new Chart(ctx, {
    type: "bar",
    data: {
      labels: ["TYT", "AYT"],
      datasets: [{ label: "Puan", data: [tytPuan, aytPuan] }]
    }
  });
}
</script>

<hr>
<footer class="text-center mt-6 mb-6">
  <a href="hakkimizda.html">Hakkımızda</a> |
  <a href="gizlilik.html">Gizlilik Politikası</a> |
  <a href="iletisim.html">İletişim</a>
</footer>

</body>
</html>
