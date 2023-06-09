# Make Read

Chapter: make crud
No.: 2
Type: native, php

```php
<?php
include_once("conn.php");
$result = mysqli_query($mysqli, "SELECT * FROM modal WHERE id");
$angka = 0;
?>
...
<?php while ($res = mysqli_fetch_array($result)) {
                    $angka++;
                    echo '<tr>';
                    echo '<th scope="row">' . $angka . '</th>';
                    echo '<td>' . $res['nama'] . '</td>';
                    echo '<td>' . $res['harga'] . '</td>';
                    echo '<td>' . $res['stock'] . '</td>';
                    echo '<td>';
                    echo '<a href="update.php?id=
                    ' . $res['id'] . '    
                    ">✏edit</a> | 
                    <a href="delete.php?id=
                    ' . $res['id'] . '
                    ">🗑 Delete</a>';
                    echo '</td>';
                } ?>
...
```