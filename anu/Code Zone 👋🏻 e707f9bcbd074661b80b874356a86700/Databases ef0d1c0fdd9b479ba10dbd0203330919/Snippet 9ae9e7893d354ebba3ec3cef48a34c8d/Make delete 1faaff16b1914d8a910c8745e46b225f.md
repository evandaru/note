# Make delete

Chapter: make crud
No.: 5
Type: native, php

```php
<?php
include_once("conn.php");
$id = $_GET['id'];
$result = mysqli_query($mysqli, "DELETE FROM modal WHERE id=$id");
header("location:read.php");
```