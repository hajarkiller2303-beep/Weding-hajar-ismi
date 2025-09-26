<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Undangan Pernikahan Editable</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      padding: 0;
      background: linear-gradient(to right, #fdf1f1, #fff);
      color: #333;
    }
    header, .section, footer {
      text-align: center;
      padding: 20px;
    }
    header {
      background: url('https://i.ibb.co/3sW7j9D/wedding-bg.jpg') center/cover no-repeat;
      color: white;
      text-shadow: 1px 1px 4px black;
    }
    header h1 { font-size: 2em; margin: 0; }
    .countdown { font-size: 1.5em; color: #b30059; margin-top: 10px; }
    .map iframe { border-radius: 10px; }
    .btn {
      display: inline-block;
      margin-top: 10px;
      padding: 10px 20px;
      background: #b30059;
      color: white;
      border-radius: 8px;
      text-decoration: none;
    }
    .gallery img {
      width: 150px;
      margin: 8px;
      border-radius: 10px;
      box-shadow: 2px 2px 10px rgba(0,0,0,0.2);
    }
    footer {
      background: #b30059;
      color: white;
      margin-top: 20px;
    }
    .editor {
      background: #fff0f5;
      padding: 15px;
      border-bottom: 2px solid #b30059;
    }
    .editor input, .editor textarea {
      display: block;
      width: 90%;
      margin: 5px auto;
      padding: 8px;
      border-radius: 6px;
      border: 1px solid #ccc;
    }
  </style>
</head>
<body>

  <!-- Panel Edit -->
  <div class="editor">
    <h3>🔧 Edit Undangan</h3>
    <input type="text" id="nama" placeholder="Nama Pasangan (contoh: Aisyah & Fikri)">
    <input type="date" id="tanggal">
    <textarea id="doa" placeholder="Tulis doa / harapan"></textarea>
    <input type="text" id="lokasi" placeholder="Lokasi Acara">
    <input type="text" id="maps" placeholder="Link Google Maps">
    <input type="file" id="foto1" accept="image/*">
    <input type="file" id="foto2" accept="image/*">
    <input type="file" id="foto3" accept="image/*">
    <button onclick="updateUndangan()" class="btn">Simpan Perubahan</button>
  </div>

  <!-- Undangan -->
  <header>
    <h1>Undangan Pernikahan</h1>
    <p id="namapasangan"><b>Aisyah & Fikri</b></p>
    <p id="tanggalacara">Sabtu, 25 Oktober 2025</p>
  </header>

  <section class="section">
    <h2>Hitung Mundur Acara</h2>
    <div id="countdown" class="countdown"></div>
  </section>

  <section class="section">
    <h2>Galeri Foto</h2>
    <div class="gallery">
      <img id="img1" src="https://i.ibb.co/4PVtGhz/wedding1.jpg">
      <img id="img2" src="https://i.ibb.co/4fDqDgx/wedding2.jpg">
      <img id="img3" src="https://i.ibb.co/GpM8N0R/wedding3.jpg">
    </div>
  </section>

  <section class="section">
    <h2>Lokasi Acara</h2>
    <p id="lokasiText">Gedung Serbaguna Harmoni, Jakarta</p>
    <div class="map">
      <iframe id="mapsFrame" src="https://www.google.com/maps/embed?pb=!1m18!..." width="300" height="200" allowfullscreen="" loading="lazy"></iframe>
    </div>
    <a id="mapsLink" class="btn" href="https://maps.app.goo.gl/" target="_blank">Buka di Google Maps</a>
  </section>

  <section class="section">
    <h2>Doa & Harapan</h2>
    <p id="doaText">“Semoga Allah memberkahi kalian berdua dan mengumpulkan kalian dalam kebaikan.”</p>
  </section>

  <footer>
    <p>❤️ Dengan penuh cinta, kami tunggu kehadiranmu ❤️</p>
  </footer>

  <!-- Musik -->
  <audio autoplay loop>
    <source src="https://www.bensound.com/bensound-music/bensound-romantic.mp3" type="audio/mp3">
  </audio>

  <script>
    // Countdown
    var countDownDate = new Date("Oct 25, 2025 10:00:00").getTime();
    var x = setInterval(function() {
      var now = new Date().getTime();
      var distance = countDownDate - now;
      var days = Math.floor(distance / (1000 * 60 * 60 * 24));
      var hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      var seconds = Math.floor((distance % (1000 * 60)) / 1000);
      document.getElementById("countdown").innerHTML = days + " Hari " + hours + " Jam " + minutes + " Menit " + seconds + " Detik ";
    }, 1000);

    // Fungsi Update
    function updateUndangan() {
      let nama = document.getElementById("nama").value;
      let tanggal = document.getElementById("tanggal").value;
      let doa = document.getElementById("doa").value;
      let lokasi = document.getElementById("lokasi").value;
      let maps = document.getElementById("maps").value;

      if (nama) document.getElementById("namapasangan").innerHTML = "<b>" + nama + "</b>";
      if (tanggal) document.getElementById("tanggalacara").innerText = new Date(tanggal).toLocaleDateString("id-ID", { weekday:'long', year:'numeric', month:'long', day:'numeric' });
      if (doa) document.getElementById("doaText").innerText = doa;
      if (lokasi) document.getElementById("lokasiText").innerText = lokasi;
      if (maps) {
        document.getElementById("mapsFrame").src = maps;
        document.getElementById("mapsLink").href = maps;
      }

      // Update foto
      let foto1 = document.getElementById("foto1").files[0];
      let foto2 = document.getElementById("foto2").files[0];
      let foto3 = document.getElementById("foto3").files[0];
      if (foto1) document.getElementById("img1").src = URL.createObjectURL(foto1);
      if (foto2) document.getElementById("img2").src = URL.createObjectURL(foto2);
      if (foto3) document.getElementById("img3").src = URL.createObjectURL(foto3);
    }
  </script>

</body>
</html>
