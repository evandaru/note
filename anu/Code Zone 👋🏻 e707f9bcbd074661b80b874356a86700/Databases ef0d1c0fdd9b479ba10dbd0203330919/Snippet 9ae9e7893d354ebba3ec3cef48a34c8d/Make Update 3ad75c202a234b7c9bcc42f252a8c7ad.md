# Make Update

Chapter: make crud
No.: 4
Type: native, php

```php
<?php
include_once("conn.php");

if (isset($_GET['update'])) {
    $id = $_GET['id'];

    $nama = $_GET['nama'];
    $harga = $_GET['harga'];
    $stock = $_GET['stock'];

    $result = mysqli_query($mysqli, "UPDATE modal SET nama='$nama', harga='$harga', stock='$stock' WHERE id=$id ");
    header("Location: read.php");
}
?>

//view the read
<?php

$id = $_GET['id'];
$result = mysqli_query($mysqli, "SELECT * FROM modal WHERE id=$id");

while ($res = mysqli_fetch_array($result)) {
    $nama = $res['nama'];
    $harga = $res['harga'];
    $stock = $res['stock'];
}

?>

//form
<div class="mb-3">
   <label for="stock" class="form-label">stock</label>
   <input type="text" name="stock" class="form-control" id="stock" value="<?php echo $stock; ?>" aria-describedby="emailHelp">
</div>
   <input type="hidden" name="id" value=<?php echo $_GET['id']; ?>>
   <button type="submit" name="update" value="update" class="btn btn-primary">update</button>
```