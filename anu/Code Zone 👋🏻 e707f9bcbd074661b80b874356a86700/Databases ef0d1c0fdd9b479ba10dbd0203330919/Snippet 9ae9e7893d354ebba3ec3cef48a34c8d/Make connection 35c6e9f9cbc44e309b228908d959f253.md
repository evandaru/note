# Make connection

Chapter: API
No.: 1
Type: native, php

```php
<?php
$API = 'https://masak-apa.tomorisakura.vercel.app/api/recipes';
$content = file_get_contents($API);
$data = json_decode($content, true);
// var_dump($data);
?>
```