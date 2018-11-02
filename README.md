# JS-knowledge
easy JS knowledge
## Array
### 1. filter()
 > $(selector).filter(function(currentValue,index,arr), thisValue)

 1. currentValue	 - 必须。当前元素的值
 2. index - 可选。当前的元素的索引值
 3. arr - 可选。当前元素属于的数组对象

 filter() 方法创建一个新的数组，新数组中的元素是通过检查指定数组中符合条件的所有元素

 filter() 不会改变原始数组，不会对空数组进行检测

 *兼容性：IE9+*
 
 示例：
 ```
 // 数组去重
 var arr = [1,2,3,4,2,2,2,2,2,3,4,3,4,3,1,2,];
 var result = arr.filter(function(element,index,self){
   return self.indexOf(element) === index;
 });
```