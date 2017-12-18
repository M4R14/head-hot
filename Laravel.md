### Route
จัดกลุ่ม Route ที่เกี่ยวข้องกัน จะได้ไม่มีปัญหาเรื่องตั้งชื่อ path ใช้ประโยชน์จากความแต่ต่างของ method ในการชื่อ path 

```php
// Bad
Route::post('/AddConsult', 'Api\ConsultController@AddConsult');
Route::post('/AddConsultChat', 'Api\ConsultController@AddConsultChat');
Route::post('/GetConsultByUser', 'Api\ConsultController@GetConsultByUser');
Route::post('/GetConsultByID', 'Api\ConsultController@GetConsultByID');
Route::post('/GetConsultChat', 'Api\ConsultController@GetConsultChat');

// Good
Route::group(['prefix' => 'consult'], function () {
  $controller = "Api\ConsultController";
  
  Route::get('/{id}', "$controller@GetConsultByID");
  Route::post('/', "$controller@AddConsult");
  
  Route::get('/user/{user_id}', "$controller@GetConsultByUser");
  
  Route::post('/chat', "$controller@AddConsultChat");
  Route::get('/chat', "$controller@GetConsultChat");
});
```
