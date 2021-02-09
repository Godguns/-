> 1. promise可以通过return来传递值而不是一直resolve或者reject   
> 2. 也可以通过return 一个promise 执行resolve/reject来传递数据   
甚至是promise.resolve     

##### 当前的promise的then走reject之后的.then依然会走resolve   
#####  在then中使用throw error的时候才会使得下一个then走reject。   
##### promise 中使用catch捕获异常细节   当then中既有reject函数同时外部还有catch函数用来捕获的时候，会找最近的reject去执行而不是走catch，同时，catch执行完后依然会返回一个fulfiled的promise，我们依然可以.then的方式去处理catch返回的promise状态   
### 可以把catch理解为一个then～