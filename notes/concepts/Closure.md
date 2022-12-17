I've only seen this used in [[JavaScript]]

When a nested function is declared a closure is created to include all the objects declared in the same scope as the nested function declaration
```
function myFunction(){
	let value; //included in closure

	function setValue(value){
		this.value = value;
	}

	function getValue(){
		return this.value;
	}
	return {setValue, getValue};
}

const {setValue, getValue} = myFunction();
setValue(1);
console.log(getValue()); //1
setValue(3);
console.log(getValue()); //3

```