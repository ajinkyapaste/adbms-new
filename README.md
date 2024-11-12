ass1
LP - I (ADBMS) 
Group A - Assignment 1 
Name: Sarvesh B. Pawar 
Roll No.: 41 
-------------------------------------------------------------------------------------------------------------------------- 
1. Create a database with suitable example using MongoDB and implement 
i) InserƟng and saving document (batch insert, insert validaƟon)
ii) Removing document 
iii) UpdaƟng document (document replacement, using modifiers, up inserts, updaƟng 
mulƟple documents, returning updated documents)
iv) Execute at least 10 queries on any suitable MongoDB database that demonstrates 
following: 
- Find and find One (specific values) 
- Query criteria (Query condiƟonals, OR queries, $not, CondiƟonal semanƟcs)
- Type-specific queries (Null, Regular expression, Querying arrays) 
- $ where queries 
- Cursors (Limit, skip, sort, advanced query opƟons)
-------------------------------------------------------------------------------------------------------------------------- 
1. Create a database 
> use TEIT41 
switched to db TEIT41 
2. Create a collecƟon
> db.createCollecƟon("CollecƟon1")
{ "ok" : 1 } 
3. InserƟng documents
> db.Employee.insert({name: "Harsh",email: "abc@gmail.com", age: 30, salary: 50000}) 
WriteResult({ "nInserted" : 1 }) 
> db.Employee.insert({name: "Shubham",email: "def@gmail.com", age: 32, salary: 60000}) 
WriteResult({ "nInserted" : 1 }) 
> db.Employee.insert({name: "Ajinkya",email: "ajp@gmail.com", age: 25, salary: 40000}) 
WriteResult({ "nInserted" : 1 }) 
> db.Employee.insert({name: "Krishna",email: "kcm@gmail.com", age: 27, salary: 70000}) 
WriteResult({ "nInserted" : 1 }) 
> db.Employee.insert({name: "Gaurav",email: "gns@gmail.com", age: 22, salary: 55000}) 
WriteResult({ "nInserted" : 1 }) 
4. Saving documents 
> db.Employee.save({name: "Latesh", email: "ljp@gmail.com", age: 48, salary: 51000}) 
WriteResult({ "nInserted" : 1 }) 
> db.Employee.save({_id: 101, name: "Umesh", email: "ums@gmail.com", age: 48, salary: 
52000}) 
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 }) 
5. Insert documents (batch insert) 
> db.Employee.insertMany([{name: "Dnyanesh", email: "dsp@gmail.com", age: 44, salary: 
22000}, 
... ... {name: "Shivjeet", email: "san@gmail.com", age: 41, salary: 75000}, 
... ... {name: "Sarvesh", email: "sbp@gmail.com", age: 38, salary: 58000}]) 
{ 
 "acknowledged" : true, 
 "insertedIds" : [ 
 ObjectId("66bc3a9a5aa4737d60ec1ec2"), 
 ObjectId("66bc3a9a5aa4737d60ec1ec3"), 
 ObjectId("66bc3a9a5aa4737d60ec1ec4") 
 ] 
} 
6. Saving documents (insert validaƟon)
> db.Employee.find() 
{ "_id" : ObjectId("66bc3a385aa4737d60ec1ebd"), "name" : "Harsh", "email" : 
"abc@gmail.com", "age" : 30, "salary" : 50000 } 
{ "_id" : ObjectId("66bc3a455aa4737d60ec1ebe"), "name" : "Shubham", "email" : 
"def@gmail.com", "age" : 32, "salary" : 60000 } 
{ "_id" : ObjectId("66bc3a535aa4737d60ec1ebf"), "name" : "Ajinkya", "email" : 
"ajp@gmail.com", "age" : 25, "salary" : 40000 } 
{ "_id" : ObjectId("66bc3a5e5aa4737d60ec1ec0"), "name" : "Krishna", "email" : 
"kcm@gmail.com", "age" : 27, "salary" : 70000 } 
{ "_id" : ObjectId("66bc3a715aa4737d60ec1ec1"), "name" : "Gaurav", "email" : 
"gns@gmail.com", "age" : 22, "salary" : 55000 } 
> db.Employee.find().preƩy()
{ 
 "_id" : ObjectId("66bc3a385aa4737d60ec1ebd"), 
 "name" : "Harsh", 
 "email" : "abc@gmail.com", 
 "age" : 30, 
 "salary" : 50000 
} 
{ 
 "_id" : ObjectId("66bc3a455aa4737d60ec1ebe"), 
 "name" : "Shubham", 
 "email" : "def@gmail.com", 
 "age" : 32, 
 "salary" : 60000 
} 
{ 
 "_id" : ObjectId("66bc3a535aa4737d60ec1ebf"), 
 "name" : "Ajinkya", 
 "email" : "ajp@gmail.com", 
 "age" : 25, 
 "salary" : 40000 
} 
{ 
 "_id" : ObjectId("66bc3a5e5aa4737d60ec1ec0"), 
 "name" : "Krishna", 
 "email" : "kcm@gmail.com", 
 "age" : 27, 
 "salary" : 70000 
} 
{ 
 "_id" : ObjectId("66bc3a715aa4737d60ec1ec1"), 
 "name" : "Gaurav", 
 "email" : "gns@gmail.com", 
 "age" : 22, 
 "salary" : 55000 
} 
7. Removing documents 
> db.Book.remove({},"justOne:true") 
WriteResult({ "nRemoved" : 1 }) 
> db.Book.remove({Ɵtle:"Shriman Yogi"})
WriteResult({ "nRemoved" : 1 }) 
> db.Book.remove({}) 
WriteResult({ "nRemoved" : 3 }) 
8. UpdaƟng documents (document replacement)
> db.Book.update({price:900},{$set:{price:600}}) 
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 }) 
9. UpdaƟng documents (using modifiers)
> db.Book.updateMany({ediƟon:{$gt:5}},{$set:{ediƟon:3}})
{ "acknowledged" : true, "matchedCount" : 3, "modifiedCount" : 3 } 
10. UpdaƟng documents (up inserts)
> db.Book.updateMany({ediƟon:{$lt:6}},{$set:{ediƟon:6}})
{ "acknowledged" : true, "matchedCount" : 3, "modifiedCount" : 3 } 
11. UpdaƟng documents (updaƟng mulƟple documents)
> db.Book.updateMany({ediƟon:{$lt:5}},{$set:{ediƟon:3}})
{ "acknowledged" : true, "matchedCount" : 4, "modifiedCount" : 1 } 
12. UpdaƟng documents (returning updated documents)
> db.Book.update({price:900},{$set:{price:600}}) 
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 }) 
> db.Book.find().preƩy()
{ 
 "_id" : ObjectId("66bc3ea75aa4737d60ec1ed7"), 
"Ɵtle" : "Pride and Prejudice",
 "price" : 450, 
 "author" : "Jane", 
"ediƟon" : 5
} 
{ 
 "_id" : ObjectId("66bc3ea75aa4737d60ec1ed8"), 
"Ɵtle" : "To Kill a Mockingbird",
 "price" : 700, 
 "author" : "Lee", 
"ediƟon" : 2
} 
{ 
 "_id" : ObjectId("66bc3ea75aa4737d60ec1ed9"), 
"Ɵtle" : "1984",
 "price" : 5500, 
 "author" : "George", 
"ediƟon" : 7
} 
{ 
 "_id" : ObjectId("66bc3ea75aa4737d60ec1eda"), 
"Ɵtle" : "Anna Karenina",
 "price" : 400, 
 "author" : "Leo", 
"ediƟon" : 8
} 
{ 
 "_id" : ObjectId("66bc3ea75aa4737d60ec1edb"), 
"Ɵtle" : "Shriman Yogi",
 "price" : 600, 
 "author" : "Ranjit", 
"ediƟon" : 6
} 
13. Find (specific values) 
> db.Student.find({marks: {$gt: 70}}) 
{ "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), "id" : 1, "name" : "Sarvesh", "age" : 19, 
"department" : "IT", "marks" : 80 } 
{ "_id" : ObjectId("66bc4cb1b81359110abf204b"), "id" : 2, "name" : "Ajinkya", "age" : 20, 
"department" : "IT", "marks" : 78 } 
{ "_id" : ObjectId("66bc4d5ĩ81359110abf204d"), "id" : 46, "name" : "Viraj", "age" : 20, 
"department" : "Mechanical", "marks" : 75 } 
{ "_id" : ObjectId("66bc4d5ĩ81359110abf204e"), "id" : 78, "name" : "Nikihil", "age" : 22, 
"department" : "Computer", "marks" : 95 } 
{ "_id" : ObjectId("66bc4d5ĩ81359110abf204f"), "id" : 3, "name" : "PraƟk", "age" : 21, 
"department" : "IT", "marks" : 88 } 
14. Find one (specific values) 
> db.Student.find({$and: [{marks: 75}, {name: "Viraj"}]}).preƩy()
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
15. Query criteria (query condiƟonals)
> db.Student.find({marks: {$gt: 70, $lt: 80}}).preƩy()
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
16. Query criteria (OR queries) 
> db.Student.find({marks: {$gte: 75, $lte: 80}}).preƩy()
{ 
 "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), 
 "id" : 1, 
 "name" : "Sarvesh", 
 "age" : 19, 
 "department" : "IT", 
 "marks" : 80 
} 
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
17. Query criteria ($not) 
> db.Student.find({marks: {$not: {$gt: 75}}}).preƩy()
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
{ 
 "_id" : ObjectId("66e273b9ab718be97bf7b116"), 
 "id" : 52, 
 "name" : "Harshad", 
 "age" : 22, 
 "department" : "IT", 
 "marks" : 55 
} 
18. Query criteria (condiƟonal semanƟcs)
> db.Student.find({name: {$regex: 'h.*'}}).preƩy()
{ 
 "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), 
 "id" : 1, 
 "name" : "Sarvesh", 
 "age" : 19, 
 "department" : "IT", 
 "marks" : 80 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204e"),
 "id" : 78, 
 "name" : "Nikihil", 
 "age" : 22, 
 "department" : "Computer", 
 "marks" : 95 
} 
{ 
 "_id" : ObjectId("66e273b9ab718be97bf7b116"), 
 "id" : 52, 
 "name" : "Harshad", 
 "age" : 22, 
 "department" : "IT", 
 "marks" : 55 
} 
19. Type-specific queries (null) 
> db.Student.find({$nor: [{marks: 55}, {name: "Viraj"}]}).preƩy()
{ 
 "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), 
 "id" : 1, 
 "name" : "Sarvesh", 
 "age" : 19, 
 "department" : "IT", 
 "marks" : 80 
} 
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204e"),
 "id" : 78, 
 "name" : "Nikihil", 
 "age" : 22, 
 "department" : "Computer", 
 "marks" : 95 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204f"),
 "id" : 3, 
"name" : "PraƟk",
 "age" : 21, 
 "department" : "IT", 
 "marks" : 88 
} 
20. Type-specific queries (regular expression) 
> db.Student.find({name: {$regex: "^A"}}).preƩy()
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
21. Type-specific queries (querying arrays) 
> db.Student.insert({id: 52,name: "Harshad", age: 22, department: "IT", marks: 55}) 
> db.Student.find().preƩy()
{ 
 "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), 
 "id" : 1, 
 "name" : "Sarvesh", 
 "age" : 19, 
 "department" : "IT", 
 "marks" : 80 
} 
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204e"),
 "id" : 78, 
 "name" : "Nikihil", 
 "age" : 22, 
 "department" : "Computer", 
 "marks" : 95 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204f"),
 "id" : 3, 
"name" : "PraƟk",
 "age" : 21, 
 "department" : "IT", 
 "marks" : 88 
} 
{ 
 "_id" : ObjectId("66e273b9ab718be97bf7b116"), 
 "id" : 52, 
 "name" : "Harshad", 
 "age" : 22, 
 "department" : "IT", 
 "marks" : 55 
} 
22. $ where queries 
> db.Fruits.find({$where: funcƟon() {return (this.name=="Watermelon")}}).preƩy()
{ 
 "_id" : ObjectId("66e27fddab718be97bf7b11a"), 
 "name" : "Watermelon", 
"quanƟty" : 6
} 
23. Cursors (limit) 
>db.Student.find().limit(2).preƩy()
{ 
 "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), 
 "id" : 1, 
 "name" : "Sarvesh", 
 "age" : 19, 
 "department" : "IT", 
 "marks" : 80 
} 
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
24. Cursors (skip) 
> db.Student.find().skip(2).preƩy()
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204e"),
 "id" : 78, 
 "name" : "Nikihil", 
 "age" : 22, 
 "department" : "Computer", 
 "marks" : 95 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204f"),
 "id" : 3, 
"name" : "PraƟk",
 "age" : 21, 
 "department" : "IT", 
 "marks" : 88 
} 
{ 
 "_id" : ObjectId("66e273b9ab718be97bf7b116"), 
 "id" : 52, 
 "name" : "Harshad", 
 "age" : 22, 
 "department" : "IT", 
 "marks" : 55 
} 
25. Cursors (sort) 
> db.Student.find().sort({marks: 1}).preƩy()
{ 
 "_id" : ObjectId("66e273b9ab718be97bf7b116"), 
 "id" : 52, 
 "name" : "Harshad", 
 "age" : 22, 
 "department" : "IT", 
 "marks" : 55 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204c"),
 "id" : 27, 
 "name" : "Akshat", 
 "age" : 21, 
 "department" : "IT", 
 "marks" : 64 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204d"),
 "id" : 46, 
 "name" : "Viraj", 
 "age" : 20, 
 "department" : "Mechanical", 
 "marks" : 75 
} 
{ 
 "_id" : ObjectId("66bc4cb1b81359110abf204b"), 
 "id" : 2, 
 "name" : "Ajinkya", 
 "age" : 20, 
 "department" : "IT", 
 "marks" : 78 
} 
{ 
 "_id" : ObjectId("66bc46b25aa4737d60ec1eea"), 
 "id" : 1, 
 "name" : "Sarvesh", 
 "age" : 19, 
 "department" : "IT", 
 "marks" : 80 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204f"),
 "id" : 3, 
"name" : "PraƟk",
 "age" : 21, 
 "department" : "IT", 
 "marks" : 88 
} 
{ 
"_id" : ObjectId("66bc4d5ĩ81359110abf204e"),
 "id" : 78, 
 "name" : "Nikihil", 
 "age" : 22, 
 "department" : "Computer", 
 "marks" : 95 
}
> ass 2
> LP-I (ADBMS) 
Group A - Assignment 2 
Name: Sarvesh B. Pawar 
Roll No.: 41 
----------------------------------------------------------------------------------------------------------------------------- 
2. Implement Map-reduce and aggregaƟon, indexing with suitable example in MongoDB.
Demonstrate the following: 
i) AggregaƟon framework
ii) Create and drop different types of indexes and explain () to show the advantage of the 
indexes. 
----------------------------------------------------------------------------------------------------------------------------- 
1. Create a database 
> use TEIT41_Ass2 
switched to db TEIT41_Ass2 
2. Create a collecƟon
> db.createCollecƟon("Orders")
{ "ok" : 1 } 
3. InserƟng documents
> db.Orders.insert({cusƟd: 044, orderdate: new Date("Sept 18, 2024"), price: 8000})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 099, orderdate: new Date("Sept 15, 2024"), price: 7500})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 675, orderdate: new Date("16 Aug, 2024"), price: 5000})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 759, orderdate: new Date("20 July, 2024"), price: 6000})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 866, orderdate: new Date("25 January, 2024"), price: 7750})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 199, orderdate: new Date("19 Dec, 2023"), price: 1000})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 876, orderdate: new Date("1 Apr, 2022"), price: 6500})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 099, orderdate: new Date("June 15, 2024"), price: 6750})
WriteResult({ "nInserted" : 1 }) 
> db.Orders.insert({cusƟd: 199, orderdate: new Date("May 10, 2024"), price: 1500})
WriteResult({ "nInserted" : 1 }) 
4. Displaying documents 
> db.Orders.find().preƩy()
{ 
 "_id" : ObjectId("66ea5fcceded1c776bd93779"), 
"cusƟd" : 36,
 "orderdate" : ISODate("2024-09-17T18:30:00Z"), 
 "price" : 8000 
} 
{ 
 "_id" : ObjectId("66ea60f0eded1c776bd9377a"), 
"cusƟd" : 99,
 "orderdate" : ISODate("2024-09-14T18:30:00Z"), 
 "price" : 7500 
} 
{ 
 "_id" : ObjectId("66ea6104eded1c776bd9377b"), 
"cusƟd" : 675,
 "orderdate" : ISODate("2024-08-15T18:30:00Z"), 
 "price" : 5000 
} 
{ 
 "_id" : ObjectId("66ea6116eded1c776bd9377c"), 
"cusƟd" : 759,
 "orderdate" : ISODate("2024-07-19T18:30:00Z"), 
 "price" : 6000 
} 
{ 
 "_id" : ObjectId("66ea6149eded1c776bd9377d"), 
"cusƟd" : 866,
 "orderdate" : ISODate("2024-01-24T18:30:00Z"), 
 "price" : 7750 
} 
{ 
 "_id" : ObjectId("66ea6169eded1c776bd9377e"), 
"cusƟd" : 199,
 "orderdate" : ISODate("2023-12-18T18:30:00Z"), 
 "price" : 1000 
} 
{ 
 "_id" : ObjectId("66ea6177eded1c776bd9377f"), 
"cusƟd" : 876,
 "orderdate" : ISODate("2022-03-31T18:30:00Z"), 
 "price" : 6500 
} 
{ 
 "_id" : ObjectId("66ea64c8eded1c776bd93780"), 
"cusƟd" : 99,
 "orderdate" : ISODate("2024-06-14T18:30:00Z"), 
 "price" : 6750 
} 
{ 
 "_id" : ObjectId("66ea64e1eded1c776bd93781"), 
"cusƟd" : 199,
 "orderdate" : ISODate("2024-05-09T18:30:00Z"), 
 "price" : 1500 
} 
5. Map-reduce 
> var mapfuncƟon = funcƟon(){emit(this.cusƟd, this.price)};
> 
> var reducefuncƟon = funcƟon(keycusƟd, valuesprice){return Array.sum(valuesprice);};
> db.Orders.mapReduce(mapfuncƟon, reducefuncƟon, {out: "MapReduceExample"})
{ "result" : "MapReduceExample", "ok" : 1 } 
> db.MapReduceExample.find().preƩy()
{ "_id" : 675, "value" : 5000 } 
{ "_id" : 876, "value" : 6500 } 
{ "_id" : 36, "value" : 8000 } 
{ "_id" : 99, "value" : 14250 } 
{ "_id" : 866, "value" : 7750 } 
{ "_id" : 759, "value" : 6000 } 
{ "_id" : 199, "value" : 2500 } 
6. AggregaƟon framework
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$sum:"$likes"}}}]) 
{ "_id" : "IT", "total" : 750 } 
{ "_id" : "COMP", "total" : 1025 } 
{ "_id" : "B. TECH.", "total" : 300 } 
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$avg:"$likes"}}}]) 
{ "_id" : "IT", "total" : 250 } 
{ "_id" : "COMP", "total" : 341.6666666666667 } 
{ "_id" : "B. TECH.", "total" : 300 } 
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$min:"$likes"}}}]) 
{ "_id" : "IT", "total" : 100 } 
{ "_id" : "COMP", "total" : 175 } 
{ "_id" : "B. TECH.", "total" : 300 } 
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$max:"$likes"}}}]) 
{ "_id" : "IT", "total" : 400 } 
{ "_id" : "COMP", "total" : 500 } 
{ "_id" : "B. TECH.", "total" : 300 } 
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$first:"$likes"}}}]) 
{ "_id" : "IT", "total" : 250 } 
{ "_id" : "COMP", "total" : 350 } 
{ "_id" : "B. TECH.", "total" : 300 } 
> db.Department.aggregate([{$group:{_id:"$Ɵtle",total:{$first:"$likes"}}}])
{ "_id" : "METBKCIOE", "total" : 250 } 
{ "_id" : "SANDIPIOE", "total" : 100 } 
{ "_id" : "METBKCIOTP", "total" : 300 } 
{ "_id" : "KKWAGHIOE", "total" : 400 } 
> db.Department.aggregate([{$group:{_id:"$Ɵtle",total:{$last:"$likes"}}}])
{ "_id" : "METBKCIOE", "total" : 350 } 
{ "_id" : "SANDIPIOE", "total" : 175 } 
{ "_id" : "METBKCIOTP", "total" : 300 } 
{ "_id" : "KKWAGHIOE", "total" : 500 } 
> db.Department.aggregate([{$group:{_id:"$Ɵtle",total:{$push:"$IT"}}}])
{ "_id" : "METBKCIOE", "total" : [ ] } 
{ "_id" : "SANDIPIOE", "total" : [ ] } 
{ "_id" : "METBKCIOTP", "total" : [ ] } 
{ "_id" : "KKWAGHIOE", "total" : [ ] } 
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$push:"$url"}}}]) 
{ "_id" : "IT", "total" : [ "hƩps://metbkcengg.ac.in/", 
"hƩps://www.kkwagh.edu.in/engineering/", 
"hƩps://www.sandipuniversity.edu.in/engineering-technology/school-of-engineeringtechnology.php" ] } 
{ "_id" : "COMP", "total" : [ "hƩps://metbkcengg.ac.in/", 
"hƩps://www.kkwagh.edu.in/engineering/", 
"hƩps://www.sandipuniversity.edu.in/engineering-technology/school-of-engineeringtechnology.php" ] } 
{ "_id" : "B. TECH.", "total" : [ "hƩps://metbhujbalknowledgecity.ac.in/metpoly/" ] }
> db.Department.aggregate([{$group:{_id:"$byuser",total:{$addToSet:"$url"}}}]) 
{ "_id" : "IT", "total" : [ "hƩps://metbkcengg.ac.in/", 
"hƩps://www.sandipuniversity.edu.in/engineering-technology/school-of-engineeringtechnology.php", "hƩps://www.kkwagh.edu.in/engineering/" ] }
{ "_id" : "COMP", "total" : [ "hƩps://www.kkwagh.edu.in/engineering/", 
"hƩps://metbkcengg.ac.in/", "hƩps://www.sandipuniversity.edu.in/engineeringtechnology/school-of-engineering-technology.php" ] } 
{ "_id" : "B. TECH.", "total" : [ "hƩps://metbhujbalknowledgecity.ac.in/metpoly/" ] }
7. Indexing (Create indexes) 
> db.Department.createIndex({"Ɵtle":1,"likes":-1}) 
{ 
 "numIndexesBefore" : 1, 
"numIndexesAŌer" : 2,
"createdCollecƟonAutomaƟcally" : false,
 "ok" : 1 
} 
> db.Department.createIndex({"byuser":1,"likes":-1}) 
{ 
 "numIndexesBefore" : 2, 
"numIndexesAŌer" : 3,
"createdCollecƟonAutomaƟcally" : false,
 "ok" : 1 
} 
> db.dept.createIndex({"Ɵtle":1,"likes":-1}) 
{ 
 "numIndexesBefore" : 1, 
"numIndexesAŌer" : 2,
"createdCollecƟonAutomaƟcally" : true,
 "ok" : 1 
} 
8. Indexing (Display indexes) 
> db.Department.getIndexes() 
[ 
 { 
 "v" : 2, 
 "key" : { 
 "_id" : 1 
 }, 
 "name" : "_id_" 
 }, 
 { 
 "v" : 2, 
 "key" : { 
 "byuser" : 1, 
 "likes" : -1 
 }, 
 "name" : "byuser_1_likes_-1" 
 } 
] 
> 
9. Indexing (Drop indexes) 
> db.Department.dropIndex({"Ɵtle":1,"likes":-1}) 
{ "nIndexesWas" : 3, "ok" : 1 } 
