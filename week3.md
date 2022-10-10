# Writing Week 1 ( 26 - 30 September 2022)
# Javascript Intermediate

## Array & Multidimensional Array
---
### Array

***Array*** adalah tipe data list order yang dapat menyimpan tipe data apapun di dalamnya. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya.

Berikut ini adalah cara untuk membuat dan mengupdate data pada array
```
let myArray = ['pisang', 'jambu', 'jeruk']

// mengakses array melalui index
console.log(myArray[0])
// index pertama array adalah 0 maka output dari perintah diatas : pisang

// mengupdate array
myArray[0] = 'durian';
console.log(myArray)
//  output : ['durian', 'jambu', 'jeruk']

```

- Jika menggunakan let, kita dapat mengubah array  dengan array baru dan konten nilai yang ada di dalam array dengan nilai lain
- Const tidak bisa melakukan update data. Namun pada Array kita dapat melakukan update konten nilai di dalam array (mutable).
- Yang tidak bisa adalah mengubah array dengan array yang baru jika menggunakan const

***Menggunakan let :***
```
let myArray = ['pisang', 'jambu', 'jeruk']

myArray = ['durian'];
console.log(myArray)
// output : ['durian']
```
***Menggunakan const :***

```
const myArray = ['pisang', 'jambu', 'jeruk']

myArray = ['durian'];
console.log(myArray)
// output : ['pisang', 'jambu', 'jeruk']

```

***Array Properties***

Salah satu property pada array adalah `length`, length akan mengembalikan nilai dari jumlah panjang data suatu array.
```
let myArray = ['pisang', 'jambu', 'jeruk']
console.log(myArray.length)
// output : 3
```

***Array Method***

Array memiliki method atau biasa disebut built-in methods. Javascript telah memnyediakan function atau method yang dapat kita gunakan. Beberapa contoh array method yaitu :
1. .push() : menambahkan item array pada index terakhir
    ```
    let myArray = ['pisang', 'jambu', 'jeruk']

    myArray.push('durian');
    console.log(myArray)
    // output : ["pisang", "jambu", "jeruk", "durian"]
    ```
2. .pop() : menghapus item array pada index terakhir
    ```
    let myArray = ['pisang', 'jambu', 'jeruk']

    myArray.pop();
    console.log(myArray)
    // output : ["pisang", "jambu"]
    ```

3. .unshift() : menambahkan item array pada index pada index paling awal
    ```
    let myArray = ['pisang', 'jambu', 'jeruk']

    myArray.unshift('mangga');
    console.log(myArray)
    // output :["mangga", "pisang", "jambu", "jeruk"]
    ```

4. .shift() : menghapus item array pada index pada index paling awal
    ```
    let myArray = ['pisang', 'jambu', 'jeruk']

    myArray.shift();
    console.log(myArray)
    // output :["jambu", "jeruk"]
    ```

5. .sort() : mengurutkan array secara Ascending atau Descending Alphanumeric
    ```
    let myArray = [4, 2, 3, 5, 1]

    myArray.sort();
    console.log(myArray)
    // output :[1, 2, 3, 4, 5]
    ```

***Looping pada Array***
1. forEach() : method untuk melakukan looping pada setiap elemen array.
   ```
    const numbers = [2, 3, 4, 5];

    numbers.forEach((number) => {
        console.log(number * 5);
    });

    // expected output: 10
    // expected output: 15
    // expected output: 20
    // expected output: 25
   ```
2. map() : melakukan perulangan/looping dengan membuat array baru.
   ```
    const numbers = [2, 3, 4, 5];

    numbers.map((number) => number * 5);
    // expected output: Array [ 10, 15, 20, 25 ]
   ```

### Multidimensional Array

Sering disebut dengan ada array didalam array. Cara mengakses multidimensional array ini dpaat dianalogikan seperti tabel ada kolom dan barisnya.
```
let Employee = [
[100, 'Ram', 'Agra'],
[101, 'Shyam', 'Aligarh'],
[102, 'Amit', 'Gwalior']
]

// console.log(namaArray[indexKolom][indexBaris])
console.log(Employee[0][2])
// output : Agra
```
Untuk method dan looping dapat menggunakan perintah yang sama seperti array biasa.


## Object & Array of Object
---
Object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method). Sama seperti array, didalam object kita dapat menyimpan properti dengan tipe data apapun. Berikut ini adalah cara untuk membuat dan mengakses suatu object.
```
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
};

// menambilkan object
console.log(person)
// output : { firstName: 'John', lastName: 'Doe', age: 50 }

// mengakses firstname
console.log(person.firstName)
// output  John
};
```
Kita juga bisa menggunakan bracket notation saat memanggil properti dari sebuah object.
```// mengakses firstname menggunakan bracket notation
console.log(person['firstName'])
// output  John
```
***Update Objects***
- Object dapat mengupdate value dari key yang sudah tersedia
- Object dapat menambahkan key dan value baru
- Jika menggunakan constant pada variable object. Kita tidak bisa mengganti seluruh data object dengan object yang baru.
```
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
};

// mengupdate age 
person.age = 51;

// menambahkan key dan value
person.addres = 'Jember';

console.log(person)
// output : { firstName: 'John', lastName: 'Doe', age: 51, addres: 'Jember' }
```
Menghapus propertei dalam suatu obbject :
```
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
};

//  mneghapus properti object
delete person.age 

console.log(person)
//  output : { firstName: 'John', lastName: 'Doe' }
```

***Nested Object*** : Object yang berasal dari turunan object lainnya.
```
const user = {
    id: 101,
    email: 'abc@eyehunts.com',
    personalInfo: {
        name: 'John',
        address: {
            line1: '101',
            line2: 'Stree Line',
            city: 'NY',
            state: 'WX'
        }
    }
}
// mengakses name 
console.log(user.personalInfo.name)
// output : John
```

***Looping Object***
Jika kita ingin menampilkan seluruh object properti. Kita bisa menggunakan looping. Tidak perlu mengakses secara manual memanggil setiap propertinya seperti pada perintah diatas.
```
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
};

//looping untuk mengakses key pada object
for (let key in person) {
    console.log(key)
}
// output :
// firstName
// lastName
// age
```

***Array of Object***
Object dapat menyimpan banyak data seperti array. 
```
const person = [
 {
    name: "aksht", 
    age: 23, 
    skill: "ruby" 
 },
 { 
    name: "nidhi", 
    age: 35, 
    skill: "java" 
 },
 { 
     name: "guddu", 
     age: 30, 
     skill: "python" 
 },
]
// mengakses array menggunakan forEach
person.forEach((item) => {
    // menampilkan value dari masing-masing key object
    console.log(item.name, item.age, item.skill);
});
// output :
// aksht 23 ruby
// nidhi 35 java
// guddu 30 python
```

## Modules
---
Module adalah file Javascript yang di dalamnya terdapat value dari objects, functions, dan variables. Kemudian file tersebut dapat diexport dan diimport oleh file lain. Yang mana file lain yang mengimportnya dapat menggunakan values yang ada di file tersebut.

***Export***

Export digunakan untuk meng-export variabel pada file JavaScript. Variabel yang diexport dapat berisi data seperti string, object, array, hingga function. Hal ini dilakukan agar file JavaScript tersebut dapat dijadikan sebuah module, sehingga variabel yang telah di-export dapat digunakan pada file JavaScript lain dengan menggunakan import.
```
let name = "Putri";

let Person = {
  nama: "Putri",
  umur: 17,
  alamat: "Jember",
};

function sayHello(user) {
  console.log(`Hello, ${user}!`);
}

// Mengexport variable name, object orang dan function sayHello sekaligus
export { name, orang, sayHello };
```

***Import*** 

Import diibaratkan sebagai pasangan dari export. Jadi import digunakan untuk menggunakan variabel yang sudah di-export dari module lainnya.
```
import { data } from "./namaModul.js";

// index.js
import { name, person, sayHello } from "./user.js";

// Menggunakan hasil import
console.log(name); // Output: Putri
console.log(person); // Output: {nama: "Putri", umur: 17, alamat: "Jember"}
sayHello(person.nama); // Output: Hello, Thoriq!
```

## Recursive
---
Recursive adalah function yang memanggil dirinya sendiri sampai kondisi tertentu. Recursive kebanyakan digunakan untuk case matematika atau hitungan. Ciri dari rekursif:

- Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti.
- Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. 

```
function sum(num){
    if (num === 0) {
        return 0;
    } else {
        return num + sum(--num)
    }
}
 
console.log(sum(4))
//output : 10
```
konsep pengerjaan fungsi : 
```
sum(4)
4 + sum(3)
4 + ( 3 + sum(2) )
4 + ( 3 + ( 2 + sum(1) ))
4 + ( 3 + ( 2 + ( 1 + sum(0) )))
4 + ( 3 + ( 2 + ( 1 + 0 ) ))
4 + ( 3 + ( 2 + 1 ) )
4 + ( 3 +  3 ) 
4 + 6 
10
```
## Asynchronous
---
Asynchronous mengizinkan komputer memproses task yang lain sambil menunggu proses yang masih berlangsung. Fungsi yang berjalan secara paralel dengan fungsi lain.
### Introduction
Ada banyak fungsi yang digunakan oleh browser yang bisa berpotensi memakan waktu lama, dan bisa menjadi asynchronous. seperti berikut :
- Membuat permintaan HTTP menggunakan ```fetch()```
- Mengakses kamera atau mikrofon pengguna menggunakan ```getUserMedia()```
- Meminta pengguna untuk memilih file menggunakan ```showOpenFilePicker()```

contoh dari synchronus yang berjalan lama, yang membuat pemrograman bisa dibubah ke asynchronus.
```
const name = 'Miriam';
const greeting = `Hello, my name is ${name}!`;
console.log(greeting);
// "Hello, my name is Miriam!"
```

kode di atas mendeklarsikan :
- string ```name```
- string lain yang disebut ```greeting```, yang menggunakan name.
- menampilkan ```greeting``` ke konsol JavaScript.\

contoh di atas menunjukkan bahwa browser menunggu baris untuk menyelesaikan pekerjaannya sebelumnya melanjutkan ke baris berikutnya. Akan lebih efektif jika dibuat asynchronus
```
function makeGreeting(name) {
  return `Hello, my name is ${name}!`;
}

const name = 'Miriam';
const greeting = makeGreeting(name);
console.log(greeting);
// "Hello, my name is Miriam!"  
---
```

```makeGreeting()``` adalah fungsi synchronus karena pemanggil fungsi tersebut dan menyelesaikan pekerjaannya dan mengembalikan nilai sebelum pemanggil dapat melanjutkan.
Itulah yang dapat dilakukan oleh fungsi asynchronus.

### Callback

Callback function adalah function yang kita letakan di dalam argumen/parameter pada function, dan function tersebut akan dieksekusi setelah function pertama menyelesaikan tugasnya. Callback fungsi yang dilewatkan di dalam fungsi lain, dan kemudian dipanggil dalam fungsi itu untuk dijalankan.
- contohnya :
    ```
    console.log('fired first');
    console.log('fired second');

    setTimeout(()=>{
        console.log('fired third');
    },2000);

    console.log('fired last');
    ```
kode akan mengeksekusi instruksi pertama, kemudian instruksi kedua, tetapi akan melewati instruksi ketiga dan mengeksekusi instruksi terakhir.

Ini ```setTimeout``` adalah fungsi JavaScript yang mengambil dua parameter. Parameter pertama adalah fungsi lain, dan yang kedua adalah waktu setelah fungsi itu harus dijalankan dalam milidetik. dan pada posisi itu callback dijalankan.
lalu  output yang dihasilkan seperti di bawah ini :
```
fired first
fired second
fired last
fired third
```

### Promise  

Promise adalah Sebuah mekanisme baru pada fitur javascript / ES6 yang merepresentasikan sebuah object request pengolahan data yang dilakukan secara asynchronous seperti ajax, dan promise ini mewakili sebuah operasi yang belum selesai. Ini memungkinkan Anda untuk mengaitkan operasi dengan nilai keberhasilan atau alasan kegagalan asynchronus.

ketika melakukan sebuah request asynchronous , maka ada 3 kemungkinan state :
- Pending (sedang dalam proses)
- Fulfilled ( berhasil )
- Rejected ( dibatalkan / gagal)

Promise mengambil dua fungsi sebagai parameter. Yaitu, ```resolve``` dan ```reject```.
contoh :
```
const getData = (dataEndpoint) => {
   return new Promise ((resolve, reject) => {
     //some request to the endpoint;
     
     if(request is successful){
       //do something;
       resolve();
     }
     else if(there is an error){
       reject();
     }
   
   });
};
```
Promise pada umumnya digunakan sebagai pengganti alternative callback. Karena disaat menggunakan callback maka kita akan ada kemungkinan dihadapkan pada callbackhell

### Async - await

Async - await adalah salah satu fitur baru dari javascript yang digunakan untuk menangani hasil dari sebuah Promise.

- Penggunaan fungsi ```async``` :
    ```
    const asyncFunc = async () => {
        const response = await fetch(resource);
        const data = await response.json();
    }
    ```
Sedangkan await berfungsi untuk menunda sebuah kode dijalankan sampai proses asynchronous berhasil. pada contoh di atas await digunakan untuk menunda penugasan sampai fungsi itu diselesaikan.

### HTTP Request fetch()
---
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
lalu dapat menggunakan Async Await 
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


## Web Storages
---
Web storage adalah salah satu Web API yang dapat menyimpan data secara lokal pada sisi client. Berbeda dengan objek atau array, data yang disimpan pada objek atau array JavaScript bersifat sementara, dan akan hilang jika terjadi reload atau pergantian URL pada browser.

### localStorage and sessionStorage
Objek localStorage and sessionStorage, bagian dari API penyimpanan web, adalah dua tools untuk menyimpan key/value secara lokal
- localStorage : data akan dipertahankan hingga pengguna menghapus cache browser secara manual atau hingga hapus data browser.
- sessionStorage : data hanya bertahan sampai jendela atau tab ditutup.

## Penggunaan localStorage  :

- membuat entri untuk localStorage dengan menggunakan method ```setItem()```. method setItem()ini mengambil dua argumen, key dan value. contohnya :
    ```
    let key = 'Item 1';
    localStorage.setItem(key, 'Value');
    ```
- dan untuk mengambil data menggunakan ```getItem()```
    ```
    let myItem = localStorage.getItem(key);
    ```
- menghapus entri dengan method removeItem(). method removeItem()ini mengambil satu argumen yang akan menjadi key di localStorage. dan yang untuk menghapus semua data yang ada di localStorage
    ```
    localStorage.removeItem(key);
    ```
    ```
    localStorage.clear();
    ```
- Menyimpan nilai Non-String dengan JSON
localStoragehanya dapat menyimpan nilai string. Jika Anda ingin menyimpan objek atau array sebagai nilai dalam localStorage, Anda dapat menggunakannya JSON.stringify()untuk mengubahnya menjadi string.
    ```
    let myObj = { name: 'Rafo', status: 'Students' };
    localStorage.setItem(key, JSON.stringify(myObj));
    ```

- Memeriksa Item 
Menggunakan if pernyataan untuk memeriksa apakah localStorage menyimpan item atau kosong. Untuk melakukan ini, periksa panjang localStorage.
    ```
    if (localStorage.length > 0) {
    // ...
    } else {
    // ...
    }
    ```
- Looping item
Objek localStoragedan sessionStoragetidak mendukung forEachmetode ini. Untuk mengulangi item di localStorage, gunakan forloop. console.log untuk menampilkan key dan value
    ```
    for (let i = 0; i < localStorage.length; i++){
    let key = localStorage.key(i);
    let value = localStorage.getItem(key);
    console.log(key, value);
    }
    ```
- Memeriksa apakah support 
menguji  localStorage dengan memeriksa apakah itu tersedia pada ```window``` objek menggunakan if
    ```
    if (window.localStorage) {
    // localStorage supported
    }
    ```


**Copyright by Putri Dresty F @2022**
