![mongo image](https://miro.medium.com/v2/resize:fit:1384/format:webp/1*PKJ28P3YWIIlVOnPdcu8DQ.png)
# learn-mongodb
Learning mongodb backend like command CRUD


### คำสั่ง SQL VS MONGO
|SQL     |    MONGO Stage|
|--------|:-------------:|
|WHERE   |   $match|
|GROUP BY|    $group| 
|SELECT|      $project|
|ORDER BY|    $sort|
|LIMIT|       $limit| 
|JOIN|        $lookup|

### **การสร้างและลบฐานข้อมูล**
-  การแสดงฐานข้อมูล <br>
  cmd 
  ```
  show dbs
  ```
- สร้างหรือเลือกฐานข้อมูล <br>
  cmd 
  ```
  use dbname
  ```
  (หากมี db อยู่แล้วจะเป็นการเรียกใช้ แต่ถ้าหากไม่มี จะเป็นการสร้างขึ้นมาแทน) <br>
  _Ex_
  ```
  use staff
  ```
  
- การลบฐานข้อมูล <br>
  cmd <br>
  `db.dropDatabase()` <br>
  (ต้องอยู่ในฐานข้อมูลนั้นก่อนเช่น `use staff` ตามด้วย `db.dropDatabase`) <br>
  _Ex_ <br>
  ```staff> db.dropDatabase()```
  _ _ _

### การจัดการ Collection
- การสร้าง collection <br>
  cmd 
  ```
  db.createCollection('collectionName')
  ``` 

- การแก้ไขชื่อ collection <br>
  cmd 
  ```
  db.ชื่อcollection.renameCollection('newCollectionName')
  ``` 

- การลบ collection <br>
  cmd <br>
  ```db.collectionName.drop()```

  * * *

### ชนิดข้อมูลใน Mongodb

|   ชนิดข้อมูล   |   รายละเอียด   |
|   :-------:   |   :-------:   |
|  String  |  เก็บ String เขียนใน "" or ''|
|  Integer  | เก็บจำนวนเต็ม |
|  Double  | เก็บตัวเลขที่เป็นทศนิยม  |
|  Boolean  | True/False  |
|  Null  | Null หรือไม่มีค่า  |
| Object   | จัดเก็บ Object เขียนในสัญลักษณ์ {} |
| Array  | เก็บชุดข้อมูล เขียนใน []  |
| ObjectId  | เก็บ id ของ document Gen ขึ้นมาโดยระบบ (Uniqe) |
|  Date  | เก็บ Date, time |
| Binary Data | จัดเก็บข้อมูล Binary  |
| Max Min Key  | เปรียบเทียบค่า มากกว่า/ น้อยกว่า กับค่าข้อมูลอื่นๆ  |

***

### การเพิ่ม Document

- การเพิ่ม Document <br>
  cmd <br>
  ```db.collectionName.insertOne('data')``` <br>
  _Sample_ <br>
  ```db.users.insertOne({name: 'sukar', age: 25, email: 'sukar@kitten.com'})```

- การเพิ่ม หลายๆ Document <br>
  cmd <br>
  ```db.collectionName.insertMany([{data1},{data2},{data...}])``` <br>
  _Sample_  <br>
  ```db.users.insertMany([{name: 'gafield', age: 24, email: 'gafield@kitten.com'},{name: 'money', age: 28, email: 'money@kitten.com'}])```
  ***


### การสอบถามข้อมูล Document ใน Collection

  - .findOne()
    เป็นการค้นหา Document ใน Collection   ผลลัพธ์ที่ได้จะได้เพียง Document เดียว <br>
หากเจอผลลัพธ์หลายรายการ จะเลือกเอา Document แรกมาแสดง หากไม่เจอ จะได้ค่า `null` <br>
  cmd 
  ```
db.user.findOne()
``` 
  Output ที่ได้ <br>
  ```{
  _id: ObjectId('61335a62f6c9d148a419fe36'),
  name: 'sukar',
  salary: 60000,
  address: 'chaiyaphum',
  general: {
    weight: 60,
    height: 170,
    gender: 'male'
  }
```
ผลลัพธ์ที่ได้จะได้เพียง Document เดียว ใน Collection user เท่านั้น

  - .find()
    เป็นการค้นหา Doument ทั้งหมดใน Collection <br>
cmd <br>
```db.user.find()```  <br>
Output <br>
ผลลัพธ์ที่ได้จะจะได้ข้อมูลทั้งหมดใน Collection <br>
***

### การสอบถามข้อมูลแบบเงื่อนไขเดียว




  

  
  
  
  




