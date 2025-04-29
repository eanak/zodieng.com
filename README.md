# zodieng.com<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ZODIENG.ID - Wisata Alam Dieng</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    body { font-family: 'Poppins', sans-serif; margin: 0; padding: 0; }
    header { background: url('hero-dieng.jpg') center/cover no-repeat; color: white; padding: 100px 20px; text-align: center; }
    nav { background: #4CAF50; padding: 10px; text-align: center; }
    nav a { color: white; margin: 0 15px; text-decoration: none; font-weight: 600; }
    section { padding: 60px 20px; }
    .paket, .galeri, .testimoni, .blog { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 20px; }
    .paket-item, .galeri-item, .testimoni-item, .blog-item { background: #f9f9f9; padding: 20px; border-radius: 10px; opacity: 0; transform: translateY(20px); transition: all 0.6s ease; }
    .show { opacity: 1; transform: translateY(0); }
    footer { background: #333; color: white; text-align: center; padding: 20px; }
    .btn { background: #FFD700; padding: 10px 20px; color: black; text-decoration: none; border-radius: 5px; font-weight: 600; }
    form { display: flex; flex-direction: column; gap: 10px; max-width: 500px; margin: auto; }
    input, textarea, select { padding: 10px; border-radius: 5px; border: 1px solid #ccc; }
    button { background: #4CAF50; color: white; padding: 10px; border: none; border-radius: 5px; cursor: pointer; }

    @media (max-width: 600px) {
      header { padding: 60px 10px; font-size: 90%; }
      nav a { display: inline-block; margin: 10px 5px; font-size: 90%; }
    }
  </style>
</head>
<body>

<header>
  <h1>Selamat Datang di ZODIENG.ID</h1>
  <p>Eksplorasi Keindahan Alam Dieng Bersama Kami</p>
  <a href="#paket" class="btn">Lihat Paket</a>
</header>

<nav>
  <a href="#paket">Paket</a>
  <a href="#galeri">Galeri</a>
  <a href="#testimoni">Testimoni</a>
  <a href="#blog">Blog</a>
  <a href="#kontak">Kontak</a>
</nav>

<section id="paket">
  <h2>Paket Wisata</h2>
  <div class="paket">
    <div class="paket-item">
      <h3>Paket Dieng Sunrise</h3>
      <p>Menikmati sunrise dari Bukit Sikunir, lengkap dengan tour Dieng.</p>
      <p><strong>Rp 350.000</strong></p>
      <a href="#kontak" class="btn">Pesan</a>
    </div>
    <div class="paket-item">
      <h3>Paket Jelajah Alam Dieng</h3>
      <p>Kunjungi kawah, telaga, dan candi-candi kuno dalam satu paket.</p>
      <p><strong>Rp 450.000</strong></p>
      <a href="#kontak" class="btn">Pesan</a>
    </div>
  </div>
</section>

<section id="galeri">
  <h2>Galeri</h2>
  <div class="galeri">
    <div class="galeri-item"><img src="foto1.jpg" alt="Dieng" style="width:100%; border-radius:10px;"></div>
    <div class="galeri-item"><img src="foto2.jpg" alt="Dieng" style="width:100%; border-radius:10px;"></div>
  </div>
</section>

<section id="testimoni">
  <h2>Testimoni</h2>
  <div class="testimoni">
    <div class="testimoni-item">
      <p>"Pelayanan ramah, pengalaman tak terlupakan di Dieng!"</p>
      <strong>- Andi, Jakarta</strong>
    </div>
  </div>
</section>

<section id="blog">
  <h2>Blog</h2>
  <div class="blog">
    <div class="blog-item">
      <h4>5 Tips Menikmati Liburan ke Dieng</h4>
      <p>Persiapkan liburan kamu dengan tips-tips ini...</p>
      <a href="#" class="btn">Baca Selengkapnya</a>
    </div>
  </div>
</section>

<section id="kontak">
  <h2>Kontak Kami</h2>
  <form onsubmit="kirimPesan(event)">
    <input type="text" id="nama" placeholder="Nama" required>
    <input type="tel" id="hp" placeholder="Nomor HP" required>
    <select id="paket">
      <option value="Paket Dieng Sunrise">Paket Dieng Sunrise</option>
      <option value="Paket Jelajah Alam Dieng">Paket Jelajah Alam Dieng</option>
    </select>
    <textarea id="catatan" placeholder="Catatan Tambahan"></textarea>
    <button type="submit">Kirim ke WhatsApp</button>
  </form>
</section>

<footer>
  <p>&copy; 2025 ZODIENG.ID | Wisata Alam Dieng</p>
</footer>

<script>
  // Efek animasi saat scroll
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('show');
      }
    });
  });
  document.querySelectorAll('.paket-item, .galeri-item, .testimoni-item, .blog-item').forEach(el => observer.observe(el));

  // Kirim ke WhatsApp
  function kirimPesan(event) {
    event.preventDefault();
    const nama = document.getElementById('nama').value;
    const hp = document.getElementById('hp').value;
    const paket = document.getElementById('paket').value;
    const catatan = document.getElementById('catatan').value;
    const noWA = '6289518481518';

    const pesan = `Halo ZODIENG.ID, saya mau pesan paket wisata:%0A- Nama: ${nama}%0A- Nomor HP: ${hp}%0A- Paket: ${paket}%0A- Catatan: ${catatan}`;
    const url = `https://api.whatsapp.com/send?phone=${noWA}&text=${pesan}`;
    window.open(url, '_blank');
  }
</script>

</body>
</html>
