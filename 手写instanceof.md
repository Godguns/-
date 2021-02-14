
```
function myInstanceof(object,constructor) {
    const prototype = constructor.prototype;
    let proto = object.__proto__;
    while(true) {
        if(proto === null) return false;
        if(proto === prototype) return true;
        proto = proto.__proto__;
    }
}

```
