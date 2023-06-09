# Make create

Chapter: make crud
No.: 3
Type: native, php

```php
<?php
include_once("conn.php");

if (isset($_POST['submit'])) {
    $nama = $_POST['nama'];
    $harga = $_POST['harga'];
    $stock = $_POST['stock'];

    $result = mysqli_query($mysqli, "INSERT INTO modal(nama,harga,stock) VALUES ('$nama', '$harga', '$stock')");
    header("Location: read.php");
}
?>
...

<form method="post/get" action="create.php">
	<input... name="nama" >nama</input>
	....

<input type="submit" name="submit">submit</input>
</form>
```