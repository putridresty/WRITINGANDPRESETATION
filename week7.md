# Writing Week 7 ( 31 Oktober - 4 November 2022)
## React Javascript
---

### PropTypes
---
**PropTypes** merupakan lib yang dapat membantu untuk memeriksa data props yang dikirim agar sesuai dengan tipe data yang diinginkan. Jika tipe data tidak sesuai dengan yang ditentukan maka akan muncul pesan error dan itu termasuk kedalam suatu bug.

Sebelum menggunakan PropTypes kita harus menginstal proptypes dahulu kedalam project react yang telah dibuat dengan perintah :
> npm install prop-types

```
    // import proptypes terlebih dahulu
    import PropTypes from 'prop-types';

    function Greeting ({name}) {
        return (
        <h1>Hello, {name}</h1>
        );
    }
    }

    Greeting.propTypes = {
    name: PropTypes.string
    }; 
```
Jika data ingin dikirim/ harus diidi maka menggunakan isRequired 
> name : PropTypes.string.isRequired

Jika ingin menggunakan beberapa tipe data dapat menggunakan oneOfType
> name : PropTypes.oneOfType([PropTypes.string, PropTypes.number])


### React Router 6
---
**Router** digunakan untuk berpindah halaman tanpa reload pada sistem Single Page Application. 

Sebelum menggunakan router kita harus menginstallnya terlebih dahulu pada folder project kita dengan perintah di base :
> npm install react-router-dom@6

Langkah-langkah penggunaan react router dom :
- Pada main.jsx
  
  Paada halam ini kita mengimport BrowserRouter dan memasang tag BrowseRouter diantara tag App
  ```
        import React from "react";
        import ReactDOM from "react-dom/client";
        import App from "./App";
        import { BrowserRouter } from "react-router-dom";

        ReactDOM.createRoot(document.getElementById("root")).render(
        <React.StrictMode>
            <BrowserRouter>
                <App />
            </BrowserRouter>
        </React.StrictMode>
        );
  ```

- Pada App.jsx
  Import beberapa library  react router DOM
  ```
    import { Routes, Route, Link } from "react-router-dom";
    import HomePage from "./pages/HomePage";
    import AboutPage from "./pages/AboutPage";

    const App = () => {
    return (
        <>
        <Routes>
            <Route path="/" element={<HomePage />} />
            <Route path="/about" element={<AboutPage />} />
        </Routes>
        </>
    );
    };

    export default App;

  ```


**Penggunaan Tag Link**

Link dalam react kegunaannya seperti tag a pada HTML, contoh penggunaannya:
```
    <nav>
        <Link to={"/"}>Home |</Link>
        <Link to={"/about"}>About</Link>
    </nav>
```
- Jika ingin menggunakan navbar pada seluruh halaman maka dapat menaruh tag navbar pada App.jsx 
- Jika ingin menggunakan dibeberapa tempat saja navbar dapat dijadikan komponen 

**Dynamic Router**
- Pada App.jsx
  kita dapat melihat detail page dari masing-masing id yang ada pada data object
  ```
    import { Routes, Route, Link } from "react-router-dom";
    import HomePage from "./pages/HomePage";
    import AboutPage from "./pages/AboutPage";
    import DetailPage from "./pages/DetailPage";

    const App = () => {
    return (
        <>
        <Routes>
            <Route path="/" element={<HomePage />} />
            <Route path="/about" element={<AboutPage />} />
            <Route path="/detail/:id" element={<DetailPage />} />
        </Routes>
        </>
    );
    };

    export default App;
  ```
- Pada DetailPage.jsx 
  id yang direquest pada path akan ditangkap menggunakan useParams
  ```
    import { useParams } from "react-router-dom";

    const DetailPage = () => {
    const { id } = useParams();

    const detailInfo = [
        {
        id: 1,
        name: "Putri",
        address: "Tulungagung",
        hobby: "Menyanyi",
        },
        {
        id: 2,
        name: "Dresty",
        address: "Jember",
        hobby: "Membaca",
        },
    ];
    return (
        <>
        {detailInfo
            .filter((el) => el.id === +id)
            .map((el) => {
            return (
                <div key={el.id}>
                <h2>Name: {el.name}</h2>
                <h2>Address: {el.address}</h2>
                <h2>Hobby: {el.hobby}</h2>
                </div>
            );
            })}
        </>
    );
    };
    export default DetailPage;
  ```

**Nested Router**
- Pada App.jsx
  kita dapat melihat detail page dari masing-masing id yang ada pada data object
  ```
    import { Routes, Route, Link } from "react-router-dom";
    import AboutStudent from "./pages/AboutStudent";
    import AboutTeacher from "./pages/AboutTeacher";
    import AboutSchool from "./pages/AboutSchool";
    import NotFound from "./pages/NotFound";

    const App = () => {
    return (
        <>
          <Route path="/about" element={<AboutPage />}>
            <Route path="student" element={<AboutStudent />} />
            <Route path="teacher" element={<AboutTeacher />} />
            <Route index element={<AboutSchool />} />
          </Route>
          <Route path="*" element={<NotFound />} />
        </Routes>
        </>
    );
    };
    export default App;
  ```
    - index : digunakan agar element AboutSchool langsung ditampilkan pertama kali ketika page about dibuka
    - (*) : handle suatu halaman ketika path tidak ditemukan

- Pada AboutPage.jsx
  Menggunakan Outlet, Outlet akan mendeteksi bahwa suatu halaman memiliki beberapa anak halama yang lainnya.
  ```
  import { Outlet, Link } from "react-router-dom";

  const AboutPage = () => {
    return (
      <>
        <Outlet />
        <Link to={"student"}>About Student |</Link>
        <Link to={"teacher"}>About Teacher</Link>
      </>
    );
  };

  export default AboutPage;

  ```

## React Redux and Thunk 
---

### **Introduction Redux**
---
Konsep dasar problem yang harus dipaham sebelum kita mulai menggunakan state management adalah props drilling.
***Props drilling*** akan memungkinkan terjadinya masalah jika ada perubahan variabel atau parameter pada parent, maka pada child juga harus diubah.
![Props Drilling](https://cdn.hashnode.com/res/hashnode/image/upload/v1626195816882/-ZvP6zFSw.jpeg?auto=compress,format&format=webp)

Solusi untuk mengahndle props drilling ini adalah menggunakan state management, salah satu caranya adalah menggunakan redux.
![Redux Data Flow](https://th.bing.com/th/id/R.06080bd35683ca5ab00ad2bd043ef4d2?rik=MrWP6E18Z7CONQ&riu=http%3a%2f%2fcodingthesmartway.com%2fwp-content%2fuploads%2f2017%2f05%2f01.png&ehk=5dijj4pxTdhT%2fV9ocS65aXwyfs%2f08VsdoVAG3VlEI4k%3d&risl=&pid=ImgRaw&r=0)
- Data akan dipusatkan(store), jika ada perubahan pada data tidak harus mengubah component yang membutuhkan data dari pusat datanya (dapat dibuat dan diubah pada pusat data saja)
- Jika suatu component membutuhkan data, maka component tersebut dapat mengambil data dari pusat data

### **React Redux**
---
Sebelum menggunakan react kita harus menginstall librarynya terlebih dahulu kedalam project kita dengan perintah :
> npm install react-redux


Set-up serta langkah menggunakan redux :
- Pada Main.jsx
  Mengimport dan menambahkan tag Provider 
  ```
    import React from 'react'
    import ReactDOM from 'react-dom/client'
    import { Provider } from 'react-redux'
    import App from './App'

    const root = ReactDOM.createRoot(document.getElementById('root'))
    root.render(
      <Provider>
        <App />
      </Provider>
    )
  ```
- Membuat store (pusat/gudang data)
  
  Melakukan instalasi untuk import store
  > npm install redux
  
  Selanjutnya membuat store nya dengan cara mengimport createStore dan membuat variabelnya
  ```
    import { createStore } from 'redux'
    import keranjangReducer from '../reducer/keranjangReducer'

    const store = createStore(keranjangReducer)

    export default store
  ```
- Membuat reducer 
  
  Reducer ini berada didalam store dan dapat disebut sebagai rak penyimpan data
  ```
    const initialState = {
      totalKeranjang: 0,
    };

    function keranjangReducer(state = initialState, action) {
      console.log(action);

      switch (action.type) {
        default : 
          return state
      }
    }

    export default keranjangReducer;

  ```
- Membuat provider 
  Mengirimkan pesan pemberitahuan jika data pada store siap di akses untuk component yang membutuhkan.
  ```
    import React from 'react'
    import ReactDOM from 'react-dom/client'
    import { Provider } from 'react-redux'
    import store from './store'
    import App from './App'

    const root = ReactDOM.createRoot(document.getElementById('root'))
    root.render(
      //Menambahkan properti store
      <Provider store={store}>
        <App />
      </Provider>
    )
  ```
- Mengambil data dari store menggunakan Hooks
  
  Pada Keranjang.jsx mengambil data menggunakan ***useSelector***
  ```
    import React from 'react'
    import { useSelector } from 'react-redux'

    function Keranjang() {
      const {totalKeranjang} = useSelector(state => state)

      // console.log(state)

      return (
        <div>
          <span>Keranjang</span>
          <span> {totalKeranjang}</span>
        </div>
      )
    }

    export default Keranjang
  ```

- Membuat action 
  
  Action merupakan aktivitas yang ingin dilakukan untuk mengubah data yang sudah dibuat pada default (pada case diatas defaultnya adalah initialState). Action merupakan sebuah function berisi object yang memiliki type.
  ```
    export const INCREMENT_KERANJANG = "INCREMENT_KERANJANG"
    export const DECREMENT_KERANJANG = "DECREMENT_KERANJANG"

    export function incrementKeranjang() {
      console.log("action dipanggil")
      return {
        type: INCREMENT_KERANJANG
      }
    }

    export function decrementKeranjang() {
      return {
        type: DECREMENT_KERANJANG
      }
    }
  ```
  Action ini akan diarahkan pada reducer 
  ```
  import { 
    INCREMENT_KERANJANG,
    DECREMENT_KERANJANG,
  } from "../action/keranjangAction";

  const initialState = {
    totalKeranjang: 0,
  };

  function keranjangReducer(state = initialState, action) {
    console.log(action);

    switch (action.type) {
      case INCREMENT_KERANJANG: 
        return {
          totalKeranjang: state.totalKeranjang + 1
        }
      case DECREMENT_KERANJANG: 
        return {
          totalKeranjang: state.totalKeranjang - 1
        } 
      default:
        return state;
    }
  }

  export default keranjangReducer;

  ```
- Memasangkan Action pada tombol yang sudah dibuat
  Pada Counter.jsx kita menggunakan ***useDispatct***. useDispatch digunakan untuk mengirimkan action kepada reducer (jembatan/perantara untuk mengubah data).
  ```
    import React, { useState } from "react";
    import { useDispatch } from "react-redux";
    import {
      incrementKeranjang,
      decrementKeranjang,
    } from "../redux/action/keranjangAction";

    function Counter() {
      const dispatch = useDispatch();
      const [count, setCount] = useState(0);

      const increment = () => {
        dispatch(incrementKeranjang())
        setCount(count + 1);
      };

      const decrement = () => {
        dispatch({
          type: "DECREMENT_KERANJANG"
        })
        setCount(count - 1);
      };

      return (
        <>
          <button onClick={decrement}>-</button>
          <span>{count}</span>
          <button onClick={increment}>+</button>
        </>
      );
    }

    export default Counter;

  ```

### **Redux Thunk Middleware**
---
Thunk digunakan untuk menunda pekerjaan pengambilan data secara asynchronous,sedangkan pada action (dispatcht) data harus dikirimkan secara langsung tanpa ada jeda (synchronous) untuk menununggu data yang diambil dari API.

Sebelum menggunakan thunk kita harus menginstallnay dahulu kedalam project kita deangan perintah :
> npm install thunk 

Lalu import kedalam file store
```
  import { createStore, applyMiddleware } from 'redux'
  import thunk from 'redux-thunk'
  import rootReducer from './reducers/index'

  const store = createStore(rootReducer, applyMiddleware(thunk))
```

Setelah itu thunk dapat digunakan seperti kode dibaawah ini, dapat menyesuaikan dengan kebutuhan 
```
  import { configureStore } from '@reduxjs/toolkit'
  import rootReducer from './reducer'
  import { myCustomApiService } from './api'

  const store = configureStore({
    reducer: rootReducer,
    middleware: getDefaultMiddleware =>
      getDefaultMiddleware({
        thunk: {
          extraArgument: myCustomApiService
        }
      })
  })

  // later
  function fetchUser(id) {
    // The `extraArgument` is the third arg for thunk functions
    return (dispatch, getState, api) => {
      // you can use api here
    }
}
```

**Copyright by Putri Dresty F @2022**
