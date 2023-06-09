# Hosting

Programing Languange: hosting
Status Learn: Not started
type: other

# buat file index

`.htaccess` didalam file html_public

```jsx
<IfModule mod_rewrite.c>
    RewriteEngine on
    RewriteRule ^(.*)$ public/$1 [L]
</IfModule>
```

> klo beli itu yang langsung sepaketnya jangan yang satu-satu
>