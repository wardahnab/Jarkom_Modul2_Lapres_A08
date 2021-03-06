# Laporan Resmi Praktikum Modul 2 Kelompok A8


## **Soal**


Semeru adalah salah satu gunung yang terkenal di Jawa Timur. Bibah adalah salah satu juru kunci Semeru. Bibah ingin menyebarkan keindahan Semeru pada dunia sehingga dia membeli 3 buah server yang berada di MALANG, MOJOKERTO dan PROBOLINGGO. Server MALANG akan digunakan sebagai DNS Server Master, MOJOKERTO akan digunakan sebagai DNS Server Slave dan PROBOLINGGO akan digunakan sebagai Web Server. Selain 3 server terdapat 2 klien yang digunakan untuk testing oleh Bibah yaitu GRESIK dan SIDOARJO. Untuk menyambungkan semua jaringan tersebut Bibah memberi router di SURABAYA. Kalian diminta untuk membuat sebuah website utama dengan 


**No 1 dan 2**

(1)alamat http://semeruyyy.pw yang memiliki (2)alias http://www.semeruyyy.pw, 


**Jawaban**


Mengubah Sever Name dan Server alias menjadi semerua08.pw dan www.semerua08.pw


![Nomor-12](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-1-2.png)


**No 3**

dan (3)subdomain http://penanjakan.semeruyyy.pw yang diatur DNS-nya pada MALANG dan mengarah ke IP Server PROBOLINGGO serta dibuatkan 


**Jawaban**


Membuat sub domain penanjakan di server malang seperti gambar di bawah


![Nomortiga](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-3.png)


**No 4**

(4)reverse domain untuk domain utama. Untuk mengantisipasi server dicuri/rusak, Bibah minta dibuatkan


**Jawaban**


Mengubah isi file di server malang pada /etc/bind/named.conf.local seperti gambar di bawah


![Nomor4](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-4%231.png)

![Nomor4](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-4%232.png)


Lalu mengubah isi file di server malang pada /etc/bind/73.151.10.in-addr.arpa seperti gambar dibawah ini


![Nomor4](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-4%233.png)


Mengecek di Client Gresik dengan ``host -t PTR 10.151.73.76``


![Nomor4](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-4%234.png)


**No 5**

(5)DNS Server Slave pada MOJOKERTO agar Bibah tidak terganggu menikmati keindahan Semeru pada Website. Selain website utama Bibah juga meminta dibuatkan


**Jawaban**


Mengubah isi file di server malang pada /etc/bind/named.conf.local seperti gambar di bawah


![Nomor5](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-5%231.png)


Lalu mengubah isi file di server malang pada /etc/bind/named.conf.local seperti gambar di bawah


![Nomor5](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-5%232.png)


**No 6 dan 7**

(6)subdomain dengan alamat http://gunung.semeruyyy.pw yang didelegasikan pada server MOJOKERTO dan mengarah ke IP Server PROBOLINGGO. Bibah juga ingin memberi petunjuk mendaki gunung semeru kepada anggota komunitas sehingga dia meminta dibuatkan (7)subdomain dengan nama http://naik.gunung.semeruyyy.pw, domain ini diarahkan ke IP Server PROBOLINGGO. Setelah selesai membuat keseluruhan domain, kamu diminta untuk segera mengatur web server.


**Jawaban**


**Subdomain gunung.semerua08.pw**

Mengubah isi file di server mojokerto pada /etc/bind/named.conf.local seperti gambar dibawah


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%231.png)


Mengecek pada Client Gresik dengan menggunakan ``ping gunung.semerua08.pw``


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%232.png)


- Delegasi Domain


Mengubah isi file di server malang pada /etc/bind/jarkom/semerua08.pw seperti gambar di bawah


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%233.png)


Uncomment pada /etc/bind/named.local.options di server seperti gambar di bawah ini


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%234.png)


Mengubah isi file di server malang pada /etc/bind/named.conf.local seperti gambar di bawah


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%235.png)


Mengubah isi file di server mojokerto pada /etc/bind/named.conf.options seperti gambar di bawah ini


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%236.png)


**subdomain naik.gunung.semerua08.pw**


Mengubah isi file di server mojokerto pada /etc/bind/delegasi/gunung.semerua08.pw seperti gambar di bawah ini


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%237.png)


- Hasil Pengecekan


Melakukan pengecekan pada client gresik dengan menggunakan ``ping gunung.semerua08.pw``


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%238.png)


Melakukan pengecekan pada client gresik dengan menggunakan ``ping naik.gunung.semerua08.pw``


![Nomor6](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/Nomor-6%239.png)


### **No 8**

(8)Domain http://semeruyyy.pw memiliki DocumentRoot pada /var/www/semeruyyy.pw. Awalnya web dapat diakses menggunakan alamat http://semeruyyy.pw/index.php/home. Karena dirasa alamat urlnya kurang bagus, maka 

**Revisi**

Meskipun konfigurasi pada ``/etc/bind/jarkom/semerua08.pw`` di Malang sudah diubah (pada A) menuju ke IP Probolinggo, namun saat dilakukan ping menuju ``semerua08.pw`` dari klien tetap menuju ke IP Malang. Karena itu, browser tidak bisa mengakses ``semerua08.pw``.
![Nomor8](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/8.1.png)

Di samping itu, berikut konfigurasi pada Probolinggo untuk ``semerua08.pw``.
![Nomor8](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/8.2.png)

### **No 9**

(9)diaktifkan mod rewrite agar urlnya menjadi http://semeruyyy.pw/home.

### **No 10**

(10)Web http://penanjakan.semeruyyy.pw akan digunakan untuk menyimpan assets file yang memiliki DocumentRoot pada /var/www/penanjakan.semeruyyy.pw dan memiliki struktur
folder sebagai berikut:

/var/www/penanjakan.semeruyyy.pw
                                /public/javascripts
                                
                                /public/css
                                
                                /public/images
                                
                                /errors


**Revisi**
Bisa dilihat pada directory listing web ``penanjakan.semerua08.pw``.
![Nomor9](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/10.1.png)

![Nomor10](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/10.2.png)


**No 11**

(11)Pada folder /public dibolehkan directory listing namun untuk folder yang berada di dalamnya tidak dibolehkan.

**Revisi**
Untuk menonaktifkan directory listing, dilakukan di dalam file berikut.
![Nomor11](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/11.2.png)

Apabila kita mencoba mengakses folder dalam public, contohnya folder *images*, maka akan muncul page **forbidden**.
![Nomor11](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/11.1.png)


**No 12**

(12)Untuk mengatasi HTTP Error code 404, disediakan file 404.html pada folder /errors untuk mengganti error default 404 dari Apache. 

**Revisi**
Untuk mengimplementasikan error code 404, dilakukan di file berikut ini.
![Nomor12](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/12.2.png)

Tampilan error code 404 sesuai pada folder */errors*.
![Nomor12](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/12.1.png)


**No 13**

(13)Untuk mengakses file assets javascript awalnya harus menggunakan url http://penanjakan.semeruyyy.pw/public/javascripts. Karena terlalu panjang maka dibuatkan konfigurasi virtual host agar ketika mengakses file assets menjadi http://penanjakan.semeruyyy.pw/js. Untuk web http://gunung.semeruyyy.pw belum dapat dikonfigurasi pada web server karena menunggu pengerjaan website selesai. 

**Revisi**
Dilakukan directory alias pada file di bawah ini dengan konfigurasi berikut.
![Nomor13](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/13.2.png)

Hasil mengakses alamat ``penanjakan.semerua08.pw/js`` adalah sebagai berikut.
![Nomor13](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/13.1.png)


**No 14**

(14)sedangkan web http://naik.gunung.semeruyyy.pw sudah bisa diakses hanya dengan menggunakan port 8888. DocumentRoot web berada pada /var/www/naik.gunung.semeruyyy.pw. 

**Revisi**
Setting web ``naik.gunung.semerua08.pw`` dilakukan pada file berikut, di mana port diganti menjadi ``8888``.

![Nomor14](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/14.1.png)

Selain itu juga menambahkan ``Listen 8888`` pada file ``/etc/apache2/ports.conf``. Berikut adalah alamat web ``naik.gunung.semerua08.pw`` yang sudah bisa diakses.

![Nomor14](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/14.2.png)


**No 15**

Dikarenakan web http://naik.gunung.semeruyyy.pw bersifat private (15)Bibah meminta kamu membuat web http://naik.gunung.semeruyyy.pw agar diberi autentikasi password dengan username “semeru” dan password “kuynaikgunung” supaya
aman dan tidak sembarang orang bisa mengaksesnya. Saat Bibah mengunjungi IP PROBOLINGGO, yang muncul bukan web utama http://semeruyyy.pw melainkan laman default Apache yang bertuliskan “It works!”.

**Revisi**
Untuk authentication, sudah dicoba memasukkan Auth di dalam file berikut (yang bagian dicomment, tapi sebelumnya diuncomment)

![Nomor15](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/15.1.png)

Dan dicoba juga menggunakan file ``.htaccess``, namun authentication masih belum bisa bekerja.
![Nomor15](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/15.2.png)

**No 16**

(16)Karena dirasa kurang profesional, maka setiap Bibah mengunjungi IP PROBOLINGGO akan dialihkan secara otomatis ke http://semeruyyy.pw.

**Revisi**
Dilakukan rewrite pada file ``.htaccess`` pada Probolinggo.
![Nomor16](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/16.2.png)

Berikut hasil redirect dari IP Probolinggo ``10.151.73.76`` menuju ke ``semerua08.pw``.
![Nomor16](https://github.com/wardahnab/Jarkom_Modul2_Lapres_A08/blob/main/Gambar/16.1.png)


**No 17**

(17)Karena pengunjung pada /var/www/penanjakan.semeruyyy.pw/public/images sangat banyak maka semua request gambar yang memiliki substring “semeru” akan diarahkan menuju semeru.jpg.
