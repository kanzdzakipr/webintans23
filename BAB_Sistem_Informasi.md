# BAB Sistem Informasi

## 1. Gambaran Umum Sistem

Website yang dikembangkan merupakan web app berbasis client-side static application untuk mendukung penyajian informasi, dokumentasi proses, knowledge base, pattern recognition, dan dashboard kinerja operasional terminal peti kemas. Sistem ini dibangun sebagai prototipe sistem informasi operasional yang dapat diakses melalui browser tanpa instalasi aplikasi khusus di perangkat pengguna.

Secara fungsi, website ini tidak hanya berperan sebagai halaman informasi profil, tetapi juga sebagai media pembelajaran, dokumentasi, visualisasi data, dan pendukung pengambilan keputusan awal. Halaman-halaman yang tersedia menghubungkan profil terminal, proses operasional, alur pemuatan dan pembongkaran peti kemas, knowledge base aktivitas terminal, pemetaan risiko, action scoring, serta dashboard kinerja berbasis grafik.

Arsitektur yang digunakan pada versi saat ini adalah static web app. Semua halaman utama dibuat menggunakan HTML, CSS, dan JavaScript. Data pada dashboard dan knowledge base sebagian besar masih ditanam langsung di dalam file HTML/JavaScript, sedangkan penyimpanan keputusan pengguna pada halaman pattern recognition menggunakan `localStorage` browser. Dengan arsitektur ini, website mudah dijalankan, dipresentasikan, dan dipindahkan, tetapi belum memiliki backend, database terpusat, autentikasi server, maupun manajemen data multi-user.

Pemilihan arsitektur static web app perlu dipahami sebagai keputusan desain yang bersifat kontekstual, bukan sebagai bentuk akhir sistem operasional. Pada tahap prototipe akademik, prioritas utama adalah keterbacaan proses, kelengkapan fitur demonstratif, dan kemudahan akses tanpa konfigurasi server. Oleh karena itu, penggunaan HTML, CSS, dan JavaScript langsung pada sisi client merupakan pilihan yang rasional karena mempercepat proses validasi ide. Namun, dari sudut pandang sistem informasi produksi, pilihan ini membawa konsekuensi kritis: data belum terpusat, autentikasi belum aman, dan histori keputusan belum dapat dikelola lintas pengguna.

Dengan demikian, sistem ini dapat diposisikan sebagai proof-of-concept sistem informasi operasional, bukan sebagai enterprise application yang siap digunakan untuk transaksi atau keputusan resmi. Pembahasan pada bab ini perlu menjaga dua posisi sekaligus: pertama, mengakui bahwa sistem telah berhasil mengintegrasikan profil, knowledge base, pattern recognition, alur proses, dan dashboard; kedua, menegaskan bahwa arsitektur yang dipilih masih perlu dikembangkan apabila sistem diarahkan untuk penggunaan institusional.

Dalam konteks pengelolaan proyek berbasis aset dan infrastruktur, web app ini juga dapat dilihat sebagai artefak digital untuk mendukung pengendalian informasi, pembelajaran organisasi, manajemen risiko, dan pemantauan kinerja. Terminal peti kemas bukan hanya objek operasional, tetapi juga bagian dari sistem aset yang membutuhkan koordinasi lintas proses, lintas peran, dan lintas indikator. Oleh karena itu, pengembangan website perlu dibaca dalam kerangka yang lebih luas: bagaimana informasi dikumpulkan, disusun, divisualisasikan, digunakan untuk menilai risiko, dan dipertanggungjawabkan sebagai dasar keputusan.

Posisi tersebut membuat bab ini tidak cukup apabila hanya menjelaskan aspek teknis pembuatan halaman web. Pembahasan perlu mengaitkan desain sistem dengan standar manajemen proyek, manajemen risiko, manajemen mutu, manajemen informasi aset, siklus hidup perangkat lunak, kualitas perangkat lunak, usability, aksesibilitas, dan keamanan aplikasi web. Rujukan standar seperti PMBOK Guide, ISO 21502, ISO 21511, ISO 31000, ISO 9001, ISO 19650, ISO/IEC/IEEE 12207, ISO/IEC 25010, ISO 9241-210, WCAG, dan OWASP digunakan untuk memperkuat argumentasi bahwa rancangan web app memiliki dasar tata kelola, bukan sekadar keputusan teknis.

### 1.1 Ruang Lingkup Sistem

Ruang lingkup sistem meliputi:

1. Menyediakan halaman login sebagai pintu masuk awal ke sistem.
2. Menampilkan profil PT Pelindo Terminal Petikemas dan jaringan terminal terkait.
3. Menyediakan profil TPK Teluk Lamong Surabaya, TPK Semarang, TPK Makassar New Port, dan IPC TPK.
4. Menyediakan knowledge base aktivitas terminal, seperti Berth Allocation, Manning & Deployment, Ship Planner, Yard Planner, Ship Talker, dan Yard Talker.
5. Menampilkan alur penanganan proses peti kemas, termasuk alur pemuatan dan pembongkaran.
6. Menyediakan pattern recognition knowledge base untuk memetakan aktivitas, risiko, penyebab, preventive measure, corrective measure, dan predictive measure.
7. Menyediakan action scoring dan pencatatan keputusan manusia/pakar/operator.
8. Menyajikan dashboard kinerja operasional, BOR, YOR, throughput, availability, utilization, tren, ranking, dan korelasi data.
9. Menyediakan fitur visualisasi grafik serta ekspor chart atau keputusan pada beberapa halaman.

Penentuan ruang lingkup tersebut dibuat dengan mempertimbangkan kebutuhan sistem informasi yang tidak hanya berorientasi pada tampilan, tetapi juga pada representasi pengetahuan operasional. Website profil biasa umumnya berhenti pada penyajian informasi umum, sedangkan sistem ini mencoba memperluas fungsi tersebut menjadi ruang dokumentasi, analisis, dan pembelajaran. Oleh karena itu, modul knowledge base dan pattern recognition dimasukkan sebagai bagian inti, bukan fitur tambahan.

Meski demikian, ruang lingkup juga sengaja dibatasi. Sistem belum mencakup proses transaksi operasional real-time, integrasi langsung dengan Terminal Operating System, input data oleh banyak pengguna, maupun validasi data melalui server. Pembatasan ini penting secara metodologis karena tujuan pengembangan adalah membangun prototipe sistem informasi yang dapat menjelaskan konsep, alur, dan analisis, bukan menggantikan sistem operasional terminal yang sudah berjalan.

### 1.2 Tujuan Sistem

Tujuan pengembangan sistem adalah:

1. Memudahkan pengguna memahami informasi terminal peti kemas melalui satu website terpadu.
2. Menyajikan dokumentasi proses operasional secara visual dan terstruktur.
3. Membantu pengguna membaca indikator kinerja melalui dashboard interaktif.
4. Menyimpan pola pengetahuan operasional dalam bentuk knowledge base.
5. Membantu pemetaan risiko dan tindakan melalui pattern recognition dan action scoring.
6. Menjadi prototipe awal yang dapat dikembangkan lebih lanjut menjadi sistem informasi berbasis database dan backend.

Tujuan tersebut menunjukkan bahwa orientasi sistem bersifat informasional dan analitis. Sistem tidak dirancang untuk mengeksekusi proses operasional seperti penjadwalan kapal secara nyata atau mengubah data resmi terminal, melainkan untuk menyajikan informasi agar pengguna dapat memahami konteks operasional dengan lebih baik. Pemisahan ini penting agar evaluasi sistem tidak keliru: keberhasilan sistem tidak diukur dari kemampuan menggantikan aplikasi produksi, tetapi dari kemampuannya menyusun informasi, memvisualisasikan data, dan memetakan pola pengetahuan.

Secara kritis, tujuan keenam menjadi jembatan antara prototipe dan pengembangan lanjutan. Dengan menyebut sistem sebagai prototipe awal, penulis dapat menjelaskan mengapa beberapa keputusan teknis seperti login statis, data hardcoded, dan localStorage masih digunakan. Keputusan tersebut dapat diterima pada tahap pembuktian konsep, tetapi harus dinyatakan sebagai keterbatasan apabila sistem dikembangkan lebih lanjut.

### 1.3 Aktor dan Pengguna Sistem

| Aktor | Peran | Kebutuhan Informasi | Fitur yang Digunakan |
| --- | --- | --- | --- |
| Pengunjung internal | Membaca informasi umum dan profil terminal | Profil, dokumentasi, indikator umum | Home, Profil TPK, Dokumentasi |
| Mahasiswa/peneliti | Menganalisis proses dan kinerja terminal | Alur proses, data kinerja, knowledge base | Knowledge Base, Pattern Recognition, Dashboard |
| Operator/pakar | Membaca pola risiko dan alternatif tindakan | Risiko, penyebab, preventive/corrective/predictive action | Pattern Recognition KB, Action Scoring |
| Admin konseptual | Mengelola data pada pengembangan lanjutan | Data user, terminal, aktivitas, risiko, dashboard | Rancangan backend dan database lanjutan |

Pembagian aktor di atas tidak hanya berfungsi sebagai daftar pengguna, tetapi juga sebagai dasar penentuan kedalaman fitur. Pengunjung internal membutuhkan navigasi yang jelas dan informasi ringkas, sedangkan mahasiswa/peneliti membutuhkan struktur data dan konteks analitis. Operator/pakar membutuhkan hubungan antara risiko, penyebab, dan tindakan. Admin konseptual belum diwujudkan sebagai aktor teknis di sistem saat ini, tetapi tetap dicantumkan karena menjadi dasar perancangan arsitektur lanjutan.

Dari perspektif akademik, pemisahan aktor ini membantu menjelaskan mengapa sistem memadukan halaman naratif, halaman visual, dan halaman analitik. Jika hanya menargetkan pengunjung umum, dashboard dan action scoring menjadi terlalu kompleks. Sebaliknya, jika hanya menargetkan analis, halaman profil dan dokumentasi visual menjadi kurang relevan. Oleh karena itu, desain sistem mengambil pendekatan multi-purpose, dengan konsekuensi bahwa navigasi dan struktur informasi harus dibuat cukup jelas agar berbagai jenis pengguna tidak tersesat.

### 1.4 Keterkaitan dengan Bab Pendukung dalam Naskah

Bab pengembangan sistem informasi ini sebaiknya tidak berdiri sendiri. Agar argumentasinya kuat, bab ini perlu ditopang oleh beberapa bab pendukung yang menjelaskan konteks teoretis, metodologis, data, implementasi, dan evaluasi. Keterkaitan antarbagian tersebut penting karena web app yang dikembangkan bukan hanya produk teknis, tetapi juga instrumen konseptual untuk membaca proses, risiko, dan kinerja.

| Bab Pendukung | Fungsi dalam Naskah | Keterkaitan dengan Bab Sistem Informasi |
| --- | --- | --- |
| Pendahuluan | Menjelaskan latar belakang kebutuhan sistem, masalah informasi, dan urgensi digitalisasi proses | Menjadi dasar mengapa web app diperlukan |
| Tinjauan Pustaka | Membahas teori sistem informasi, manajemen proyek, risiko, knowledge base, dashboard, dan decision support | Menjadi dasar akademik bagi fitur dan arsitektur |
| Metodologi Penelitian | Menjelaskan pendekatan pengembangan, sumber data, validasi, dan metode evaluasi | Menjelaskan bagaimana sistem dibangun dan diuji |
| Analisis Proses Operasional | Menguraikan alur aktivitas terminal, WBS, risiko, dan indikator kinerja | Menjadi input bagi knowledge base dan dashboard |
| Perancangan Sistem | Menjelaskan use case, activity diagram, sitemap, arsitektur, dan rancangan data | Menjadi jembatan antara kebutuhan dan implementasi |
| Implementasi dan Pengujian | Menyajikan hasil web app, fitur, screenshot, black-box test, usability, dan performa | Membuktikan bahwa rancangan telah diwujudkan |
| Pembahasan | Menganalisis kelebihan, keterbatasan, kesesuaian standar, dan arah pengembangan | Menilai kontribusi dan batas validitas sistem |

Secara kritis, tabel tersebut membantu mencegah bab sistem informasi menjadi terlalu teknis dan terlepas dari konteks penelitian. Jika bab ini hanya memuat daftar fitur, kontribusi akademiknya akan lemah. Sebaliknya, jika bab ini dihubungkan dengan teori, proses, risiko, dan evaluasi, maka web app dapat dipahami sebagai instrumen analitis yang mendukung tata kelola informasi dan pembelajaran berbasis data.

CATATAN PENYAJIAN: Subbab ini dapat didampingi ilustrasi "overview web app" yang menampilkan pengguna mengakses web app melalui browser, lalu masuk ke modul profil, knowledge base, alur proses, pattern recognition, dan dashboard.

Prompt ilustrasi:

```text
Buat diagram overview sistem informasi berbasis web untuk terminal peti kemas. Tampilkan aktor pengguna di sisi kiri yang mengakses browser, lalu panah menuju web app dengan lima modul utama: Profil Terminal, Knowledge Base, Alur Proses Peti Kemas, Pattern Recognition & Action Scoring, dan Dashboard Kinerja. Gunakan gaya diagram akademik modern, warna biru pelabuhan, ikon kapal kontainer, crane, database konseptual, dan grafik. Output bersih, rasio 16:9, cocok untuk laporan skripsi.
```

## 2. Landasan Teori yang Digunakan

### 2.1 Sistem Informasi Berbasis Web

Sistem informasi berbasis web adalah sistem yang menggunakan teknologi web untuk mengelola, menyajikan, dan mendistribusikan informasi kepada pengguna melalui browser. Dalam website ini, sistem informasi digunakan untuk menyatukan informasi profil terminal, dokumentasi aktivitas, knowledge base, dan dashboard kinerja. Keunggulan pendekatan web adalah kemudahan akses, tidak membutuhkan instalasi aplikasi khusus, serta dapat dikembangkan menjadi sistem yang lebih luas dengan backend dan database.

Pada versi saat ini, sistem berjalan sebagai static web app. Artinya, logika sistem berada pada sisi client melalui JavaScript, sedangkan data masih tersimpan di dalam file halaman. Arsitektur ini cocok untuk prototipe, simulasi, presentasi, atau dokumentasi akademik.

Pemilihan sistem informasi berbasis web dibandingkan aplikasi desktop atau dokumen statis memiliki dasar rasional yang kuat. Aplikasi web lebih mudah didistribusikan karena pengguna cukup membuka browser, sementara dokumen statis kurang mampu mendukung interaksi seperti filter, chart, modal, scoring, dan export. Di sisi lain, pendekatan web juga menghadirkan tuntutan desain yang lebih besar, terutama pada konsistensi navigasi, kecepatan muat, kompatibilitas browser, dan keamanan akses.

Secara kritis, sistem berbasis web memiliki dua lapisan nilai. Lapisan pertama adalah nilai presentasional, yaitu menyajikan informasi dalam format yang mudah dibaca. Lapisan kedua adalah nilai analitis, yaitu memungkinkan pengguna memproses data melalui grafik, filter, dan scoring. Website ini berupaya memenuhi kedua lapisan tersebut, tetapi karena masih static client-side, nilai analitisnya masih terbatas pada data yang sudah tertanam di halaman.

### 2.2 Software Development Life Cycle

Software Development Life Cycle (SDLC) digunakan sebagai kerangka pengembangan sistem. Tahapan SDLC membantu proses pembuatan website lebih terarah, mulai dari identifikasi kebutuhan, perancangan, implementasi, pengujian, hingga evaluasi.

Dalam penelitian ini, SDLC diterapkan sebagai berikut:

| Tahap SDLC | Penerapan pada Website |
| --- | --- |
| Analisis kebutuhan | Mengidentifikasi kebutuhan halaman profil, knowledge base, alur proses, dashboard, dan pattern recognition |
| Perancangan | Membuat struktur navigasi, rancangan halaman, rancangan modul, rancangan chart, dan rancangan knowledge base |
| Implementasi | Membangun halaman menggunakan HTML, CSS, JavaScript, library chart, aset visual, dan localStorage |
| Pengujian | Menguji login, navigasi, dropdown, chart, filter, scoring, export, dan responsivitas |
| Evaluasi | Menilai kelebihan, keterbatasan, dan pengembangan lanjutan menuju backend/database |

Pemilihan SDLC dalam penelitian ini lebih tepat dibandingkan pendekatan pengembangan yang sepenuhnya eksploratif karena sistem memiliki keluaran yang dapat dirumuskan sejak awal. Modul yang dibutuhkan sudah relatif jelas, yaitu login, home, profil, knowledge base, alur proses, pattern recognition, dan dashboard. Dengan demikian, model bertahap memudahkan penulis menjelaskan hubungan antara kebutuhan, rancangan, implementasi, dan pengujian.

Namun, penerapan SDLC pada proyek web app ini tidak bersifat kaku sepenuhnya. Pada praktiknya, desain dashboard dan antarmuka membutuhkan penyesuaian berulang karena tampilan grafik, kepadatan data, dan pengalaman pengguna baru terlihat setelah halaman diimplementasikan. Oleh sebab itu, model yang digunakan dapat disebut Waterfall dengan iterasi terbatas pada tahap implementasi UI dan visualisasi data. Penegasan ini penting agar metodologi tidak terkesan dipaksakan.

### 2.3 Knowledge Management System

Knowledge Management System adalah sistem yang membantu proses penyimpanan, pengelompokan, pencarian, dan penggunaan ulang pengetahuan. Dalam website ini, konsep knowledge management diterapkan pada halaman `knowledge-base.html` dan `pattern-recognition-knowledge-base.html`.

Knowledge base memuat aktivitas terminal, risiko, penyebab, dan tindakan. Pattern recognition digunakan untuk membaca pola hubungan antara aktivitas, risiko, penyebab, dan tindakan. Dengan demikian, sistem membantu pengguna memahami pola operasional dan alternatif penyelesaian masalah.

Penggunaan knowledge base dipilih karena proses operasional terminal peti kemas memiliki banyak pengetahuan tacit yang sering bergantung pada pengalaman operator. Jika pengetahuan tersebut hanya disampaikan secara lisan atau tersebar dalam dokumen terpisah, pengguna baru akan kesulitan memahami hubungan antara aktivitas, risiko, dan tindakan. Knowledge base membantu mengubah pengetahuan tersebut menjadi struktur yang lebih eksplisit.

Meski demikian, knowledge base pada sistem ini belum dapat dianggap sebagai knowledge management system penuh. Sistem belum memiliki fitur validasi pakar, histori revisi, manajemen versi, maupun mekanisme pembaruan data oleh admin. Oleh karena itu, kontribusinya lebih tepat diposisikan sebagai prototipe basis pengetahuan terstruktur. Kelebihannya terletak pada pemetaan pola, sedangkan kelemahannya terletak pada belum adanya tata kelola pengetahuan secara berkelanjutan.

### 2.4 Dashboard dan Data Visualization

Dashboard adalah tampilan ringkas yang menyajikan indikator penting melalui angka, grafik, tabel, dan visualisasi interaktif. Website ini menggunakan dashboard untuk menyajikan indikator seperti BOR, YOR, throughput, total box, total TEUs, produktivitas, equipment availability, dan equipment utilization.

Data visualization digunakan agar pengguna dapat membaca tren, perbandingan, ranking, distribusi, dan korelasi secara lebih cepat. Library yang digunakan meliputi Chart.js, ApexCharts, dan ECharts.

Pemilihan dashboard sebagai media penyajian data didasarkan pada karakteristik data operasional terminal yang cenderung numerik, periodik, dan komparatif. Indikator seperti BOR, YOR, throughput, availability, dan utilization akan sulit dibaca apabila hanya disajikan dalam tabel panjang. Grafik memungkinkan pengguna menemukan kecenderungan, anomali, dan perbandingan antarperiode secara lebih cepat.

Walaupun demikian, visualisasi data juga memiliki risiko interpretasi. Grafik yang menarik secara visual belum tentu menghasilkan pemahaman yang benar apabila skala, label, konteks, atau sumber data tidak dijelaskan. Oleh karena itu, penggunaan dashboard dalam sistem ini harus dilengkapi dengan narasi interpretatif dan keterangan indikator. Dalam laporan, penting untuk menegaskan bahwa dashboard adalah alat bantu analisis, bukan bukti kesimpulan tunggal tanpa verifikasi data.

### 2.5 Decision Support dan Action Scoring

Decision support pada website ini masih berupa prototipe. Sistem belum mengambil keputusan otomatis, tetapi memberikan struktur penilaian untuk membantu manusia/pakar/operator memilih tindakan. Pada halaman pattern recognition, setiap entri risiko memiliki alternatif preventive, corrective, dan predictive measure. Setiap alternatif dapat diberi skor berdasarkan kriteria efektivitas, kemudahan, kecepatan, dampak, dan kesiapan.

Sistem memberikan rekomendasi berdasarkan skor tertinggi, tetapi keputusan akhir tetap berada pada manusia. Hal ini sesuai dengan prinsip human-in-the-loop, yaitu sistem membantu analisis tetapi tidak menggantikan pertimbangan pengguna.

Pemilihan action scoring dilakukan karena tidak semua tindakan memiliki nilai yang sama dalam konteks operasional. Suatu tindakan dapat sangat efektif, tetapi sulit diterapkan; tindakan lain mungkin cepat dilakukan, tetapi dampaknya terbatas. Dengan skor multi-kriteria, pengguna dapat membandingkan tindakan secara lebih transparan. Pendekatan ini juga membuat proses rekomendasi lebih dapat dijelaskan dibandingkan rekomendasi otomatis yang tidak memiliki dasar penilaian terlihat.

Keterbatasan kritis dari action scoring adalah sifat skor yang masih bergantung pada input pengguna dan asumsi baseline. Tanpa data historis yang terverifikasi, skor belum dapat dianggap sebagai hasil prediksi objektif. Oleh karena itu, sistem menempatkan manusia sebagai pengambil keputusan akhir. Posisi ini penting secara metodologis karena menghindari klaim berlebihan bahwa sistem mampu menentukan tindakan terbaik secara otomatis.

### 2.6 User Interface dan User Experience

UI/UX digunakan untuk memastikan sistem mudah dipahami dan digunakan. Website menerapkan navigasi tetap, dropdown menu, card, tabel, chart, tombol interaktif, modal, slider, dark mode pada beberapa dashboard, dan tampilan responsif. Desain antarmuka diarahkan agar pengguna dapat berpindah dari informasi umum menuju informasi analitis secara bertahap.

Pertimbangan UI/UX pada sistem ini tidak hanya menyangkut estetika, tetapi juga beban kognitif pengguna. Website memuat banyak jenis informasi, mulai dari profil, foto, flowchart, tabel risiko, sampai chart analitik. Jika struktur visual tidak dibuat terarah, pengguna akan mengalami kesulitan memahami prioritas informasi. Oleh karena itu, penggunaan navbar, dropdown, card, dan heading bertingkat dipilih untuk membagi informasi menjadi unit-unit yang lebih mudah dipindai.

Di sisi lain, penggunaan banyak halaman HTML terpisah berpotensi menimbulkan inkonsistensi gaya dan pengalaman pengguna. Hal ini terlihat sebagai risiko maintainability dalam static web app, karena perubahan desain harus dilakukan di banyak file. Untuk pengembangan lanjutan, UI sebaiknya dipusatkan melalui komponen reusable atau framework frontend agar konsistensi antarmuka lebih terjaga.

### 2.7 Pemetaan Teori terhadap Modul Sistem

| Teori/Konsep | Modul Website | Bentuk Implementasi |
| --- | --- | --- |
| Sistem informasi berbasis web | Semua halaman | HTML, CSS, JavaScript, browser-based access |
| SDLC | Proses pengembangan | Analisis, desain, implementasi, pengujian, evaluasi |
| Knowledge management | Knowledge Base, Pattern Recognition KB | Kartu aktivitas, tabel risiko, action scoring |
| Data visualization | Dashboard kinerja | Chart.js, ApexCharts, ECharts, KPI cards |
| Decision support | Pattern Recognition KB | Skor tindakan, rekomendasi skor tertinggi, keputusan manusia |
| UI/UX | Navigasi dan tampilan | Navbar, dropdown, card, chart, modal, responsive layout |

Tabel pemetaan teori di atas menunjukkan bahwa setiap modul tidak berdiri sendiri, tetapi merepresentasikan konsep sistem informasi tertentu. Hal ini penting untuk memperkuat argumen akademik bahwa website bukan sekadar kumpulan halaman HTML, melainkan rancangan sistem dengan dasar teoritis. Misalnya, dashboard terkait dengan data visualization, sedangkan pattern recognition dan action scoring terkait dengan knowledge management serta decision support.

Secara kritis, tabel ini juga membantu mengidentifikasi bagian yang masih lemah. Konsep decision support sudah hadir dalam bentuk scoring, tetapi belum didukung model prediktif atau database historis. Konsep sistem informasi berbasis web sudah hadir melalui akses browser, tetapi belum lengkap sebagai sistem multi-user. Dengan demikian, pemetaan teori bukan hanya pembenaran, tetapi juga alat evaluasi kesenjangan antara prototipe dan sistem ideal.

### 2.8 Kerangka Standar dan Literatur Pendukung

Pengembangan web app ini perlu diposisikan dalam kerangka standar yang relevan agar keputusan desainnya tidak bersifat arbitrer. Standar tidak digunakan sebagai daftar formal yang harus dipenuhi secara penuh pada tahap prototipe, tetapi sebagai rujukan untuk menilai apakah rancangan sistem telah bergerak ke arah tata kelola informasi, kualitas, risiko, dan pengembangan perangkat lunak yang dapat dipertanggungjawabkan.

| Standar/Literatur | Fokus Utama | Relevansi terhadap Web App | Tautan Resmi |
| --- | --- | --- | --- |
| PMBOK Guide dan The Standard for Project Management | Prinsip, domain kinerja, value delivery, tailoring, governance, risk, stakeholder, resources | Menjadi dasar pemikiran bahwa web app harus mendukung nilai proyek, pengendalian informasi, pemantauan kinerja, dan pengambilan keputusan | [PMI - PMBOK Guide](https://www.pmi.org/standards/pmbok) |
| ISO 21502:2020 | Panduan manajemen proyek untuk berbagai organisasi, kompleksitas, dan pendekatan delivery | Mendukung struktur metodologi pengembangan, pengendalian scope, stakeholder, resource, schedule, dan risk | [ISO 21502](https://committee.iso.org/sites/tc258/home/projects/published/iso-21502.html) |
| ISO 21511:2018 | Work Breakdown Structures untuk project dan programme management | Mendukung pemetaan aktivitas terminal, struktur knowledge base, dan hubungan WBS dengan risiko/tindakan | [ISO 21511](https://committee.iso.org/sites/tc258/home/projects/published/iso-21511-ed1.html) |
| ISO 31000:2018 | Prinsip dan pedoman manajemen risiko | Menjadi dasar pemetaan risiko, penyebab, tindakan preventive/corrective/predictive, serta action scoring | [ISO 31000](https://www.iso.org/standard/65694.html) |
| ISO 9001:2015 | Sistem manajemen mutu dan perbaikan berkelanjutan | Mendukung evaluasi kualitas informasi, konsistensi proses, dokumentasi, dan improvement cycle | [ISO 9001 Explained](https://www.iso.org/home/insights-news/resources/iso-9001-explained.html) |
| ISO 19650-1:2018 | Manajemen informasi pada aset bangunan dan pekerjaan sipil, termasuk BIM | Mendukung prinsip pengelolaan informasi aset, struktur data, versioning, dan kolaborasi informasi | [ISO 19650-1](https://www.iso.org/standard/68078.html) |
| ISO/IEC/IEEE 12207:2026 | Proses siklus hidup perangkat lunak | Mendukung argumentasi pengembangan sistem dari konsepsi, development, operation, maintenance, sampai retirement | [ISO/IEC/IEEE 12207](https://www.iso.org/standard/90219.html) |
| ISO/IEC 25010 | Model kualitas produk perangkat lunak | Mendukung penilaian kualitas web app dari sisi usability, reliability, maintainability, portability, security, dan performance | [ISO/IEC 25010 preview/adoption reference](https://standardsbis.bsbedge.com/BIS_Preview.aspx?id=16443_2024) |
| ISO 9241-210:2019 | Human-centred design untuk interactive systems | Mendukung pertimbangan UI/UX, kebutuhan pengguna, konteks penggunaan, dan evaluasi usability | [ISO 9241-210](https://www.iso.org/standard/77520.html) |
| WCAG 2.2 | Aksesibilitas konten web | Mendukung evaluasi aksesibilitas halaman, teks alternatif, kontras, navigasi keyboard, dan responsive accessibility | [W3C WCAG 2.2](https://www.w3.org/TR/WCAG22/) |
| OWASP ASVS | Standar verifikasi keamanan aplikasi web | Mendukung evaluasi keamanan, terutama kelemahan login client-side dan kebutuhan autentikasi server | [OWASP ASVS](https://owasp.org/www-project-application-security-verification-standard/) |

Pemilihan standar tersebut mencerminkan sifat web app sebagai sistem lintas-disiplin. PMBOK Guide dan ISO 21502 memberi dasar tata kelola proyek; ISO 21511 memberi dasar pemecahan pekerjaan dan struktur aktivitas; ISO 31000 memberi dasar risiko; ISO 9001 memberi dasar mutu; ISO 19650 memberi dasar manajemen informasi aset; ISO/IEC/IEEE 12207 dan ISO/IEC 25010 memberi dasar rekayasa perangkat lunak; ISO 9241-210 dan WCAG memberi dasar desain berpusat pengguna; OWASP ASVS memberi dasar keamanan aplikasi.

Secara kritis, standar-standar tersebut tidak boleh dibaca sebagai klaim bahwa sistem telah memenuhi seluruh persyaratan formal. Pada tahap saat ini, standar digunakan sebagai analytical lens untuk menilai kecukupan rancangan dan mengidentifikasi gap. Misalnya, sistem telah mendukung visualisasi kinerja dan knowledge base, tetapi belum memenuhi prinsip keamanan aplikasi web karena login masih berada di sisi client. Sistem telah memiliki struktur informasi, tetapi belum memenuhi pengelolaan informasi penuh karena belum ada versioning, audit trail, dan database.

### 2.9 Pemetaan Standar terhadap Keputusan Desain Sistem

| Keputusan Desain | Standar/Literatur Pendukung | Alasan Akademik | Keterbatasan Saat Ini |
| --- | --- | --- | --- |
| Menggunakan web app berbasis browser | ISO/IEC/IEEE 12207, ISO 9241-210 | Web app mendukung akses luas, interaksi, dan evaluasi pengguna | Belum ada siklus operasi dan maintenance formal |
| Menggunakan Waterfall dengan iterasi UI terbatas | PMBOK Guide, ISO 21502, ISO/IEC/IEEE 12207 | Cocok untuk scope prototipe yang relatif jelas, tetapi tetap membutuhkan penyesuaian desain | Belum ada change control formal |
| Menyusun knowledge base aktivitas terminal | ISO 21511, ISO 19650, ISO 9001 | Aktivitas perlu distrukturkan agar informasi dapat dicari, dipelajari, dan dievaluasi | Belum ada metadata, versioning, dan validasi pakar terpusat |
| Memetakan risiko dan tindakan | ISO 31000, PMBOK Guide | Risiko perlu diidentifikasi, dianalisis, dievaluasi, dan ditangani | Scoring belum berbasis data historis terverifikasi |
| Menampilkan dashboard KPI | PMBOK Guide, ISO 9001, ISO 21502 | Kinerja perlu dipantau untuk mendukung pengendalian dan improvement | Periode dan sumber data perlu didokumentasikan lebih rinci |
| Menggunakan localStorage | ISO/IEC 25010, OWASP ASVS | Memudahkan prototipe penyimpanan lokal keputusan | Tidak aman dan tidak mendukung multi-user |
| Menggunakan login client-side | OWASP ASVS | Menyediakan simulasi akses untuk prototipe | Tidak memenuhi keamanan aplikasi produksi |
| Menggunakan tabel, chart, card, dan navigasi visual | ISO 9241-210, WCAG 2.2 | Mendukung keterbacaan dan pengalaman pengguna | Perlu pengujian aksesibilitas dan usability formal |

Pemetaan tersebut menunjukkan bahwa setiap keputusan desain memiliki dasar dan konsekuensi. Keputusan teknis yang tampak sederhana, seperti penggunaan localStorage atau login client-side, sebenarnya memiliki implikasi terhadap keamanan, auditabilitas, dan tata kelola data. Dengan demikian, pembahasan sistem informasi harus menghindari narasi teknis yang terlalu optimistis. Sistem perlu dinilai berdasarkan kecocokan antara tujuan prototipe dan tingkat kematangan implementasi.

### 2.10 Posisi Web App sebagai Artefak Pengelolaan Informasi Proyek dan Aset

Web app ini dapat ditempatkan sebagai artefak digital yang mendukung pengelolaan informasi pada proses berbasis aset. Fungsi tersebut terlihat dari adanya pemetaan proses, WBS aktivitas, dokumentasi visual, knowledge base, dashboard kinerja, dan action scoring. Dalam kerangka PMBOK Guide dan ISO 21502, sistem seperti ini dapat dikaitkan dengan value delivery karena informasi disusun untuk membantu pengguna memahami kondisi, risiko, dan kinerja.

Dalam kerangka ISO 19650, informasi pada sistem belum dapat disebut sebagai information model yang matang karena belum memiliki struktur metadata, versioning, dan pertukaran data terkelola. Namun, arah pengembangannya sudah konsisten dengan prinsip pengorganisasian informasi aset. Folder aset, halaman profil, dashboard, dan knowledge base dapat menjadi embrio struktur informasi yang lebih formal.

Dalam kerangka ISO 31000, halaman pattern recognition menunjukkan upaya menghubungkan risiko dengan penyebab dan tindakan. Namun, sistem belum memiliki siklus risk management penuh karena belum ada prosedur identifikasi risiko formal, penilaian probabilitas/dampak berbasis data, risk owner, monitoring berkala, dan review tindakan. Oleh karena itu, modul risiko perlu diposisikan sebagai knowledge-assisted risk mapping.

Dalam kerangka ISO/IEC 25010, kualitas sistem saat ini kuat pada portability dan functional suitability untuk prototipe, tetapi masih lemah pada security, maintainability, dan scalability. Analisis ini penting karena sistem yang berfungsi belum tentu memiliki kualitas perangkat lunak yang memadai untuk penggunaan jangka panjang.

CATATAN PENYAJIAN: Tambahkan ilustrasi "peta teori terhadap modul sistem" dalam bentuk diagram matriks atau mind map.

Prompt ilustrasi:

```text
Buat mind map akademik berjudul "Pemetaan Teori terhadap Modul Web App Terminal Peti Kemas". Node tengah: Sistem Informasi Web App. Cabang: SDLC, Knowledge Management, Data Visualization, Decision Support, UI/UX. Hubungkan tiap cabang dengan modul: Login, Home, Profil Terminal, Knowledge Base, Pattern Recognition, Dashboard Kinerja. Gunakan gaya bersih, profesional, warna biru-putih, ikon minimalis, tanpa dekorasi berlebihan.
```

## 3. Metodologi Pengembangan

### 3.1 Model Pengembangan

Model pengembangan yang digunakan adalah Waterfall sederhana. Model ini dipilih karena kebutuhan utama sistem telah dapat didefinisikan sejak awal, yaitu menyajikan informasi terminal, knowledge base, alur proses, pattern recognition, dan dashboard kinerja. Waterfall juga sesuai untuk penyusunan laporan akademik karena setiap tahap dapat dijelaskan secara sistematis.

Walaupun model utama adalah Waterfall, proses implementasi teknis juga bersifat iteratif pada tahap desain antarmuka dan dashboard. Hal ini terlihat dari adanya beberapa halaman dashboard dan modul visual yang disesuaikan berdasarkan kebutuhan data.

Pemilihan Waterfall tidak berarti bahwa pengembangan web selalu paling tepat menggunakan model linear. Dalam banyak proyek perangkat lunak modern, Agile atau Scrum lebih sering dipilih karena kebutuhan berubah cepat dan melibatkan banyak iterasi pengguna. Namun, pada konteks penelitian dan prototipe ini, Waterfall lebih sesuai karena ruang lingkup sistem sudah ditetapkan dan dokumentasi setiap tahap dibutuhkan untuk kepentingan laporan akademik.

Kelemahan Waterfall adalah rendahnya fleksibilitas apabila kebutuhan berubah setelah implementasi. Untuk mengurangi kelemahan tersebut, pengembangan antarmuka dan dashboard tetap dilakukan secara iteratif dalam skala kecil. Dengan kata lain, metodologi yang digunakan dapat dipahami sebagai Waterfall dokumentatif dengan praktik iteratif pada desain visual. Pendekatan ini lebih jujur secara akademik dibandingkan menyatakan proses sepenuhnya linear.

Jika dikaitkan dengan PMBOK Guide dan ISO 21502, pemilihan model pengembangan harus dipahami sebagai proses tailoring. Artinya, pendekatan pengembangan tidak dipilih karena satu model dianggap paling benar, tetapi karena sesuai dengan tujuan, kompleksitas, sumber daya, dan tingkat ketidakpastian proyek. Pada web app ini, kebutuhan utama sudah dapat dirumuskan sejak awal sehingga pendekatan prediktif lebih mudah dipertanggungjawabkan. Namun, aspek UI/UX dan visualisasi data tetap membutuhkan iterasi karena kualitas tampilan baru dapat dinilai setelah pengguna melihat dan mencoba sistem.

Dengan demikian, metodologi yang digunakan bukan Waterfall murni dalam pengertian mekanis, melainkan predictive development dengan ruang adaptasi terbatas. Formulasi ini lebih kuat secara akademik karena mengakui bahwa pengembangan perangkat lunak, sekalipun dalam proyek yang terstruktur, tetap membutuhkan evaluasi ulang terhadap tampilan, keterbacaan informasi, dan usability.

### 3.2 Tahapan Pengembangan

| Tahap | Aktivitas | Output |
| --- | --- | --- |
| Analisis kebutuhan | Mengidentifikasi kebutuhan pengguna, fitur, dan informasi terminal | Daftar kebutuhan sistem dan modul halaman |
| Pengumpulan data/aset | Mengumpulkan data kinerja, gambar terminal, video, flowchart, dan materi aktivitas | Dataset statis, gambar, video, dan dokumen visual |
| Perancangan arsitektur | Menentukan bentuk static web app, struktur halaman, aset, dan library | Arsitektur client-side dan sitemap |
| Perancangan UI | Membuat layout halaman login, home, profil, dashboard, dan knowledge base | Rancangan antarmuka |
| Implementasi | Menulis HTML, CSS, JavaScript, chart, filter, scoring, dan navigasi | File website siap dijalankan |
| Pengujian | Menguji fitur, halaman, chart, responsivitas, dan export | Hasil black-box test |
| Evaluasi | Menilai kelebihan, kekurangan, dan rekomendasi pengembangan | Diskusi dan saran pengembangan |

Setiap tahap pada tabel tersebut memiliki konsekuensi terhadap mutu sistem. Analisis kebutuhan menentukan apakah fitur yang dibuat benar-benar relevan; pengumpulan data/aset menentukan apakah konten sistem dapat dipercaya; perancangan arsitektur menentukan batas kemampuan teknis; perancangan UI menentukan keterbacaan; implementasi menentukan fungsi; pengujian menentukan kelayakan; dan evaluasi menentukan arah pengembangan. Dengan demikian, metodologi tidak hanya menjadi urutan kerja, tetapi juga kerangka kendali kualitas.

Pada tahap pengumpulan data/aset, perhatian khusus perlu diberikan pada validitas data operasional. Dataset yang ditanam dalam halaman dashboard perlu dijelaskan sumber, periode, dan batas interpretasinya. Tanpa kejelasan tersebut, chart dapat terlihat meyakinkan tetapi belum tentu memiliki kekuatan analitis yang cukup. Oleh karena itu, laporan final sebaiknya menambahkan keterangan sumber data pada setiap dashboard.

Tahapan pengembangan juga dapat dibaca melalui prinsip quality management. Mengacu pada pendekatan perbaikan berkelanjutan dalam ISO 9001, sistem tidak cukup hanya "selesai dibuat"; sistem perlu dievaluasi, ditemukan ketidaksesuaian, lalu diperbaiki. Dalam konteks web app ini, siklus tersebut dapat diterapkan melalui pengujian fungsi, evaluasi usability, perbaikan visualisasi, optimasi aset, dan penyusunan rekomendasi backend/database.

Keterkaitan dengan ISO/IEC/IEEE 12207 terlihat pada kebutuhan untuk memandang web app sebagai produk perangkat lunak yang memiliki siklus hidup. Pada tahap prototipe, fokus berada pada development dan verification. Pada tahap lanjutan, sistem perlu memasuki operation, maintenance, dan retirement planning. Dengan demikian, pengembangan tidak berhenti pada file HTML yang berjalan, tetapi juga mencakup rencana keberlanjutan sistem.

### 3.3 Kebutuhan Fungsional

| Kode | Kebutuhan Fungsional | Modul Terkait | Status Implementasi |
| --- | --- | --- | --- |
| KF-01 | Sistem menyediakan halaman login | `index.html` | Sudah |
| KF-02 | Sistem mengarahkan pengguna ke halaman utama setelah login | `index.html`, `home.html` | Sudah |
| KF-03 | Sistem menyediakan navigasi antarhalaman | Semua halaman utama | Sudah |
| KF-04 | Sistem menampilkan profil terminal | Halaman profil TPK | Sudah |
| KF-05 | Sistem menampilkan knowledge base aktivitas terminal | `knowledge-base.html`, folder `activity` | Sudah |
| KF-06 | Sistem menampilkan alur proses peti kemas | `alur-penanganan.html` | Sudah |
| KF-07 | Sistem menampilkan flowchart pemuatan dan pembongkaran | `alur-penanganan.html`, aset proses | Sudah |
| KF-08 | Sistem menampilkan pattern recognition map | `pattern-recognition-knowledge-base.html` | Sudah |
| KF-09 | Sistem menyediakan scoring tindakan | `pattern-recognition-knowledge-base.html` | Sudah |
| KF-10 | Sistem menyimpan skor dan keputusan pada browser | `localStorage` | Sudah |
| KF-11 | Sistem mengekspor keputusan ke CSV | `pattern-recognition-knowledge-base.html` | Sudah |
| KF-12 | Sistem menampilkan dashboard kinerja | Halaman dashboard | Sudah |
| KF-13 | Sistem menyediakan export chart | Beberapa dashboard | Sudah pada beberapa halaman |
| KF-14 | Sistem menyediakan manajemen data admin | Backend/database lanjutan | Belum |
| KF-15 | Sistem menyediakan autentikasi server | Backend lanjutan | Belum |

Kebutuhan fungsional di atas menunjukkan bahwa mayoritas fungsi presentasional dan analitis telah tersedia, sementara fungsi administratif dan keamanan masih berada pada tahap rancangan lanjutan. Hal ini konsisten dengan posisi sistem sebagai prototipe. Fungsi seperti login, navigasi, dashboard, dan scoring dibangun untuk membuktikan alur kerja sistem, sedangkan autentikasi server dan manajemen data belum diprioritaskan karena membutuhkan backend.

Secara kritis, daftar kebutuhan fungsional ini juga memperlihatkan perbedaan antara fitur yang terlihat oleh pengguna dan fitur yang dibutuhkan untuk operasional jangka panjang. Pengguna dapat melihat chart dan melakukan scoring, tetapi pengelola sistem belum dapat memperbarui data secara mudah. Kesenjangan ini menjadi dasar rekomendasi penambahan admin panel, database, dan API pada tahap berikutnya.

### 3.4 Kebutuhan Nonfungsional

| Aspek | Kebutuhan | Kondisi Saat Ini | Catatan |
| --- | --- | --- | --- |
| Usability | Mudah digunakan dan dipahami | Navigasi, card, chart, dan dropdown tersedia | Perlu validasi dengan SUS/UAT |
| Portability | Mudah dijalankan di browser | Static web app | Cocok untuk prototipe dan presentasi |
| Performance | Halaman dapat dimuat dengan lancar | Umumnya cepat, tetapi tergantung aset dan CDN | Perlu pengukuran Lighthouse |
| Reliability | Chart dan navigasi berjalan stabil | Bergantung pada file lokal dan CDN | Library lokal dibutuhkan untuk mode offline |
| Security | Login dan data aman | Login masih client-side | Perlu backend authentication |
| Maintainability | Data mudah diperbarui | Data masih tertanam dalam HTML/JS | Perlu database dan CMS/admin panel |
| Scalability | Mendukung banyak pengguna dan data | Belum optimal | Perlu server dan database |

Kebutuhan nonfungsional sering kali lebih menentukan kelayakan sistem produksi dibandingkan kebutuhan fungsional. Sebuah fitur dapat berjalan, tetapi belum tentu aman, mudah dipelihara, atau mampu melayani banyak pengguna. Pada sistem ini, portability dan kemudahan demonstrasi menjadi keunggulan utama, sedangkan security, scalability, dan maintainability menjadi area paling lemah.

Keputusan untuk memprioritaskan portability dapat dibenarkan karena sistem berada pada tahap prototipe akademik. Namun, keputusan tersebut tidak boleh menutupi risiko teknis. Login client-side, data hardcoded, dan localStorage harus ditulis sebagai batasan eksplisit. Dengan demikian, pembaca memahami bahwa sistem berhasil sebagai prototipe, tetapi masih memerlukan rekayasa ulang apabila digunakan secara operasional.

Kebutuhan nonfungsional tersebut dapat diperluas menggunakan model kualitas ISO/IEC 25010. Functional suitability terlihat pada kemampuan sistem menyediakan modul yang dibutuhkan. Usability terlihat pada penggunaan navigasi, card, chart, dan struktur visual. Performance efficiency perlu diuji karena halaman dashboard memuat banyak library dan data. Compatibility perlu diperhatikan apabila sistem dibuka pada browser berbeda. Reliability belum dapat dinilai penuh karena belum ada monitoring. Security masih lemah karena autentikasi berada di client. Maintainability menjadi tantangan karena banyak kode terpisah di file HTML. Portability menjadi kekuatan karena sistem mudah dijalankan sebagai static web app.

Analisis berbasis ISO/IEC 25010 membantu membuat evaluasi lebih sistematis. Tanpa model kualitas, pembahasan nonfungsional mudah berubah menjadi daftar umum. Dengan model kualitas, setiap aspek dapat dikaitkan dengan risiko desain dan rekomendasi teknis yang spesifik.

CATATAN PENYAJIAN: Subbab metodologi dapat dilengkapi dengan flow SDLC dari analisis sampai evaluasi.

Prompt ilustrasi:

```text
Buat diagram alur Waterfall untuk pengembangan web app terminal peti kemas. Tahapan: Analisis Kebutuhan, Pengumpulan Data dan Aset, Perancangan Arsitektur, Perancangan UI, Implementasi, Pengujian, Evaluasi. Tambahkan output kecil di bawah tiap tahap. Gaya akademik, bersih, warna biru laut dan abu-abu, format 16:9.
```

## 4. Arsitektur Sistem

### 4.1 Arsitektur Saat Ini

Arsitektur sistem saat ini adalah client-side static web app. Pengguna membuka website melalui browser. Browser memuat file HTML, CSS, JavaScript, gambar, video, dan library eksternal dari CDN. Pemrosesan data dashboard, rendering chart, filter, scoring, dan interaksi halaman dilakukan langsung di sisi browser. Pada halaman pattern recognition, sebagian data input pengguna disimpan di `localStorage`.

Arsitektur ini dipilih karena sesuai dengan tujuan awal pengembangan, yaitu membuat prototipe yang mudah dijalankan dan mudah dievaluasi tanpa memerlukan instalasi server, konfigurasi database, atau deployment backend. Dalam konteks akademik, keputusan ini mempercepat proses pembuktian konsep karena fokus pengembangan dapat diarahkan pada penyusunan informasi, tampilan dashboard, dan pemetaan knowledge base.

Namun, arsitektur client-side static memiliki batas yang jelas. Seluruh logika validasi dan sebagian data dapat dilihat melalui browser, sehingga tidak cocok untuk menyimpan informasi sensitif. Selain itu, karena tidak ada API dan database, sistem belum dapat melakukan sinkronisasi data lintas pengguna. Oleh karena itu, arsitektur saat ini lebih tepat disebut sebagai arsitektur demonstratif dan bukan arsitektur operasional produksi.

Jika dikaitkan dengan OWASP ASVS, arsitektur ini belum memenuhi prinsip verifikasi keamanan aplikasi web karena autentikasi, kontrol akses, dan penyimpanan data belum berada pada lingkungan yang terlindungi. Validasi di sisi client hanya dapat digunakan untuk kenyamanan pengguna, bukan sebagai kontrol keamanan utama. Oleh karena itu, rancangan arsitektur harus secara eksplisit membedakan antara fitur simulatif dan fitur produksi.

Dari perspektif ISO 19650, arsitektur saat ini juga belum menyediakan information management environment yang lengkap. Informasi memang telah dikumpulkan dalam halaman dan folder aset, tetapi belum ada pengaturan formal mengenai penamaan, versioning, status informasi, approval, dan pertukaran data. Hal ini menunjukkan bahwa web app telah memulai pengorganisasian informasi, tetapi belum mencapai tata kelola informasi aset yang matang.

Alur kerja arsitektur saat ini:

1. Pengguna membuka `index.html`.
2. Pengguna memasukkan username dan password.
3. JavaScript melakukan validasi akun statis.
4. Jika valid, pengguna diarahkan ke `home.html`.
5. Pengguna memilih modul melalui navbar.
6. Browser memuat halaman HTML terkait.
7. JavaScript pada halaman menjalankan chart, filter, modal, slider, scoring, dan export.
8. Data keputusan tertentu disimpan di `localStorage`.

Alur tersebut memperlihatkan bahwa browser memiliki peran sangat dominan. Dominasi browser membuat sistem ringan dari sisi server, tetapi menambah beban pada perangkat pengguna. Halaman dengan dataset besar, tabel panjang, atau chart kompleks dapat mengalami penurunan performa pada perangkat berspesifikasi rendah. Oleh sebab itu, optimasi aset, pembatasan ukuran dataset, dan pemilihan chart yang tepat menjadi perhatian penting.

### 4.2 Komponen Arsitektur

| Komponen | Peran | Implementasi Saat Ini |
| --- | --- | --- |
| Browser/client | Menjalankan halaman, JavaScript, chart, dan interaksi | Chrome/Edge/Firefox |
| HTML pages | Struktur halaman dan konten | `index.html`, `home.html`, dashboard, profil, knowledge base |
| CSS | Layout, warna, animasi, responsivitas | Inline CSS pada masing-masing file HTML dan framework CDN |
| JavaScript | Login, chart, filter, scoring, export, modal, slider | Script internal pada halaman |
| Aset lokal | Foto, video, flowchart, ilustrasi | Folder `aset`, `aset proses penanganan`, `slidingphoto`, `Dokum semarang` |
| CDN library | Library UI, ikon, chart, font | Chart.js, ApexCharts, ECharts, Swiper, Font Awesome, Google Fonts |
| localStorage | Penyimpanan lokal skor dan keputusan | Halaman pattern recognition |
| Backend server | Autentikasi dan API | Belum tersedia |
| Database | Penyimpanan data terpusat | Belum tersedia |

Komponen arsitektur di atas menunjukkan adanya pemisahan antara komponen yang sudah konkret dan komponen yang masih konseptual. Browser, HTML, CSS, JavaScript, aset lokal, CDN, dan localStorage sudah digunakan secara langsung. Sebaliknya, backend server dan database belum diimplementasikan, tetapi tetap dicantumkan untuk menunjukkan celah pengembangan. Pencantuman ini penting agar pembahasan arsitektur tidak berhenti pada kondisi saat ini, tetapi juga membuka evaluasi tentang apa yang dibutuhkan agar sistem naik kelas menjadi aplikasi produksi.

Keputusan menggunakan CDN perlu dibaca secara kritis. CDN mempermudah pemanggilan library dan mengurangi kebutuhan menyimpan file dependency secara lokal, tetapi menciptakan ketergantungan terhadap koneksi internet dan ketersediaan layanan pihak ketiga. Untuk prototipe, risiko ini masih dapat diterima. Untuk produksi atau demonstrasi offline, library perlu dibundel secara lokal.

### 4.3 Struktur File dan Modul

| Modul | File/Folder | Fungsi Utama |
| --- | --- | --- |
| Login | `index.html` | Validasi akun statis dan redirect ke home |
| Home | `home.html` | Halaman utama, profil umum, statistik, slider, navigasi |
| Knowledge Base | `knowledge-base.html`, `activity/` | Daftar aktivitas terminal dan detail aktivitas |
| Pattern Recognition | `pattern-recognition-knowledge-base.html` | Pemetaan risiko, scoring tindakan, export CSV |
| Alur proses | `alur-penanganan.html`, `aset proses penanganan/`, `Alur baru/` | Flowchart dan penjelasan pemuatan/pembongkaran |
| Profil terminal | `profil-surabaya.html`, `profil-semarang.html`, `profil-makassar.html`, `profil-IPC-TPK.html` | Informasi terminal dan indikator kinerja |
| Dashboard Semarang | `kinerja-operasional-semarang.html`, `availability-utilization-semarang.html`, `YOR-semarang.html` | Analisis operasional Semarang |
| Dashboard Makassar | `kinerja-makassar.html`, `YOR-makassar.html`, `kunjungan-kapal-makassar.html`, `operasional-makassar.html` | Analisis operasional Makassar |
| Dashboard Surabaya | `kinerja-operasional-surabaya.html` | Analisis operasional Surabaya/Teluk Lamong |
| Dokumentasi | `dokum-semarang.html`, folder media | Dokumentasi visual terminal |

Struktur file menunjukkan pendekatan halaman terpisah atau multi-page static website. Pendekatan ini sederhana dan mudah dipahami karena setiap modul memiliki file sendiri. Keunggulannya adalah proses debugging lebih langsung dan setiap halaman dapat dibuka secara independen. Kekurangannya, komponen yang berulang seperti navbar, footer, style, atau script harus dipelihara di banyak file. Hal ini dapat menimbulkan inkonsistensi jika perubahan desain dilakukan hanya pada sebagian halaman.

Jika sistem dikembangkan lebih lanjut, struktur file sebaiknya ditata ulang menggunakan komponen reusable, template engine, atau frontend framework. Tujuannya bukan semata mengikuti tren teknologi, tetapi mengurangi duplikasi kode dan meningkatkan maintainability. Dengan demikian, pemilihan struktur static multi-page saat ini dapat dianggap tepat untuk prototipe, tetapi belum efisien untuk pengembangan jangka panjang.

### 4.4 Aliran Data

| Sumber Data | Bentuk Data | Diproses Oleh | Output |
| --- | --- | --- | --- |
| Dataset statis di JavaScript | Array/object | Fungsi kalkulasi KPI dan chart | KPI, tabel, grafik |
| Aset gambar dan video | JPG, PNG, WebP, MP4 | HTML/CSS/browser | Galeri, slider, ilustrasi proses |
| Input login | Username/password | JavaScript client-side | Akses ke halaman home atau pesan error |
| Input filter dashboard | Pilihan/select/search | JavaScript filter | Chart dan tabel terbarui |
| Input scoring | Nilai 1-5 | JavaScript dan localStorage | Total skor dan rekomendasi |
| Input keputusan pengguna | Pilihan dan catatan | localStorage | Riwayat keputusan lokal |
| Tombol export | Data keputusan/chart | JavaScript Blob/canvas | CSV atau PNG |

Aliran data pada sistem ini bersifat lokal dan satu arah dalam banyak kasus. Dataset yang sudah tertanam di JavaScript diproses menjadi tampilan, tetapi perubahan data oleh pengguna tidak dikembalikan ke sumber data utama. Satu-satunya penyimpanan perubahan berada pada `localStorage`, yaitu penyimpanan lokal browser. Konsekuensinya, data keputusan bersifat personal terhadap perangkat/browser tertentu dan belum dapat digunakan sebagai basis kolaborasi.

Secara akademik, kondisi ini perlu dijelaskan agar pembaca tidak menganggap sistem sudah memiliki database. Dalam sistem informasi ideal, aliran data seharusnya memiliki mekanisme input, validasi, penyimpanan, pembaruan, dan audit. Pada prototipe ini, aliran data lebih tepat disebut sebagai aliran presentasi dan interaksi lokal.

### 4.5 Perbandingan Arsitektur Saat Ini dan Arsitektur Lanjutan

| Aspek | Arsitektur Saat Ini: Static Client-Side | Arsitektur Lanjutan: Full Web App |
| --- | --- | --- |
| Hosting | Static hosting atau file lokal | Web server + application server |
| Autentikasi | Validasi akun di JavaScript | Login server-side, password hashing, session/JWT |
| Database | Belum ada database terpusat | MySQL/PostgreSQL/MongoDB |
| API | Belum ada | REST API atau GraphQL |
| Penyimpanan keputusan | `localStorage` browser | Database server |
| Multi-user | Terbatas | Mendukung multi-user dan role |
| Keamanan | Rendah untuk produksi | Lebih aman dengan backend |
| Pembaruan data | Edit file HTML/JS | Form admin atau import data |
| Koneksi internet | Diperlukan untuk CDN | Dapat dibuat offline-ready dengan asset bundling |
| Cocok untuk | Prototipe, demo, laporan akademik | Sistem operasional produksi |

Komparasi tersebut memperjelas bahwa tidak ada arsitektur yang selalu unggul untuk semua konteks. Static client-side lebih unggul dalam kesederhanaan, portabilitas, dan kecepatan pengembangan. Full web app lebih unggul dalam keamanan, integritas data, kolaborasi, dan skalabilitas. Dengan demikian, pilihan arsitektur harus dinilai berdasarkan tujuan. Untuk tahap pembuktian konsep, arsitektur saat ini tepat; untuk tahap operasional, arsitektur ini perlu ditingkatkan.

Pertimbangan ini juga menjelaskan mengapa pengembangan lanjutan tidak sekadar menambahkan fitur, tetapi mengubah fondasi sistem. Perpindahan dari static app ke full web app berarti menambahkan lapisan backend, database, autentikasi, role access, dan tata kelola data. Perubahan tersebut akan meningkatkan kompleksitas, tetapi diperlukan untuk menjamin keamanan dan keberlanjutan sistem.

### 4.6 Rancangan Arsitektur Pengembangan Lanjutan

Jika sistem dikembangkan menjadi aplikasi produksi, arsitektur yang disarankan adalah:

1. Frontend: HTML/CSS/JavaScript atau framework seperti React/Vue.
2. Backend API: Node.js/Express, Laravel, Django, atau framework sejenis.
3. Database: PostgreSQL atau MySQL untuk menyimpan user, terminal, aktivitas, risiko, tindakan, scoring, dan dataset kinerja.
4. Authentication: login server-side dengan hashing password dan role-based access control.
5. Admin panel: fitur tambah/edit/hapus data dashboard dan knowledge base.
6. File storage: penyimpanan aset gambar, video, dan dokumen.
7. Reporting: export PDF, CSV, dan dashboard summary.

Rancangan arsitektur lanjutan di atas disusun berdasarkan kelemahan utama sistem saat ini. Backend diperlukan untuk memindahkan proses autentikasi dari client ke server. Database diperlukan untuk menyimpan data secara terpusat. Admin panel diperlukan agar pembaruan data tidak lagi dilakukan dengan mengedit kode. File storage diperlukan agar aset visual dapat dikelola secara terstruktur. Reporting diperlukan karena sistem informasi operasional umumnya tidak hanya dibaca di layar, tetapi juga digunakan sebagai bahan laporan.

Namun, pengembangan menuju arsitektur produksi juga memiliki konsekuensi. Kompleksitas deployment meningkat, kebutuhan keamanan bertambah, dan proses maintenance menjadi lebih besar. Oleh karena itu, pengembangan lanjutan sebaiknya dilakukan bertahap. Tahap pertama dapat dimulai dari pemisahan data ke file JSON atau API sederhana, kemudian dilanjutkan dengan database, autentikasi, dan admin panel.

Pada tahap produksi, arsitektur lanjutan sebaiknya dirancang dengan prinsip traceability. Setiap data risiko, tindakan, skor, dan keputusan perlu memiliki sumber, waktu pembaruan, pihak yang memperbarui, dan status validasi. Prinsip ini sejalan dengan kebutuhan audit dalam manajemen informasi dan mutu. Tanpa traceability, sistem dapat menyajikan informasi, tetapi sulit mempertanggungjawabkan asal-usul dan validitas informasi tersebut.

Rancangan lanjutan juga perlu memperhitungkan aksesibilitas sejak awal. WCAG 2.2 dapat digunakan untuk mengevaluasi apakah informasi pada dashboard, tabel, tombol, dan chart tetap dapat diakses oleh pengguna dengan kebutuhan berbeda. Pada sistem yang memuat banyak grafik, aksesibilitas menjadi isu penting karena tidak semua pengguna dapat memahami informasi visual tanpa teks alternatif, label yang jelas, dan navigasi keyboard.

CATATAN PENYAJIAN: Bagian arsitektur wajib didampingi diagram. Buat dua diagram: arsitektur saat ini dan arsitektur pengembangan lanjutan.

Prompt diagram arsitektur saat ini:

```text
Buat diagram arsitektur static client-side web app untuk sistem informasi terminal peti kemas. Tampilkan User Browser di kiri, lalu Static HTML Pages, CSS, JavaScript Modules, Local Assets, CDN Libraries, dan Browser localStorage. Jelaskan bahwa chart rendering, filter, login statis, scoring, dan export berjalan di browser. Tidak ada backend dan tidak ada database server. Gaya diagram teknis akademik, warna biru, putih, abu-abu, ikon browser, file HTML, chart, folder aset, cloud CDN, dan localStorage.
```

Prompt diagram arsitektur lanjutan:

```text
Buat diagram arsitektur target full-stack web app untuk sistem informasi terminal peti kemas. Tampilkan User Browser -> Frontend Web App -> Backend API -> Database Server. Tambahkan Authentication Service, Admin Panel, File Storage, Dashboard Analytics, Knowledge Base Service, dan Export Report. Gunakan gaya profesional, clean architecture, warna biru laut dan hijau, format 16:9, cocok untuk bab metodologi skripsi.
```

## 5. Perancangan Sistem

### 5.1 Use Case Sistem

Use case utama sistem adalah:

| Aktor | Use Case | Deskripsi |
| --- | --- | --- |
| Pengguna | Login | Memasukkan username dan password untuk masuk ke sistem |
| Pengguna | Melihat halaman utama | Membaca ringkasan profil dan navigasi |
| Pengguna | Melihat profil terminal | Membuka informasi terminal dan indikator kinerja |
| Pengguna | Membuka knowledge base | Melihat aktivitas terminal dan detail pekerjaan |
| Pengguna | Membuka alur proses peti kemas | Memahami alur pemuatan dan pembongkaran |
| Pengguna | Membuka dashboard kinerja | Melihat KPI, chart, tren, dan tabel |
| Pengguna | Menggunakan filter dashboard | Menyesuaikan data yang ditampilkan |
| Pengguna/Pakar | Memberi skor tindakan | Menilai preventive, corrective, dan predictive measure |
| Pengguna/Pakar | Menyimpan keputusan | Memilih tindakan dan menulis catatan keputusan |
| Pengguna/Pakar | Mengekspor data | Mengunduh CSV atau chart PNG |

Use case di atas dipilih karena mewakili aktivitas utama pengguna dalam sistem, yaitu mengakses informasi, memahami proses, menganalisis data, dan membuat keputusan awal. Use case tidak mencantumkan transaksi operasional seperti mengubah jadwal kapal atau memasukkan data real-time karena fungsi tersebut berada di luar ruang lingkup prototipe.

Secara kritis, use case juga memperlihatkan batas tanggung jawab sistem. Sistem menyediakan informasi dan rekomendasi berbasis skor, tetapi tidak mengeksekusi keputusan operasional. Hal ini penting agar sistem tidak dipahami sebagai pengganti kewenangan operator atau manajemen terminal. Posisi sistem adalah decision support, bukan decision maker.

Prompt use case diagram:

```text
Buat use case diagram UML untuk web app sistem informasi terminal peti kemas. Aktor utama: Pengguna, Pakar/Operator, Admin Pengembangan Lanjutan. Use case: Login, Melihat Home, Melihat Profil Terminal, Membuka Knowledge Base, Membuka Alur Proses Peti Kemas, Melihat Dashboard Kinerja, Memfilter Data, Memberi Action Scoring, Menyimpan Keputusan, Export CSV/PNG, Mengelola Data (khusus admin lanjutan). Gunakan gaya UML bersih hitam-putih dengan aksen biru.
```

### 5.2 Activity Diagram

Alur aktivitas pengguna:

1. Pengguna membuka halaman login.
2. Pengguna memasukkan username dan password.
3. Sistem memvalidasi input.
4. Jika salah, sistem menampilkan pesan error.
5. Jika benar, sistem mengarahkan pengguna ke home.
6. Pengguna memilih menu.
7. Sistem menampilkan halaman sesuai menu.
8. Jika pengguna membuka dashboard, sistem memuat dataset dan menampilkan chart.
9. Jika pengguna membuka pattern recognition, sistem menampilkan relasi KB dan opsi scoring.
10. Pengguna dapat melakukan filter, scoring, menyimpan keputusan, atau export data.

Activity diagram perlu disusun untuk memperlihatkan titik keputusan pengguna dan sistem. Pada tahap login, sistem mengambil keputusan sederhana berdasarkan kecocokan username dan password. Pada tahap pemilihan menu, pengguna menentukan jalur informasi. Pada tahap dashboard dan pattern recognition, pengguna berinteraksi dengan data melalui filter, scoring, dan export.

Kritik utama terhadap alur aktivitas saat ini adalah tidak adanya proses validasi server dan pencatatan audit. Dalam sistem produksi, aktivitas login, perubahan skor, dan export data seharusnya dapat dicatat untuk kebutuhan keamanan dan akuntabilitas. Karena sistem masih prototipe, pencatatan tersebut belum dilakukan. Keterbatasan ini dapat dijadikan dasar rekomendasi pengembangan.

Prompt activity diagram:

```text
Buat activity diagram UML untuk alur penggunaan web app terminal peti kemas. Mulai dari buka login, input username/password, validasi, kondisi salah menampilkan error, kondisi benar menuju home, pilih menu, buka profil/knowledge base/alur proses/dashboard/pattern recognition, lakukan filter atau scoring, simpan keputusan, export data, selesai. Gunakan swimlane sederhana antara Pengguna dan Sistem.
```

### 5.3 Sitemap dan Struktur Navigasi

| Level | Halaman | Relasi Navigasi |
| --- | --- | --- |
| 0 | `index.html` | Titik awal/login |
| 1 | `home.html` | Halaman utama setelah login |
| 2 | `knowledge-base.html` | Menu utama Knowledge Base |
| 3 | `activity/aktivitas1.html` sampai `activity/aktivitas6.html` | Detail aktivitas terminal |
| 2 | `pattern-recognition-knowledge-base.html` | Pattern Recognition KB |
| 2 | `alur-penanganan.html` | Alur proses peti kemas |
| 2 | `profil-surabaya.html` | Profil TPK Teluk Lamong Surabaya |
| 2 | `profil-semarang.html` | Profil TPK Semarang |
| 2 | `profil-makassar.html` | Profil TPK Makassar New Port |
| 2 | `profil-IPC-TPK.html` | Profil IPC TPK |
| 3 | Dashboard kinerja | Terhubung dari halaman profil/menu terkait |

Sitemap menunjukkan bahwa sistem menggunakan struktur navigasi bercabang dari halaman utama. Struktur ini dipilih karena pengguna perlu mengakses berbagai jenis informasi yang cukup berbeda: profil, knowledge base, alur proses, pattern recognition, dan dashboard. Dengan menggunakan halaman terpisah, setiap modul dapat memiliki ruang tampilan yang lebih fokus.

Kelemahan struktur ini adalah potensi fragmentasi pengalaman pengguna. Jika navigasi tidak konsisten di seluruh halaman, pengguna dapat kehilangan orientasi. Oleh karena itu, navbar tetap dan dropdown profil menjadi komponen penting. Untuk pengembangan lanjutan, sitemap sebaiknya disederhanakan melalui routing yang lebih terstruktur atau layout template agar pengguna merasakan konsistensi antarmodul.

Prompt sitemap:

```text
Buat sitemap visual untuk website terminal peti kemas. Root: index.html/Login. Setelah login menuju home.html. Dari home bercabang ke Knowledge Base, Pattern Recognition KB, Alur Penanganan Proses Petikemas, Profil TPK, dan Dashboard Kinerja. Di bawah Knowledge Base tampilkan enam aktivitas: Berth Allocation, Manning & Deployment, Ship Planner, Yard Planner, Ship Talker, Yard Talker. Di bawah Profil TPK tampilkan Teluk Lamong Surabaya, Semarang, Makassar New Port, IPC TPK. Gaya diagram pohon rapi, akademik, warna biru dan abu-abu.
```

### 5.4 Rancangan Data Konseptual

Karena sistem saat ini belum memiliki database, rancangan data berikut digunakan sebagai acuan pengembangan lanjutan.

| Entitas | Atribut Utama | Keterangan |
| --- | --- | --- |
| `users` | `id_user`, `username`, `password_hash`, `role` | Menyimpan data pengguna dan hak akses |
| `terminal` | `id_terminal`, `nama_terminal`, `lokasi`, `profil` | Menyimpan profil terminal |
| `aktivitas` | `id_aktivitas`, `id_terminal`, `kode_aktivitas`, `nama_aktivitas`, `kategori` | Menyimpan aktivitas operasional |
| `risiko` | `id_risiko`, `id_aktivitas`, `kode_risiko`, `deskripsi_risiko` | Menyimpan risiko pada aktivitas |
| `penyebab` | `id_penyebab`, `id_risiko`, `deskripsi_penyebab` | Menyimpan penyebab risiko |
| `tindakan` | `id_tindakan`, `id_risiko`, `jenis`, `deskripsi_tindakan` | Preventive, corrective, predictive |
| `scoring` | `id_scoring`, `id_tindakan`, `efektif`, `mudah`, `cepat`, `dampak`, `kesiapan` | Menyimpan nilai tindakan |
| `keputusan` | `id_keputusan`, `id_user`, `id_tindakan`, `catatan`, `tanggal` | Menyimpan keputusan manusia |
| `dataset_kinerja` | `id_data`, `id_terminal`, `periode`, `indikator`, `nilai` | Menyimpan data dashboard |

Rancangan data konseptual dibuat untuk menjembatani kondisi sistem saat ini dengan kebutuhan pengembangan lanjutan. Karena data masih hardcoded, sistem belum memiliki model data eksplisit di level database. Tabel entitas di atas menunjukkan bagaimana data seharusnya dinormalisasi jika sistem diubah menjadi aplikasi berbasis database.

Pemilihan entitas `aktivitas`, `risiko`, `penyebab`, `tindakan`, `scoring`, dan `keputusan` didasarkan pada struktur pengetahuan yang sudah muncul pada halaman pattern recognition. Dengan demikian, rancangan database bukan dibuat secara abstrak, tetapi diturunkan dari modul yang sudah berjalan. Pendekatan ini membuat pengembangan lanjutan lebih realistis karena mengikuti kebutuhan aktual sistem.

Prompt ERD:

```text
Buat Entity Relationship Diagram untuk rancangan database sistem informasi terminal peti kemas. Entitas: users, terminal, aktivitas, risiko, penyebab, tindakan, scoring, keputusan, dataset_kinerja. Tampilkan relasi: terminal memiliki banyak aktivitas, aktivitas memiliki banyak risiko, risiko memiliki banyak penyebab dan tindakan, tindakan memiliki scoring, user membuat keputusan, terminal memiliki banyak dataset_kinerja. Gunakan notasi crow's foot, gaya akademik hitam-putih dengan sedikit aksen biru.
```

## 6. Teknologi dan Tools

### 6.1 Stack Teknologi

| Kategori | Teknologi | Fungsi |
| --- | --- | --- |
| Markup | HTML5 | Struktur halaman |
| Styling | CSS3 | Desain visual, layout, animasi, responsivitas |
| Programming | JavaScript | Interaksi, validasi, chart, scoring, export |
| Charting | Chart.js | Line, bar, scatter, radar, donut chart |
| Charting | ApexCharts | Gauge/radial chart dan visualisasi analitis |
| Charting | ECharts | Dashboard analisis yang lebih kompleks |
| UI helper | Bootstrap/Tailwind CSS | Layout dan komponen pada beberapa dashboard |
| Icon | Font Awesome | Ikon menu, tombol, kartu, dan dashboard |
| Slider | Swiper.js | Slider gambar pada halaman profil/dokumentasi |
| Font | Google Fonts/Poppins | Tipografi |
| Storage | localStorage | Penyimpanan skor dan keputusan lokal |
| Asset | WebP, JPG, PNG, MP4 | Gambar, flowchart, dokumentasi, video |

Stack teknologi yang digunakan menunjukkan kompromi antara kemudahan implementasi dan kelengkapan fungsi. HTML, CSS, dan JavaScript dipilih karena dapat langsung dijalankan di browser. Chart.js, ApexCharts, dan ECharts dipilih karena masing-masing memiliki keunggulan dalam visualisasi tertentu. Font Awesome dan Swiper membantu mempercepat pembangunan antarmuka tanpa membuat seluruh komponen dari awal.

Secara kritis, penggunaan banyak library sekaligus dapat meningkatkan ukuran halaman dan kompleksitas pemeliharaan. Jika setiap halaman menggunakan library berbeda, konsistensi visual dan performa perlu diawasi. Untuk prototipe, pendekatan ini masih wajar karena mempercepat eksplorasi. Untuk produksi, perlu standardisasi library agar beban dependency lebih terkendali.

### 6.2 Komparasi Teknologi dengan Alternatif

| Kebutuhan | Teknologi yang Dipakai | Alternatif | Alasan Pemilihan |
| --- | --- | --- | --- |
| Website prototipe | HTML/CSS/JS | React, Vue, Laravel | Lebih ringan dan mudah dijalankan |
| Grafik dashboard | Chart.js, ApexCharts, ECharts | D3.js, Highcharts | Lebih cepat diterapkan dan cukup lengkap |
| Penyimpanan sementara | localStorage | Database server | Cocok untuk prototipe tanpa backend |
| Ikon | Font Awesome | Lucide, Material Icons | Mudah dipanggil melalui CDN |
| Slider | Swiper.js | Carousel custom | Lebih stabil dan responsif |
| Hosting | Static hosting/lokal | VPS full-stack | Sesuai dengan arsitektur saat ini |

Komparasi teknologi memperlihatkan bahwa pemilihan teknologi bukan hanya soal kecanggihan, tetapi kesesuaian dengan kebutuhan. React atau Vue dapat memberikan struktur komponen yang lebih baik, tetapi mungkin terlalu berat untuk prototipe yang ingin cepat diselesaikan. Database server memberikan integritas data, tetapi membutuhkan backend dan skema pengelolaan. Oleh karena itu, teknologi yang digunakan saat ini dipilih berdasarkan prinsip cukup untuk membuktikan konsep.

Kritik terhadap pilihan ini adalah adanya technical debt. Semakin banyak data dan fitur ditanam langsung dalam HTML/JavaScript, semakin sulit sistem dirawat. Dengan kata lain, pilihan teknologi saat ini menguntungkan tahap awal, tetapi menambah beban migrasi jika sistem diperbesar. Hal ini perlu disadari sejak awal agar pengembangan lanjutan tidak sekadar menambah halaman baru, tetapi mulai menata ulang struktur aplikasi.

### 6.3 Catatan Kesiapan Produksi

| Area | Kondisi Saat Ini | Rekomendasi Produksi |
| --- | --- | --- |
| Login | Akun statis di JavaScript | Backend authentication dan password hashing |
| Data | Hardcoded di HTML/JS | Database dan API |
| Keputusan | localStorage | Tabel keputusan di database |
| Asset | File lokal dalam folder | File storage terstruktur |
| Library | Sebagian CDN | Bundling lokal atau dependency management |
| Keamanan | Minimal | HTTPS, role access, audit log |
| Monitoring | Belum ada | Logging dan monitoring performa |

Tabel kesiapan produksi menunjukkan perbedaan mendasar antara prototipe dan sistem operasional. Prototipe menekankan demonstrasi konsep, sedangkan sistem produksi menuntut keamanan, reliabilitas, auditabilitas, dan kemudahan pemeliharaan. Website ini telah mencapai tahap demonstrasi konsep, tetapi belum memenuhi persyaratan produksi.

Analisis ini penting agar laporan tidak hanya menonjolkan keberhasilan implementasi, tetapi juga menunjukkan kesadaran terhadap risiko. Dalam konteks akademik, kemampuan mengidentifikasi batasan sistem merupakan bagian dari kualitas penelitian. Sistem yang baik bukan hanya sistem yang memiliki banyak fitur, tetapi sistem yang batas kemampuannya dapat dijelaskan secara jujur.

## 7. Implementasi Sistem

### 7.1 Implementasi Modul

| Modul | File Utama | Fitur Implementasi |
| --- | --- | --- |
| Login | `index.html` | Validasi akun, show/hide password, toast notification, redirect |
| Home | `home.html` | Ringkasan profil, statistik, slider, perbandingan terminal, navigasi |
| Profil TPK | `profil-*.html` | Profil terminal, gambar, indikator BOR/YOR, link dashboard |
| Knowledge Base | `knowledge-base.html` | Kartu aktivitas terminal dan akses halaman aktivitas |
| Aktivitas Terminal | `activity/aktivitas*.html` | Detail aktivitas seperti Berth Allocation dan Yard Planner |
| Alur Penanganan | `alur-penanganan.html` | Flowchart, hotspot, modal, alur pemuatan dan pembongkaran |
| Pattern Recognition | `pattern-recognition-knowledge-base.html` | Pattern map, tabel risiko, scoring, keputusan, CSV export |
| Dashboard Kinerja | File dashboard | KPI, chart, filter, dark mode, export PNG pada beberapa halaman |

Implementasi modul menunjukkan bahwa sistem dibangun dengan pendekatan modular berbasis halaman. Setiap halaman berfungsi sebagai unit implementasi yang relatif mandiri. Pendekatan ini mempercepat pembangunan karena pengembangan satu modul tidak selalu bergantung pada modul lain. Misalnya, dashboard Semarang dapat dikembangkan tanpa harus mengubah halaman knowledge base.

Namun, pendekatan ini juga menciptakan risiko fragmentasi kode. Banyak halaman memiliki pola navigasi, style, dan script yang mirip, tetapi belum diabstraksikan menjadi komponen bersama. Dalam jangka pendek, hal ini tidak menjadi masalah besar. Dalam jangka panjang, duplikasi dapat menyulitkan perubahan desain, perbaikan bug, dan konsistensi antarmuka. Oleh karena itu, implementasi saat ini perlu dibaca sebagai implementasi prototipe yang menekankan kelengkapan fungsi.

### 7.2 Implementasi Halaman Login

Halaman login berfungsi sebagai pintu masuk awal sistem. Validasi dilakukan di sisi client menggunakan objek akun statis pada JavaScript. Ketika username dan password sesuai, sistem mengarahkan pengguna ke `home.html`. Jika tidak sesuai, sistem menampilkan pesan error melalui toast notification.

Potongan kode inti:

```javascript
const accounts = {
  user: "user123",
  admin: "admin123",
  knowledgebase: "cp16426",
};

function login() {
  const username = document.getElementById("username").value.trim().toLowerCase();
  const password = document.getElementById("password").value;

  if (!(username in accounts) || accounts[username] !== password) {
    showToast("Username or password is incorrect.", "error");
    return;
  }

  showToast("Login successful! Redirecting...", "success");
  setTimeout(() => {
    window.location.href = "home.html";
  }, 1400);
}
```

Catatan akademik: login ini cukup untuk prototipe, tetapi belum aman untuk implementasi produksi karena akun dapat dilihat pada source code browser.

Keputusan menggunakan login statis memiliki alasan praktis, yaitu menyediakan simulasi akses masuk tanpa membangun backend. Untuk kebutuhan demonstrasi, login ini cukup memperlihatkan bahwa sistem memiliki halaman awal, validasi input, pesan kesalahan, dan proses redirect. Dengan demikian, aspek alur pengguna dapat diuji.

Namun, dari sisi keamanan, login client-side tidak dapat digunakan pada sistem nyata. Username dan password yang disimpan di JavaScript dapat dilihat melalui fitur inspect/source pada browser. Tidak ada hashing, session, token, pembatasan percobaan login, atau otorisasi berbasis peran. Oleh karena itu, bagian implementasi login perlu ditulis secara kritis sebagai simulasi autentikasi, bukan autentikasi sebenarnya.

### 7.3 Implementasi Knowledge Base

Knowledge base mengelompokkan aktivitas terminal ke dalam kartu akses. Aktivitas yang disediakan mencakup Berth Allocation, Manning & Deployment, Ship Planner, Yard Planner, Ship Talker, dan Yard Talker. Modul ini membantu pengguna memahami peran dan proses kerja pada aktivitas operasional terminal.

| Aktivitas | Fungsi Umum |
| --- | --- |
| Berth Allocation | Mengatur perencanaan sandar kapal |
| Manning & Deployment | Mengatur kebutuhan tenaga kerja dan penempatan personel |
| Ship Planner | Menyusun rencana bongkar muat kapal |
| Yard Planner | Mengatur alokasi lapangan penumpukan |
| Ship Talker | Mengkoordinasikan aktivitas kapal |
| Yard Talker | Mengkoordinasikan aktivitas lapangan |

Knowledge base diimplementasikan dalam bentuk kartu aktivitas karena bentuk ini mudah dipahami pengguna. Setiap aktivitas menjadi titik masuk menuju informasi yang lebih detail. Model kartu juga membantu membagi informasi operasional yang kompleks menjadi kategori-kategori yang lebih terstruktur.

Secara kritis, bentuk kartu memiliki keterbatasan apabila jumlah aktivitas bertambah banyak. Pengguna mungkin membutuhkan fitur pencarian, filter kategori, tagging, atau hubungan antaraktivitas. Pada versi saat ini, knowledge base masih bersifat navigasional, belum sepenuhnya menjadi sistem pencarian pengetahuan. Oleh karena itu, pengembangan lanjutan dapat menambahkan struktur metadata agar knowledge base lebih mudah diperbarui dan ditelusuri.

### 7.4 Implementasi Pattern Recognition dan Action Scoring

Halaman pattern recognition menghubungkan elemen aktivitas terminal, risiko, penyebab, dan tindakan. Pola utama yang digunakan adalah:

```text
Aktivitas Terminal -> Aktivitas Detail -> Risiko -> Penyebab -> Preventive/Corrective/Predictive Measure
```

Setiap tindakan dapat diberi skor menggunakan lima kriteria:

| Kriteria | Makna |
| --- | --- |
| Efektif | Seberapa besar tindakan mengurangi atau menyelesaikan risiko |
| Mudah | Seberapa mudah tindakan diterapkan |
| Cepat | Seberapa cepat tindakan dapat dilakukan |
| Dampak | Seberapa besar pengaruh tindakan terhadap kinerja |
| Kesiapan | Seberapa siap data/sumber daya untuk menjalankan tindakan |

Potongan kode inti:

```javascript
const SCORE_CRITERIA = ["Efektif", "Mudah", "Cepat", "Dampak", "Kesiapan"];

function totalScore(r, opt) {
  return SCORE_CRITERIA.reduce(
    (sum, _, i) => sum + Number(getScore(r, opt.type, i, opt.defaults[i])),
    0
  );
}
```

Implementasi action scoring memiliki nilai akademik karena memperlihatkan bagaimana pengetahuan operasional dapat diterjemahkan menjadi mekanisme evaluasi tindakan. Penggunaan lima kriteria membuat proses penilaian lebih transparan dibandingkan hanya memilih tindakan secara subjektif. Pengguna dapat melihat mengapa suatu tindakan memperoleh rekomendasi lebih tinggi.

Meskipun demikian, skor yang digunakan belum berasal dari model statistik atau machine learning. Skor masih bergantung pada input pengguna, default value, dan penilaian pakar. Oleh karena itu, hasil rekomendasi harus diposisikan sebagai rekomendasi berbasis pembobotan sederhana, bukan keputusan otomatis. Jika sistem dikembangkan, scoring dapat diperkuat dengan data historis kejadian, frekuensi risiko, dampak biaya, waktu penanganan, dan tingkat keberhasilan tindakan.

### 7.5 Implementasi Dashboard Kinerja

Dashboard kinerja digunakan untuk menampilkan indikator terminal dalam bentuk KPI card, grafik, tabel, dan analisis. Beberapa bentuk grafik yang digunakan adalah line chart, bar chart, scatter chart, radar chart, donut chart, gauge chart, dan area chart.

Contoh perhitungan KPI:

```javascript
function calculateKPIs() {
  const totalBox = activeDataset.reduce((sum, d) => sum + d.total_box, 0);
  const totalTeus = activeDataset.reduce((sum, d) => sum + d.total_teus, 0);
  const avgBor = (
    activeDataset.reduce((sum, d) => sum + d.bor, 0) / activeDataset.length
  ).toFixed(2);

  document.getElementById("kpi-total-box").innerText = totalBox.toLocaleString("id-ID");
  document.getElementById("kpi-total-teus").innerText = totalTeus.toLocaleString("id-ID");
  document.getElementById("kpi-avg-bor").innerText = `${avgBor}%`;
}
```

Dashboard kinerja dipilih karena indikator operasional terminal memiliki karakter periodik dan komparatif. KPI card memberikan ringkasan cepat, sedangkan chart membantu membaca pola. Pemisahan antara KPI, chart, dan tabel statistik penting agar pengguna dapat bergerak dari gambaran umum menuju analisis yang lebih detail.

Namun, dashboard juga perlu dipahami secara kritis. Grafik hanya sebaik kualitas data yang digunakan. Jika dataset tidak lengkap, tidak mutakhir, atau tidak dijelaskan sumbernya, maka interpretasi dashboard dapat menjadi lemah. Oleh karena itu, laporan final sebaiknya menambahkan keterangan periode data, sumber data, dan batasan interpretasi pada setiap dashboard.

### 7.6 Tabulasi Fitur Dashboard

| Halaman | Fokus Analisis | Visualisasi Utama |
| --- | --- | --- |
| `kinerja-operasional-semarang.html` | Kinerja operasional terminal | KPI, grouped chart, time series, scatter, boxplot |
| `availability-utilization-semarang.html` | Kesiapan dan penggunaan alat | Trend chart, bar comparison, scatter, radar |
| `YOR-semarang.html` | Yard Occupancy Ratio | Trend tahunan, YoY, monthly chart, radar, ranking |
| `kinerja-makassar.html` | Kinerja Makassar New Port | Executive summary, BOR/YOR trend, outlier analysis |
| `YOR-makassar.html` | Yard performance intelligence | Gauge, donut, trend, scatter, ranking, growth |
| `kunjungan-kapal-makassar.html` | Kunjungan kapal | Grafik kunjungan dan analisis operasional |
| `operasional-makassar.html` | Operasional terminal Makassar | Dashboard operasional dan visualisasi performa |

Tabulasi fitur dashboard memperlihatkan bahwa sistem tidak hanya memiliki satu halaman visualisasi, tetapi beberapa dashboard dengan fokus berbeda. Hal ini memberi kekayaan analisis, tetapi juga menimbulkan kebutuhan standarisasi. Setiap dashboard sebaiknya menggunakan istilah indikator yang konsisten, format angka yang seragam, dan pola warna yang tidak membingungkan.

Secara kritis, semakin banyak dashboard berarti semakin besar tanggung jawab validasi data. Dashboard Semarang, Makassar, dan Surabaya/Teluk Lamong perlu dijelaskan apakah menggunakan periode data yang sama, indikator yang sebanding, dan metode perhitungan yang konsisten. Jika tidak, perbandingan antarhalaman dapat menimbulkan kesimpulan yang kurang tepat.

CATATAN PENYAJIAN: Tambahkan screenshot setiap modul utama dalam bentuk grid 2 kolom: Login, Home, Knowledge Base, Pattern Recognition, Alur Proses, Dashboard.

Prompt ilustrasi/screenshot mockup:

```text
Buat komposisi mockup enam layar web app terminal peti kemas dalam grid 2x3. Layar: Login, Home, Knowledge Base, Pattern Recognition Action Scoring, Alur Penanganan Peti Kemas, Dashboard Kinerja. Gunakan tampilan browser frame, warna biru pelabuhan, grafik, tabel, flowchart, dan elemen terminal peti kemas. Gaya realistis-profesional, cocok untuk dokumentasi skripsi.
```

## 8. Pengujian Sistem

### 8.1 Metode Pengujian

Pengujian dilakukan menggunakan black-box testing, yaitu menguji fungsi sistem berdasarkan input dan output yang terlihat oleh pengguna. Fokus pengujian meliputi login, navigasi, halaman profil, knowledge base, alur proses, dashboard, filter, scoring, localStorage, dan export.

Black-box testing dipilih karena sistem diuji dari sudut pandang pengguna. Pada prototipe web app, tujuan utama pengujian adalah memastikan bahwa fitur yang terlihat dapat digunakan sesuai rancangan. Metode ini tepat untuk mengevaluasi login, navigasi, filter, chart, modal, scoring, dan export karena keberhasilan fitur dapat diamati langsung melalui perubahan tampilan atau file keluaran.

Namun, black-box testing belum cukup untuk menilai kualitas internal kode, keamanan, dan performa detail. Login client-side, dependency CDN, dan pengolahan data di browser membutuhkan pengujian tambahan apabila sistem akan diproduksikan. Oleh karena itu, black-box testing ditempatkan sebagai pengujian dasar, bukan satu-satunya metode evaluasi.

Selain black-box testing, sistem dapat diuji menggunakan:

1. User Acceptance Test (UAT) untuk menilai kesesuaian sistem dengan kebutuhan pengguna.
2. Usability testing untuk mengukur kemudahan penggunaan.
3. Performance testing sederhana menggunakan Chrome DevTools atau Lighthouse.
4. Responsive testing dengan membuka halaman pada ukuran desktop, tablet, dan mobile.

Pemilihan kombinasi metode pengujian di atas didasarkan pada karakteristik sistem yang memiliki antarmuka visual kuat dan banyak interaksi client-side. UAT menilai kesesuaian dengan kebutuhan pengguna, usability testing menilai kemudahan penggunaan, performance testing menilai kecepatan dan beban halaman, sedangkan responsive testing menilai kemampuan tampilan beradaptasi pada berbagai perangkat.

Pengujian juga perlu dikaitkan dengan standar kualitas yang relevan. ISO/IEC 25010 dapat digunakan sebagai kerangka untuk menilai kualitas produk perangkat lunak, ISO 9241-210 untuk menilai desain berpusat pengguna, WCAG 2.2 untuk aksesibilitas, dan OWASP ASVS untuk keamanan aplikasi web. Dengan demikian, pengujian tidak hanya memeriksa apakah tombol berjalan, tetapi juga menilai apakah sistem cukup usable, accessible, secure, maintainable, dan fit-for-purpose.

### 8.2 Skenario Black-Box Testing

| No | Modul | Skenario Uji | Data Uji | Hasil yang Diharapkan | Status |
| --- | --- | --- | --- | --- | --- |
| 1 | Login | Login dengan akun benar | `user/user123` | Masuk ke `home.html` | Sesuai |
| 2 | Login | Login dengan password salah | `user/salah` | Muncul pesan error | Sesuai |
| 3 | Login | Field kosong | Kosong | Muncul peringatan input wajib | Sesuai |
| 4 | Navigasi | Klik menu Home | Klik navbar | Halaman home terbuka | Sesuai |
| 5 | Navigasi | Klik dropdown Profil TPK | Hover/klik menu profil | Daftar terminal muncul | Sesuai |
| 6 | Knowledge Base | Klik kartu aktivitas | Berth Allocation | Halaman aktivitas terbuka | Sesuai |
| 7 | Alur Proses | Klik hotspot/flowchart | Area proses | Modal/detail muncul | Sesuai |
| 8 | Dashboard | Buka halaman dashboard | Dashboard Semarang/Makassar | Chart tampil | Sesuai |
| 9 | Dashboard | Gunakan filter/select | Tahun/terminal/alat | Chart berubah sesuai filter | Sesuai |
| 10 | Pattern Recognition | Filter data relasi | Proses/alur/tahap | Tabel dan map berubah | Sesuai |
| 11 | Action Scoring | Ubah skor tindakan | Nilai 1-5 | Total skor berubah | Sesuai |
| 12 | Decision | Pilih keputusan dan catatan | Select/textarea | Tersimpan di localStorage | Sesuai |
| 13 | Export CSV | Klik export keputusan | Tombol CSV | File CSV terunduh | Sesuai |
| 14 | Export Chart | Klik export chart | Tombol PNG | Chart terunduh sebagai PNG | Sesuai pada halaman terkait |
| 15 | Responsive | Buka layar kecil | Mobile viewport | Layout menyesuaikan | Perlu pengujian detail |

Skenario black-box tersebut disusun untuk mencakup jalur utama dan jalur kesalahan. Jalur utama meliputi login berhasil, navigasi, membuka halaman, menggunakan filter, dan export. Jalur kesalahan meliputi login gagal dan input kosong. Dengan demikian, pengujian tidak hanya membuktikan fitur berjalan pada kondisi ideal, tetapi juga memeriksa respons sistem saat pengguna melakukan kesalahan.

Status "Sesuai" pada tabel harus dipahami sebagai hasil pengujian fungsional awal. Untuk laporan final, status sebaiknya dilengkapi bukti berupa screenshot, tanggal pengujian, browser yang digunakan, dan catatan hasil. Jika memungkinkan, setiap skenario juga diberi kolom "Bukti" atau "Keterangan" agar hasil pengujian lebih dapat diverifikasi.

### 8.3 Rancangan Performance Testing

| Halaman | Metrik yang Diukur | Tools | Catatan |
| --- | --- | --- | --- |
| `index.html` | Load time, transfer size | Lighthouse/DevTools | Halaman ringan |
| `home.html` | Load time, image size, script load | Lighthouse/DevTools | Perlu optimasi jika gambar besar |
| `knowledge-base.html` | Load time dan interaksi kartu | DevTools | Relatif ringan |
| `pattern-recognition-knowledge-base.html` | Render time, DOM size, localStorage | DevTools | Perlu cek karena tabel dan data besar |
| `alur-penanganan.html` | Load time aset flowchart dan modal | DevTools | Bergantung ukuran aset |
| Dashboard | Chart render time, script load | DevTools | Bergantung dataset dan CDN |

Performance testing menjadi penting karena sistem menggunakan banyak aset visual dan library eksternal. Halaman yang memuat chart, gambar besar, video, atau tabel panjang berpotensi lebih lambat. Pada static web app, server tidak melakukan pemrosesan berat, tetapi beban berpindah ke browser pengguna. Oleh karena itu, performa harus dilihat dari sisi load time, jumlah request, ukuran aset, dan waktu render chart.

Secara kritis, performa yang baik pada laptop pengembang belum tentu sama pada perangkat pengguna lain. Pengujian sebaiknya dilakukan pada beberapa kondisi, misalnya koneksi internet cepat/lambat, layar desktop/mobile, dan browser berbeda. Untuk laporan akademik, cukup disajikan rancangan dan hasil pengukuran awal, tetapi batas pengujian perlu dituliskan.

### 8.4 Rancangan Usability Test

Usability test dapat menggunakan SUS atau kuesioner Likert 1-5. Jika memakai SUS, responden diminta menilai 10 pertanyaan standar. Jika memakai kuesioner sederhana, aspek yang dinilai dapat disesuaikan dengan modul website.

| Aspek | Pertanyaan | Skala |
| --- | --- | --- |
| Navigasi | Menu website mudah dipahami | 1-5 |
| Informasi | Informasi profil terminal mudah ditemukan | 1-5 |
| Knowledge base | Aktivitas terminal mudah dipelajari | 1-5 |
| Alur proses | Flowchart membantu memahami proses | 1-5 |
| Dashboard | Grafik membantu membaca kinerja | 1-5 |
| Pattern recognition | Relasi risiko dan tindakan mudah dipahami | 1-5 |
| Scoring | Fitur scoring mudah digunakan | 1-5 |
| Tampilan | Desain nyaman dibaca | 1-5 |

Usability test diperlukan karena keberhasilan sistem informasi tidak hanya ditentukan oleh kelengkapan fitur. Sistem yang kaya fitur dapat tetap gagal apabila pengguna kesulitan menemukan informasi atau memahami grafik. Oleh karena itu, aspek navigasi, kejelasan istilah, keterbacaan chart, dan kemudahan scoring perlu dinilai oleh pengguna.

Penggunaan skala Likert 1-5 lebih sederhana dan mudah diterapkan, sedangkan SUS memberikan ukuran usability yang lebih standar. Jika responden terbatas, kuesioner Likert dapat digunakan sebagai evaluasi awal. Jika ingin hasil yang lebih kuat secara akademik, SUS lebih disarankan karena memiliki prosedur perhitungan dan interpretasi yang umum digunakan.

### 8.5 Matriks Evaluasi Berbasis Standar

Matriks berikut dapat digunakan untuk memperkuat evaluasi sistem. Matriks ini tidak dimaksudkan untuk menyatakan sertifikasi atau kepatuhan penuh, tetapi sebagai alat pemeriksaan akademik terhadap aspek kualitas yang relevan.

| Dimensi Evaluasi | Rujukan Standar | Indikator yang Diperiksa | Kondisi Saat Ini | Rekomendasi |
| --- | --- | --- | --- | --- |
| Functional suitability | ISO/IEC 25010 | Modul utama tersedia dan sesuai kebutuhan | Modul login, home, KB, pattern, alur, dashboard tersedia | Tambahkan traceability kebutuhan-fitur |
| Usability | ISO 9241-210, SUS | Navigasi, keterbacaan, kemudahan filter/scoring | Struktur dasar tersedia | Lakukan usability test dengan responden |
| Accessibility | WCAG 2.2 | Alt text, kontras, keyboard navigation, label form | Belum diuji formal | Lakukan audit WCAG level A/AA |
| Security | OWASP ASVS | Autentikasi, kontrol akses, penyimpanan data | Login masih client-side | Migrasi ke backend authentication |
| Maintainability | ISO/IEC 25010 | Kemudahan modifikasi, duplikasi kode, struktur modul | Multi-page static dengan potensi duplikasi | Gunakan template/component system |
| Portability | ISO/IEC 25010 | Kemudahan dijalankan di browser/hosting statis | Kuat untuk prototipe | Dokumentasikan cara deploy |
| Risk management | ISO 31000 | Identifikasi risiko, analisis, evaluasi, treatment | Mapping risiko dan tindakan tersedia | Tambahkan risk owner, likelihood, impact |
| Information management | ISO 19650 | Struktur informasi, versioning, status, approval | Informasi terkumpul tetapi belum terkelola formal | Tambahkan metadata dan database |
| Quality management | ISO 9001 | Konsistensi proses dan improvement | Evaluasi awal tersedia | Tambahkan siklus review dan perbaikan |

Matriks ini membantu membedakan antara fitur yang sudah ada dan kualitas sistem yang masih perlu dikembangkan. Misalnya, sistem dapat memiliki dashboard yang berfungsi, tetapi belum tentu memenuhi accessibility atau security. Dengan pendekatan ini, evaluasi menjadi lebih seimbang karena tidak hanya berfokus pada keberhasilan implementasi, tetapi juga pada kesiapan sistem menuju penggunaan yang lebih luas.

Prompt ilustrasi pengujian:

```text
Buat ilustrasi alur pengujian web app terminal peti kemas. Tampilkan empat jenis pengujian: Black-box Testing, Performance Testing, Responsive Testing, dan Usability Testing. Masing-masing diwakili ikon checklist, speedometer, perangkat desktop-tablet-mobile, dan form kuesioner. Gaya infografik akademik, bersih, warna biru dan hijau.
```

## 9. Diskusi

### 9.1 Kelebihan Sistem

Kelebihan website ini adalah integrasi informasi yang cukup luas dalam satu web app. Sistem menggabungkan informasi profil terminal, dokumentasi visual, knowledge base aktivitas, alur proses peti kemas, pattern recognition, action scoring, dan dashboard kinerja. Integrasi ini membuat website dapat digunakan sebagai media pembelajaran sekaligus alat bantu analisis.

Dari sisi visualisasi, sistem menyediakan banyak bentuk grafik yang membantu pengguna memahami data. Dashboard tidak hanya menampilkan angka, tetapi juga tren, ranking, distribusi, korelasi, dan perbandingan. Hal ini meningkatkan keterbacaan data operasional.

Pada aspek knowledge base, sistem memiliki nilai tambah karena menghubungkan aktivitas, risiko, penyebab, dan tindakan. Action scoring memberi struktur penilaian yang dapat mendukung keputusan manusia. Pendekatan ini penting karena keputusan operasional terminal peti kemas tidak cukup hanya berdasarkan angka, tetapi juga membutuhkan konteks aktivitas dan risiko.

Dari sisi implementasi, sistem mudah dijalankan karena berbasis static web app. Website dapat dibuka di browser, dipindahkan antarperangkat, atau diunggah ke static hosting tanpa konfigurasi backend.

Kelebihan tersebut perlu dibaca dalam konteks tujuan sistem sebagai prototipe. Sistem berhasil memperlihatkan bagaimana berbagai informasi operasional dapat ditempatkan dalam satu lingkungan web. Nilai utamanya bukan hanya pada jumlah halaman, tetapi pada keterhubungan antarhalaman: pengguna dapat mulai dari profil terminal, masuk ke knowledge base, memahami alur proses, lalu membaca dashboard dan pattern recognition.

Secara kritis, kelebihan integrasi ini juga menciptakan tantangan. Semakin banyak modul, semakin besar kebutuhan konsistensi data dan antarmuka. Oleh karena itu, keunggulan sistem perlu diimbangi dengan strategi maintainability pada pengembangan berikutnya. Tanpa strategi tersebut, sistem dapat berkembang menjadi kumpulan halaman yang kaya tetapi sulit dikelola.

### 9.2 Keterbatasan Sistem

Keterbatasan utama adalah sistem belum memiliki backend dan database. Data masih tertanam di file HTML/JavaScript sehingga pembaruan data membutuhkan perubahan kode. Hal ini belum ideal untuk penggunaan jangka panjang, terutama jika data perlu diperbarui secara rutin.

Login masih bersifat client-side. Akun dan password berada pada JavaScript sehingga tidak aman untuk produksi. Selain itu, keputusan pengguna disimpan di `localStorage`, sehingga hanya tersimpan pada browser yang sama dan tidak dapat digunakan sebagai data bersama.

Keterbatasan lain adalah ketergantungan pada CDN eksternal. Jika koneksi internet bermasalah, library chart, ikon, font, atau slider dapat gagal dimuat. Untuk kebutuhan offline atau produksi, dependency sebaiknya dibundel secara lokal.

Keterbatasan sistem bukan berarti sistem gagal, tetapi menunjukkan batas validitas prototipe. Dalam penelitian sistem informasi, batasan perlu dijelaskan agar klaim kontribusi tetap proporsional. Website ini layak disebut prototipe integratif karena mampu menyatukan informasi dan visualisasi, tetapi belum layak disebut sistem enterprise karena belum memiliki manajemen data, keamanan, dan audit trail.

Keterbatasan yang paling fundamental adalah data governance. Data dashboard dan knowledge base belum memiliki mekanisme validasi, pembaruan, dan riwayat perubahan. Jika sistem digunakan untuk keputusan operasional, aspek ini harus diselesaikan terlebih dahulu. Tanpa tata kelola data, dashboard dapat menjadi menarik secara visual tetapi lemah sebagai dasar pengambilan keputusan formal.

### 9.3 Komparasi dengan Jenis Sistem Lain

| Aspek | Website Profil Biasa | Dashboard Biasa | Website Ini | DSS Produksi Penuh |
| --- | --- | --- | --- | --- |
| Profil terminal | Ada | Terbatas | Ada | Ada |
| Knowledge base | Tidak umum | Tidak umum | Ada | Ada |
| Flowchart proses | Jarang | Tidak umum | Ada | Ada |
| Dashboard data | Terbatas | Ada | Ada | Ada |
| Pattern recognition | Tidak | Tidak | Ada secara rule/relasi | Ada, dapat berbasis model/AI |
| Action scoring | Tidak | Tidak | Ada | Ada dan tersimpan di database |
| Backend/database | Opsional | Umumnya ada | Belum | Ada |
| Multi-user | Terbatas | Ada | Belum optimal | Ada |
| Cocok untuk | Informasi umum | Monitoring data | Prototipe akademik dan knowledge base | Operasional produksi |

Tabel komparasi tersebut membantu menempatkan kontribusi sistem secara lebih objektif. Website ini berada di antara website profil dan decision support system penuh. Dibanding website profil, sistem lebih unggul karena memiliki knowledge base dan dashboard. Dibanding dashboard biasa, sistem lebih kaya konteks karena menyertakan alur proses dan risiko. Namun, dibanding DSS produksi penuh, sistem masih belum memiliki backend, database, dan model prediktif yang matang.

Dengan posisi tersebut, kontribusi utama sistem adalah sebagai model awal integrasi informasi terminal peti kemas. Sistem memperlihatkan bagaimana profil, proses, risiko, tindakan, dan kinerja dapat disajikan bersama dalam satu platform. Kontribusi ini penting sebagai dasar pengembangan, tetapi tidak boleh dilebihkan menjadi klaim sistem operasional penuh.

### 9.4 Rekomendasi Pengembangan Lanjutan

| Area | Rekomendasi |
| --- | --- |
| Backend | Menambahkan API server untuk autentikasi, data dashboard, dan knowledge base |
| Database | Menyimpan terminal, aktivitas, risiko, tindakan, scoring, keputusan, dan dataset kinerja |
| Admin panel | Menambahkan fitur CRUD data dan upload aset |
| Security | Menggunakan password hashing, session/JWT, HTTPS, dan role-based access control |
| Data integration | Menghubungkan dashboard dengan file CSV, API operasional, atau database real-time |
| Reporting | Menambahkan export PDF, laporan periodik, dan ringkasan otomatis |
| Offline readiness | Menyimpan library secara lokal atau membuat PWA |
| Usability | Melakukan SUS/UAT dan memperbaiki tampilan berdasarkan masukan pengguna |

Rekomendasi pengembangan lanjutan disusun berdasarkan analisis kesenjangan antara prototipe dan sistem produksi. Backend dan database menjadi prioritas karena keduanya menyelesaikan masalah paling mendasar, yaitu keamanan login, penyimpanan data, dan pembaruan informasi. Setelah itu, admin panel, reporting, dan integrasi data dapat ditambahkan untuk meningkatkan nilai operasional.

Urutan pengembangan sebaiknya tidak dilakukan sekaligus. Strategi bertahap lebih realistis: pertama, pisahkan data dari file HTML ke JSON; kedua, bangun API sederhana; ketiga, pindahkan data ke database; keempat, tambahkan autentikasi; kelima, bangun admin panel; keenam, integrasikan data real-time dan predictive analytics. Pendekatan bertahap ini mengurangi risiko perubahan besar yang sulit dikendalikan.

CATATAN PENYAJIAN: Bagian diskusi dapat ditutup dengan roadmap pengembangan.

Prompt roadmap:

```text
Buat roadmap pengembangan web app terminal peti kemas dari prototipe menuju sistem produksi. Tahap 1: Static Prototype, Tahap 2: Backend API, Tahap 3: Database dan Admin Panel, Tahap 4: Real-time Dashboard, Tahap 5: Decision Support dan Predictive Analytics. Gunakan timeline horizontal, ikon web, server, database, grafik real-time, dan AI analytics. Gaya profesional, bersih, warna biru-hijau.
```

## 10. Kerangka Ilustrasi Pendamping Bab

Bagian ini berisi daftar ilustrasi yang disarankan untuk mendampingi penulisan bab sistem informasi. Ilustrasi dapat dibuat secara manual menggunakan draw.io, Figma, Canva, PowerPoint, atau image generator.

Ilustrasi tidak hanya berfungsi sebagai pelengkap visual, tetapi juga sebagai alat argumentasi akademik. Diagram arsitektur membantu pembaca memahami batas teknis sistem, use case menjelaskan hubungan aktor dan fungsi, ERD menggambarkan arah pengembangan data, sedangkan roadmap menunjukkan rencana peningkatan sistem. Oleh karena itu, ilustrasi sebaiknya dipilih berdasarkan kebutuhan penjelasan, bukan sekadar memperindah laporan.

Prompt pembuatan ilustrasi disertakan agar proses pembuatan visual lebih konsisten dengan narasi bab. Setiap prompt harus tetap diperiksa ulang setelah gambar dibuat, terutama jika menggunakan image generator, karena diagram akademik membutuhkan ketepatan istilah, relasi, dan struktur. Jika hasil visual kurang presisi, gunakan prompt sebagai draf awal lalu rapikan manual menggunakan draw.io, Figma, atau PowerPoint.

| No | Ilustrasi | Lokasi di Bab | Tujuan | Jenis Visual | Prompt/Ringkasan |
| --- | --- | --- | --- | --- | --- |
| 1 | Overview sistem | Bab 1 | Menjelaskan gambaran web app | Diagram modul | User -> browser -> modul profil, KB, alur, pattern, dashboard |
| 2 | Peta teori | Bab 2 | Menghubungkan teori dengan modul | Mind map | SDLC, KMS, dashboard, DSS, UI/UX |
| 3 | Waterfall | Bab 3 | Menjelaskan metodologi | Flow diagram | Analisis -> desain -> implementasi -> testing -> evaluasi |
| 4 | Arsitektur saat ini | Bab 4 | Menjelaskan static client-side app | Technical architecture | Browser, HTML, CSS, JS, aset, CDN, localStorage |
| 5 | Arsitektur lanjutan | Bab 4 | Menjelaskan target produksi | Full-stack diagram | Frontend, backend API, database, auth, file storage |
| 6 | Use case diagram | Bab 5 | Menjelaskan interaksi aktor | UML | Pengguna, pakar/operator, admin |
| 7 | Activity diagram | Bab 5 | Menjelaskan alur penggunaan | UML activity | Login, pilih menu, filter, scoring, export |
| 8 | Sitemap | Bab 5 | Menjelaskan struktur navigasi | Tree diagram | index -> home -> modul |
| 9 | ERD konseptual | Bab 5 | Menjelaskan rancangan database | ERD | users, terminal, aktivitas, risiko, tindakan, scoring |
| 10 | Mockup modul | Bab 7 | Menunjukkan implementasi UI | Screenshot grid | Login, home, KB, pattern, alur, dashboard |
| 11 | Flow data scoring | Bab 7 | Menjelaskan localStorage/action scoring | Flowchart | Input skor -> total -> rekomendasi -> keputusan |
| 12 | Testing framework | Bab 8 | Menjelaskan pengujian | Infografik | Black-box, performance, responsive, usability |
| 13 | Komparasi sistem | Bab 9 | Menjelaskan posisi kontribusi | Comparison matrix | Profil biasa vs dashboard vs web app ini vs DSS |
| 14 | Roadmap | Bab 9 | Menjelaskan pengembangan lanjutan | Timeline | Prototype -> backend -> database -> realtime -> predictive |

### 10.1 Prompt Lengkap Ilustrasi Flow Data Action Scoring

Ilustrasi flow data action scoring diperlukan karena modul ini merupakan bagian yang paling dekat dengan konsep decision support. Tanpa diagram, pembaca mungkin hanya melihat scoring sebagai fitur tabel biasa. Dengan flowchart, hubungan antara knowledge base, input pengguna, perhitungan skor, rekomendasi, keputusan manusia, localStorage, dan export CSV menjadi lebih mudah dipahami.

Secara kritis, ilustrasi ini juga harus menegaskan bahwa keputusan akhir tidak dibuat otomatis oleh sistem. Bagian "manusia/pakar memilih keputusan final" perlu ditampilkan secara eksplisit agar prinsip human-in-the-loop terlihat jelas. Hal ini penting untuk menghindari kesan bahwa sistem telah menjadi artificial intelligence atau decision maker penuh.

```text
Buat flowchart teknis untuk modul Pattern Recognition dan Action Scoring pada web app terminal peti kemas. Alur: Data Knowledge Base -> Pilih aktivitas/risiko -> Tampilkan preventive, corrective, predictive measure -> Pengguna memberi skor lima kriteria -> Sistem menghitung total skor -> Sistem menampilkan rekomendasi skor tertinggi -> Manusia/pakar memilih keputusan final -> Simpan ke browser localStorage -> Export CSV. Gaya diagram akademik, warna biru dan hijau, ikon tabel, risiko, checklist, kalkulator skor, pengguna, localStorage, dan file CSV.
```

### 10.2 Prompt Lengkap Ilustrasi Dashboard Analytics

Ilustrasi dashboard analytics digunakan untuk memperlihatkan bagaimana data operasional diterjemahkan menjadi informasi visual. Dashboard tidak hanya menampilkan grafik, tetapi menyusun indikator menjadi struktur pembacaan: ringkasan KPI, tren, perbandingan, distribusi, dan korelasi. Oleh karena itu, ilustrasi dashboard harus menonjolkan hierarki informasi, bukan sekadar banyaknya chart.

Secara kritis, ilustrasi ini harus dihindarkan dari tampilan yang terlalu dekoratif. Dashboard operasional sebaiknya terlihat profesional, padat, dan mudah dibaca. Tujuan visualnya adalah memperjelas analisis kinerja, bukan menciptakan kesan promosi. Jika gambar dibuat dengan image generator, pastikan istilah KPI dan indikator tetap dapat dibaca atau diganti manual setelahnya.

```text
Buat ilustrasi dashboard analytics untuk terminal peti kemas. Tampilkan KPI cards: Total Box, Total TEUs, BOR, YOR, Availability, Utilization. Tambahkan line chart tren, bar chart ranking, scatter chart korelasi, radar chart distribusi, dan gauge chart performa. Gunakan gaya web dashboard profesional, warna biru pelabuhan, putih, abu-abu, aksen hijau, tampilan laptop/browser, tanpa teks terlalu kecil.
```

### 10.3 Prompt Lengkap Ilustrasi Knowledge Base

Ilustrasi knowledge base diperlukan untuk menunjukkan bahwa modul ini bukan hanya kumpulan menu aktivitas, tetapi representasi pengetahuan operasional. Kartu aktivitas harus dihubungkan dengan risiko dan tindakan agar pembaca memahami bahwa knowledge base berfungsi sebagai jembatan antara proses kerja dan pengambilan tindakan.

Secara kritis, ilustrasi knowledge base sebaiknya tidak dibuat seperti katalog biasa. Fokusnya adalah struktur pengetahuan: aktivitas, risiko, penyebab, dan tindakan. Dengan demikian, visual dapat mendukung argumen bahwa sistem memiliki dimensi knowledge management, meskipun belum memiliki backend dan mekanisme pembaruan pengetahuan secara penuh.

```text
Buat ilustrasi knowledge base operasional terminal peti kemas. Tampilkan enam kartu aktivitas: Berth Allocation, Manning & Deployment, Ship Planner, Yard Planner, Ship Talker, Yard Talker. Hubungkan kartu ke tabel risiko dan tindakan. Tambahkan ikon kapal kontainer, crane, yard, planner, dan checklist. Gaya infografik akademik modern, warna biru dan putih, cocok untuk laporan sistem informasi.
```

### 10.4 Prompt Lengkap Ilustrasi Alur Proses Peti Kemas

Ilustrasi alur proses peti kemas penting karena proses pemuatan dan pembongkaran bersifat berurutan, melibatkan banyak aktor, dan mudah keliru dipahami apabila hanya dijelaskan dalam paragraf. Flowchart membantu pembaca melihat titik awal, perpindahan kontainer, aktivitas yard, aktivitas kapal, serta keluaran proses.

Secara kritis, flowchart perlu dibedakan dari diagram arsitektur sistem. Flowchart ini menjelaskan proses operasional terminal, bukan alur data aplikasi. Pemisahan tersebut penting agar pembaca tidak mencampuradukkan proses bisnis peti kemas dengan proses teknis web app. Jika memungkinkan, buat dua jalur terpisah antara pemuatan dan pembongkaran agar perbedaannya terlihat jelas.

```text
Buat flowchart alur proses peti kemas untuk terminal pelabuhan. Tampilkan dua jalur: pemuatan dan pembongkaran. Jalur pemuatan: gate in, yard stacking, planning, quay crane loading, vessel departure. Jalur pembongkaran: vessel arrival, quay crane unloading, yard stacking, document/inspection, gate out. Gunakan ikon kontainer, truck, yard, quay crane, kapal. Gaya diagram operasional profesional, warna biru laut dan oranye keselamatan, format landscape.
```

### 10.5 Prompt Lengkap Ilustrasi Komparasi Arsitektur

Ilustrasi komparasi arsitektur digunakan untuk menjelaskan perbedaan antara kondisi sistem saat ini dan arah pengembangan lanjutan. Visual split-screen membantu pembaca memahami bahwa sistem tidak hanya "belum lengkap", tetapi memang berada pada fase arsitektur yang berbeda. Static client-side menekankan kemudahan prototipe, sedangkan full-stack web app menekankan keamanan, database, dan pengelolaan data.

Secara kritis, ilustrasi ini harus memperlihatkan trade-off, bukan membuat arsitektur lanjutan seolah otomatis lebih baik dalam semua konteks. Untuk prototipe, arsitektur saat ini lebih cepat dan sederhana. Untuk produksi, arsitektur lanjutan lebih kuat tetapi lebih kompleks. Dengan demikian, gambar mendukung argumentasi akademik tentang kesesuaian teknologi dengan tujuan sistem.

```text
Buat infografik komparasi dua arsitektur sistem. Kolom kiri: Current Static Client-Side Web App dengan HTML, CSS, JavaScript, local assets, CDN, localStorage, no backend, no database. Kolom kanan: Future Full-Stack Web App dengan frontend, backend API, authentication, database, admin panel, file storage, reporting, analytics. Gunakan visual split-screen, ikon teknis, warna biru dan hijau, gaya akademik rapi.
```

## 11. Ringkasan Bab

Berdasarkan uraian di atas, website yang dikembangkan merupakan prototipe sistem informasi terminal peti kemas berbasis web app statis. Sistem mengintegrasikan halaman profil, knowledge base, alur proses, pattern recognition, action scoring, dan dashboard kinerja. Arsitektur saat ini berpusat pada browser dengan HTML, CSS, JavaScript, aset lokal, CDN library, dan `localStorage`.

Secara akademik, sistem ini dapat dijelaskan melalui teori sistem informasi berbasis web, SDLC, knowledge management, data visualization, decision support, dan UI/UX. Keunggulan utama sistem adalah integrasi informasi dan visualisasi operasional dalam satu website. Keterbatasan utamanya adalah belum adanya backend, database, autentikasi server, dan manajemen data terpusat. Oleh karena itu, sistem cocok disebut sebagai prototipe web information system dan dapat dikembangkan menjadi full-stack decision support system pada penelitian atau implementasi lanjutan.

Bab ini juga menegaskan bahwa keputusan teknis yang digunakan dalam sistem tidak bersifat netral. Pemilihan static web app, data hardcoded, CDN, dan localStorage memberikan keuntungan pada kecepatan pengembangan dan kemudahan demonstrasi, tetapi membawa konsekuensi pada keamanan, skalabilitas, dan tata kelola data. Dengan demikian, evaluasi sistem harus dilakukan secara seimbang: mengapresiasi keberhasilan integrasi modul, sekaligus mengakui batas arsitektur yang digunakan.

Kesimpulan kritis dari bab ini adalah bahwa website telah berhasil membangun dasar sistem informasi dan knowledge base terminal peti kemas, tetapi masih berada pada tahap prototipe akademik. Agar dapat digunakan secara lebih luas, sistem membutuhkan transformasi menuju arsitektur full-stack dengan backend, database, autentikasi, admin panel, dan mekanisme validasi data. Transformasi tersebut menjadi arah pengembangan yang logis dan dapat dijadikan dasar penelitian lanjutan.

## 12. Referensi Pendukung

Referensi berikut digunakan sebagai kerangka pendukung untuk menempatkan pengembangan web app dalam konteks manajemen proyek, manajemen risiko, manajemen mutu, pengelolaan informasi aset, siklus hidup perangkat lunak, kualitas perangkat lunak, usability, aksesibilitas, dan keamanan aplikasi web. Format penulisan referensi menggunakan gaya APA.

### 12.1 Daftar Referensi Format APA

Bureau of Indian Standards. (2024). *IS 16443:2024/ISO/IEC 25010:2023 systems and software engineering - Systems and software quality requirements and evaluation (SQuaRE) - Product quality model*. https://standardsbis.bsbedge.com/BIS_Preview.aspx?id=16443_2024

International Organization for Standardization. (2018a). *ISO 31000:2018 risk management - Guidelines*. https://www.iso.org/standard/65694.html

International Organization for Standardization. (2018b). *ISO 19650-1:2018 organization and digitization of information about buildings and civil engineering works, including building information modelling (BIM) - Information management using building information modelling - Part 1: Concepts and principles*. https://www.iso.org/standard/68078.html

International Organization for Standardization. (2019). *ISO 9241-210:2019 ergonomics of human-system interaction - Part 210: Human-centred design for interactive systems*. https://www.iso.org/standard/77520.html

International Organization for Standardization. (2020). *ISO 21502:2020 project, programme and portfolio management - Guidance on project management*. https://committee.iso.org/sites/tc258/home/projects/published/iso-21502.html

International Organization for Standardization. (n.d.). *ISO 9001 explained*. https://www.iso.org/home/insights-news/resources/iso-9001-explained.html

International Organization for Standardization Technical Committee 258. (2018). *ISO 21511:2018 work breakdown structures for project and programme management*. https://committee.iso.org/sites/tc258/home/projects/published/iso-21511-ed1.html

International Organization for Standardization, International Electrotechnical Commission, & Institute of Electrical and Electronics Engineers. (2026). *ISO/IEC/IEEE 12207:2026 systems and software engineering - Software life cycle processes*. https://www.iso.org/standard/90219.html

OWASP Foundation. (n.d.). *Application security verification standard*. https://owasp.org/www-project-application-security-verification-standard/

Project Management Institute. (2025). *A guide to the project management body of knowledge (PMBOK guide) and the standard for project management*. https://www.pmi.org/standards/pmbok

World Wide Web Consortium. (2024). *Web content accessibility guidelines (WCAG) 2.2*. https://www.w3.org/TR/WCAG22/

### 12.2 Matriks Fungsi Referensi dalam Bab

| No | Referensi | Relevansi dalam Bab |
| --- | --- | --- |
| 1 | Project Management Institute (2025) | Mendukung pembahasan value delivery, tailoring, performance domains, governance, risk, stakeholders, dan project delivery |
| 2 | International Organization for Standardization (2020) | Mendukung metodologi pengembangan, pengendalian proyek, stakeholder, scope, resources, schedule, risk, dan delivery approach |
| 3 | International Organization for Standardization Technical Committee 258 (2018) | Mendukung penyusunan struktur aktivitas, WBS, knowledge base, dan pemetaan aktivitas-risiko-tindakan |
| 4 | International Organization for Standardization (2018a) | Mendukung pemetaan risiko, penyebab, tindakan, scoring, dan rekomendasi pengembangan risk management formal |
| 5 | International Organization for Standardization (n.d.) | Mendukung pembahasan quality management, konsistensi proses, dokumentasi, evaluasi, dan continual improvement |
| 6 | International Organization for Standardization (2018b) | Mendukung pembahasan pengelolaan informasi aset, struktur informasi, versioning, recording, organizing, dan collaboration |
| 7 | International Organization for Standardization, International Electrotechnical Commission, & Institute of Electrical and Electronics Engineers (2026) | Mendukung pembahasan siklus hidup perangkat lunak dari konsepsi, development, operation, maintenance, hingga retirement |
| 8 | Bureau of Indian Standards (2024) | Mendukung evaluasi kualitas perangkat lunak seperti functional suitability, usability, performance, maintainability, security, dan portability |
| 9 | International Organization for Standardization (2019) | Mendukung pembahasan user-centred design, konteks penggunaan, kebutuhan pengguna, dan evaluasi usability |
| 10 | World Wide Web Consortium (2024) | Mendukung evaluasi aksesibilitas web, termasuk teks alternatif, kontras, navigasi, dan kompatibilitas perangkat |
| 11 | OWASP Foundation (n.d.) | Mendukung evaluasi keamanan aplikasi web, autentikasi, kontrol akses, validasi, dan perlindungan dari kerentanan umum |

Daftar referensi tersebut perlu diperlakukan sebagai rujukan konseptual dan metodologis. Pada tahap prototipe, sistem belum mengklaim kepatuhan penuh terhadap standar-standar tersebut. Namun, standar tersebut memberikan dasar untuk menjelaskan mengapa fitur tertentu dipilih, bagaimana keterbatasannya dievaluasi, dan ke arah mana sistem sebaiknya dikembangkan. Dengan demikian, referensi tidak hanya ditempatkan sebagai daftar pustaka, tetapi menjadi alat analisis untuk menilai kematangan sistem.

## 13. Evaluasi Kritis dan Penguatan Celah Narasi Akademis

Bab ini telah menjelaskan sistem dari sisi teori, metodologi, arsitektur, implementasi, pengujian, standar pendukung, dan referensi. Namun, agar argumentasinya lebih kuat, masih diperlukan evaluasi terhadap celah narasi akademis yang mungkin muncul. Evaluasi ini penting karena sebuah bab pengembangan sistem tidak hanya dinilai dari kelengkapan fitur, tetapi juga dari ketepatan klaim, keterhubungan teori-metode-implementasi, kejelasan batasan, dan kekuatan kontribusi.

Secara umum, celah utama dalam narasi sistem informasi semacam ini biasanya berada pada empat area. Pertama, potensi kesenjangan antara klaim akademik dan tingkat kematangan sistem. Kedua, potensi lemahnya justifikasi mengapa teknologi tertentu dipilih. Ketiga, potensi kurangnya bukti evaluasi empiris, terutama pada usability, performa, dan validasi pakar. Keempat, potensi belum kuatnya hubungan antara standar yang dirujuk dengan keputusan desain yang benar-benar diterapkan. Oleh karena itu, bagian ini disusun untuk memperjelas batas klaim, memperkuat rasionalitas desain, dan menyiapkan agenda validasi lanjutan.

### 13.1 Evaluasi Kesesuaian Klaim dan Tingkat Kematangan Sistem

Sistem yang dikembangkan telah memiliki banyak modul, yaitu login, home, profil terminal, knowledge base, alur proses, pattern recognition, action scoring, dan dashboard kinerja. Kelengkapan tersebut dapat menimbulkan kesan bahwa sistem telah siap digunakan sebagai sistem operasional. Namun, secara akademik klaim tersebut perlu dibatasi. Sistem masih berada pada tingkat prototipe karena belum memiliki backend, database, autentikasi server, audit trail, dan manajemen data multi-user.

Dengan demikian, klaim yang paling tepat adalah bahwa sistem ini merupakan prototipe web information system yang mengintegrasikan informasi proses, pengetahuan operasional, risiko, tindakan, dan kinerja. Sistem belum dapat diklaim sebagai platform operasional produksi, sistem manajemen risiko penuh, atau decision support system berbasis prediksi. Batas klaim ini perlu ditulis secara eksplisit agar kontribusi sistem tetap proporsional.

| Potensi Klaim | Status yang Lebih Tepat | Alasan Pembatasan |
| --- | --- | --- |
| Sistem informasi operasional produksi | Prototipe sistem informasi operasional | Belum ada backend, database, dan audit trail |
| Decision support system penuh | Prototipe decision support berbasis scoring | Belum ada model prediktif dan data historis tervalidasi |
| Knowledge management system lengkap | Knowledge base terstruktur | Belum ada validasi pakar, metadata, versioning, dan workflow approval |
| Risk management system formal | Risk mapping dan action scoring | Belum ada likelihood, impact, risk owner, monitoring, dan review formal |
| Dashboard manajemen real-time | Dashboard statis berbasis dataset lokal | Belum ada integrasi API/data real-time |

Penguatan narasi: Sistem sebaiknya diposisikan sebagai artefak integratif yang membuktikan kemungkinan penyatuan profil terminal, dokumentasi proses, knowledge base, risk-action mapping, dan visualisasi kinerja dalam satu lingkungan web. Kontribusinya terletak pada integrasi konseptual dan rancangan prototipe, bukan pada klaim kesiapan produksi.

### 13.2 Evaluasi Hubungan Teori, Standar, dan Implementasi

Bab ini telah menggunakan PMBOK Guide, ISO 21502, ISO 21511, ISO 31000, ISO 9001, ISO 19650, ISO/IEC/IEEE 12207, ISO/IEC 25010, ISO 9241-210, WCAG 2.2, dan OWASP ASVS. Celah yang perlu diantisipasi adalah standar tersebut jangan hanya menjadi daftar rujukan, tetapi harus benar-benar terlihat fungsinya dalam argumentasi.

Hubungan standar dengan implementasi dapat diperkuat melalui tiga cara. Pertama, standar digunakan untuk menjelaskan alasan fitur dipilih. Misalnya, ISO 31000 mendukung kebutuhan pemetaan risiko dan tindakan. Kedua, standar digunakan untuk menilai keterbatasan. Misalnya, OWASP ASVS menunjukkan bahwa login client-side belum aman. Ketiga, standar digunakan untuk menyusun agenda pengembangan. Misalnya, ISO 19650 mengarah pada kebutuhan metadata, versioning, dan tata kelola informasi.

| Standar | Peran dalam Narasi | Bukti Implementasi | Celah yang Masih Ada |
| --- | --- | --- | --- |
| PMBOK Guide/ISO 21502 | Menjelaskan value delivery, tailoring, dan pengendalian proyek | Sistem mendukung informasi, dashboard, dan pengambilan keputusan awal | Belum ada governance workflow dan change control |
| ISO 21511 | Menjelaskan struktur aktivitas dan WBS | Knowledge base disusun berdasarkan aktivitas terminal | WBS belum ditautkan ke cost/schedule/resource secara formal |
| ISO 31000 | Menjelaskan risiko dan tindakan | Pattern recognition memuat risiko, penyebab, tindakan | Belum ada likelihood-impact matrix dan risk owner |
| ISO 19650 | Menjelaskan pengelolaan informasi aset | Folder aset, halaman profil, dokumentasi, knowledge base | Belum ada metadata, status, approval, dan versioning |
| ISO/IEC 25010 | Menilai kualitas perangkat lunak | Functional suitability dan portability terlihat | Security, maintainability, reliability perlu diperkuat |
| ISO 9241-210/WCAG | Menilai usability dan accessibility | Navigasi, card, chart, dan responsive layout tersedia | Belum ada audit usability/accessibility formal |
| OWASP ASVS | Menilai keamanan aplikasi web | Celah keamanan login client-side teridentifikasi | Belum ada backend auth, session, role, dan secure storage |

Penguatan narasi: Setiap standar perlu disebut sebagai alat evaluasi, bukan klaim kepatuhan. Kalimat yang disarankan adalah: "Standar digunakan sebagai kerangka pembacaan dan evaluasi desain, bukan sebagai klaim sertifikasi atau pemenuhan penuh."

### 13.3 Evaluasi Metodologi dan Validasi

Metodologi pengembangan telah dijelaskan menggunakan pendekatan Waterfall dokumentatif dengan iterasi terbatas pada UI dan dashboard. Celah yang perlu diperkuat adalah hubungan antara metodologi pengembangan dan validasi hasil. Jika sistem hanya dijelaskan sebagai selesai dibuat, maka pembuktian akademiknya masih lemah. Sistem perlu dievaluasi melalui beberapa lapisan validasi.

Validasi minimal yang disarankan meliputi black-box testing, usability testing, performance testing, dan expert review. Black-box testing membuktikan fungsi berjalan. Usability testing membuktikan sistem dapat digunakan. Performance testing membuktikan halaman cukup responsif. Expert review membuktikan isi knowledge base, risiko, dan tindakan masuk akal menurut pengguna berpengalaman.

| Jenis Validasi | Tujuan | Bukti yang Perlu Disiapkan |
| --- | --- | --- |
| Black-box testing | Memastikan fitur berjalan sesuai skenario | Tabel pengujian, screenshot hasil, browser, tanggal uji |
| Usability testing/SUS | Mengukur kemudahan penggunaan | Daftar responden, skor, interpretasi, rekomendasi perbaikan |
| Performance testing | Mengukur waktu muat dan beban halaman | Lighthouse/DevTools report, ukuran aset, waktu render chart |
| Expert review | Memvalidasi knowledge base, risiko, tindakan, dan indikator | Catatan pakar/operator, revisi konten, persetujuan konseptual |
| Accessibility review | Memeriksa keterbacaan dan aksesibilitas web | Audit WCAG dasar, alt text, kontras, keyboard navigation |
| Security review | Mengidentifikasi kelemahan keamanan | Catatan OWASP gap, rekomendasi backend auth |

Penguatan narasi: Bab ini sebaiknya menyatakan bahwa evaluasi yang dilakukan pada tahap prototipe bersifat formatif, bukan final. Evaluasi formatif bertujuan menemukan celah dan memperbaiki rancangan. Evaluasi sumatif baru dapat dilakukan setelah sistem memiliki backend, database, dan data operasional yang lebih stabil.

### 13.4 Evaluasi Kekuatan dan Kelemahan Arsitektur

Arsitektur static client-side dipilih karena sesuai untuk prototipe. Keunggulannya adalah mudah dijalankan, tidak membutuhkan server, cepat dikembangkan, dan cocok untuk demonstrasi akademik. Namun, kelemahannya signifikan jika sistem diarahkan ke penggunaan operasional. Data belum terpusat, login tidak aman, pembaruan konten membutuhkan edit kode, dan keputusan pengguna hanya tersimpan pada browser lokal.

Narasi akademik perlu menekankan bahwa arsitektur bukan sekadar pilihan teknis, tetapi pilihan metodologis. Arsitektur yang ringan mendukung eksplorasi konsep, tetapi membatasi validitas operasional. Oleh karena itu, arsitektur saat ini harus dibaca sebagai strategi prototyping, sedangkan arsitektur lanjutan menjadi agenda transformasi.

| Aspek Arsitektur | Kekuatan | Kelemahan | Implikasi Akademik |
| --- | --- | --- | --- |
| Static HTML/CSS/JS | Mudah dijalankan dan dipresentasikan | Duplikasi kode dan sulit scaling | Tepat untuk proof-of-concept |
| Data hardcoded | Cepat dibuat dan mudah dikontrol | Sulit diperbarui dan tidak multi-user | Perlu migrasi ke JSON/API/database |
| CDN library | Implementasi cepat | Bergantung koneksi internet | Perlu bundling lokal untuk offline/produksi |
| localStorage | Mudah menyimpan keputusan lokal | Tidak aman dan tidak tersinkronisasi | Hanya cocok untuk simulasi keputusan |
| Login client-side | Memperlihatkan alur login | Tidak aman untuk produksi | Harus disebut simulasi autentikasi |

Penguatan narasi: Arsitektur saat ini tidak perlu dipertahankan sebagai bentuk final. Justru kekuatannya adalah menunjukkan tahapan awal yang jelas sebelum sistem ditingkatkan menjadi full-stack web app.

### 13.5 Evaluasi Kontribusi Ilmiah dan Praktis

Kontribusi ilmiah sistem terletak pada penyusunan model digital yang menghubungkan proses, pengetahuan, risiko, tindakan, dan indikator kinerja. Kontribusi ini lebih kuat dibandingkan sekadar membuat website profil karena sistem membangun relasi antara aktivitas terminal, potensi risiko, penyebab, tindakan, scoring, dan dashboard. Dengan kata lain, sistem mengubah informasi operasional yang tersebar menjadi struktur pengetahuan yang dapat dibaca ulang.

Kontribusi praktisnya terletak pada kemudahan pengguna memahami alur proses, membaca indikator, dan mengevaluasi alternatif tindakan. Sistem dapat digunakan sebagai media pembelajaran, demonstrasi, diskusi pakar, atau dasar pengembangan sistem yang lebih matang. Namun, kontribusi praktis ini masih terbatas pada penggunaan non-produksi.

| Jenis Kontribusi | Bentuk Kontribusi | Batasan |
| --- | --- | --- |
| Konseptual | Integrasi process mapping, knowledge base, risk-action mapping, dan dashboard | Belum diuji dalam lingkungan operasional nyata |
| Metodologis | Penggunaan standar untuk mengevaluasi desain web app | Belum menjadi audit kepatuhan formal |
| Teknis | Prototipe static web app dengan chart, scoring, filter, dan export | Belum full-stack dan belum database-driven |
| Praktis | Media pembelajaran dan analisis awal | Belum digunakan sebagai sistem produksi |

Penguatan narasi: Kontribusi tidak perlu dibesar-besarkan sebagai sistem final. Kontribusi yang lebih kuat secara akademik adalah bahwa sistem menyediakan kerangka integratif yang dapat diuji, dikritisi, dan dikembangkan.

### 13.6 Celah Penelitian dan Agenda Pengembangan Lanjutan

Celah penelitian yang masih terbuka dapat diarahkan pada validasi model, peningkatan arsitektur, integrasi data, dan pengembangan decision support yang lebih kuat. Celah ini penting untuk menunjukkan bahwa sistem bukan akhir penelitian, melainkan titik pijak untuk pengembangan berikutnya.

| Celah Penelitian | Penjelasan | Agenda Lanjutan |
| --- | --- | --- |
| Validasi knowledge base | Risiko dan tindakan perlu divalidasi oleh pakar/operator | Delphi, expert judgment, atau focus group discussion |
| Penguatan scoring | Skor masih berbasis input dan asumsi | Tambahkan bobot, AHP, fuzzy logic, atau data historis |
| Integrasi data kinerja | Dashboard masih statis | Hubungkan ke database/API/CSV pipeline |
| Tata kelola informasi | Belum ada metadata dan versioning | Terapkan prinsip ISO 19650 untuk information container |
| Keamanan sistem | Login masih client-side | Implementasi backend authentication dan role-based access |
| Evaluasi usability | Belum ada hasil SUS/UAT formal | Lakukan pengujian pengguna dan iterasi desain |
| Evaluasi aksesibilitas | Belum ada audit WCAG | Lakukan audit aksesibilitas dasar |
| Kesiapan produksi | Belum ada backend, database, monitoring | Susun roadmap arsitektur produksi |

Agenda pengembangan yang paling logis adalah bertahap. Tahap pertama adalah memisahkan data dari file HTML menjadi JSON atau modul data terstruktur. Tahap kedua adalah menambahkan backend API. Tahap ketiga adalah memindahkan data ke database. Tahap keempat adalah menambahkan autentikasi dan role access. Tahap kelima adalah melakukan validasi pakar dan usability test. Tahap keenam adalah mengembangkan model decision support yang lebih kuat berbasis data historis.

### 13.7 Rumusan Penutup Evaluatif

Berdasarkan evaluasi kritis tersebut, bab ini dapat ditutup dengan posisi akademik yang lebih tegas: web app yang dikembangkan merupakan prototipe integratif untuk pengelolaan informasi proses, risiko, tindakan, pengetahuan, dan kinerja pada konteks operasional terminal peti kemas. Sistem telah menunjukkan kelayakan konseptual dan fungsional awal, tetapi belum memenuhi prasyarat sistem produksi. Nilai utama sistem terletak pada kemampuannya menyusun informasi lintas modul menjadi struktur yang dapat dianalisis, bukan pada klaim otomatisasi atau keputusan final.

Dengan demikian, celah narasi akademis telah diperjelas menjadi celah pengembangan yang produktif. Keterbatasan sistem tidak hanya menjadi kelemahan, tetapi menjadi dasar argumentasi untuk penelitian lanjutan: penguatan tata kelola data, validasi pakar, integrasi backend, peningkatan keamanan, evaluasi usability, dan pengembangan decision support berbasis data. Posisi ini membuat bab pengembangan web tidak berhenti pada dokumentasi teknis, tetapi menjadi bagian dari argumentasi ilmiah mengenai bagaimana artefak digital dapat mendukung pengelolaan informasi, risiko, dan kinerja secara lebih sistematis.
