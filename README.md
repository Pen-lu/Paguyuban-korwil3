# Paguyuban-korwil3
Semua bisa di lihat di sini
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Website Paguyuban Korwil</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: url("foto.jpg.jpg") no-repeat center center fixed;
      background-size: cover;
      color: white;
      text-align: center;
    }
    header {
      background: rgba(0,0,0,0.6);
      padding: 15px;
      font-size: 22px;
      font-weight: bold;
    }
    nav {
      background: rgba(0,0,0,0.7);
      padding: 10px;
    }
    nav a {
      color: white;
      margin: 0 10px;
      text-decoration: none;
      font-weight: bold;
    }
    section {
      background: rgba(0,0,0,0.5);
      margin: 20px auto;
      padding: 20px;
      max-width: 800px;
      border-radius: 10px;
    }
    .hidden { display: none; }
    button {
      background: #4CAF50;
      border: none;
      padding: 8px 15px;
      color: white;
      cursor: pointer;
      border-radius: 5px;
    }
    input, textarea {
      width: 90%;
      padding: 8px;
      margin: 5px;
      border-radius: 5px;
      border: none;
    }
  </style>
</head>
<body>
  <header>🌐 Paguyuban Korwil Resmi</header>
  <nav>
    <a href="#jadwal">Jadwal</a>
    <a href="#galeri">Galeri</a>
    <a href="#pengumuman">Pengumuman</a>
    <a href="#login">Admin</a>
  </nav>

  <section id="jadwal">
    <h2>📅 Jadwal Rutin</h2>
    <div id="jadwalContent">Arisan Bulanan: Minggu pertama<br>Rapat Korwil: Minggu ketiga</div>
  </section>

  <section id="galeri">
    <h2>🖼️ Galeri Kegiatan</h2>
    <div id="galeriContent">Belum ada foto</div>
  </section>

  <section id="pengumuman">
    <h2>📢 Pengumuman</h2>
    <div id="pengumumanContent">Belum ada pengumuman</div>
  </section>

  <!-- Admin Login -->
  <section id="login">
    <h2>🔑 Login Admin</h2>
    <input type="password" id="password" placeholder="Masukkan Password">
    <button onclick="login()">Login</button>
  </section>

  <!-- Admin Panel -->
  <section id="adminPanel" class="hidden">
    <h2>⚙️ Panel Admin</h2>
    <h3>Ubah Jadwal</h3>
    <textarea id="jadwalInput"></textarea><br>
    <button onclick="updateJadwal()">Simpan</button>

    <h3>Tambah Pengumuman</h3>
    <textarea id="pengumumanInput"></textarea><br>
    <button onclick="updatePengumuman()">Simpan</button>

    <h3>Tambah Foto Galeri (Link)</h3>
    <input type="text" id="fotoInput" placeholder="URL foto"><br>
    <button onclick="updateGaleri()">Tambah</button>
  </section>

  <script>
    const adminPass = "korwil123"; // ganti password sesuai keinginan
    function login() {
      let pass = document.getElementById("password").value;
      if(pass === adminPass){
        document.getElementById("adminPanel").classList.remove("hidden");
        alert("Login berhasil!");
      } else {
        alert("Password salah!");
      }
    }
    function updateJadwal(){
      let val = document.getElementById("jadwalInput").value;
      document.getElementById("jadwalContent").innerHTML = val;
    }
    function updatePengumuman(){
      let val = document.getElementById("pengumumanInput").value;
      document.getElementById("pengumumanContent").innerHTML = val;
    }
    function updateGaleri(){
      let val = document.getElementById("fotoInput").value;
      let galeri = document.getElementById("galeriContent");
      galeri.innerHTML += `<br><img src="${val}" width="200" style="margin:5px;border-radius:10px;">`;
    }
  </script>
</body>
</html>
