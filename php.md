```php
//bad
if ($X == 1) {
  $Y = f(1);
}

if ($X == 2) {
  $Y = f(2);
}

if ($X == 3){
  $Y = f(3);
}

//good
if (in_array($X, [1, 2, 3])) {
  $Y = f($X);
}
```
