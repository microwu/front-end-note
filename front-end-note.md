# js数据类型
基本类型：String Number Boolean Null Undefined Symbol(es6新增 表示独一无二的值) <br>
引用类型：Object Array Function

# 获取元素
通过ID获取（getElementById）<br>
通过name属性（getElementsByName）<br>
通过标签名（getElementsByTagName）<br>
通过类名（getElementsByClassName）<br>
获取html的方法（document.documentElement）<br>
获取body的方法（document.body）<br>
通过选择器获取一个元素（querySelector）<br>
通过选择器获取一组元素（querySelectorAll）

# HTTP Code
200：请求被正常处理 <br>
204：请求被受理但没有资源可以返回 <br>
206：客户端只是请求资源的一部分，服务器只对请求的部分资源执行GET方法，相应报文中通过Content-Range指定范围的资源。 <br>
301：永久性重定向 <br>
302：临时重定向 <br>
303：与302状态码有相似功能，只是它希望客户端在请求一个URI的时候，能通过GET方法重定向到另一个URI上 <br>
304：发送附带条件的请求时，条件不满足时返回，与重定向无关 <br>
307：临时重定向，与302类似，只是强制要求使用POST方法 <br>
400：请求报文语法有误，服务器无法识别 <br>
401：请求需要认证 <br>
403：请求的对应资源禁止被访问 <br>
404：服务器无法找到对应资源 <br>
500：服务器内部错误 <br>
502：服务器挂了<br>
503：服务器正忙

# Http缓存头
*Expires* ：它通常的使用格式是 Expires:Fri ,24 Dec 2027 04:24:07 GMT，后面跟的是日期和时间，超过这个时间后，缓存的内容将失效 

*Last-Modified / If-Modified*：一般服务端在响应头中返回一个Last-Modified字段，告诉浏览器这个页面的最后修改时间 

*Etag/If-None-Match*：用于验证缓存有效性

# Array的方法

**toString()** 返回数组中每个值的字符串形式拼接而成的以逗号分隔的字符串
```js
var arr = [1,2,4,5];
console.log(arr.toString());//1,2,4,5
```

**valueOf()** 返回的还是数组
```js
var arr = ["1","2","4","5"];
console.log(arr.valueOf());//["1","2","4","5"]
```

**join()** 返回字符串，使用不同分隔符来构建字符串【默认为逗号】
```js
var arr = [1,2,3,4,5];
console.log(arr.join());//1,2,3,4,5
console.log(arr.join(""));//12345
console.log(arr.join("|"));//1|2|3|4|5
```
## 栈方法

- **push()** 栈方法，添加到数组**末尾**，返回修改后数组的长度

- **pop()** 栈方法，从数组末尾移除**最后一项**，返回移除的项

## 队列方法
- **shift()** 队列方法，取得数组**第一项**

- **unshift()** 队列方法，添加到数组**前端**
```js
var colors = [];
var count = colors.push("red","blue"); // 2
//colors = ["red","blue"]；

count = colors.unshift("green","white"); //4
//colors = [“green”,"white","red","blue"]

colors.pop();   //"blue"
colors.shift(); //"green"
```
## 重排序方法
- **reverse()** 反转数组项的顺序,返回值是经过反转后的数组

- **sort()** 默认按照升序排列数组【调用每个数组项的**toString()方法比较**字符串。即使数组都是数值，也是比较**字符串**】，可接受比较函数作为参数。返回值是经过排序后的数组
```js
var arr = [10,2,7,3,5];
arr.reverse();//[5,3,7,2,10]
arr.sort();//[10,2,3,5,7]

function compare1(v1,v2){
    if(v1 < v2)
        return -1;
    else if( v1 > v2)
        return 1;
    else 
        return 0;
}

arr.sort(compare1);//[2,3,5,7,10]

//另一种更为简便的方式
function compare2(v1,v2){
    return v2-v1;
}

arr.sort(compare2);//[10,7,5,3,2]
```
## 操作方法
- **concat()** 基于当前数组中所有项创建一个**新数组**。在没有参数的时候，只是复制当前数组并返回副本。有参数则将值**添加到数组末尾**
```js
var colors=["red","blue"];
var colors2 = colors.concat("yellow",["black","white"]);
//["red","blue","yellow","black","white"]
```

- **slice()** 创建一个新数组 <br>
  - slice(start,end) 返回起始和结束位置之间的项【不包括结束位置】。结束位置小于起始位置返回空数组 <br>
  - slice(start) 返回从start位置到末尾的所有项<br>
若是负数，用数组长度+该负数来表示位置
```js
var colors = ["red","green","blue","black","yellow"];
    var colors2 = colors.slice(1);//["green","blue","black","yellow"]
    var colors3 = colors.slice(1,4);//["green","blue","black"]
    var colors4 = colors.slice(-2,-1);//与slice(3,4)效果相同。["black"]
```

- **splice()** 返回被删除的项。splice(start,delete_count,insert_item[可选])
  - 删除 splice(start,count) start要删除的第一项的位置，count要删除的项数
  - 插入 splice(start,0,inserts) start要插入的位置，0（要删除的项数为0），inserts要插入的项（可以是任意多个项）
  - 替换 splice(start,d_count,inserts) start起始位置，d_count为要删除的项数，inserts为要插入的项。插入的项数与删除的项数不必相等。
```js
var colors = ["red","green","blue","black","yellow"];
    var removed = colors.splice(0,1);//删除第一项
    //colors = ["green","blue","black","yellow"];
    //removed = ["red"]
    
    removed = colors.splice(1,0,"pink","orange");//从位置1开始插入2项
    //colors = ["green","pink","orange","blue","black","yellow"];
    //removed = [];没有删除元素，返回空数组
    
    removed = colors.splice(1,1,"red","purple");//从位置1删除一个，再插入2项
    //colors = ["green","red","purple","orange","blue","black","yellow"];
    //removed = ["pink"];
```
## 位置方法
- **indexOf()** 从数组开头开始查找所在项的位置

- **lastIndexOf()** 从数组末尾开始向前查找<br>
  - 比较参数和数组中每一项时，使用全等操作符。=== 
  - 没有找到时返回-1

## 迭代方法 对数组中每一项运行给定函数
- **every()** 若函数对每一项都返回true,则返回true
- **filter()** 返回这个函数会返回true的数组
- **forEach()** 没有返回值，本质上与使用for循环迭代数组一样。
- **map()** 返回每次函数调用的结果组成的数组
- **some()** 如果函数对任一项返回true,则返回true<br>
【兼容性】IE9+,Chrome,Firefox 2+,Safari 3+,Opera 9.5+支持

```js
var numbers=[1,2,3,4,5,6,7];

var everyResult = numbers.every(function(item,index,array){
    return (item > 3);
});
//everyResult的值为false。因为1,2,3返回的是flase,而每一项都返回true才会返回true

var someResult = numbers.some(function(item,index,array){
    return (item > 3);
});
//someResult的值为true。因为有返回true的值，则返回true

var filterResult = numbers.filter(function(item,index,array){
    return (item > 2);
});
//filterResult的值为[3,4,5,6,7],返回符合条件的值

var mapResult = numbers.map(function(){
    return item*2;
});
//mapResult的值为[2,4,6,8,10,12,14]，返回每个数的结果
```

## 归并方法
- **reduce()** 从数组第一项开始，逐个遍历到最后
- **reduceRight()** 从数组的最后一项开始，向前遍历到第一项
都支持4个参数。(prev【前一个值】,cur【当前值】,index【项的索引】,array【数组对象】)<br>
reduce()和reduceRight()的差别在于从哪头开始遍历数组。除此之外都一样。<br>
【兼容性】IE9+,Chrome,Firefox 3+,Safari 4+,Opera 10.5支持<br>
这个函数返回的任何值都会作为第一个参数自动传给下一项。第一次迭代从数组的第二项开始。
```js 
    //利用reduce求数组中所有值的和
    var values = [1,2,3,4,5];
    var sum = values.reduce(function(prev,cur,index,array){
        return prev + cur;
    });
    //sum的值为15;
```

# CSS选择器优先级
1. id选择器的权值为100
2. class、属性和伪类选择器的权值为10
3. 标签选择器的权值为1
4. 权值较大的优先级越高
5. 比较样式时，将对应的选择器权值相加，大的优先级高
6. 权值相同的，根据从上往下的原则，后定义的优先级高
7. 特殊！important，优先级最高
```css
div > #title{color: blue;}............ 1(div)+100(#title)=101
div > h3#title.title{color: red;}..... 1(div)+1(h3)+100(#title)+10(.title)=112
[lang=”en”] h3.title{color: green;}... 10([lang='en'])+1(h3)+10(.title)=21
[lang=”en”] #title{color: gray;}...... 10([lang=”en”])+100(#title)=110
```