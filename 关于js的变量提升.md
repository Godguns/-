大致意思是js中无论哪种形式声明(var, let, const, function, function*, class)都会存在提升现象，不同的是，  var,function,function*的声明会在提升时进行初始化赋值为 undefined，因此访问这些变量的时候，不会报 ReferenceError 异常，而使用 let,const,class 声明的变量，被提升后不会被初始化，这些变量所处的状态被称为“temporal dead zone”，此时如果访问这些变量会抛出ReferenceError 异常，看上去就像没被提升一样。

 ### 函==数提升优先级比变量提升要高，且不会被变量声明覆盖，但是会被变量赋值覆盖==
 ### 同一个标识符的情况下，变量声明与函数声明都会提升；函数声明会覆盖变量声明，但不会覆盖变量赋值，即：如果声明变量的同时初始化或赋值那么变量优先级高于函数。