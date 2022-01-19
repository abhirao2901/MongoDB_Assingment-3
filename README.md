# MongoDB_Assingment-3
complex queries
assingment3
db.addresses.find()
  db.addresses.find({ },{ restaurant_id:1,name:1, borough:1, cuisine:1})
 db.addresses.find({ },{ restaurant_id:1,name:1, borough:1, cuisine:1,_id:0})
 db.addresses.find({ },{ restaurant_id:1,name:1, borough:1, "address.zipcode":1,_id:0})
db.addresses.find({"borough" : "Bronx"}).limit(5)
db.addresses.find({"borough" : "Bronx"})
> db.addresses.find({"borough" : "Bronx"}).skip(5).limit(5)
db.addresses.find({"grades.score": {$gt: 90}}
db.addresses.find({$and : [{"grades.score" : {"$gt" : 80}},{"grades.score" : {"$lt" : 100}}]})
db.addresses.find({$and : [{"grades.score" : {"$gt" : 80}},{"grades.score" : {"$lt" : 100}}]})
db.addresses.find({"address.coord.0" : {$lt : -95.754168}})
> db.addresses.find({$and : [{"cuisine" : {$ne : "American "}}, {"address.coord.0" : {$lt : -65.754168}}, {"grades.score" : {$gt : 70}}]})
12 -------
db.addresses.find({$and : [{"cuisine" : {$ne : "American "}}, {"grades.grade" : "A"}, {"borough" : {$ne : "Brooklyn "}}]}).sort({cuisine : -1})
db.addresses.find({"name" : { $regex: "Wil"}}, {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
> db.addresses.find({"name" : { $regex: "ces$"}}, {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
db.addresses.find({"name" : { $regex: "Reg"}}, {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
db.addresses.find({borough: "Bronx", cuisine: {$in: ["American ","Chinese"]}}, {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
 db.addresses.find({$or: [{"borough": "Staten Island"}, {"borough": "Bronxor Brooklyn"}, {"borough": "Queens"}]}, {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
db.addresses.find( {borough: {$nin: ["Staten Island","Queens","Bronx","Brooklyn"]}} , {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
> db.addresses.find({"grades.score": {$lte: 10}}, {_id:0, restaurant_id:1, name:1, borough:1, cuisine:1})
21
22
23
24
25- db.addresses.find({},{_id:0, name:1}).sort( {name: 1})
> db.addresses.find({},{_id:0, name:1}).sort( {name: -1})
28
 db.addresses.find({}, {_id:0, cuisine:1, borough:1}).sort({cuisine: 1, borough: -1})
> db.addresses.find({"address.coord": {$type: "double"}}, {_id:0, address:1})
db.addresses.find({name: {$regex: /^Mad.*/}},{_id:0, name:1, borough:1, "address.coord":1, cuisine:1})
> db.addresses.find({name: {$regex: /mon/}},{_id:0, name:1, borough:1, "address.coord":1, cuisine:1})
