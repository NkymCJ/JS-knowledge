# JS-knowledge

一些简单的JS知识点

## Array

### 1. filter() - 迭代方法

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

### 2. some() - 迭代方法

 > $(selector).some(function(currentValue,index,arr), thisValue)

 1. currentValue  - 必须。当前元素的值
 2. index  - 可选。当前的元素的索引值
 3. arr  - 可选。当前元素属于的数组对象
 4. thisValue  - 可选。传递给函数的值一般用 "this" 值。如果这个参数为空， "undefined" 会传递给 "this" 值

 *some() 方法检测数组中的元素是否有一个以上满足指定条件，若有，则返回true，且不再执行检测，若无，则返回false*

 *some() 不会改变原始数组，不会对空数组进行检测*

 *兼容性：IE9+*
 
 示例：
 ```
 // 检测数组中的元素是否有大于等于5
 var arr = [1, 2, 3, 4, 2, 2, 2, 2, 2, 3, 4, 3, 4, 3, 1, 6];
 var result = arr.some(function (currentValue, index, arr) {
   return currentValue >= 5;
 });
 console.log(result);
```

### 3. every() - 迭代方法

 > $(selector).every(function(currentValue,index,arr), thisValue)

 1. currentValue  - 必须。当前元素的值
 2. index  - 可选。当前的元素的索引值
 3. arr  - 可选。当前元素属于的数组对象
 4. thisValue  - 可选。传递给函数的值一般用 "this" 值。如果这个参数为空， "undefined" 会传递给 "this" 值

 *every() 方法检测数组中的元素是否都满足指定条件，若有一个不满足，则返回false，且不再执行检测，若都满足，则返回true*

 *every() 不会改变原始数组，不会对空数组进行检测*

 *兼容性：IE9+*
 
 示例：
 ```
 // 检测数组中的元素是否都大于等于1
 var arr = [1, 2, 3, 4, 2, 2, 2, 2, 2, 3, 4, 3, 4, 3, 1, 2];
 var result = arr.every(function (currentValue, index, arr) {
   return currentValue >= 3;
 });
 console.log(result);
```

### 4. map() - 迭代方法

 > $(selector).map(function(currentValue,index,arr), thisValue)

 1. currentValue  - 必须。当前元素的值
 2. index  - 可选。当前的元素的索引值
 3. arr  - 可选。当前元素属于的数组对象
 4. thisValue  - 可选。传递给函数的值一般用 "this" 值。如果这个参数为空， "undefined" 会传递给 "this" 值

 *map() 方法创建一个新的数组，新数组中的元素是原数组元素处理后的值，按原数组的顺序依次处理元素*

 *map() 不会改变原始数组，不会对空数组进行检测*

 *兼容性：IE9+*
 
 示例：
 ```
 // 创建新数组，新数组的每个元素为数组中的每个元素乘以100
 var arr = [1,2,3,4,2,2,2,2,2,3,4,3,4,3,1,2];
 var result = arr.map(function(currentValue,index,arr){
   return currentValue * 100;
 });
 console.log(result);
```

### 5. forEach() - 迭代方法

 > $(selector).forEach(function(currentValue,index,arr), thisValue)

 1. currentValue  - 必须。当前元素的值
 2. index  - 可选。当前的元素的索引值
 3. arr  - 可选。当前元素属于的数组对象
 4. thisValue  - 可选。传递给函数的值一般用 "this" 值。如果这个参数为空， "undefined" 会传递给 "this" 值

 *forEach() 方法用于调用数组的每个元素，并将元素传递给回调函数，返回undefined*

 *forEach() 对于空数组是不会执行回调函数的*

 *兼容性：IE9+*
 
 示例：
 ```
 // 创建新数组，新数组的每个元素为数组中的每个元素乘以100
 var arr = [1, 2, 3, 4, 2, 2, 2, 2, 2, 3, 4, 3, 4, 3, 1, 2];
 var result = arr.forEach(function (currentValue, index, arr) {
   console.log(index + ': ' + currentValue + '<br/>');
 });
 console.log(result);
```

### 6. reduce() - 归并方法

 > $(selector).reduce(function(total,currentValue,currentIndex,arr), initialValue)

 1. total  - 必须。初始值，或者每一趟计算结束后的返回值
 2. currentValue  - 必须。当前元素的值
 3. currentIndex  - 可选。当前的元素的索引值
 4. arr  - 可选。当前元素属于的数组对象
 5. initialValue  - 可选。传递给函数的初始值

 *reduce() 方法接收一个函数作为累加器，从左到右，返回最终的计算结果*

 *reduce() 对于空数组是不会执行回调函数的*

 *兼容性：IE9+*
 
 示例：
 ```
 // 数组累加
 var arr = [1, 1, 1, 2, 3];
 var result = arr.reduce(function (total, currentValue, currentIndex, arr) {
   return total + currentValue;
 }, 0);
 console.log(result);
```

