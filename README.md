
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>YKS Net ve Puan Hesaplama | TYT AYT 2026</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background:#f4f6f9;
}

/* BANNER */
.banner{
  max-width:1200px;
  margin:auto;
  padding:20px;
}
.banner img{
  width:100%;
  height:auto;
  border-radius:12px;
  display:block;
}

/* 3 KUTU */
.features{
  max-width:1200px;
  margin:40px auto;
  padding:0 15px;
}
.feature-grid{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:20px;
}
.feature-box{
  background:#fff;
  border-radius:20px;
  box-shadow:0 10px 25px rgba(0,0,0,.1);
  text-align:center;
  padding:30px;
  transition:.3s;
}
.feature-box:hover{
  transform:translateY(-6px);
}
.feature-box span{
  font-size:44px;
  display:block;
  margin-bottom:10px;
}
.feature-box h3{
  margin:0;
  font-size:18px;
}

/* MOBİL KARE DÜZELTME */
@media(max-width:640px){
  .feature-grid{
    grid-template-columns:repeat(3,1fr);
  }
  .feature-box{
    aspect-ratio:1/1;
    padding:10px;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
  }
  .feature-box h3{
    font-size:14px;
    line-height:1.2;
  }
}

/* HESAPLAMA */
.calc{
  max-width:900px;
  margin:40px auto;
  background:#fff;
  padding:25px;
  border-radius:15px;
  box-shadow:0 10px 25px rgba(0,0,0,.08);
}
.calc h2{
  text-align:center;
  margin-bottom:20px;
}
.inputs{
  display:grid;
  grid-template-columns:repeat(3,1fr);
  gap:15px;
}
.inputs input{
  padding:10px;
  font-size:16px;
}
button{
  margin-top:20px;
  width:100%;
  padding:12px;
  font-size:18px;
  border:none;
  border-radius:10px;
  background:#ff7a18;
  color:#fff;
  cursor:pointer;
}
.result{
  margin-top:20px;
  font-size:18px;
}
</style>
</head>

<body>

<!-- BANNER -->
<div class="banner">
  <!-- kendi banner görsel yolun -->
  <img src="banner.png" alt="YKS Net ve Puan Hesapla">
</div>

<!-- 3 KUTU -->
<div class="features">
  <div class="feature-grid">
    <div class="feature-box">
      <span>✍️</span>
      <h3>Kolay Net Girişi</h3>
    </div>
    <div class="feature-box">
      <span>⚡</span>
      <h3>Hızlı Puan Hesaplama</h3>
    </div>
    <div class="feature-box">
      <span>📱</span>
      <h3>Mobil Uyumlu</h3>
    </div>
  </div>
</div>

<!-- HESAPLAMA -->
<div class="calc">
<h2>YKS Net & Puan Hesaplama</h2>

<div class="inputs">
  <input type="number" id="tyt" placeholder="TYT Net (0-120)">
  <input type="number" id="ayt" placeholder="AYT Net (0-80)">
  <input type="number" id="dip" placeholder="Diploma Notu (0-100)">
</div>

<button onclick="hesapla()">Hesapla</button>

<div class="result" id="sonuc"></div>
</div>

<script>
function hesapla(){
  let tyt = Number(document.getElementById("tyt").value);
  let ayt = Number(document.getElementById("ayt").value);
  let dip = Number(document.getElementById("dip").value);

  if(tyt<0||tyt>120||ayt<0||ayt>80||dip<0||dip>100){
    document.getElementById("sonuc").innerHTML =
    "❌ Lütfen geçerli aralıkta değer gir.";
    return;
  }

  let tytP = tyt * 3.4;
  let aytP = ayt * 3.7;
  let obp = dip * 0.6;

  let toplam = Math.round(tytP + aytP + obp);

  document.getElementById("sonuc").innerHTML =
  `TYT Puan: ${tytP.toFixed(1)}<br>
   AYT Puan: ${aytP.toFixed(1)}<br>
   OBP: ${obp.toFixed(1)}<br><br>
   <b>Toplam Puan: ${toplam}</b>`;
}
</script>

</body>
</html>
