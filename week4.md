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
Bostrap merupakan framework css untuk melakukan styling. Bootstrap dapat mempermudah pembuatan web dengan memasukkan class tertentu yang disediakan oleh bootstrap. Elemen yang disediakan bootstrap juga. Bootstrap juga mempermudahkan kita untuk membuat web menjadi responsive dengan class yang disediakan. 

### Cara Penggunaan Bootstrap
- dengan memasukkan starter template CDN yang disediakan boostrap ke dalam file HTML kita
```
<!doctype html>
<html lang="en">
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">

    <!-- Bootstrap CSS -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min css"  rel="stylesheet" integrity="sha384-EVSTQN3 azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

    <title>Hello, world!</title>
  </head>
  <body>
    <h1>Hello, world!</h1>

    <!-- Optional JavaScript; choose one of the two! -->

    <!-- Option 1: Bootstrap Bundle with Popper -->
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js" integrity="sha384-IQsoLXl5PILFhosVNubq5LC7Qb9DXgDA9i+tQ8Zj3iwWAwPtgFTxbJ8NT4GN1R8p" crossorigin="anonymous"></script>
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.min.js" integrity="sha384-cVKIPhGWiC2Al4u+LWgxfKTRIcfu0JTxR+EQDz/bgldoEyl4H0zUF0QKbrJ0EcQF" crossorigin="anonymous"></script>
    
  </body>
</html>
```
---
Setelah memasukkan starter template yang disediakan Bootstrap maka kita dapat memakai class yang ada pada bootstrap, dengan syarat kita juga harus terhubung ke internet.

### Layout Bootstrap
- Default container 
---
```
<div class="container">
  <!-- Content here -->
</div>
```
- Responsive container pada bootstrap 
---
responsive container memungkinkan anda menentukan kelas yang lebarnya 100% dan disesuaikan dengan ukuran mulai dari ```container-sm``` sampai ```container-xxl```
```
<div class="container-sm">100% wide until small breakpoint</div>
<div class="container-md">100% wide until medium breakpoint</div>
<div class="container-lg">100% wide until large breakpoint</div>
<div class="container-xl">100% wide until extra large breakpoint</div>
<div class="container-xxl">100% wide until extra extra large breakpoint</div>
```
- Container Fluid
---
container dengan lebar penuh, yang mencakup seluruh lebar viewport.
```
<div class="container-fluid">
  ...
</div>
```
### Grid
Sistem grid Bootstrap terdiri dari flexbox dan ukurannya 12 kolom pada halaman. Pada 12 kolom itu juga bisa dibagi beberapa kolom sesuai dengan kebutuhan.
- contoh grid dengan pembagian kolom
```
<div class="container text-center">
  <div class="row">
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
    <div class="col">
      Column
    </div>
  </div>
</div>
```
syntax di atas menunjukkan flexbox yang dibagi menjadi 3 kolom dengan berukuran yang sama,

### Content 
content pada bootstrap disini saya mengambil contoh tabel yang biasanya digunakan
- Table
---
Basic table merupakan tabel sederhana yang ada di bootstrap. Agar dapat menggunakan jenis tabel ini kita dapat menggunakan class table pada bootstrap. tabel pada bootstrap juga sudah mendukung responsive desain agar tampilan tabel dapat lebih baik saat diakses diberbagai jenis perangkat.
```
<table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">First</th>
      <th scope="col">Last</th>
      <th scope="col">Handle</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">1</th>
      <td>Mark</td>
      <td>Otto</td>
      <td>@mdo</td>
    </tr>
    <tr>
      <th scope="row">2</th>
      <td>Jacob</td>
      <td>Thornton</td>
      <td>@fat</td>
    </tr>
    <tr>
      <th scope="row">3</th>
      <td colspan="2">Larry the Bird</td>
      <td>@twitter</td>
    </tr>
  </tbody>
</table>
```
- Variant tabel
---
ada beberapa variant tabel yang ada pada bootstrap dan bisa digunakan dengan cara memasukkan class warna seperty ```primary``` untuk warna biru ```success``` untuk warna hijau, ```danger``` , dan lain-lain.
![Variant Tabel](https://www.tutorialrepublic.com/lib/images/bootstrap-5/bootstrap-table-with-accented-rows.png)

#### Component 
componen dalam bootstrap merupakan bagaian yang penting untuk membuat website dengan fitur-fitur tertentu, contoh penggunaan beberapa component :
---
- Membuat Navbar
- Menggunakan Card
- Membuat Form
- Membuat Button
---
- Navbar 
```
<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Navbar</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarNav">
      <ul class="navbar-nav">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">Home</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Features</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">Pricing</a>
        </li>
        <li class="nav-item">
          <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
        </li>
      </ul>
    </div>
  </div>
</nav>
```
membuat navbar pada bootstrap dengan menambahkan tag ```<nav>```, juga bisa ditambahkan style background-colour seperti ```bg-dark```, ```bg-primary```, ```bg-light```. 

- Card 
---
Card merupakan salah satu component yang bisa memuat thumbnail, tittle, deskripsi, dan bisa ditambahkan button di dalam card.
```
<div class="card" style="width: 18rem;">
  <img src="..." class="card-img-top" alt="...">
  <div class="card-body">
    <h5 class="card-title">Card title</h5>
    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
    <a href="#" class="btn btn-primary">Go somewhere</a>
  </div>
</div>
```

- Form
---
Sesuai namanya form adalah salah satu component yang berguna untuk pengisian sebuah data
```
<div class="mb-3">
  <label for="exampleFormControlInput1" class="form-label">Email address</label>
  <input type="email" class="form-control" id="exampleFormControlInput1" placeholder="name@example.com">
</div>
<div class="mb-3">
  <label for="exampleFormControlTextarea1" class="form-label">Example textarea</label>
  <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
</div>
```

![form](https://media.geeksforgeeks.org/wp-content/uploads/20201229155434/displayFormControls.png)

- Button 
---
Bootstrap mempunyai style pada button yang telah ditentukan, masing-masing punya tujuan semantiknya sendiri, dengan beberapa tambahan untuk kontrol lebih. itu juga bisa ditunjukkan dengan menambahkan class untuk memberikan style warnanya. untuk menambahkan button bisa menggunakan tag ```<button>```.
```
<button type="button" class="btn btn-primary">Primary</button>
<button type="button" class="btn btn-secondary">Secondary</button>
<button type="button" class="btn btn-success">Success</button>
<button type="button" class="btn btn-danger">Danger</button>
<button type="button" class="btn btn-warning">Warning</button>
<button type="button" class="btn btn-info">Info</button>
<button type="button" class="btn btn-light">Light</button>
<button type="button" class="btn btn-dark">Dark</button>
<button type="button" class="btn btn-link">Link</button>
```

**Copyright by Putri Dresty F @2022**


