---
title: "Minlength(number)"
tag: 
- 
---
# Minlength (number) (Mongoose)
[[String 用 Validators]]
```js
// define a schema
const studentSchema = new mongoose.Schema({
	name: {
		type: String,
		required: [true, "Required"]
		maxlength: [15, "name is to long."]
	}
})
// create a model
const Student = mongoose.model.('Student', studentSchema);

// create a object
const newStudent = new Student({
	name: 'fjeoifjweiojfowefijiowefjioefjioefj',
})
// error
```
> [[Create]]
#database #nosql #mongoose #mongodb #validators