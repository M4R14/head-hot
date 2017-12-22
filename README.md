# 🔥 Head Hot 🔥 [PHP]
แชร์ Code ที่ทำให้หัวร้อน

#### ไม่เอาๆ อย่าเขียน code ซ้ำ
```php
// bad
function A($number){
 $class = 'A';
 if ($number < 80) {
  $class = 'B';
 } elseif ($number < 60) {
  $class = 'C';
 } elseif ($number < 40) {
  $class = 'D';
 } elseif ($number < 20) {
  $class = 'F';
 }
 
 if ($class == 'A') {
  return 'Good';
 }
 return 'Bad';
}

function B($number){
 $class = 'A';
 if ($number < 80) {
  $class = 'B';
 } elseif ($number < 60) {
  $class = 'C';
 } elseif ($number < 40) {
  $class = 'D';
 } elseif ($number < 20) {
  $class = 'F';
 }
 
 if ($class == 'F') {
  return 'Good bye!!';
 }
 return 'OK!!';
}

// good
function class_($number){
 $class = 'A';
 if ($number < 80) {
  $class = 'B';
 } elseif ($number < 60) {
  $class = 'C';
 } elseif ($number < 40) {
  $class = 'D';
 } elseif ($number < 20) {
  $class = 'F';
 }
 return $class;
}

function A($number){
 $class = class_($number);
 if ($class == 'A') {
  return 'Good';
 }
 return 'Bad';
}

function B($number){
 $class = class_($number);
 if ($class == 'F') {
  return 'Good bye!!';
 }
 return 'OK!!';
}

```
#### 1 Line.
```php
// Bad
if (isset($X)) { 
 $Y = $X;
}

// Good
$Y = isset($X) ? $X : null;
```

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
