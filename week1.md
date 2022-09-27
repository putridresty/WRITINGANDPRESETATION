# Writing Week 1 ( 19 - 24 September 2022)

## Unix Command Line
---
Sebelum masuk ke perintah dasar ada beberapa hal yang harus diketahui :
- `Shell` : user interface yang bertugas untuk memproses semua perintah yang diketik di CLI.
- `CLI` :  CLI adalah akronim dari Command Line Interface. Dengan program ini, user bisa mengetikkan perintah dalam bentuk teks dan memberikan instruksi pada komputer untuk mengerjakan tugas tertentu.

Mempelajari beberapa perintah dasar pada sistem operasi unix berupa command line. Perintah dasar yang digunakan berupa teks yang ditulis dalam shell (CLI - Command Line Interface) yang dapat di akses pada terminal.
Perintah-perintah dasar tersebut adalah :
- ***pwd*** (print working directory): command untuk melihat current working directory
- ***ls*** (lists): command untuk melihat file apa saja yang ada didalam suatu directory
- ***cd*** (change directory): command untuk berpindah directory (ex : cd namadorectory)
- ***touch*** : command untuk membuat suatu file
- ***mkdir*** : command untuk membuat suatu direktori
- ***head*** : command beberapa line awal dari sebuah file text
- ***tail*** : command beberapa line akhir dari sebuah file
- ***cat*** : command untuk melihat isi suatu file
- ***cp*** : command untuk mengcopy/menyalin file/direktori
- ***mv*** : command untuk memindahkan suatu file/direktori dan bisa digunakan untuk merename
- ***rm*** : command untuk menghapus file/direktori


## Git and Github
---
***Git*** adalah *version control system* yang digunakan para developer untuk mengembangkan software secara bersama-bersama. Fungsi utamanya adalah mengatur versi dari source code program dengan memberi tanda baris dan code sebagai penanda mana yang diganti atau ditambah. 

***Github*** adalah platform berbasis cloud yang digunakan untuk manajemen project dengan sistem versioning code

Setup awal git dan diarahkan pada akun github :
```
git config --global user.name "nama kalian"
git config --global user.email emailkalian@mail.com
```
lalu cek apakah instalasi berhasil dengan 
```
git config --list
```
Ada beberapat perintah dasar pada git yang harus diketahui :

- git init : Digunakan untuk membuat repository yang ada pada file lokal dan berlokasi di folder .git. 

- git status : Digunakan untuk mengecek status repository lokal. 

- git add : Digunakan untuk perintah menambahkan file baru ke repository yang baru dipilih. (Menambahakan file ke dalam kondisi staging)

- git commit : perintah untuk mengubah kondisi file dari staged ke commited. Commited adalah kondisi dimana revisi sudah disimpan di version control.

- git log : Untuk melihat id perrubahan pada file yang telah di commit.

- git checkout : Jika kita membuat kesalahan  kita dapat mengganti perubahan pada working tree dengan konten terakhir sebelum terjadi kesalahan. (dapat mengubah versi kedalam kondisi yang kita inginkan)

- git reset : Perintah ini akan mengembalikan file ke kondisi sebelumnya,kemudian menghapus catatan versi commit beikutnya.

- git revert : Perintah ini menciptakan komit baru yang membatalkan perubahan dari komit sebelumnya.  

- git remote add origin : Jika kalian belum menghubungkan repository lokal kalian ke remote server. tambahkan server agar dapat mengepushnya.

- git push : Mengirim perubahan ke master branch dari repository remote kita.

- git pull : Mengambil perubahan pada remote ke direktori lokal.

- git clone : Perintah dasar untuk membuat salinan repository ke lokal.
  
- git merge : Untuk menggabungkan branch yang berbeda ke branch kita yang sedang aktif 


## HTML
---
***HTML*** atau kepanjangan dari Hypertext Markup Language. HTML dapat digunakan untuk menampilkan konten yang telah disusun pada web browser. HTML memiliki kerangka/stuktur yang berisi tag. 

***Tag*** merupakan suatu penanda pada awal dan akhiran dari sebuah elemen pada HTML.
Ada beberapa tag popular yang sering digunakan :
```
- <h1></h1> : merupakan tag hading untuk membedakan judul dengan paragraf dibawahnya
- <p></p> : digunakan untuk membungkus paragraf tang telah dibuat
- <img> : digunakan untuk memberikan konten berupa foto/gambar
- <table></table> : digunakan untuk membuat tabel pada html
- dan masih banyak yang lainnya
``` 
***Semantic HTML*** merupakan elemen atau tag yang memiliki sebuah arti, elemen semantik dengan jelas menjelaskan langsung arti dari masing-masing bagiannya. 
![Structure Semantic HTML Image](https://1.bp.blogspot.com/-jL7tUuFADJE/VV6Xm-eoq8I/AAAAAAAAAEw/M-pZ8tjPhqg/s1600/semantic.jpg)


## CSS
---
***CSS*** atau Cascading Style Sheet merupakan bahasa yang digunakan untuk mendesain halaman website. Pada CSS kita dapat mengubah warna, custom font, mengatur tata letak dan lainnya.

### Syntax CSS
```
h1 {
  color: blue;
  font-size: 12px;
}
```
- `h1` merupakan selector.
- `color` dan `font-size` merupakan properti.
- `blue` dan `12px` merupakan value.

### Selector CSS
Selector digunakan untuk menunjuk elemen HTML mana yang hendak kita ubah styling-nya menggunakan CSS. Terdapat 4 buah selector dasar pada CSS sebagai berikut:

- #id
```
    #header {
        color: blue;
        font-size: 12px;
    }
```
- tag
```
    h1 {
        color: blue;
        font-size: 12px;
    }
```
- .class
```
    .active-link {
        color: blue;
        font-size: 12px;
    }
```
- (*)
```
    * {
        color: blue;
        font-size: 12px;
    }
```

Ada 3 cara yang digunakan dalan penulisan CSS :
```
1. Inline 
    
    <h1 style="background-color: aqua;">Hi.. Aku Putri</h1>
    
2. Internal

    h1 {
        border: black 1px solid;
    }


3. Eksternal
    <link rel="stylesheet" href="style.css">

```

### Flexbox pada CSS

Flexbox adalah cara untuk mengatur layout. Flexbox direkomendasikan karena penggunaannya yang mudah dan didukung oleh kebanyakan browser. Flexbox juga dapat mengatur layout secara otomatis. 

![Flexbox Concept](https://bethsoderberg.com/slides/2016/wordcamp-pittsburgh/images/flex-terms.png)

***flex-direction***

properti flex-direction digunakan untuk mengatur letak item child. ada 4 value flex-direction yang harus kamu ketahui:
- row (default): secara default letak item child membentuk sebuah baris dari kiri ke kanan.
- row-reverse: letak item child membentuk sebuah baris dari kanan ke kiri
- column: letak item child membentuk sebuah baris dari atas ke bawah
- column-reverse: letak item child membentuk sebuah baris dari bawah ke atas

***justify-content***

properti justify-content digunakan untuk mengatur tata letak dan space antar item child secara horizontal atau main axis. justify-content memiliki 6 value yaitu:
- flex-start
- flex-end
- center
- space-between
- space-around
- space-evenly

***align-items***

properti align-items digunakan untuk mengatur align dari item child secara vertikal atau cross axis. justify-content memiliki 5 value:
- flex-start
- flex-end
- center
- baseline
- stretch



## Algoritma
---
Secara definisi `algoritma` adalah suatu urutan dari beberapa langkah logis (masuk akal) dan sistematis (terurut) yang digunakan untuk menyelesaikan masalah tertentu.

### Pseudocode
Pseudocode adalah menuliskan algoritma dengan umumnya bahasa inggris sebelum kita implementasikan ke bahasa pemograman tertentu. Pseudocode merupakan suatu bahasa yang memungkinkan programmer untuk berpikir terhadap permasalahan yang harus dipecahkan tanpa harus memikirkan syntax dari bahasa pemrograman yang tertentu.

***Membuat Algoritma sederhana***

> Menghitung luas segitiga
Secara deskripsi dapat ditulish sebagai :
- membuat variabel untuk sisi alas segitiga
- membuat variabel untuk tinggi segitiga
- membuat variabel untuk rumus luas segitiga 
- menampilkan variabel luas segitiga

> Penulisan dengan Pseudocode :
```
Judul
Program luas_segitiga

Deskripsi
var alas, tinggi;

Implementasi

alas ← 100;
tinggi ← 64;
luas_segitiga ← 1/2* alas * tinggi;

print luas_segitiga;
```

```

STORE "alas" with any value
STORE "tinggi" with any value

STORE "luas_segitiga" with
CALCULATE 1/2 times "alas" times "tinggi"

DISPLAY "luas_segitiga"
```

> Penulisan menggunakan JavaScript
```
    let alas = 3;
    let tinggi = 6;
    let luas_segitiga = 1/2*alas*tinggi;
    console.log(luas_segitiga)

```
akan menghasilkan output : 9

## JS Dasar
---
***Javascipt*** adalah bahasa pemrograman komputer yang dinamis. Pada umumnya Javascipt digunakan pada web browser untuk menciptakan halaman web yang menarik, interaktif serta merapkan berbagai fungsi pada halaman web.

### Tipe Data pada Javascript

- ***number*** : tipe data yang mengandung semua angka termasuk angka desimal.
- ***string*** : grup karakter yang ada pada keyboard laptop/PC kita yaitu letters (huruf), number (angka), spaces (spasi), symbol, dan lainnya.
- ***boolean*** : tipe data yang hanya mempunyai 2 buah nilai (TRUE dan FALSE).
- ***null*** : tipe data yang diartikan bahwa sebuah variable/data tidak memiliki nilai.
- ***undefined*** :tipe data yang merepresentasikan varibel/data yang tidak memiliki nilai. Tipe data undefined biasanya didapat dari hasil kesalahan program (error), kelalaian programmer, dan tidak direncanakan.
- ***object*** : koleksi data yang saling berhubungan (related).


### Operator Javascript

1. ***Assignment Operator***
   Assignment operator digunakan untuk menyimpan sebuah nila pada variabel. Tanda operatoin ini adalah sama denga (=)

2. ***Mathematical Assignment Operator***
   Menggunakan gabungan tanda operator matematika dan sama dengan, misal +=, -= dan lain sebagainya.

3. ***Increment dan Decrement***
   Gunakan increment atau decrement untuk menambah atau mengurangi sebesar 1 nilai. Tanda operatormya adalah ++  atau --.

4. ***Arithmetic Operator***
   Arithmetic operator adalah operator yang melibatkan operasi matematika.
   - Tambah (+)
   - Kuramg (-)
   - Perkalian (*)
   - Pembagian (/)
   - Modulus (%)

5. ***Comparison Operator***
   Comparison operator adalah operator yang membandingkan satu nilai dengan nilai lainnya. Hasil operasi yang melibatkan comparison operator adalah antara true or false
   
6. ***Simbol comparison operator***
   - Lebih kecil dari : <
   - Lebih besar dari: >
   - Lebih kecil atau sama dengan: <=
   - Lebih besar atau sama dengan: >=
   - Sama dengan: ===
   - Tidak sama dengan: !==


7. ***Logical Operator***
   Logical operator biasa digunakan untuk sebuah CONDITIONAL pada pemograman. Menghasilkan nilai BOOLEAN yaitu TRUE or FALSE. Simbol dari Logical Operator adalah sebagai berikut:
   - AND operator (&&) : AND akan menghasilkan nilai true jika kedua atau semua premis bernilai TRUE.
   - OR operator (||) : OR akan menghasilkan nilai true jika salah satu premis mengandung nilai TRUE
   - NOT operator (!) : NOT akan membalikkan sebuah nilai BOOLEAN. TRUE menjadi FALSE dan sebaliknya.

### Conditional
Conditional merupakan statement percabangan yang menggambarkan suatu kondisi.

***IF ... ELSE IF ... STATEMENT***

Perkondisan remote control (menggunakan if else). Else … If statement dapat kita gunakan jika kita mempunyai berbagai kondisi.

```
let tombol = 4;

if (tombol === 1) {
    console.log('SCTV');
} else if (tombol === 2) {
    console.log('Indosiar');
}else if (tombol === 3) {
    console.log('Trans 7');
} else if (tombol === 4) {
    console.log('Trans TV');
} else {
    console.log('Channel tidak ditemukan');
}
```

***SWITCH CASE CONDITIONAL***

Switch case :digunakan untuk mempermudah ketika pengkodisian lumayan panjang/banyak
```
let tombol = 11;
switch(tombol) {
    case 1:
        console.log('SCTV');
        break;
    case 2:
        console.log('Indosiar');
        break;
    case 3:
        console.log('Trans 7');
        break;
    case 4:
        console.log('Trans TV');
        break;
    default:
        console.log('Channel tidak ditemukan');
}
```

***TRURHY AND FALSY***

Truthy and falsy digunakan untuk mengecek apakah variabel telah terisi namun tidak mementingkan nilainya.

```
let data = 'Data';

// cek data by truthy
if (data) {
    console.log('Data ini tidak kosong');
} else {
    console.log('Data kosong');
}
```


***TERNARY OPERATOR***

Ternary operator - kurang cocok untuk mengecek banyak kondisi -kalau lebih dari 3 disarankan pake if else
```
let makan = true;

makan ? console.log('sudah kenyang') : console.log('lapar');
```


### Looping

***FOR LOOP***

For loop  dapat digunakan ketika sudah tau batas awal dan akhir looping di angka berapa. Cara penulisan for :

> for (initialitation; condition; post-exression) { statement }

- Inisialisasi: Sebagai inisialisasi awal dari mana mulainya sebuah pengulangan. Kita memberikan nilai awal/default pada parameter ini
- Condition: For loop akan terus berjalan selama kondisi ini terpenuhi. Selama kondisi bernilai TRUE.
- Post-expression (Increment/Decrement): Iterasi statement yang digunakan untuk mengupdate variabel yang menjadi kontrol pada pengulangan

```
let angka = 1;
for (angka; angka <= 10; angka++) {
    console.log(angka);
}
```

***WHILE LOOP***

Gunakan WHILE LOOP jika kita tidak mengetahui jumlah pasti pengulangan. WHILE LOOP akan menjalankan instruksi pengulangan kondisi bernilai TRUE.

> WHILE (expression) { statement }

```
let count = 1;
while (count <= 10 ) {
    console.log(count);
    count +=1;
}
```

***DO WHILE LOOP***

Do while cara penulisannya mirip seperti if statement tetapi kalau if statement hanya sekali atau tidak ada perulangan, maka do while akan diulang tetapi belum menegrti hasil dan titik akhirnya.

cara penulisan :

```
do {
    statement(s);
}while (expression;)
```

contoh penggunaan :
Angka yang dapat dibagi dengan 2,3,4,5,6 
```
let i = 1
let isKetemu = false

while (!isKetemu) {
    if (
        i % 2 == 0 &&
        i % 3 == 0 &&
        i % 4 == 0 &&
        i % 5 == 0 &&
        i % 6 == 0 
    ) {
        console.log(i);
        isKetemu = true
    }

    i++
}
```

**Copyright by Putri Dresty F @2022**