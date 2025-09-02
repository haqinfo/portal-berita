<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Berita Terkini - Portal Berita</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background: #f4f4f4;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, #1a237e, #3f51b5);
            color: white;
            padding: 1rem 0;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 2rem;
            font-weight: bold;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
        }

        .date-time {
            font-size: 0.9rem;
            opacity: 0.9;
        }

        /* Navigation */
        nav {
            background: #1a1a1a;
            padding: 0.5rem 0;
        }

        .nav-links {
            display: flex;
            list-style: none;
            flex-wrap: wrap;
        }

        .nav-links li {
            margin-right: 2rem;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            transition: all 0.3s ease;
        }

        .nav-links a:hover {
            background: #3f51b5;
            transform: translateY(-2px);
        }

        /* Breaking News */
        .breaking-news {
            background: linear-gradient(45deg, #ff5722, #ff9800);
            color: white;
            padding: 1rem 0;
            margin-bottom: 2rem;
            overflow: hidden;
            position: relative;
        }

        .breaking-text {
            display: flex;
            align-items: center;
        }

        .breaking-label {
            background: #d32f2f;
            padding: 0.5rem 1rem;
            border-radius: 4px;
            margin-right: 1rem;
            font-weight: bold;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 1; }
            50% { opacity: 0.7; }
        }

        .scrolling-text {
            animation: scroll 20s linear infinite;
            white-space: nowrap;
        }

        @keyframes scroll {
            0% { transform: translateX(100%); }
            100% { transform: translateX(-100%); }
        }

        /* Main Content */
        .main-content {
            display: grid;
            grid-template-columns: 2fr 1fr;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        /* Featured Article */
        .featured-article {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
        }

        .featured-article:hover {
            transform: translateY(-5px);
        }

        .featured-image {
            width: 100%;
            height: 300px;
            background: linear-gradient(45deg, #3f51b5, #2196f3);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            position: relative;
        }

        .category-tag {
            position: absolute;
            top: 15px;
            left: 15px;
            background: #ff5722;
            color: white;
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .article-content {
            padding: 1.5rem;
        }

        .article-title {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            color: #333;
            line-height: 1.3;
        }

        .article-meta {
            color: #666;
            font-size: 0.9rem;
            margin-bottom: 1rem;
            display: flex;
            gap: 1rem;
        }

        .article-excerpt {
            color: #555;
            line-height: 1.7;
        }

        .read-more {
            display: inline-block;
            margin-top: 1rem;
            background: #3f51b5;
            color: white;
            padding: 0.5rem 1rem;
            text-decoration: none;
            border-radius: 5px;
            transition: background 0.3s ease;
        }

        .read-more:hover {
            background: #303f9f;
        }

        /* Sidebar */
        .sidebar {
            display: flex;
            flex-direction: column;
            gap: 2rem;
        }

        .sidebar-section {
            background: white;
            padding: 1.5rem;
            border-radius: 10px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.1);
        }

        .sidebar-title {
            font-size: 1.2rem;
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 3px solid #3f51b5;
            color: #333;
        }

        .trending-item {
            display: flex;
            align-items: center;
            padding: 0.5rem 0;
            border-bottom: 1px solid #eee;
            transition: background 0.3s ease;
        }

        .trending-item:hover {
            background: #f8f9fa;
            padding-left: 0.5rem;
        }

        .trending-number {
            background: #3f51b5;
            color: white;
            width: 25px;
            height: 25px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            margin-right: 0.8rem;
            font-weight: bold;
        }

        .trending-title {
            font-size: 0.9rem;
            color: #333;
        }

        /* News Grid */
        .news-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .news-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
        }

        .news-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.15);
        }

        .news-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(45deg, #4caf50, #81c784);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1rem;
            position: relative;
        }

        .news-content {
            padding: 1rem;
        }

        .news-title {
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            color: #333;
        }

        .news-excerpt {
            color: #666;
            font-size: 0.9rem;
            line-height: 1.6;
        }

        /* Footer */
        footer {
            background: #1a1a1a;
            color: white;
            padding: 2rem 0;
            margin-top: 3rem;
        }

        .footer-content {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .footer-section h3 {
            margin-bottom: 1rem;
            color: #3f51b5;
        }

        .footer-section ul {
            list-style: none;
        }

        .footer-section ul li {
            margin-bottom: 0.5rem;
        }

        .footer-section ul li a {
            color: #ccc;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-section ul li a:hover {
            color: #3f51b5;
        }

        .footer-bottom {
            border-top: 1px solid #333;
            padding-top: 1rem;
            margin-top: 2rem;
            text-align: center;
            color: #ccc;
        }

        /* Weather Widget */
        .weather-widget {
            background: linear-gradient(135deg, #2196f3, #21cbf3);
            color: white;
            padding: 1rem;
            border-radius: 10px;
            text-align: center;
        }

        .weather-temp {
            font-size: 2rem;
            font-weight: bold;
            margin: 0.5rem 0;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .header-content {
                text-align: center;
            }
            
            .nav-links {
                justify-content: center;
            }
            
            .nav-links li {
                margin: 0.25rem;
            }
            
            .news-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">📰 Portal Berita</div>
                <div class="date-time" id="datetime"></div>
            </div>
        </div>
    </header>

    <!-- Navigation -->
    <nav>
        <div class="container">
            <ul class="nav-links">
                <li><a href="#home">Beranda</a></li>
                <li><a href="#politik">Politik</a></li>
                <li><a href="#ekonomi">Ekonomi</a></li>
                <li><a href="#olahraga">Olahraga</a></li>
                <li><a href="#teknologi">Teknologi</a></li>
                <li><a href="#hiburan">Hiburan</a></li>
                <li><a href="#kesehatan">Kesehatan</a></li>
                <li><a href="#internasional">Internasional</a></li>
            </ul>
        </div>
    </nav>

    <!-- Breaking News -->
    <div class="breaking-news">
        <div class="container">
            <div class="breaking-text">
                <div class="breaking-label">🚨 BREAKING NEWS</div>
                <div class="scrolling-text">
                    Pemerintah mengumumkan kebijakan baru untuk pertumbuhan ekonomi nasional • 
                    Tim nasional berhasil meraih kemenangan gemilang di turnamen internasional • 
                    Penemuan teknologi revolusioner dari universitas terkemuka Indonesia
                </div>
            </div>
        </div>
    </div>

    <div class="container">
        <!-- Main Content -->
        <div class="main-content">
            <!-- Featured Article -->
            <div class="featured-article">
                <div class="featured-image">
                    <div class="category-tag">Utama</div>
                    <div>🏛️ Foto Utama Berita</div>
                </div>
                <div class="article-content">
                    <h1 class="article-title">Perkembangan Ekonomi Indonesia Menunjukkan Tren Positif di Kuartal Ketiga</h1>
                    <div class="article-meta">
                        <span>📅 2 September 2025</span>
                        <span>👤 Admin Portal</span>
                        <span>💬 24 Komentar</span>
                    </div>
                    <p class="article-excerpt">
                        Data terbaru menunjukkan bahwa perekonomian Indonesia mengalami pertumbuhan yang signifikan pada kuartal ketiga tahun ini. Berbagai sektor industri menunjukkan kinerja yang menggembirakan, dengan sektor teknologi dan manufaktur menjadi pendorong utama pertumbuhan. Para ekonom memprediksi tren positif ini akan berlanjut hingga akhir tahun.
                    </p>
                    <a href="#" class="read-more">Baca Selengkapnya</a>
                </div>
            </div>

            <!-- Sidebar -->
            <div class="sidebar">
                <!-- Trending News -->
                <div class="sidebar-section">
                    <h3 class="sidebar-title">🔥 Trending Hari Ini</h3>
                    <div class="trending-item">
                        <div class="trending-number">1</div>
                        <div class="trending-title">Inovasi teknologi AI terbaru dari Indonesia</div>
                    </div>
                    <div class="trending-item">
                        <div class="trending-number">2</div>
                        <div class="trending-title">Prestasi atlet Indonesia di kompetisi dunia</div>
                    </div>
                    <div class="trending-item">
                        <div class="trending-number">3</div>
                        <div class="trending-title">Kebijakan pendidikan baru dari pemerintah</div>
                    </div>
                    <div class="trending-item">
                        <div class="trending-number">4</div>
                        <div class="trending-title">Perkembangan infrastruktur transportasi</div>
                    </div>
                    <div class="trending-item">
                        <div class="trending-number">5</div>
                        <div class="trending-title">Tren investasi startup lokal</div>
                    </div>
                </div>

                <!-- Weather Widget -->
                <div class="sidebar-section">
                    <h3 class="sidebar-title">🌤️ Cuaca Hari Ini</h3>
                    <div class="weather-widget">
                        <div>Makassar</div>
                        <div class="weather-temp">32°C</div>
                        <div>Cerah Berawan</div>
                        <div style="font-size: 0.9rem; margin-top: 0.5rem;">
                            Kelembaban: 75% | Angin: 15 km/h
                        </div>
                    </div>
                </div>

                <!-- Quick Links -->
                <div class="sidebar-section">
                    <h3 class="sidebar-title">🔗 Menu Cepat</h3>
                    <ul style="list-style: none;">
                        <li><a href="#" style="color: #666; text-decoration: none;">📺 Live TV</a></li>
                        <li><a href="#" style="color: #666; text-decoration: none;">📻 Radio Online</a></li>
                        <li><a href="#" style="color: #666; text-decoration: none;">📱 Aplikasi Mobile</a></li>
                        <li><a href="#" style="color: #666; text-decoration: none;">💌 Newsletter</a></li>
                        <li><a href="#" style="color: #666; text-decoration: none;">📞 Hubungi Redaksi</a></li>
                    </ul>
                </div>
            </div>
        </div>

        <!-- News Grid -->
        <div class="news-grid">
            <div class="news-card">
                <div class="news-image">
                    <div class="category-tag">Politik</div>
                    <div>🏛️ Politik</div>
                </div>
                <div class="news-content">
                    <h3 class="news-title">Rapat Kabinet Bahas Program Prioritas Nasional</h3>
                    <p class="news-excerpt">Presiden memimpin rapat kabinet terbatas untuk membahas program-program prioritas nasional yang akan dilaksanakan pada semester kedua.</p>
                </div>
            </div>

            <div class="news-card">
                <div class="news-image" style="background: linear-gradient(45deg, #ff9800, #ffc107);">
                    <div class="category-tag">Ekonomi</div>
                    <div>💰 Ekonomi</div>
                </div>
                <div class="news-content">
                    <h3 class="news-title">Nilai Tukar Rupiah Menguat Terhadap Dolar AS</h3>
                    <p class="news-excerpt">Rupiah mengalami penguatan signifikan di pasar valuta asing berkat stabilitas ekonomi makro dan kepercayaan investor.</p>
                </div>
            </div>

            <div class="news-card">
                <div class="news-image" style="background: linear-gradient(45deg, #f44336, #e91e63);">
                    <div class="category-tag">Olahraga</div>
                    <div>⚽ Olahraga</div>
                </div>
                <div class="news-content">
                    <h3 class="news-title">Timnas Indonesia Siap Berlaga di Ajang Internasional</h3>
                    <p class="news-excerpt">Persiapan intensif telah dilakukan untuk menghadapi turnamen sepak bola internasional yang akan berlangsung bulan depan.</p>
                </div>
            </div>

            <div class="news-card">
                <div class="news-image" style="background: linear-gradient(45deg, #9c27b0, #673ab7);">
                    <div class="category-tag">Teknologi</div>
                    <div>💻 Teknologi</div>
                </div>
                <div class="news-content">
                    <h3 class="news-title">Peluncuran Satelit Komunikasi Terbaru Indonesia</h3>
                    <p class="news-excerpt">Indonesia berhasil meluncurkan satelit komunikasi generasi terbaru untuk meningkatkan konektivitas digital nasional.</p>
                </div>
            </div>

            <div class="news-card">
                <div class="news-image" style="background: linear-gradient(45deg, #607d8b, #455a64);">
                    <div class="category-tag">Kesehatan</div>
                    <div>🏥 Kesehatan</div>
                </div>
                <div class="news-content">
                    <h3 class="news-title">Program Vaksinasi Nasional Capai Target 90%</h3>
                    <p class="news-excerpt">Pencapaian program vaksinasi nasional mencapai 90% dari target populasi, menunjukkan komitmen masyarakat terhadap kesehatan.</p>
                </div>
            </div>

            <div class="news-card">
                <div class="news-image" style="background: linear-gradient(45deg, #795548, #8d6e63);">
                    <div class="category-tag">Pendidikan</div>
                    <div>🎓 Pendidikan</div>
                </div>
                <div class="news-content">
                    <h3 class="news-title">Kurikulum Baru Fokus pada Keterampilan Digital</h3>
                    <p class="news-excerpt">Kementerian Pendidikan meluncurkan kurikulum baru yang menekankan pengembangan keterampilan digital dan teknologi.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-section">
                    <h3>Tentang Portal Berita</h3>
                    <p>Portal berita terpercaya yang menyajikan informasi terkini dan akurat untuk masyarakat Indonesia. Berkomitmen memberikan berita berkualitas dan objektif.</p>
                </div>
                <div class="footer-section">
                    <h3>Kategori Berita</h3>
                    <ul>
                        <li><a href="#">Politik & Pemerintahan</a></li>
                        <li><a href="#">Ekonomi & Bisnis</a></li>
                        <li><a href="#">Olahraga</a></li>
                        <li><a href="#">Teknologi & Sains</a></li>
                        <li><a href="#">Kesehatan</a></li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Kontak</h3>
                    <ul>
                        <li>📧 redaksi@portalberita.com</li>
                        <li>📞 (021) 123-4567</li>
                        <li>📍 Jakarta, Indonesia</li>
                        <li>🌐 www.portalberita.com</li>
                    </ul>
                </div>
                <div class="footer-section">
                    <h3>Ikuti Kami</h3>
                    <ul>
                        <li><a href="#">📘 Facebook</a></li>
                        <li><a href="#">🐦 Twitter</a></li>
                        <li><a href="#">📷 Instagram</a></li>
                        <li><a href="#">📺 YouTube</a></li>
                        <li><a href="#">💼 LinkedIn</a></li>
                    </ul>
                </div>
            </div>
            <div class="footer-bottom">
                <p>&copy; 2025 Portal Berita. Semua hak cipta dilindungi. | Kebijakan Privasi | Syarat & Ketentuan</p>
            </div>
        </div>
    </footer>

    <script>
        // Update date and time
        function updateDateTime() {
            const now = new Date();
            const options = { 
                weekday: 'long', 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric',
                hour: '2-digit',
                minute: '2-digit',
                second: '2-digit'
            };
            document.getElementById('datetime').textContent = now.toLocaleDateString('id-ID', options);
        }

        // Update time every second
        updateDateTime();
        setInterval(updateDateTime, 1000);

        // Smooth scrolling for navigation links
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href').substring(1);
                const targetElement = document.getElementById(targetId);
                if (targetElement) {
                    targetElement.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Add click effects to cards
        document.querySelectorAll('.news-card, .featured-article, .trending-item').forEach(card => {
            card.addEventListener('click', function() {
                this.style.transform = 'scale(0.98)';
                setTimeout(() => {
                    this.style.transform = '';
                }, 150);
            });
        });

        // Simple search functionality placeholder
        function handleSearch(query) {
            if (query.trim()) {
                alert('Fitur pencarian untuk: ' + query + '\n(Ini adalah demo - implementasi pencarian sesungguhnya memerlukan backend)');
            }
        }

        // Add search functionality on Enter key
        document.addEventListener('keydown', function(e) {
            if (e.ctrlKey && e.key === '/') {
                e.preventDefault();
                const query = prompt('Cari berita:');
                if (query) handleSearch(query);
            }
        });

        // Add reading progress indicator
        window.addEventListener('scroll', function() {
            const scrolled = (window.pageYOffset / (document.documentElement.scrollHeight - window.innerHeight)) * 100;
            const progressBar = document.querySelector('.progress-bar');
            if (progressBar) {
                progressBar.style.width = scrolled + '%';
            }
        });
    </script>
</body>
</html>
