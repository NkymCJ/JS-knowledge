# Bubble-Sort

冒泡排序

### 介绍

比较相邻元素，如果第一个比第二个大，就交换

假设数组为：[0,4,1,3,2]

04 14 34 24 0,1,3,2,4 第一趟比较完成后，数组最后一个数为数组中最大值，所以下一趟数组最后一个数不参与比较

01 13 23 第二趟完成时，数组倒数第二个为数组中的第二大值，所以下一趟数组最后两个数不参与比较

以此类推，每一趟比较次数-1

时间复杂度：O(n2) 

空间复杂度：O(1) (临时变量所占空间不随处理数据n的大小改变而改变，所以空间复杂度为O(1))

稳定性：稳定

缺点：即使已经排好序了，还是会执行所有的循环判断

优化：设置标识，当一趟里面没有发生任何交换时则证明数组已经排好序

示例:
```
// 基本写法
function BubbleSort(arr) {
    var len = arr.length;
    var tmp = 0;
    for (var i = 0; i < len - 1; i++) {
        for (var j = 0; j < len - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                tmp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = tmp;
            }
        }
    }
}
// 优化写法
function BubbleSort_Better(arr) {
    var len = arr.length;
    var tmp = 0;
    var isSort = true;
    for (var i = 0; i < len - 1; i++) {
        isSort = true;
        for (var j = 0; j < len - 1 - i; j++) {
            if (arr[j] > arr[j + 1]) {
                tmp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = tmp;
                isSort = false;
            }
        }
        if (isSort) {
            break;
        }
    }
}
```
