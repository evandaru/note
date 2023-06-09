# javascript

Programing Languange: javascript
Status Learn: Not started
type: native

# Document object modeling (DOM💥)

### make a limit in checkbox with a condition

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <select name="ikan" id="ikan">
        <option value="laki">laki</option>
        <option value="perempuan">perempuan</option>
    </select>
    <input type="checkbox" id=""> Checkbox 1 <br>
    <input type="checkbox" id=""> Checkbox 2 <br>
    <input type="checkbox" id=""> Checkbox 3 <br>
    <input type="checkbox" id=""> Checkbox 4 <br>
    <input type="checkbox" id=""> Checkbox 4 <br>

    <script>
        let limit;
        let checkboxCount = 0;
        const select = document.querySelector('#ikan');

        select.addEventListener('change', function () {
            if (this.value === 'laki') {
                limit = 3;
            } else {
                limit = 2;
            }
        });

        function handleCheckboxChange(e) {
            if (e.target.checked) {
                checkboxCount++;
            } else {
                checkboxCount--;
            }

            if (checkboxCount >= limit) {
                document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
                    if (!checkbox.checked) {
                        checkbox.disabled = true;
                    }
                });
            } else {
                document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
                    checkbox.disabled = false;
                });
            }
        }

        document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
            checkbox.addEventListener('change', handleCheckboxChange);
        });
    </script>
</body>

</html>
```

### make a limit in checkbox without a condition

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <select name="ikan" id="ikan">
        <option value="laki">laki</option>
        <option value="perempuan">perempuan</option>
    </select>
    <input type="checkbox" id=""> Checkbox 1 <br>
    <input type="checkbox" id=""> Checkbox 2 <br>
    <input type="checkbox" id=""> Checkbox 3 <br>
    <input type="checkbox" id=""> Checkbox 4 <br>
    <input type="checkbox" id=""> Checkbox 4 <br>

    <script>
        
        let checkboxCount = 0;

        function handleCheckboxChange(e) {
            if (e.target.checked) {
                checkboxCount++;
            } else {
                checkboxCount--;
            }

            if (checkboxCount >= 3) {
                document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
                    if (!checkbox.checked) {
                        checkbox.disabled = true;
                    }
                });
            } else {
                document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
                    checkbox.disabled = false;
                });
            }
        }

        document.querySelectorAll('input[type="checkbox"]').forEach(checkbox => {
            checkbox.addEventListener('change', handleCheckboxChange);
        });
    </script>
</body>

</html>
```

fetch data from api

ohya btw `.then`sama `.catch` itu kek `if else` cmn ini versi operasi asinkron seperti permintaan HTTP

`get`

```php
let link = 'https://script.google.com/macros/s/AKfycby4jY2BZR8kYwMPRNrUGraEYdloM-rFNaCRkD2M3t34jnKCcj_t5iUmpXzybEedeRW6Sg/exec'
fetch(link)
    .then((res) => res.json())
    .then((datas) => console.log(datas.data[0]['skill']))
```

`post`

```php
let link = 'https://script.google.com/macros/s/AKfycby4jY2BZR8kYwMPRNrUGraEYdloM-rFNaCRkD2M3t34jnKCcj_t5iUmpXzybEedeRW6Sg/exec'

fetch(link, {
    method: 'post',
    headers: {
        'content-type': 'application/json'
    },
    body: JSON.stringify({
        id: 'ikan',
        nama: 'ikan',
        skill: 'ikan',
        pekerjaan: 'ikan',
    })
})
    .then((res) => res.json())
    .then((data) => console.log(data))
```

wes itu tinggal copy aje aokwokwaow😭

# Some a function

```jsx
.pop(); //hapus last element

.push([....]); //lempar

.shift(); // hapus awal
```

![Untitled](javascript%203d11f9d674c44c569b2a24cbf5786c4a/Untitled.png)