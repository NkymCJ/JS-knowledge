# Bubble-Sort

计算时间工具：console.time(timer) 与 console.timeEnd(timer)

冒泡排序

### 分析

比较相邻元素，如果第一个比第二个大，就交换：

假设数组为：[0,4,1,3,2]。

04 14 34 24 -> 0,1,3,2,4 第一趟比较完成后，数组最后一个数为数组中最大值，所以下一趟数组最后一个数不参与比较；

01 13 23 -> 0,1,2,3,4 第二趟完成时，数组倒数第二个为数组中的第二大值，所以下一趟数组最后两个数不参与比较......

以此类推，每一趟比较次数-1。

![图示](/bubble-Sort.gif)

### 示例: 
```
var arr = [84, 20, 29, 77, 5, 41, 100, 96, 90, 32, 52, 82, 100, 95, 77, 37, 12, 92, 9, 23, 13, 61, 27, 59, 78, 74, 35, 18, 20, 79, 44, 78, 64, 45, 58, 69, 3, 71, 87, 30, 36, 2, 98, 51, 91, 88, 98, 16, 1, 28]
console.log('普通版-----------------------');
var arr = arr;
var temp = 0;
var len = arr.length;
console.time("排序时间");
for (var i = 0; i < len - 1; i++) { // 趟数
    for (var j = 0; j < len - i - 1; j++) { // 趟次数
        if (arr[j] > arr[j + 1]) { // 相邻元素进行对比
            // 交换
            temp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = temp;
        }
    }
}
console.timeEnd("排序时间");
console.log('排序后：' + arr);
```

### 时间复杂度：O(n2) 

### 空间复杂度：O(1) (临时变量所占空间不随处理数据n的大小改变而改变，所以空间复杂度为O(1))。

### 稳定性：稳定

### 缺点：即使已经排好序了，还是会执行所有的循环判断

### 优化：设置标识，当一趟里面没有发生任何交换时则证明数组已经排好序

### 优化示例: 
```
var arr = [84, 20, 29, 77, 5, 41, 100, 96, 90, 32, 52, 82, 100, 95, 77, 37, 12, 92, 9, 23, 13, 61, 27, 59, 78, 74, 35, 18, 20, 79, 44, 78, 64, 45, 58, 69, 3, 71, 87, 30, 36, 2, 98, 51, 91, 88, 98, 16, 1, 28]
 {
    console.log('优化方式一----------------------');
    var arr = arr;
    var temp = 0;
    var len = arr.length;
    var flag = false; // 发生交换标识
    console.time("排序时间");
    for (var i = 0; i < len - 1; i++) {
        // 每趟初始都是没有交换的
        flag = false;
        for (var j = 0; j < len - i - 1; j++) {
            if (arr[j] > arr[j + 1]) {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                flag = true; // 发生了交换
            }
        }
        if (!flag) {
            // 如果这一趟里面没有发生任何交换，
            // 则证明数组已经排好序了
            break;
        }
    }
    console.timeEnd("排序时间");
    console.log('排序后：' + arr);
}
 {
    console.log('优化方式二-----------------------');
    var arr = arr;
    var temp = 0;
    var i = arr.length - 1; // 初始为数组的最后位置
    console.time("排序时间");
    while (i > 0) {
        var pos = 0; // 记录交换位置
        for (var j = 0; j < i; j++) {
            if (arr[j] > arr[j + 1]) {
                pos = j;
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
            }
        }
        // 上面for循环完后，pos记录的是最后一次发生交换的位置
        // 那么下趟循环的最大值就是它了
        // 如果一趟下来没有发生过交换，则pos为0，i=pos，i=0，结束循环
        i = pos;
    }
    console.timeEnd("排序时间");
    console.log('排序后：' + arr);
}

// 补充：优化的两种方式从思路上是一样的，都是设置标识
```
