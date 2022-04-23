---
title: "Static Method"
tag: 
- 
---
# Static method
[[Mongoose Method]]
給 model 用的，[[Instance Method]] 是給 Schema 用的

[[Create#Define a Schema]] 之後
```js
// create instance method
studentSchema.methods.addAge = function() {
	this.age++;
}
// create static method
studentSchema.statics.setOtherToZero = function() {
	// this 指向整個 model
	this.updateMany({}, {'scholarship.other': 0})
}

// create a model
const Student = mongoose.model("Student", studentSchema);

// 直接對整個 model 使用
Student.setOtherToZero()
	.then(meg => {
		console.log(meg);
	}).catch(e => {
		console.log(e);
	})
	
Student.find({});		// 所有 other 已經歸零
```

#database #mongoose #crud 