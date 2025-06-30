<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Saya - [Nama Lengkap Anda]</title>

    <script src="https://kit.fontawesome.com/YOUR_FONT_AWESOME_KIT_ID.js" crossorigin="anonymous"></script>

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">

    <style>
        /* Variabel Warna dan Ukuran */
        :root {
            --primary-color: #007bff; /* Biru cerah - bisa diubah */
            --secondary-color: #28a745; /* Hijau sukses - bisa diubah */
            --accent-color: #ffc107; /* Kuning aksen - bisa diubah */
            --text-color-primary: #333;
            --text-color-secondary: #fff;
            --bg-light: #f8f9fa; /* Latar belakang terang */
            --bg-dark: #343a40; /* Latar belakang gelap */
            --border-radius: 10px;
            --box-shadow: 0 5px 15px rgba(0, 0, 0, 0.15);
            --transition-duration: 0.3s;
            --header-height: 280px; /* Tinggi header baru */
        }

        /* Reset CSS */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            font-family: 'Poppins', sans-serif;
            line-height: 1.7;
            color: var(--text-color-primary);
            background-color: var(--bg-light);
            margin: 0;
            padding-top: var(--header-height); /* Memberi ruang untuk header tetap */
        }

        /* Header Baru yang Menarik */
        header {
            background: linear-gradient(135deg, var(--primary-color) 0%, var(--secondary-color) 100%);
            color: var(--text-color-secondary);
            padding: 2rem;
            text-align: center;
            position: fixed; /* Header tetap di atas */
            top: 0;
            left: 0;
            width: 100%;
            height: var(--header-height);
            z-index: 1000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        .profile-pic-container {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            overflow: hidden;
            margin-bottom: 1rem;
            border: 5px solid var(--accent-color); /* Border foto profil */
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            animation: pulse 2s infinite alternate; /* Animasi pulsa */
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            100% { transform: scale(1.05); }
        }

        .profile-pic {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        header h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
        }

        header .tagline {
            font-size: 1.2rem;
            font-style: italic;
            opacity: 0.8;
        }

        /* Navigasi Horizontal */
        nav {
            background-color: rgba(0, 0, 0, 0.05); /* Sedikit transparan */
            position: sticky; /* Navigasi tetap di bawah header */
            top: var(--header-height); /* Dimulai tepat di bawah header */
            z-index: 999;
            box-shadow: 0 1px 5px rgba(0, 0, 0, 0.1);
        }

        nav ul {
            list-style: none;
            padding: 1rem;
            margin: 0;
            display: flex;
            justify-content: center;
        }

        nav ul li {
            margin: 0 1.5rem;
        }

        nav ul li a {
            color: var(--primary-color);
            text-decoration: none;
            font-weight: 600;
            padding: 0.5rem 1rem;
            border-radius: var(--border-radius);
            transition: background-color var(--transition-duration) ease, color var(--transition-duration) ease;
        }

        nav ul li a:hover,
        nav ul li a.active {
            background-color: var(--primary-color);
            color: var(--text-color-secondary);
        }

        /* Gaya Umum Konten Utama */
        main {
            max-width: 960px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        /* Gaya Umum untuk Setiap Bagian (Section) */
        section {
            background-color: #fff;
            padding: 2rem;
            margin-bottom: 2rem;
            border-radius: var(--border-radius);
            box-shadow: var(--box-shadow);
            opacity: 0; /* Untuk animasi fade-in */
            transform: translateY(20px); /* Untuk animasi fade-in */
            transition: opacity 0.5s ease-out, transform 0.5s ease-out;
        }

        section.fade-in {
            opacity: 1;
            transform: translateY(0);
        }

        /* Judul H2 di Setiap Bagian */
        section h2 {
            color: var(--secondary-color);
            font-size: 2.2rem;
            margin-bottom: 1.5rem;
            border-bottom: 3px solid var(--secondary-color);
            padding-bottom: 0.8rem;
            text-align: left;
        }

        section p {
            line-height: 1.8;
            margin-bottom: 1rem;
        }

        /* Hobi dengan Íkon Lingkaran */
        .hobbies-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 1.5rem;
            margin-top: 1rem;
        }

        .hobby-item {
            text-align: center;
        }

        .hobby-icon {
            background-color: var(--accent-color);
            color: var(--text-color-secondary);
            width: 60px;
            height: 60px;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 1.5rem;
            margin: 0 auto 0.5rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .hobby-item h3 {
            font-size: 1.1rem;
            margin-bottom: 0.3rem;
            color: var(--text-color-primary);
        }

        /* Riwayat Pendidikan (Timeline Vertikal) */
        .timeline {
            position: relative;
            padding: 1rem 0;
            margin-top: 1rem;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 50%;
            top: 0;
            width: 2px;
            height: 100%;
            background-color: var(--accent-color);
            transform: translateX(-50%);
        }

        .timeline-item {
            width: 45%;
            padding: 1rem;
            margin-bottom: 1.5rem;
            background-color: #fff;
            border-radius: var(--border-radius);
            box-shadow: 0 2px 7px rgba(0, 0, 0, 0.1);
            position: relative;
        }

        .timeline-item:nth-child(odd) {
            left: 5%; /* Item di sisi kiri */
        }

        .timeline-item:nth-child(even) {
            left: 50%; /* Item di sisi kanan */
        }

        .timeline-item::after {
            content: '';
            position: absolute;
            width: 12px;
            height: 12px;
            background-color: var(--primary-color);
            border-radius: 50%;
            top: 10px;
            transform: translateY(-50%);
            z-index: 1;
        }

        .timeline-item:nth-child(odd)::after {
            left: -6px; /* Titik di sebelah kiri untuk item kiri */
        }

        .timeline-item:nth-child(even)::after {
            right: -6px; /* Titik di sebelah kanan untuk item kanan */
        }

        .timeline-date {
            font-size: 0.9rem;
            color: #777;
            margin-bottom: 0.5rem;
            display: block;
        }

        .timeline-item h3 {
            color: var(--primary-color);
            margin-bottom: 0.3rem;
        }

        /* Keterampilan sebagai Label Berwarna */
        .skills-category {
            margin-bottom: 1.5rem;
        }

        .skills-category h3 {
            color: var(--primary-color);
            font-size: 1.3rem;
            margin-bottom: 0.7rem;
            border-bottom: 2px solid var(--primary-color);
            padding-bottom: 0.4rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.6rem;
        }

        .skill-tags span {
            background-color: var(--secondary-color);
            color: var(--text-color-secondary);
            padding: 0.4rem 0.8rem;
            border-radius: 20px;
            font-size: 0.9rem;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        /* Kontak dengan Tombol Berikon */
        .contact-links {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 1.2rem;
            margin-top: 1.5rem;
        }

        .contact-button {
            background-color: var(--primary-color);
            color: var(--text-color-secondary);
            padding: 0.8rem 1.5rem;
            border-radius: var(--border-radius);
            text-decoration: none;
            font-weight: 600;
            transition: background-color var(--transition-duration) ease, transform var(--transition-duration) ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .contact-button:hover {
            background-color: #0056b3; /* Sedikit lebih gelap */
            transform: translateY(-3px); /* Efek angkat */
        }

        .contact-button i {
            font-size: 1.2rem;
        }

        /* Footer Modern */
        footer {
            text-align: center;
            padding: 1.5rem;
            margin-top: 3rem;
            background-color: var(--bg-dark);
            color: var(--text-color-secondary);
            font-size: 0.9rem;
        }

        /* Responsivitas yang Ditingkatkan */
        @media (max-width: 768px) {
            :root {
                --header-height: 220px; /* Tinggi header di tablet */
            }
            header h1 {
                font-size: 2rem;
            }
            nav ul {
                padding: 0.8rem;
                flex-direction: column; /* Navigasi menjadi kolom */
                align-items: center;
            }
            nav ul li {
                margin: 0.8rem 0;
            }
            .timeline::before {
                left: 20px; /* Garis timeline pindah ke kiri */
            }
            .timeline-item {
                width: 90%; /* Item timeline menjadi lebih lebar */
                margin-left: 10%; /* Dorong ke kanan sedikit */
            }
            .timeline-item:nth-child(even) {
                left: 10%; /* Pastikan item kanan juga sesuai */
            }
            .timeline-item::after {
                left: -6px; /* Titik timeline diatur ulang */
            }
        }

        @media (max-width: 480px) {
            :root {
                --header-height: 180px; /* Tinggi header di ponsel */
            }
            header h1 {
                font-size: 1.8rem;
            }
            .profile-pic-container {
                width: 100px;
                height: 100px;
            }
            section {
                padding: 1.5rem;
            }
            section h2 {
                font-size: 2rem;
            }
            .hobbies-grid {
                grid-template-columns: 1fr; /* Hobi menjadi satu kolom */
            }
            .skill-tags {
                justify-content: center; /* Skill tags menjadi di tengah */
            }
            .contact-links {
                flex-direction: column; /* Tombol kontak menjadi kolom */
                align-items: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="profile-pic-container">
            <img src="C:\Users\ZYREX\Pictures\5b13616c-8e62-483e-b818-35de4df31f79.jfif"alt="Foto Profil Anda" class="profile-pic">
        </div>
        <h1>Hello World !</h1>
        <p class="tagline">WELCOME TO MY PROFILE</p>
    </header>

    <nav>
        <ul>
            <li><a href="#about" class="active">Tentang Saya</a></li>
            <li><a href="#hobbies">Hobi</a></li>
            <li><a href="#education">Pendidikan</a></li>
            <li><a href="#skills">Keterampilan</a></li>
            <li><a href="#contact">Kontak</a></li>
        </ul>
    </nav>

    <main>
        <section id="about" class="fade-in">
            <h2>Tentang Saya</h2>
            <p>Hai! Saya Margareth Maylan Niwele.</p>
            <p>Tempat Tanggal/Lahir : Seram Bagian Barat, 29 Mei-2005.</p>
			<p>Saya berasal dari Seram Bagian Barat, Kec Taniwel.</p
        </section>

        <section id="hobbies" class="fade-in">
            <h2>Hobi & Minat</h2>
            <div class="hobbies-grid">
                <div class="hobby-item">
                    <div class="hobby-icon"><i class="fas fa-camera"></i></div>
                    <h3>Live/Siaran Langsung</h3>
                    <p>Saya suka sekali Siaran Langsung pada aplikasi Facebook dan Instagram.</p>
                </div>
                <div class="hobby-item">
                    <div class="hobby-icon"><i class="fas fa-cooking"></i></div>
                    <h3>Memasak</h3>
                    <p>Hobi saya yang sangat Fav yaitu memasak, membuat kue dan Dessert.</p>
                </div>
                </div>
        </section>

        <section id="education" class="fade-in">
            <h2>Riwayat Pendidikan</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <h3>SD KRISTEN TANIWEL</h3>
                </div>
                <div class="timeline-item">
                    <h3>SMP NEGERI 1 TANIWEL</h3>
                </div>
				<div class="timeline-item">
                    <h3>SMAN 4 SERAM BAGIAN BARAT</h3>
				</div>
				<div class="timeline-item">
                    <h3>UNIVERSITAS KRISTEN INDONESIA MALUKU</h3>
					<p><strong>Fakultas Ilmu Komputer/Program Studi Informatika</strong></p>
                </div>
        </section>

        <section id="skills" class="fade-in">
            <h2>Keterampilan Saya</h2>
            <div class="skills-category">
                <h3>Bahasa Pemrograman</h3>
                <div class="skill-tags">
                    <span>HTML5</span>
                    <span>CSS3</span>
                    <span>JavaScript</span>
                    </div>
            </div>
            <div class="skills-category">
                <h3>Lainnya</h3>
                <div class="skill-tags">
                    <span>Capcut</span>
                    <span>Adobe Photoshop</span>
                    </div>
            </div>
        </section>

        <section id="contact" class="fade-in">
            <h2>Hubungi Saya</h2>
            <p>Saya selalu terbuka untuk peluang baru, kolaborasi, atau sekadar berdiskusi. Jangan ragu untuk menghubungi saya!</p>
            <div class="contact-links">
                <a href="https://www.facebook.com/share/15w7Rbh55A/?mibextid=wwXIfr" class="contact-button"><i class="fas fa-facebook"></i> Facebook</a>
                <a href="https://www.instagram.com/gitaniwele?igsh=cmdhcmVvaHZ6dnJq" target="_blank" class="contact-button"><i class="fab fa-Instagram"></i> Instagram</a>
                <a href="https://wa.me/6281248349746." target="_blank" class="contact-button"><i class="fab fa-whatsapp"></i> Whatsapp</a>
                </div>
        </section>
    </main>

    <footer>
        &copy; 2025 Profil Saya. Hak Cipta Dilindungi.
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            // --- Fungsionalitas Navigasi dan Animasi Scroll ---

            // Smooth scrolling untuk navigasi
            document.querySelectorAll('nav a').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault(); // Mencegah perilaku default tautan (loncat langsung)

                    // Hapus kelas 'active' dari semua tautan navigasi
                    document.querySelectorAll('nav a').forEach(navLink => navLink.classList.remove('active'));
                    // Tambahkan kelas 'active' ke tautan yang baru saja diklik
                    this.classList.add('active');

                    const targetId = this.getAttribute('href').substring(1); // Ambil ID bagian dari atribut href
                    const targetElement = document.getElementById(targetId); // Dapatkan elemen bagian target

                    if (targetElement) {
                        // Hitung offset untuk header dan navigasi yang sticky
                        const headerOffset = document.querySelector('header').offsetHeight;
                        const navOffset = document.querySelector('nav').offsetHeight;
                        const offsetPosition = targetElement.offsetTop - (headerOffset + navOffset + 10); // Tambah 10px padding ekstra

                        // Gulir ke posisi target dengan efek mulus
                        window.scrollTo({
                            top: offsetPosition,
                            behavior: 'smooth'
                        });
                    }
                });
            });

            // Animasi fade-in saat bagian masuk ke viewport menggunakan Intersection Observer
            const sections = document.querySelectorAll('section'); // Dapatkan semua elemen <section>
            const observerOptions = {
                root: null, // Mengamati di dalam viewport utama dokumen
                rootMargin: '0px', // Tidak ada margin tambahan
                threshold: 0.2 // Ketika 20% dari bagian terlihat, picu callback
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) { // Jika bagian sedang terlihat di viewport
                        entry.target.classList.add('fade-in'); // Tambahkan kelas 'fade-in'
                        // observer.unobserve(entry.target); // Opsional: Hentikan observasi setelah animasi pertama kali
                    }
                });
            }, observerOptions);

            // Mulai observasi untuk setiap bagian
            sections.forEach(section => {
                observer.observe(section);
            });

            // Atur tautan navigasi 'active' berdasarkan posisi scroll
            function setActiveNavLinkOnScroll() {
                const headerOffset = document.querySelector('header').offsetHeight;
                const navOffset = document.querySelector('nav').offsetHeight;
                const scrollPosition = window.scrollY + headerOffset + navOffset + 10; // Sesuaikan dengan offset di smooth scroll

                document.querySelectorAll('nav a').forEach(anchor => {
                    const targetId = anchor.getAttribute('href').substring(1);
                    const targetElement = document.getElementById(targetId);

                    if (targetElement) {
                        // Jika posisi scroll berada di antara bagian atas dan bawah section
                        if (scrollPosition >= targetElement.offsetTop && scrollPosition < targetElement.offsetTop + targetElement.offsetHeight) {
                            document.querySelectorAll('nav a').forEach(navLink => navLink.classList.remove('active'));
                            anchor.classList.add('active');
                        }
                    }
                });
                 // Kasus khusus untuk bagian "Tentang Saya" saat di paling atas
                if (window.scrollY < document.getElementById('about').offsetTop - (headerOffset + navOffset + 10)) {
                    document.querySelectorAll('nav a').forEach(navLink => navLink.classList.remove('active'));
                    document.querySelector('nav a[href="#about"]').classList.add('active');
                }
            }

            // Panggil fungsi setActiveNavLinkOnScroll saat halaman dimuat dan saat menggulir
            window.addEventListener('load', setActiveNavLinkOnScroll);
            window.addEventListener('scroll', setActiveNavLinkOnScroll);

            // Panggilan awal untuk memastikan tautan navigasi yang benar aktif saat halaman pertama kali dimuat
            setActiveNavLinkOnScroll();
        });
    </script>
</body>
</html>
