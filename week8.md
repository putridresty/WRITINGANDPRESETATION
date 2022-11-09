# Writing Week 8 ( 7 - 9 November 2022)
## React Javascript
---

## React Context
---
Kegunaan react context ini hampir sama dengan react redux yaitu menghindari props drilling dan sebagai state managemen. React context tidak perlu menginstall depedencies tambahan hanya memanfaatkan fitur yang dimiliki react. Secara arti componen context digunakan untuk mengglobalkan suatu data.

Jika react redux harus membuat file javascript untuk menggunakannya, react context hanya perlu membuat component context. Dimana component context ini akan memprovide keseluruhan component yang telah kita miliki.

Cara membuat provider pada component context adalah :
```
import React, { createContext } from 'react'

function KeranjangCountProvider({children}) {

  return (
    <KeranjangCountContext.Provider>
      
    </KeranjangCountContext.Provider>
  )
}

export default KeranjangCountProvider
```

Selanjutnya component context ini akan membungkus App pada Main.jsx, component context ini akan menjadi parent dan childernnya adalam componen App. Selanjutnya komponen App ini akan dikirim sebagai props dan ditampilkan kembali pada componen context.
```
import React, { createContext, useState } from 'react'

export const KeranjangCountContext = createContext()

function KeranjangCountProvider({children}) {
  const [keranjangCount, setKeranjangCount] = useState(0)

  return (
    <KeranjangCountContext.Provider value={{keranjangCount, setKeranjangCount}}>
      {children}
    </KeranjangCountContext.Provider>
  )
}

export default KeranjangCountProvider
```
Cara memanggil data untuk digunakan pada component lain yaitu menggunakan ***useContext***.


## Testing
---
Tipe testing ada 2 :
1. Manual : saat kita mengecek source code kita seperti mengecek variabel, data dll.
2. Automation (otomatis) : testing yang dikerjakan oleh suatu code

Secara umum ada 3 bagian dalam automation testing, yaitu :
- End-to-end 
- Integration testing
- Unit Testing

Kita akan melakukan unit testing dengan Jest dan RTL. Sebelumnyi kita harus mengenal TDD atau Test Driven Development terlebih dahulu. Atau sering dikenal dengan membuat kode testingnya terlebih dahulu, lalu unit functionnya.
![image TDD](https://miro.medium.com/max/1104/0*aU8saa7wKBaRpdFo.png)

### Jest
---
Jest merupakan library dari javascript yang digunakan untuk proses testing. Sebelum kita menggunakan jest kita harus menginstallnya terlebih dahulu : 
> npm install --save-dev jest

- Membuat file dengan nama sum.test.js

Kita membuat ekspetasinya terlebih dahulu :
```
const sum = require('./sum'); //import fungsi

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
  expect(sum(1, 3)).toBe(4);
  expect(sum(2, 3)).toBe(5);
});
```

- Membuat file dengan nama sum.js
- Lalu membuat fungsi dan mengeksport fungsi yang akan di import pada code testingnya.
```
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```

### RTL (React Testing Library)
---
Didalam RTL ini sudah include dengan jest. Penggunaan rtl ini kurang lebih sama dengan jest, tetapi RTL sudah langsung dapat digunakan tanpa menginstall library lagi.

Contoh penggunaan pada counter.js, kita akan mengecek apakah ada button + dan - pada counter tersebut. 

- Pada Counter.js
  ```
    import React, { useState } from 'react'

    function Counter() {
      const [count, setCount] = useState(0)

      return (
        <div>
          <button>-</button>
          <span>0</span>
          <button>+</button>
        </div>
      )
    }

    export default Counter
  ```

- Pada Counter.test.js
  ```
    import { fireEvent, render, screen } from '@testing-library/react';
    import Counter from './Counter';

    test("render counter", () => {
      render(<Counter/>)
      const decrementBtn = screen.getByText("-")
      const incrementBtn = screen.getByText("+")

      expect(decrementBtn).toBeInTheDocument()
      expect(incrementBtn).toBeInTheDocument()
    })

  ```




**Copyright by Putri Dresty F @2022**