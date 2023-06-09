# supaya bisa akses gambar dari google drive

# sebelum

```php
<img src="https://drive.google.com/file/d/1RgJj7rnj-bdHeu81_oi0gifdBzjbEAjJ/view?usp=share_link" alt="">
```

# setelah

```php
<img src="https://drive.google.com/uc?id=1RgJj7rnj-bdHeu81_oi0gifdBzjbEAjJ" alt="">
```

yaitu dengan menghapus

`/file/d/`  dan mengganti dengan `uc?id=`

trus yang dibelakang `/view?usp=share_link` dihapus