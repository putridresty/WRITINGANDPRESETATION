# Writing Week 6 ( 24 - 28 Oktober 2022)
## React Javascript
---
### Intro to React.js, Virtual DOM, and JSX
React adalah library atau framework yview library Javascript untuk membuat tampilan (user Interface) pada website. Keuntungan menggunakan react :
- React dapat mempercepat pembuatan suatu aplikasi front-end
- Pada react kita dapat menerapkan konsep modular (membagi 1 tampilan website menjadi komopnen-komponen kecil)
- React dapat digunakan pada skala yang kecil hingga besar dan kompleks
- React sangat populer dan memiliki komunitas yang besar


Dalam penggunaan react kita harus mendowload node,js terlebih dahulu. Langkah-langlah menggunakan React JS :
  - Menginstall node js
  - Menginstall folder proyek dengan memilih salah satu perintah dibawah 
  ```
        # npm 6.x
        npm create vite@latest my-vue-app --template vue

        # npm 7+, extra double-dash is needed:
        npm create vite@latest my-vue-app -- --template vue

        # yarn
        yarn create vite my-vue-app --template vue

        # pnpm
        pnpm create vite my-vue-app --template vue

  ```
  atau bisa mengikuti panduan pada link dibawah ini :
  > https://vitejs.dev/guide/


**JSX**

JSX merupakan syntax extension untuk Javascrip yang digunakan pada react js.
- Rules JSX
  - Hanya boleh memiliki 1 parent 
  - Memiliki DOM manipulation/Virtual DOM
  - Atribut class di tag HTML harus menggunakan className jika pada JSX
  - Menggunakan curly braces untuk mengakses variabel pada JSX

**Virtual DOM**

Pada javascript DOM Manipulation merupakan core, dengan DOM kita dapat berinteraksi seperti update data pada web page. 
Sedangkan, pada react js memiliki fitur virtual DOM. Ini merupakan duplikasi dari real DOM.


### Functional Component
Component adalah salah satu core dari react JS. Component dibuat jika component itu bersifat reusable code (seperti code untuk membuat navbar), component ini akan dibutuhkan tidak hanya pada 1 page. Cara membuat component :
  - Menggunakan function
  - Menggunakan class




### Props and State

**Stateless & Statefull Component**
Stateless component adalah component fungsional sederhana tanpa memiliki state lokal tetapi ingat ada hooks yang dapat bereaksi untuk menambahkan perilaku state dalam komponen fungsional juga.
```
    import React from 'react';
    const player = (props) => {
    return (
        <div>
            <p>I'm a Player: My name {props.name} and my score is
            {props.score}</p>
            {props.children}
        </div>
    );
    }
    export default player;
```

Statefull component dapat berisi objek status dan fungsi penanganan peristiwa, tindakan pengguna juga.
```
    import React, {Component} from 'react';
    import './App.css';
    import Player from './Player'
    class App extends Component {
    state = {
        players:[
            {name: 'Smith', score:100 },
            {name: 'David', score:90},
            {name: 'Phil', score:80}
        ],
    otherObject:'Test'
    }
    switchPlayerHandler = () =>{
    this.setState({players:[
        {name: 'Smith', score:200},
        {name: 'David', score:290},
        {name: 'Phil', score:380}]});
    }
    render(){
        return (
            <div className="App">
                <button onClick={this.switchPlayerHandler}>
                Switch Player
                </button>
                <Player name={this.state.players[0].name}
                score={this.state.players[0].score}
                click={this.switchPlayerHandler}/>
                <Player name={this.state.players[1].name}
                score={this.state.players[1].score}
                click={this.switchPlayerHandler}>
                Plays for Australia
                </Player>
                <Player name={this.state.players[2].name}
                score={this.state.players[2].score}
                click={this.switchPlayerHandler}/>
            </div>
        );
    }
    }
    export default App;
```

**Props and State***

Props dan statse adalah sesuatu yang berhubungan dengan Stateless & Statefull Component. Pengertian sederhana dari Stateless & Statefull Component adalah :
- Stateless berarti tidak memiliki state, dia hanya memiliki props
- Statelfull berarti memiliki state dan bisa mengirim state ke component

***State*** adalah data lokal.

***Props*** digunakan agar component memiliki data yang dinamis yang telah dikirim dari komponen lain (menangkap data yang diberikan oleh state)


### Styling

Styling pada React JS 
  - Styling Inline : menggunakan style ini, nilainya harus berupa object JavaScript
    ``` 
      class MyHeader extends React.Component {
      render() {
      return (
        <>
        <h1 style={{color: "red"}}>Hello Style!</h1>
        <p>Add a little style!</p>
        </>
      );
     }
    }
    ```
  - Jika pada stylle css nama properti yang lebih dari satu akan dinamai dengan tanda strip maka pada react akan menggunakan CamelCase 
  
    misal : background-color menjadi backgroundColor

    ```
        class MyHeader extends React.Component {
        render() {
        return (
            <>
            <h1 style={{backgroundColor: "lightblue"}}>Hello Style!</h1>
            <p>Add a little style!</p>
            </>
        );
       }
      }
     ```
 - CSS Stylesheets
     ```
        background-color: #282c34;
        color: white;
        padding: 40px;
        text-align: center;
     ```

### Handling Events
Handling atau penanganan event pada elemen React mirip dengan event yang ada pada Javascript, namun dengan beberapa perbedaan yaitu:

- Penamaan event pada React menggunakan camelCase, tidak lagi lowercase
- Event handler diisi dengan nama fungsi saja, tidak perlu pemanggilan fungsi.
```
import React from "react"

export default function App() {
  function clickButton() {
    alert("Tombol telah diklik")
  }
  return (
    <div className='App'>
      <button onClick={clickButton}>Click Me</button>
    </div>
  )
}
```

### Lifecycle Method
Lifecycle adalah siklus hidup pada React js
- Struktur Lifecycle :
  - Constructor: inisialisasi struktur data pada suatu component
  - function : fungsi yg dibutuhkan pada komponen
  - Render: proses return atau mengembalikan component asli 
- Jenis - jenis Lifecycle Component Class:
  - Mounting : Siklus ketika aplikasi sesaat sebelum component dibuka.
    - componentDidMount adalah ketika memuat aplikasi sebelum di render
    - componentWillMount adalah ketika aplikasi dimuat setelah proses render dilakukan.
  - Updating : Ketika component di update atau diubah
  - Unmount : Proses menghancurkan component yang sebelumnya di definisikan

### Hooks
Hooks mdigunakan untuk melakukan state management dan memberikan side effect pada function component. Kelebihan hooks adalah code yang digunakan akan lebih pendek, clean dan mudah dimengerti.

**Use State** digunakan untuk mengupdate state. Penggunaan useState pada hooks biasanya digunakan untuk penyimpanan data pada form yang selanjutnya data tersebut akan di post ke api lalu dproses.
  
Contoh penggunaan :
``` 
  import React, { useState } from 'react';
  export default function App() {
  const [state, setState] = useState('nama');
  const handleChange = () => {
    setState('putri');

  };
  return (
    <>
      <h1>Hello</h1>
      <p>My namaku adalah {state}</p>
      <button onClick={handleChange}>Ganti Nama</button>
    </>
      );
    }
```

**Use Effect**

Use effect ini biasa digunakan untuk membuat suatu lifecycle pada functional component. Lifecycle pada hooks hanya menggunakan useEffect yang menyatukan component DidMount, ComponentDidUpdate dan componenetWillUnmount.

Contoh penggunaan :
  ```
   import React, { useState, useEffect } from 'react';
   function Example() {
   const [count, setCount] = useState(0);
   // Mirip dengan componentDidMount dan componentDidUpdate:
   useEffect(() => {
    // Memperbarui judul dokumen menggunakan API browser
    document.title = `You clicked ${count} times`;
    });
    return (
    <div>
     <p>You clicked {count} times</p>
     <button onClick={() => setCount(count + 1)}>
        Click me
     </button>
     </div>
    );
  }
  ```

### Forms

Struktur penulisan form pada react js dan HTML sebenarnya sama, hanya saja ada beberapa penyesuaian salah satunya adalah:
- Pada react penulisan susatau elemen harus berada dalam sebuah component 

contoh penggunaan : 
```
    import { useState } from "react";

    const Form = () => {
    return (
        <>
        <form action="" >
            <label htmlFor="name">Name</label>
            <input type="text" value={name}/>
            <label htmlFor="address">Address</label>
            <input type="text" value={address}/>
            <label htmlFor="option">Program</label>
            <select value={program}>
            <option value="">select program</option>
            <option value="KM">KM</option>
            <option value="SIC">SIC</option>
            <option value="Amman">Amman</option>
            </select>
            <button type="submit">Submit</button>
        </form>

        <br />
        <h2>Name: {data.name}</h2>
        <h2>Address: {data.address}</h2>
        <h2>Program: {data.program}</h2>
        </>
    );
    };

    export default Form;

```

**Copyright by Putri Dresty F @2022**
