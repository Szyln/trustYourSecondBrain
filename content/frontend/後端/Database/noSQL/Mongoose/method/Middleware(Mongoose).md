---
title: "Middleware(Mongoose)"
tag: 
- 
---
# Middleware (Mongoose)
[[Mongoose Method]]
[[Mongoose 建置]]


## Schema.pre()
可以定義哪些動作之前（`pre`）要做什麼動作
```js
const fs = require('fs') 	// file system

// define a schema


// 定義在 'save' 之前要做什麼事
// writeFile: 建立一個檔案，指定寫入什麼內容
studentSchema.pre('save', async function(){
	fs.writeFile('history.txt', "One data is trying to be saved.", (e) => {
		if (e) throw e;
	})
})

// create a model
const Student = mongoose.model('Student', studentSchema);

const newStudent = new Student({
	name: 'Kelly',
	age: ,
	major: ,
	sholarship: { merit: , other: }
});


// save 
newStudent.save()
	.then(() => {
		console.log('saved');
	}).catch(e => {
		console.log('not saved.')
	})
	

```
> [[fs (File System)]]
## Schema.post()
```js
student.Schema.post('save', async function() {
	fs.writeFile('history.txt', 'one data has been saved.'), (e) => {
		if (e) throw e;
	}
});

// create a model
const Student = mongoose.model('Student', studentSchema);

const newStudent = new Student({
	name: 'James',
	age: ,
	major: ,
	sholarship: { merit: , other: }
});


// save 
newStudent.save()
	.then(() => {
		console.log('saved');
	}).catch(e => {
		// log 在終端
		console.log('not saved.');
		// 顯示在 history.txt 內
		fs.writeFile('history.txt', "data is not saved"), (e) => {
			if (e) throw e;
		}
	})
	
```

#database #nosql #json #mongoose 