#### X ต้องมีค่าเท่ากับ 1, 2 หรือ 3 อย่างใดอย่างหนึ่งเท่านั้น ค่อยทำ f(x)
```php
// Bad
if ($X == 1) {
  $Y = f(1);
}

if ($X == 2) {
  $Y = f(2);
}

if ($X == 3){
  $Y = f(3);
}

// Good
if (in_array($X, [1, 2, 3])) {
  $Y = f($X);
}
```

#### การประกาศ Array
```php
// Bad
$data = array();

// Good
$data = [];
```

#### การกำหนดค่าใน Array
```php
// Bad
$data = new array();
$data['a'] = 1;
$data['b'] = 2;
$data['c'] = 3;

// Good
$data = [
  'a' => 1,
  'b' => 2,
  'c' => 3
]
```
