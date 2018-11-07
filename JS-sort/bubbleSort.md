## SORT 排序

### BubbleSort 冒泡排序

#### 一般写法



 > $(selector).filter(function(currentValue,index,arr), thisValue)

 1. currentValue  - 必须。当前元素的值
 2. index  - 可选。当前的元素的索引值
 3. arr  - 可选。当前元素属于的数组对象
 4. thisValue  - 可选。传递给函数的值一般用 "this" 值。如果这个参数为空， "undefined" 会传递给 "this" 值

 *filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中返回true的该项的元素*

 *filter() 不会改变原始数组，不会对空数组进行检测*

 *兼容性：IE9+*
 
 示例：
 ```
 // 数组去重
 var arr = [1, 2, 3, 4, 2, 2, 2, 2, 2, 3, 4, 3, 4, 3, 1, 2];
 var result = arr.filter(function (currentValue, index, arr) {
   return arr.indexOf(currentValue) === index;
 });
```