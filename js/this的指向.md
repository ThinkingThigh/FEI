# this的指向问题
1. 普通函数中，this指向其函数的直接调用者；
2. 箭头函数中，this指向其定义环境
3. 构造函数中，如果不使用new，则this指向window，如果使用new创建了一个实例，则this指向该实例
4. window内置函数中，如setInterval，setTimeout等，其内部的this指向Window
5. 匿名函数的this指向Window