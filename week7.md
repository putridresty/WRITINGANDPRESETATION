# Writing Week 7 ( 31 Oktober - 4 NovemberCY7GMPY 2022)
## React Javascript
---

### PropTypes
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



**Copyright by Putri Dresty F @2022**
