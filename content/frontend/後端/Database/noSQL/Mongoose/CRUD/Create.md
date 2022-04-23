# Create(Mongoose)
> - [[建立架構 Define a Schema]] 之後可以利用 model 來建立，可以對 model 進行 [[Mongoose CRUD]]
> - 更改過後需要存入 DB：[[透過 Mongoose 存入 MongoDB(Save)]]

## create an object
```js
const Jon = new Studtent({
	name: 'John',
	age: 25,
	major: 'EE',
	scholarship: {
		merit: 2500,
		other: 1300
	}
})
```
> 更改過後需要存入 DB：[[透過 Mongoose 存入 MongoDB(Save)]]

## Insert
```js
Model.insertMany()
// 沒有 insertOne() ，因為直接用 save 就好
```

#mongoose #mogodb #database #crud #nosql #json