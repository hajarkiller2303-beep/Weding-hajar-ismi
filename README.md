<!DOCTYPE html><html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Undangan Pernikahan | Hajar & Nurul</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(135deg, #000, #fff);
      color: #fff;
      text-align: center;
    }
    .overlay {
      background: rgba(0,0,0,0.6);
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
    }
    header {
      position: relative;
      height: 100vh;
      background: url('https://i.ibb.co/dPK6bg4/IMG-20250922-WA0000.jpg') center/cover no-repeat;
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
    }
    header h1 {
      font-size: 2.5rem;
      z-index: 2;
    }
    .content {
      padding: 2rem;
      background: rgba(0,0,0,0.7);
    }
    .countdown {
      font-size: 1.5rem;
      margin: 1rem 0;
    }
    .map-btn {
      display: inline-block;
      padding: 10px 20px;
      margin: 1rem;
      border-radius: 30px;
      background: #fff;
      color: #000;
      text-decoration: none;
      font-weight: bold;
    }
    footer {
      padding: 2rem;
      background: #000;
      font-size: 0.9rem;
    }
  </style>
</head>
<body>
  <header>
    <div class="overlay"></div>
    <h1>Undangan Pernikahan<br/>Hajar & Nurul</h1>
  </header>
  <div class="content">
    <h2>بِسْمِ اللَّهِ الرَّحْمَنِ الرَّحِيم</h2>
    <p>Maha Suci Allah yang telah menciptakan makhluk-Nya berpasang-pasangan. Dengan rahmat dan ridho-Nya, kami bermaksud menyelenggarakan pernikahan kami.</p><h3>Pasangan</h3>
<p><strong>Hajar Aswad 🤍 Nurul Ismi</strong></p>

<h3>Waktu & Tempat</h3>
<p>🗓 Sabtu, 08 November 2025<br/>⏰ 09.00 - selesai<br/>📍 Barraba, Desa Bialo, Kab. Bulukumba</p>

<div class="countdown" id="countdown"></div>

<a class="map-btn" href="https://maps.google.com/?q=Barraba+Desa+Bialo+Kab+Bulukumba" target="_blank">Lihat Lokasi</a>

<h3>Doa</h3>
<p>"Semoga Allah SWT menjadikan pernikahan ini sebagai pernikahan yang penuh berkah, sakinah, mawaddah, warahmah."</p>

  </div>  <footer>
    <p>Dengan hormat, kami mengundang Bapak/Ibu/Saudara/i untuk hadir dan memberikan doa restu 🙏</p>
    <p>Hajar & Nurul</p>
  </footer>  <script>
    // Countdown
    const countdown = document.getElementById("countdown");
    const weddingDate = new Date("Nov 8, 2025 09:00:00").getTime();
    const timer = setInterval(() => {
      const now = new Date().getTime();
      const distance = weddingDate - now;

      const days = Math.floor(distance / (1000 * 60 * 60 * 24));
      const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      const seconds = Math.floor((distance % (1000 * 60)) / 1000);

      countdown.innerHTML = `⏳ ${days} Hari ${hours} Jam ${minutes} Menit ${seconds} Detik`;

      if (distance < 0) {
        clearInterval(timer);
        countdown.innerHTML = "Acara telah berlangsung";
      }
    }, 1000);
  </script></body>
</html>
