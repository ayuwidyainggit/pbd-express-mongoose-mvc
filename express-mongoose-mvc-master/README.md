untuk mongoDB saya menggunakan mongoDB 32 bit 

selanjutnya membuat folder data didalam folder mongoDB yang saya buat dengan  file config.cfg  
kemudian di cmd ketik dbpath=C:\mongodb\data\db logpath=E:\mongodb\log\mongo.log  ( taruh di didalam folder mongodb )
setelah itu buka cmd untuk menjalankan server masuklah ke  E:\mongoDB\bin dan ketik :           mongod.exe –dbpath=E:\mongoDB\data tunggu proses selesai.
selanjutnya ketik mongo “E:\mongoDB\bin: mongo” jika ada tulisan Welcome to the mongodb shell berarti sekarang kita bisa menggunakan  mongoDB untuk mulai membuat database aplikasi kita.

kemudian membuka mongo, dan mengetikkan perintah untuk menggunakan database.
untuk kali ini saya menggunakan data base  db dari file models, yaitu 

var mongoose = require('mongoose'),
    Schema = mongoose.Schema;

mongoose.connect('mongodb://localhost/mydb');

var employeeSchema = new Schema({
    name: String,
    address: String,
    phone: String,
    email: String
});
 
module.exports = mongoose.model('Employee', employeeSchema);

//ini merupakan tabel pegawai dengan field name, address, phone, dan email.

kemudian saya isikan data dengan peritah 
db.db.insert({name:"ayu", address:"bantul", phone:"08787265424", email="widyaayu560@gmail.com"})
db.db.insert({name:"widya", address:"bantul", phone:"08787265424", email="widyaayu5601@gmail.com"})
db.db.insert({name:"inggit", address:"bantul", phone:"08787265424", email="widyaayu5602@gmail.com"})

kemudian untuk menampilkan hasilnya adalah dengan memberikan perintah  db.db.find().pretty()
