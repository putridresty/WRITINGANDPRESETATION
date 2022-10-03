# Writing Week 1 ( 19 - 24 September 2022)

## Jawacript Scope and Function
---

### ***Scope***
`Scope` adalah konsep dalam flow data variabel. Kita dapat menentukan suatu variabel bisa diakses pada scope tertentu atau tidak.

Pada scope kita juga dapat mengenal blocks diaman 'blocks` merupakan code yang ada didalam curly braces {}.

1. Global Scope
   
   `Global scope` berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file. Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.

   ```
    let nama = 'Putri'; 

    function greeting() {
        return nama;
    }

    console.log(nama) //Output : Putri
   ```

2. Local Scope

    `Local scope` berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping. Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.
    ```
    function greeting() {
    let nama = 'Putri';
    return nama;
    }

    console.log(greeting()) //Output : Putri
    console.log(nama) //Output : null (karena yang dipanggil variabel yang ada didalam fungsi)
    ```


### ***Function***

`Function` adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur. Saat kita membutuhkan fitur tersebut nantinya, kita bisa kembali menmanggil fungsi tersebut dan menggunakannya.

Cara penulisan fungsi adlah sebagai berikut :
![Funtion Stucture](https://s3.ap-south-1.amazonaws.com/s3.studytonight.com/tutorials/uploads/pictures/1587882057-1.png)

Cara memanggil dan menampilkan fungsi :
```
//memanggil suatu fuungsi
fname()

//cara menampilkan fungsi tanpa argumen
console.log(fname()) 

//cara menampilkan fungsi dengan argumen
console.log(fname(arg1, arg2)) 
```

- Dengan parameter, function dapat menerima sebuah inputan data (argumenn) dan menggunakannya untuk melakukan task/tugas.
- Saat membuat function/fitur, kita harus tahu data-data yang dibutuhkan. Misalnya saat membuat function penambahan 2 buah nilai. Data yang dibutuhkan adalah 2 buah nilai tersebut.

Contoh penggunaan fungsi :
```
// fungsi tanpa menggunakan parameter dan argumen
function greeting() {
  let nama = 'Putri';
  return nama;
}
console.log(greeting()) //Output : Putri

// fungsi menggunakan parameter dan argumen
function luas_persegi(s) {
  return s*s
}
console.log(luas_persegi(2)) //Output : 4

```

## Data Type Built in Prototype & Method
---
Didalam setiap data type pasti ada properti pendukung. Properti ini digunakan untuk mengakses dan mengolah suatu data. Properti ini dapat dicari dalam dokumentasi javabscript seperti pada 
> https://developer.mozilla.org/en-US/docs/Web/javascript

## DOM (Document Object Model)
---
`DOM` merupakan dokumen (HTML) yang dimodelkan dalam sebuah objek. DOM dalam javascript bisa diartikan sebagai jembetan antara bahasa pemrograman dan dokumen HTML-nya.

Objek dari dokumen ini menyediakan sekumpulan fungsi dan atribut/data yang bisa kita manfaatkan dalam membuat program Javascript. Inilah yang disebut API (Application Programming Interface).

Cara mengakses DOM ada 2 yaitu :
1. By Element
   - Hanya dapat mengakses HTML by element
   - Misal tag seperti `<span>` dan `<div`

2. By Node
   - Dapat mengakses setiap bagian terkesil di HTML
   - text, comment, dan tag


### ***DOM Traversing Elements***

Traversing dapat dibagi menjadi 3 bagian :
1. Ke bawah 
   
   Cara untuk mengakses elemen :
   ```
    getElementByID
    getElementsByClassName
    getElemeentsByTagName
    querySelector Familiy
    children
   ```

2. Ke atas 
   ```
   parentElement
   closest
   ```

3. Ke samping
   ```
    nextElementSibling
    previousElementSibling
   ```



### ***DOM Manipulating Document***
- Definisi DOM Manipulating Document
  
   Saat menulis halaman web dan aplikasi, salah satu hal paling umum yang ingin Anda lakukan adalah memanipulasi struktur dokumen dengan cara tertentu. Ini biasanya dilakukan dengan menggunakan Document Object Model (DOM), satu set API untuk mengontrol HTML dan informasi gaya yang memanfaatkan objek dokumen. 

- Cara Menambahkan Javascript ke HTML
  
  Menambahkan kode JavaScript dalam dokumen HTML dengan menggunakan tag HTML khusus yang membungkus kode JavaScript. ```<script>```
  Tag dapat ditempatkan di bagian HTML Anda atau di bagian tersebut, tergantung pada kapan Anda ingin JavaScript dimuat.```<script><head><body>```
  
  harus meletakkannya pada titik di mana ia harus dipanggil, biasanya di dalam bagian tersebut ```.document.write<body>```

  1. Kita dapat menambahkan JavaScript di bawah tag, misalnya, seperti yang ditunjukkan di bawah ini: ```<head><title>```
      ```
      <head>
         <meta charset="UTF-8">
         <meta name="viewport" content="width=device-width, initial-scale=1">
         <title>Today's Date</title>
         <script>
            let d = new Date();
            alert("Today's date is " + d);
         </script>
      </head>
      ```

   1. Memodifikasi apa yang ditampilkan dalam tubuh HTML, kita perlu menerapkannya setelah bagian tersebut sehingga ditampilkan pada halaman, seperti pada contoh di bawah ini:```<head>```
      ```
      <body>
      
      <script>
            let d = new Date();
            document.body.innerHTML = "<h1>Today's date is " + d + "</h1>"
      </script>
      
      </body>
      ```
   2. Membuat file javascript terpisah dari HTML dengan membuat file baru dengan nama  `script.js` dan mengakses file javascriptnya di dalam tag `<script src="script.js"></script>` dan mengetikkan kode di dalam file script.js seperti di bawah ini.
      ```
      let d = new Date();
      document.body.innerHTML = "<h1>Today's date is " + d + "</h1>"
      ```
   
### ***DOM Manipulating Styles***
1. Definisi DOM Manipulating Style 
   Selain elemen HTML, manipulasi Javascript DOM dapat dilakukan pada CSS menggunakan metode .style. Nama variabel dituliskan sebelum kata .style diikuti oleh .cssProperty.

2. Cara penggunaan DOM Manipulating Style
   contohnya di bawah ini untuk memberikan sebuah style dengan DOM ```.style```

   ```
    div.style.border = "5px solid yellow"; 
    div.style.backgroundColor = "purple"; 
    div.style.color = "white";
    div.style.height = "200px"; 
    div.style.width = "200px"; 
   ```

### ***DOM Events***

1. Definisi DOM Events
   DOM events digunakan untuk membuat perubahan dalam dokumen atau stylesheet pada kondisi tertentu. Sebuah Events dapat dipicu oleh user.
   Browser memicu Events ketika pengguna berinteraksi dengan browser. Pengguna memicu Events ketika pengguna berinteraksi dengan halaman web.

   ada 2 terminology pada DOM Events :
   - Event Listener : objek yang mendengarkan events tertentu seperti klik, penekanan tombol, gerakan mouse, dll.
   - Event Handler :  merupakan fungsi yang dipanggil ketika events tertentu terjadi
  
2. Beberapa contoh DOM Events yang sering digunakan
     - Window Event Attributes: 
        - onload
        - onresize
     - Mouse Events
        - onclick
        - onMouseover
        - onclick 
      - KeyBoard Events:
        - onKeydown
        - onKeyup
   
3. Cara Menggunakan DOM Events
    langsung mengatur event handler ke elemen HTML sebagai atribut bernama dan dapat memicu peristiwa pada tindakan tersebut. ```on<event>```

    Misalnya jika Anda ingin menggunakan event ke elemen HTML, gunakan atribut. Contoh ```clickonclick<button onclick="doSomething()">```

    ```
    <button onclick="doSomething()" id="button">Fire Event</button>

    <script>
      function doSomething() {
        alert("Event Fired");
      }
    </script>
    ```

**Copyright by Putri Dresty F @2022**