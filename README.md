# EXPLORATORY DATA ANALYSIS (EDA) - CRIME IN BOSTON
### Prepared and Presented by Kevin
<hr>

## PROJECT GUIDELINE
Pada Modul 2 program *Job Connector Data Science* di **Purwadhika Digital Technology School** yang mencakup pembelajaran tentang Data Analysis, siswa telah mempelajari materi SQL, *data manipulation*, *data visualization*, dan *statistics*. Capstone Project modul 2 ini bertujuan untuk mengimplementasikan materi yang telah dipelajari oleh siswa dalam sebuah projek.

Pengerjaan Capstone Project modul 2 ini diharapkan mampu melatih siswa dalam membuat sebuah rangkaian analisis. Dalam proyek ini, siswa akan memposisikan diri sebagai *data analyst* dalam sebuah perusahaan. Siswa akan membuat serangkaian pertanyaan sesuai berdasarkan keperluan bisnis dan masalah yang mungkin dihadapi oleh perusahaan terkait sesuai dengan data yang didapatkan.

Siswa akan menjawab pertanyaan yang telah dibuat melalui analisis data, membuat cerita dan visualisasi, serta mempresentasikan *insight* dari analisis yang kemudian bisa digunakan *stakeholders* sebagai dasar pengambilan keputusan bisnis.

<hr> 

## PROJECT PRESENTATION
![Crime in Boston](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide01.PNG?raw=True)
- Dataset yang saya pilih adalah untuk membuat Capstone Project ini berjudul *Crime in Boston*. 

![Agenda](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide02.PNG?raw=True)
- Isi dari presentasi ini meliputi *Data Profiling* yaitu identifikasi detail dan limitasi dari proyek ini, kemudian merumuskan masalah yang ingin dicarikan *insight*nya dalam proyek ini, dilanjutkan dengan ekstraksi *insight* dari dataset yang diperoleh yang nantinya akan digunakan sebagai dasar dalam memberikan rekomendasi kepada *stakeholders*.

![Position](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide03.PNG?raw=True)
- Posisi berbicara saya dalam presentasi kali ini adalah sebagai konsultan kriminal yang handal dalam memakai data sebagai dasar pemberian konsultasi bagi klien saya. Sedangkan, klien saya di posisi ini adalah Boston Police Department, yaitu satuan kepolisian yang bertanggung jawab atas keamanan warga kota Boston yang terletak di negara bagian Massachusetts, Amerika Serikat. Kota Boston sendiri adalah salah satu kota metropolitan terbesar di Amerika Serikat. Petugas yang akan mengimplementasikan rekomendasi yang diberikan adalah bagian Penjadwalan dalam Boston Police Department yang bertanggung jawab mengatur jumlah staf polisi yang diturunkan untuk berjaga di titik-titik tertentu di kota Boston.

![Profiling](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide04.PNG?raw=True)
- *Data profiling* adalah aktivitas untuk mengidentifikasi dataset yang didapatkan agar dapat digunakan dalam analisa pencarian *insight*.

![Limit](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide05.PNG?raw=True)
- Dataset yang didapatkan diperoleh dari situs Kaggle.com
- Dataset ini diperoleh dari tindakan polisi yang diambil di kota Boston selama periode 14 Juni 2015 - 3 September 2018
- Data ini merupakan hasil dari sistem baru yang diimplementasikan kepolisian kota Boston yang berfokus pada pencatatan data lokasi dan waktu terjadinya tindakan kriminal beserta respon polisi terhadap insiden tersebut

![Column](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide06.PNG?raw=True)
- Dalam dataset ini, kolom-kolom yang terdapat didalamnya dapat dijabarkan sebagai berikut:
    - Kolom `Incident Number`: merupakan angka unik untuk setiap insiden, namun nomor yang sama akan dipakai untuk merepresentasikan beberapa respon polisi di dalam 1 kejadian. Maka, `Incident Number` digabung dengan `Offense Code` sehingga setiap angka unik dari kombinasi ini akan merepresentasikan 1 respon spesifik dari polisi terhadap 1 kejadian spesifik di lapangan.
    - Kategori Offense Code: dijabarkan melalui kolom `Code` (kode unik untuk setiap jenis respon polisi), `Name` (deskripsi singkat), `Group` (kategori tipe tindak kriminal yang terjadi), dan `Description` (deskripsi lengkap).
    - Kategori Crime Location: dijabarkan melalui kolom `District` yang berisi kode distrik. Kolom ini kemudian menjadi basis ditambahkannya kolom sintetis untuk menampung nama distrik dari setiap nomor distrik. Kemudian, ada angka unik berupa `Reporting Area` dan `Street Name` yang sulit untuk dikaitkan dengan kolom lainnya. Selain itu, dengan adanya kolom `Location` beserta kolom `Longitude` dan `Latitude` yang bisa langsung menunjukkan secara spesifik lokasi insiden di peta, maka relevansi kolom `Reporting Area` dan `Street Name` pun berkurang dan menyebabkan kolom ini tidak digunakan untuk analisa.
    - Kategori Crime Details: berisi inti dari dipakainya sistem pencatatan ini oleh polisi, yaitu untuk mencatat waktu secara lengkap dari tanggal, bulan, tahun, jam, menit, dan detik dari setiap pelaporan. Kemudian ada juga kolom `Shooting` yang mengindikasikan apakah terjadi penembakan dalam insiden tersebut. Lalu ada pula kolom Uniform Crime Reporting (UCR) Part yang mengkategorisasi setiap tindakan polisi kepada 4 Part yang berbeda dan akan dilaporkan kepada satuan keamanan yang berbeda.

![Problem](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide07.PNG?raw=True)
- Berikut rumusan masalah yang bisa dijawab menggunakan informasi yang tersedia di dalam dataset yang ada.

![BigPicture](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide08.PNG?raw=True)
- Keseluruhan proyek ini bertujuan untuk memberikan informasi kepada Staf / Bagian Pengatur Jadwal di dalam Boston Police Department untuk dapat mengerahkan staf di lapangan secara efektif, efisien dan dilengkapi dengan perlengkapan yang memadai.
- Diperlukannya jumlah polisi yang tepat dalam patroli disebabkan riset mengungkapkan bahwa polisi secara fisik memberikan rasa aman bagi masyarakat dan dapat mempengaruhi keputusan seseorang untuk melakukan tindak kriminal. Selain itu, angka kejahatan di kota Boston secara spesifik mengalami tren peningkatan di tahun 2020 sehingga diperlukan adanya langkah strategis untuk menekan tingkat kriminalitas ini.

![Question](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide09.PNG?raw=True)
- Berikut adalah 6 pertanyaan yang dapat menjawab pertanyaan utama dari proyek ini dan dapat dijawab menggunakan informasi dalam dataset.

![Extraction](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide10.PNG?raw=True)
- Melalui aktivitas analisa, dilakukan ekstraksi terhadap dataset yang ada untuk mendapatkan *insight* yang relevan untuk menjawab *Big Question* yang ada.

![No1.1](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide11.PNG?raw=True)
- Dapat dilihat bahwa aktivitas yang paling banyak dilakukan polisi adalah mencari atau memberikan bantuan medis kepada individu di TKP. Ada pula aktivitas untuk melakukan investigasi kepada individu/kelompok sebelum dilakukan penangkapan. Selain itu, ada pula respon terhadap insiden pengrusakan harta benda dan kabur dengan kendaraan bermotor, vandalisme dan ancaman.

![No1.2](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide12.PNG?raw=True)
- Dikarenakan aktivitas memberikan bantuan medis adalah yang tertinggi, maka polisi harus dibekali pelatihan untuk bantuan pertama di TKP dengan prinsip DRSABC. Selain itu, Boston Police Department juga harus berkoordinasi dengan rumah sakit terdekat dengan titik-titik lokasi insiden kriminal sering terjadi dan memastikan fasilitas kesehatan di rumah sakit tersebut memadai dan punya staf yang siap untuk terjun ke lokasi kejadian.
- Jika dibutuhkan, tambah jumlah sheriff atau detektif profesional dikarenakan banyak dibutuhkannya tenaga investigator.

![No2.1](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide13.PNG?raw=True)
- Berikut tren jumlah respon polisi yang diberikan per tahun dan per triwulan. Untuk 2015Q1 dan 2018Q3, jumlahnya tidak relevan dikarenakan tidak mewakili periode waktu 3 bulan penuh.
- Tren cukup stabil dengan angka per tahun berkisar di angka 100 ribu dan per triwulan di angka 25 ribu.

![No2.2](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide14.PNG?raw=True)
- Tren yang stagnan ini berarti polisi harus lebih efektif lagi dalam menerapkan langkah dalam mengurangi jumlah insiden kriminal di kota Boston. Ada setidaknya 6 langkah yang dapat dilakukan tanpa menggunakan senjata api dikarenakan pemakaian senjata api hanya akan membuat masyarakat semakin antipati dengan pihak kepolisian setelah maraknya isu *police brutality* dalam satu tahun belakangan.

![No3.1](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide15.PNG?raw=True)
- Menurut riset dari Alison Baird et al. tahun 2019, kriminalitas ringan lebih sering terjadi pada siang hari di hari kerja, sedangkan kriminalitas berat cenderung terjadi saat malam hari.
- Dilakukan uji hipotesis yang menghasilkan bahwa proporsi kejadian pada akhir pekan dibawah 50%

![No3.2](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide16.PNG?raw=True)
- Jika ditampilkan dalam grafik per hari, dapat dilihat bahwa polisi cenderung lebih sibuk saat hari kerja dibandingkan akhir pekan

![No3.3](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide17.PNG?raw=True)
- Dengan perbedaan yang tipis, maka polisi tidak perlu membuat program khusus untuk pengamanan pada hari-hari tertentu dalam satu minggu.
- Kota Boston menduduki peringkat 9 dari 10 kota metropolitan terbesar di AS dalam hal tingkat kriminalitas, namun Boston Police Department sebaiknya tidak berpuas diri karena sesuai poin nomor 2, angka kriminalitas di Boston cenderung stagnan.

![No4.1](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide18.PNG?raw=True)
- Ini adalah penjabaran dari 4 kasus terbanyak dalam setiap kategori UCR

![No4.2](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide19.PNG?raw=True)
- Ini adalah contoh satu `Incident Number` yang sama yang dipakai untuk beberapa respon polisi yang berbeda

![No4.3](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide20.PNG?raw=True)
- Secara keseluruhan, sistem kategorisasi di UCR sudah baik karena sudah bisa membagi setiap tindakan polisi kepada UCR Part yang sesuai.
- Butuh adanya pola penomoran baru yang dipakai agar satu nomor insiden dapat mewakili 1 tindakan polisi yang berbeda, dan bukan untuk 1 insiden yang didalamnya memungkinkan beberapa tindakan polisi untuk diambil.

![No5.1](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide21.PNG?raw=True)
- Berikut proporsi setiap periode waktu yang ditentukan.
- Night terlihat mempunyai proporsi paling tinggi, walaupun memang periode waktunya jauh diatas kategori lainnya (9 jam sedangkan yang lainnya hanya 2-3 jam)
- Early morning merupakan waktu dimana paling sedikit aktivitas polisi terjadi

![No5.2](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide22.PNG?raw=True)
- Perbanyak patroli pada malam hati dan persiapkan shift khusus untuk malam hari jika diperlukan, karena ada riset dimana banyak kasus kejahatan berat terjadi saat malam hari
- Sesuaikan shift kerja dengan jam sibuk polisi, usahakan pergantian shift dilakukan di late afternoon dan early morning dimana aktivitas polisi paling rendah

![No6.1](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide23.PNG?raw=True)
- Berikut peta kota Boston yang dibagi menjadi 12 distrik. Setiap distrik ditandai warna yang makin gelap mengartikan semakin banyak aktivitas polisi terjadi.
- Sisi ujung utara dan selatan kota Boston menjadi kawasan paling sedikit aktivitas polisi terjadi
- Roxbury dan beberapa distrik disekitarnya menjadi hot-spot dimana distrik-distrik dengan jumlah aktivitas polisi yang paling banyak berada
- Ada 10 titik yang menandakan 10 koordinat terjadinya aktivitas polisi terbanyak, 7 diantaranya sekitar utara Downtown sampai utara Roxbury

![No6.2](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide24.PNG?raw=True)
- Untuk mengakses dashboard aktivitas polisi per Distrik, silahkan kunjungi link tertera

![No6.3](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide25.PNG?raw=True)
- Perhatikan 10 titik spesifik dimana aktivitas polisi paling sering terjadi, koordinasikan juga dengan rumah sakit yang dekat dengan 10 titik tersebut
- Buat satuan kerja khusus untuk kontrol daerah utara Downtown sampai utara Roxbury

![Conclusion](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide26.PNG?raw=True)
- Kesimpulan dari proyek ini adalah sbb:
    1. Perlu adanya training kepada polisi lapangan untuk memberikan bantuan pertama sembari menunggu tim medis hadir, berikut pelatihan investigasi jika diperlukan
    2. Diusahakan tidak menggunakan tindakan represif dengan senjata api untuk menghindari citra negatif terhadap kepolisian
    3. Buat pola penomoran atas `Incident Number` yang memiliki nilai khusus kepada setiap tindakan polisi, dan bukan 1 insiden
    4. Kendalikan titik-titik dimana aktivitas polisi paling banyak terjadi selama periode waktu didalam dataset

![Thanks](https://github.com/kevinchenkc/EDA-Crime-in-Boston/blob/main/Images/Slide27.PNG?raw=True)
- Kritik, saran, dan ajakan kolaborasi dapat disampaikan melalui email atau sosial media pribadi saya. Terima kasih
<hr>

### *For queries or collaboration, please reach me on my social media below*:
[Instagram](https://www.instagram.com/kevinchenkc) |
[LinkedIn](https://www.linkedin.com/in/kevinchenkc/) |
[Facebook](https://www.facebook.com/kevin.chen.5688476/) |
📞: (+62)-877 8123 2862