
```
	//实现settimeout模拟setinteval  
	function myintereval(func,time){
		function inside() {
			func()
			setTimeout(inside,time)
		}
		setTimeout(inside,time)
	}   
	function like() {
		console.log("gggggg")
	}
	myintereval(like,1000)
```
