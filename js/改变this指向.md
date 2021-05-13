# Call/apply/bind 的作用和区别？
call 和 apply 是为了改变函数体内部 this 的指向。对于 apply、call 二者而言，作用完全一样，只是接受参数的方式不太一样。bind()最简单的用法是创建一个函数，使这个函数不论怎么调用都有同样的this值。
示例：
```
function func(arg1, arg2) {};
func.call(this, arg1, arg2); // 参数字符串
func.apply(this, [arg1, arg2]) // 参数数组
var obj = {
    a: 123,
};
var foo = {
    getV: function(k) {
        return this.a + k;
    }
}
console.log(foo.getV.bind(obj, 1)());  //124 需要调用
console.log(foo.getV.call(obj, 1));    //124 立即调用，参数字符串
console.log(foo.getV.apply(obj, [1]));   //124 立即调用，参数数组
```
区别：
传参不同，调用不同。bind 是返回对应函数，便于稍后调用；apply 、call 则是立即调用 。