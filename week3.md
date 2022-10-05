# Writing Week 1 ( 19 - 24 September 2022)
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

## Modules
---


## Web Storages
---


## Asynchronous
---
### Introduction

### Promise 



**Copyright by Putri Dresty F @2022**
