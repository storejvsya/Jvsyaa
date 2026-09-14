<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Toko Online Pink - Pastel & Cute</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
  
  <style>
    :root {
      --primary-pink: #ff6584;
      --soft-pink: #ffeef2;
      --accent-pink: #ff8fa3;
      --dark-pink: #d84a68;
      --text-dark: #333333;
      --bg-cream: #fffafa;
      --white: #ffffff;
      --shadow: 0 4px 15px rgba(255, 101, 132, 0.15);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background-color: var(--bg-cream);
      color: var(--text-dark);
      line-height: 1.6;
    }

    /* Navbar */
    header {
      background: var(--white);
      box-shadow: var(--shadow);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    nav {
      max-width: 1200px;
      margin: 0 auto;
      padding: 1rem 2rem;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--primary-pink);
      text-decoration: none;
    }

    .cart-btn-nav {
      background: var(--soft-pink);
      color: var(--dark-pink);
      border: 2px solid var(--accent-pink);
      padding: 0.5rem 1.2rem;
      border-radius: 20px;
      cursor: pointer;
      font-weight: 600;
      display: flex;
      align-items: center;
      gap: 8px;
      transition: all 0.3s ease;
    }

    .cart-btn-nav:hover {
      background: var(--primary-pink);
      color: var(--white);
    }

    /* Hero Section */
    .hero {
      text-align: center;
      padding: 4rem 1.5rem;
      background: linear-gradient(180deg, #ffeef2 0%, #fffafa 100%);
    }

    .hero h1 {
      font-size: 2.5rem;
      color: var(--dark-pink);
      margin-bottom: 0.5rem;
    }

    .hero p {
      font-size: 1.1rem;
      color: #666;
      max-width: 600px;
      margin: 0 auto 1.5rem;
    }

    /* Product Grid */
    .container {
      max-width: 1200px;
      margin: 2rem auto;
      padding: 0 1.5rem;
    }

    .section-title {
      text-align: center;
      font-size: 2rem;
      color: var(--dark-pink);
      margin-bottom: 2rem;
    }

    .product-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
      gap: 2rem;
    }

    .card {
      background: var(--white);
      border-radius: 16px;
      overflow: hidden;
      box-shadow: var(--shadow);
      display: flex;
      flex-direction: column;
      transition: transform 0.3s ease;
      border: 1px solid #ffe1e8;
    }

    .card:hover {
      transform: translateY(-5px);
    }

    .card img {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }

    .card-body {
      padding: 1.2rem;
      display: flex;
      flex-direction: column;
      flex-grow: 1;
    }

    .card-title {
      font-size: 1.2rem;
      font-weight: 600;
      margin-bottom: 0.5rem;
      color: #444;
    }

    .card-desc {
      font-size: 0.85rem;
      color: #777;
      margin-bottom: 1rem;
      flex-grow: 1;
    }

    .card-price {
      font-size: 1.1rem;
      font-weight: 700;
      color: var(--primary-pink);
      margin-bottom: 1rem;
    }

    .btn-add {
      background: var(--primary-pink);
      color: var(--white);
      border: none;
      padding: 0.7rem;
      border-radius: 8px;
      cursor: pointer;
      font-weight: 600;
      transition: background 0.3s ease;
      width: 100%;
    }

    .btn-add:hover {
      background: var(--dark-pink);
    }

    /* Floating Cart Sidebar */
    .cart-drawer {
      position: fixed;
      top: 0;
      right: -100%;
      width: 100%;
      max-width: 380px;
      height: 100%;
      background: var(--white);
      box-shadow: -4px 0 15px rgba(0,0,0,0.1);
      z-index: 1000;
      display: flex;
      flex-direction: column;
      transition: right 0.3s ease;
    }

    .cart-drawer.open {
      right: 0;
    }

    .cart-header {
      padding: 1.2rem;
      background: var(--soft-pink);
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #ffd6e0;
    }

    .cart-header h3 {
      color: var(--dark-pink);
    }

    .btn-close {
      background: none;
      border: none;
      font-size: 1.5rem;
      cursor: pointer;
      color: var(--dark-pink);
    }

    .cart-items {
      flex-grow: 1;
      overflow-y: auto;
      padding: 1rem;
    }

    .cart-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0.8rem 0;
      border-bottom: 1px solid #f0f0f0;
    }

    .item-info h4 {
      font-size: 0.95rem;
      color: #333;
    }

    .item-info span {
      font-size: 0.85rem;
      color: var(--primary-pink);
      font-weight: 600;
    }

    .btn-remove {
      background: none;
      border: none;
      color: #ff4757;
      cursor: pointer;
      font-size: 0.85rem;
    }

    .cart-footer {
      padding: 1.2rem;
      border-top: 1px solid #eee;
      background: var(--bg-cream);
    }

    .total-price {
      display: flex;
      justify-content: space-between;
      font-weight: 700;
      margin-bottom: 1rem;
      font-size: 1.1rem;
    }

    .btn-checkout {
      display: block;
      width: 100%;
      background: #25d366;
      color: white;
      text-align: center;
      padding: 0.8rem;
      border-radius: 8px;
      text-decoration: none;
      font-weight: 600;
      cursor: pointer;
      border: none;
      transition: background 0.3s;
    }

    .btn-checkout:hover {
      background: #1ebc59;
    }

    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.4);
      display: none;
      z-index: 999;
    }

    .overlay.open {
      display: block;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 2rem;
      background: var(--soft-pink);
      color: #777;
      margin-top: 4rem;
      border-top: 1px solid #ffd6e0;
    }
  </style>
</head>
<body>

  <!-- Navbar -->
  <header>
    <nav>
      <a href="#" class="logo">🌸 PinkStore</a>
      <button class="cart-btn-nav" onclick="toggleCart()">
        🛒 Keranjang (<span id="cart-count">0</span>)
      </button>
    </nav>
  </header>

  <!-- Hero Section -->
  <section class="hero">
    <h1>Koleksi Spesial & Elegan</h1>
    <p>Temukan produk favoritmu dengan harga terbaik dan pelayanan ramah langsung lewat WhatsApp.</p>
  </section>

  <!-- Product Section -->
  <main class="container">
    <h2 class="section-title">Daftar Produk</h2>
    
    <div class="product-grid" id="product-container">
      <!-- Produk akan dimuat lewat JavaScript -->
    </div>
  </main>

  <!-- Sidebar Keranjang Belanja -->
  <div class="overlay" id="overlay" onclick="toggleCart()"></div>
  <div class="cart-drawer" id="cart-drawer">
    <div class="cart-header">
      <h3>Keranjang Kamu</h3>
      <button class="btn-close" onclick="toggleCart()">&times;</button>
    </div>
    
    <div class="cart-items" id="cart-items">
      <p style="text-align: center; color: #999; margin-top: 2rem;">Keranjang masih kosong.</p>
    </div>

    <div class="cart-footer">
      <div class="total-price">
        <span>Total:</span>
        <span id="cart-total">Rp 0</span>
      </div>
      <button class="btn-checkout" onclick="checkoutWA()">Pesan via WhatsApp</button>
    </div>
  </div>

  <!-- Footer -->
  <footer>
    <p>&copy; 2026 PinkStore. All Rights Reserved.</p>
  </footer>

  <script>
    // Ganti dengan nomor WhatsApp toko kamu (gunakan format 62xxx)
    const WA_NUMBER = "6281355087750";

    // Data Produk (Bisa ditambah/diubah sesuka hati)
    const products = [
      {
        id: 1,
        name: "Akun Premium Netflix 1 Bulan",
        desc: "Akses full UHD 4K, anti-on hold, garansi penuh.",
        price: 35000,
        image: "https://images.unsplash.com/photo-1574375927938-d5a98e8ffe85?w=500&auto=format&fit=crop"
      },
      {
        id: 2,
        name: "Spotify Individual 3 Bulan",
        desc: "Dengarkan musik tanpa iklan, kualitas audio tinggi.",
        price: 45000,
        image: "https://images.unsplash.com/photo-1614680376593-902f749f7ffc?w=500&auto=format&fit=crop"
      },
      {
        id: 3,
        name: "Canva Pro Garansi 1 Tahun",
        desc: "Buka semua template premium, font, dan elemen desain.",
        price: 25000,
        image: "https://images.unsplash.com/photo-1626785774573-4b799315345d?w=500&auto=format&fit=crop"
      },
      {
        id: 4,
        name: "YouTube Premium 1 Bulan",
        desc: "Bebas iklan, background play, dan YouTube Music.",
        price: 15000,
        image: "https://images.unsplash.com/photo-1611162617213-7d7a39e9b1d7?w=500&auto=format&fit=crop"
      }
    ];

    let cart = [];

    // Format Rupiah
    function formatRupiah(number) {
      return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', maximumFractionDigits: 0 }).format(number);
    }

    // Render Produk
    function displayProducts() {
      const container = document.getElementById('product-container');
      container.innerHTML = products.map(item => `
        <div class="card">
          <img src="${item.image}" alt="${item.name}">
          <div class="card-body">
            <h3 class="card-title">${item.name}</h3>
            <p class="card-desc">${item.desc}</p>
            <div class="card-price">${formatRupiah(item.price)}</div>
            <button class="btn-add" onclick="addToCart(${item.id})">+ Masukkan Keranjang</button>
          </div>
        </div>
      `).join('');
    }

    // Toggle Tampilan Keranjang
    function toggleCart() {
      document.getElementById('cart-drawer').classList.toggle('open');
      document.getElementById('overlay').classList.toggle('open');
    }

    // Tambah Produk ke Keranjang
    function addToCart(productId) {
      const product = products.find(p => p.id === productId);
      const existing = cart.find(item => item.id === productId);

      if (existing) {
        existing.qty += 1;
      } else {
        cart.push({ ...product, qty: 1 });
      }

      updateCart();
      toggleCart(); // Buka keranjang langsung saat item ditambahkan
    }

    // Hapus Produk dari Keranjang
    function removeFromCart(productId) {
      cart = cart.filter(item => item.id !== productId);
      updateCart();
    }

    // Update Tampilan Keranjang & Total
    function updateCart() {
      const cartItemsContainer = document.getElementById('cart-items');
      const cartCount = document.getElementById('cart-count');
      const cartTotal = document.getElementById('cart-total');

      const totalItems = cart.reduce((sum, item) => sum + item.qty, 0);
      cartCount.innerText = totalItems;

      if (cart.length === 0) {
        cartItemsContainer.innerHTML = '<p style="text-align: center; color: #999; margin-top: 2rem;">Keranjang masih kosong.</p>';
        cartTotal.innerText = 'Rp 0';
        return;
      }

      let total = 0;
      cartItemsContainer.innerHTML = cart.map(item => {
        const subtotal = item.price * item.qty;
        total += subtotal;
        return `
          <div class="cart-item">
            <div class="item-info">
              <h4>${item.name}</h4>
              <span>${item.qty}x ${formatRupiah(item.price)}</span>
            </div>
            <button class="btn-remove" onclick="removeFromCart(${item.id})">Hapus</button>
          </div>
        `;
      }).join('');

      cartTotal.innerText = formatRupiah(total);
    }

    // Checkout ke WhatsApp
    function checkoutWA() {
      if (cart.length === 0) {
        alert("Keranjang masih kosong!");
        return;
      }

      let text = "Halo kak, saya ingin memesan:%0A%0A";
      let total = 0;

      cart.forEach((item, index) => {
        const subtotal = item.price * item.qty;
        total += subtotal;
        text += `${index + 1}. *${item.name}* (x${item.qty}) - ${formatRupiah(subtotal)}%0A`;
      });

      text += `%0A*Total Pembayaran: ${formatRupiah(total)}*%0A%0AMohon konfirmasi pembayarannya ya, terima kasih!`;

      const url = `https://wa.me/${WA_NUMBER}?text=${text}`;
      window.open(url, '_blank');
    }

    // Jalankan saat pertama kali dibuka
    displayProducts();
  </script>
</body>
</html>
