# Writing Week 1 ( 10 - 14 Oktober 2022)

## Javascript Intermediate
---

### HTTP Request fetch()

```fetch()``` memulai proses pengambilan data dari server ataupun dari internet.
```
const URL = ('https://api.themoviedb.org/3/movie/550?api_key=65cf174fae8bc3274e79960d1c5782b6')
const options = { 
    method: 'POST'
    headers: {
        'Content-Type': 'application/json',
    },
    body: JSON.stringify(data),
}

fetch(URL,options)
```
dari contoh di atas fetch memiliki 2 parameter utama yaitu URL untuk mengakses ke server, dan options untuk mendeklarasikan method yang akan digunakan

lalu kita bisa gunakan untuk mengambil data dari API yang sudah kita cantumkan di URL dan method diubah menjadi ```GET```
```
const getDataAPI = () => {
    const URL = ('http://example.com/movies.json')
    const options = { 
        method: 'GET',
        headers: {
            'Content-Type': 'application/json',
        },
        body: JSON.stringify(data),
    }
    
    fetch(URL,options)
    .then(response => response.json())
    .then(result => result.json())
    .catch(console.error("terdapat error"))
}
```
lalu dapat menggunakan `Async Await`
```
const getDataAPIAsyncAwait = async () => {
    const URL = ('http://example.com/movies.json')
    const options = { 
        method: 'GET',
    }
    
    let response = await fetch(URL, options)
    response = await response.json()
    console.log(response);
}

getDataAPIAsyncAwait()
```
mengambil data dengan async await bertujuan untuk menunda eksekusi hingga proses asynchronous selesai. 


## Git dan Github 
---
pada git dan github lanjutan ini mempelajari bagaimana cara berkolaborasi untuk mengerjakan project pada github.

Sebelum membuat repository sebaiknya kita membuat organization pada github dan meng-invite anggota team serta mengubah aksesnya menjadi owner agar masing-masing team dapat mengedit file dan repo pada organization tersebut.

***Buat Repo di organization***
1. Team lead buat repo untuk project yg akan di buat
2. Repo dibuat public, dan ceklis README
3. Buat branch bernama dev


***Mengecek pull request***
1. Setiap ada pull request, team lead akan mengeceknya
2. Jika pull request belum sesuai, bisa dikasih komen atau beri kabar anggota yg melakukan pull request tersebut
3. Jika sudah sesuai, lakukan merge branch

***Ketika tahap development selesai***
1. Jika sekiranya sudah tidak ada update terbaru dari development, saatnya menggabungkan antara branch dev ke branch main/master
2. lakukan pull request untukmenggabungkan branch dev ke branc main

***Langkah-langkah yang harus dilakukan oleh anggotan team***
1. Masing-masing anggota team lakukan `git clone [url-repo]` pada repo yg sudah dibuat 
2. Bagi tugas pada masing-masing anggota kelompok
3. Pindah ke branch dev dengan perintah `git switch dev`
4. Sebelum memulai proses coding, lakukan `git pull` pada branch dev untuk update kode terbaru
5. Anggota membuat branch dari dev dengan perintah `git branch [nama-branch]`
6. Pindah ke dalam branch yg sudah dibuat `git switch [nama-branch]`
7. Lakukan pengerjaan fitur pada branch yang telah kalian buat
8. Jika fitur sudah selesai, sebelum di push lakukan langkah no 3, 4, dan 6
9. Lalu `git merge de`v untuk menhindari conflict di github
10. Jika ada conflict, selesaikan code yang conflict dahulu sebelum ke tahap selanjutnya
11. jika sudah aman, commit lalu `git push origin [nama-branch]`
12. lakukan pull request untuk merge ke branch dev
13. tunggu pull request di acc oleh team lead
14. Jika sudah, ulangi proses dari no 2

*Note: langkah no 8 dan 9 dapat di ganti dgn `git pull origin dev`*

## Responsive Web 
---

Responsive Web Design tujuannya adalah untuk membuat design website dapat diakses dalam device apapun dan tampilannya tetap tertata rapi. Ukuran layar dalam design dapat disebut dengan `viewport`. Vieport ini sebenarnya sudah ada pada kerangka html menggunakan tag meta, tetapi masih harus di styling agar webbsite dapat responsive.
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

***max-width***

Properti ini digunakan untuk ntuk mengatur lebar maksimum elemen. Hal ini mencegah nilai properti lebar dari menjadi lebih besar dari max-width.

contoh penggunaan:
```
p {
    max-width: 100px;
}
```

***CSS Relative Units***

Satuan ukur yang bersifat relative. 
Beberapa satuan unit yang relative :
- em : relatif/mengikuti ukuran huruf (font-size).
- rem : relatif/mengikuti ukuran huruf (font-size) pada root element.
- vw : relatif 1% dari ukuran lebar viewport.
- vh : relatif 1% dari ukuran tinggi viewport.
- % : ukurannya relatif pada parent terdekat.

contoh penggunaan: 
```
.container {
    font-size: 20px;
}

.title {
    font-size: 2rem;
}
```

***Media Query***

Media query digunakan untuk membuat beberapa styles tergantung pada jenis device. `Breakpoint` merupakan cara kerja media query untuk mengecek ukuran viewport (layar/area dimana konten terlihat) apakah sesuai dengan kondisi yang kita deklarasikan, jika benar maka kode dalam kondisi tersebut yang akan dieksekusi. Dengan kata lain media query memberikan kemampuan menggunakan kode css yang sesuai dengan kondisi yang ditentukan.

```
@media not|only mediatype and (expressions) {
  CSS-Code;
}

// contoh penggunaan 
@media screen and (min-width: 480px) {
  body {
    background-color: lightgreen;
  }
}
```

***Flexbox***

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

## Boostrap
---
Bostrap merupakan framework css untuk melakukan styling. 


**Copyright by Putri Dresty F @2022**


