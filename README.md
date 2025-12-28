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
<body class="bg-gray-100 p-4 sm:p-6">

<div class="max-w-full sm:max-w-2xl mx-auto bg-white p-4 sm:p-6 rounded-xl shadow">

  <h1 class="text-2xl font-bold text-center mb-6">YKS Net & Puan Hesaplama</h1>
  <img src="images/banner.jpg" alt="YKS Net ve Puan Hesaplama" class="w-full h-auto max-h-80 sm:max-h-96 rounded-xl mb-6 object-cover">

  <!-- Hızlı Özellikler -->
  <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 mt-4 mb-6 text-center">
    <div class="p-4 bg-yellow-100 rounded-xl shadow-lg transform transition hover:scale-105">
      <div class="text-4xl mb-2 animate-bounce">📝</div>
      <h4 class="font-semibold">Kolay Net Girişi</h4>
      <p class="text-sm mt-1">Doğru ve yanlışlarını hızlıca gir, netini öğren.</p>
    </div>

    <div class="p-4 bg-green-100 rounded-xl shadow-lg transform transition hover:scale-105">
      <div class="text-4xl mb-2 animate-bounce">📊</div>
      <h4 class="font-semibold">Hızlı Puan Hesaplama</h4>
      <p class="text-sm mt-1">TYT ve AYT tahmini puanını anında gör.</p>
    </div>

    <div class="p-4 bg-blue-100 rounded-xl shadow-lg transform transition hover:scale-105">
      <div class="text-4xl mb-2 animate-bounce">📱</div>
      <h4 class="font-semibold">Mobil Uyumlu</h4>
      <p class="text-sm mt-1">Telefon ve bilgisayarda sorunsuz kullanım.</p>
    </div>
  </div>

  <!-- TYT Tablosu -->
  <h2 class="text-xl font-semibold mb-2">TYT</h2>
  <div class="overflow-x-auto mb-4">
    <table class="w-full border border-gray-300 rounded-lg">
      <thead class="bg-gray-100">
        <tr>
          <th class="p-2 border">Ders</th>
          <th class="p-2 border">Doğru</th>
          <th class="p-2 border">Yanlış</th>
        </tr>
      </thead>
      <tbody>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Türkçe</td>
          <td class="p-2 border"><input id="t_dogru" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="t_yanlis" type="number" class="w-full border p-1 rounded"></td>
        </tr>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Matematik</td>
          <td class="p-2 border"><input id="m_dogru" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="m_yanlis" type="number" class="w-full border p-1 rounded"></td>
        </tr>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Sosyal</td>
          <td class="p-2 border"><input id="s_dogru" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="s_yanlis" type="number" class="w-full border p-1 rounded"></td>
        </tr>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Fen</td>
          <td class="p-2 border"><input id="f_dogru" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="f_yanlis" type="number" class="w-full border p-1 rounded"></td>
        </tr>
      </tbody>
    </table>
  </div>

  <!-- AYT Tablosu -->
  <h2 class="text-xl font-semibold mb-2">AYT</h2>
  <div class="overflow-x-auto mb-4">
    <table class="w-full border border-gray-300 rounded-lg">
      <thead class="bg-gray-100">
        <tr>
          <th class="p-2 border">Ders</th>
          <th class="p-2 border">Doğru</th>
          <th class="p-2 border">Yanlış</th>
        </tr>
      </thead>
      <tbody>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Matematik</td>
          <td class="p-2 border"><input id="ayt_m_d" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="ayt_m_y" type="number" class="w-full border p-1 rounded"></td>
        </tr>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Edebiyat</td>
          <td class="p-2 border"><input id="ayt_e_d" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="ayt_e_y" type="number" class="w-full border p-1 rounded"></td>
        </tr>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Sosyal</td>
          <td class="p-2 border"><input id="ayt_s_d" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="ayt_s_y" type="number" class="w-full border p-1 rounded"></td>
        </tr>
        <tr class="hover:bg-gray-50">
          <td class="p-2 border">Fen</td>
          <td class="p-2 border"><input id="ayt_f_d" type="number" class="w-full border p-1 rounded"></td>
          <td class="p-2 border"><input id="ayt_f_y" type="number" class="w-full border p-1 rounded"></td>
        </tr>
      </tbody>
    </table>
  </div>

  <label class="block mt-4 mb-3">Diploma Notu:
    <input id="diploma" type="number" class="border p-2 w-full rounded">
  </label>

  <button onclick="hesapla()" class="w-full bg-blue-600 text-white p-2 rounded hover:bg-blue-700 transition">
    Hesapla
  </button>

  <div id="sonuc" class="mt-4 font-semibold text-center"></div>
  <canvas id="grafik" class="mt-6"></canvas>

  <!-- Net & Puan Kartları -->
  <div class="grid grid-cols-1 sm:grid-cols-2 gap-4 mt-6">
    <div class="bg-blue-100 p-4 rounded-xl shadow-lg transform transition hover:scale-105">
      <h3 class="text-lg font-semibold text-center">TYT</h3>
      <p class="text-center mt-2">Net: <span id="kartTytNet">0</span></p>
      <p class="text-center">Puan: <span id="kartTytPuan">0</span></p>
    </div>

    <div class="bg-green-100 p-4 rounded-xl shadow-lg transform transition hover:scale-105">
      <h3 class="text-lg font-semibold text-center">AYT</h3>
      <p class="text-center mt-2">Net: <span id="kartAytNet">0</span></p>
      <p class="text-center">Puan: <span id="kartAytPuan">0</span></p>
    </div>
  </div>

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

  // Kartları güncelle
  document.getElementById("kartTytNet").textContent = tytNet.toFixed(2);
  document.getElementById("kartTytPuan").textContent = tytPuan.toFixed(2);
  document.getElementById("kartAytNet").textContent = aytNet.toFixed(2);
  document.getElementById("kartAytPuan").textContent = aytPuan.toFixed(2);
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
