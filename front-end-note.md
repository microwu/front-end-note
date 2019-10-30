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
100 &emsp; Continue &emsp; 继续。客户端应继续其请求

101 &emsp; Switching Protocols &emsp; 切换协议。服务器根据客户端的请求切换协议。只能切换到更高级的协议，例如，切换到HTTP的新版本协议

200 &emsp; OK &emsp; 请求成功。一般用于GET与POST请求

201 &emsp; Created &emsp; 已创建。成功请求并创建了新的资源

202 &emsp; Accepted &emsp; 已接受。已经接受请求，但未处理完成

203 &emsp; Non-Authoritative Information &emsp; 非授权信息。请求成功。但返回的meta信息不在原始的服务器，而是一个副本

204 &emsp; No Content &emsp; 无内容。服务器成功处理，但未返回内容。在未更新网页的情况下，可确保浏览器继续显示当前文档

205 &emsp; Reset Content &emsp; 重置内容。服务器处理成功，用户终端（例如：浏览器）应重置文档视图。可通过此返回码清除浏览器的表单域

206 &emsp; Partial Content &emsp; 部分内容。服务器成功处理了部分GET请求

300 &emsp; Multiple Choices &emsp; 多种选择。请求的资源可包括多个位置，相应可返回一个资源特征与地址的列表用于用户终端（例如：浏览器）选择

301 &emsp; Moved Permanently &emsp; 永久移动。请求的资源已被永久的移动到新URI，返回信息会包括新的URI，浏览器会自动定向到新URI。今后任何新的请求都应使用新的URI代替

302 &emsp; Found &emsp; 临时移动。与301类似。但资源只是临时被移动。客户端应继续使用原有URI

303 &emsp; See Other &emsp; 查看其它地址。与301类似。使用GET和POST请求查看

304 &emsp; Not Modified &emsp; 未修改。所请求的资源未修改，服务器返回此状态码时，不会返回任何资源。客户端通常会缓存访问过的资源，通过提供一个头信息指出客户端希望只返回在指定日期之后修改的资源

305 &emsp; Use Proxy &emsp; 使用代理。所请求的资源必须通过代理访问

306 &emsp; Unused &emsp; 已经被废弃的HTTP状态码

307 &emsp; Temporary Redirect &emsp; 临时重定向。与302类似。使用GET请求重定向

400 &emsp; Bad Request &emsp; 客户端请求的语法错误，服务器无法理解

401 &emsp; Unauthorized &emsp; 请求要求用户的身份认证

402 &emsp; Payment Required &emsp; 保留，将来使用

403 &emsp; Forbidden &emsp; 服务器理解请求客户端的请求，但是拒绝执行此请求

404 &emsp; Not Found &emsp; 服务器无法根据客户端的请求找到资源（网页）。通过此代码，网站设计人员可设置"您所请求的资源无法找到"的个性页面

405 &emsp; Method Not Allowed &emsp; 客户端请求中的方法被禁止

406 &emsp; Not Acceptable &emsp; 服务器无法根据客户端请求的内容特性完成请求

407 &emsp; Proxy Authentication Required &emsp; 请求要求代理的身份认证，与401类似，但请求者应当使用代理进行授权

408 &emsp; Request Time-out &emsp; 服务器等待客户端发送的请求时间过长，超时

409 &emsp; Conflict &emsp; 服务器完成客户端的PUT请求是可能返回此代码，服务器处理请求时发生了冲突

410 &emsp; Gone &emsp; 客户端请求的资源已经不存在。410不同于404，如果资源以前有现在被永久删除了可使用410代码，网站设计人员可通过301代码指定资源的新位置

411 &emsp; Length Required &emsp; 服务器无法处理客户端发送的不带Content-Length的请求信息

412 &emsp; Precondition Failed &emsp; 客户端请求信息的先决条件错误

413 &emsp; Request Entity Too Large    由于请求的实体过大，服务器无法处理，因此拒绝请求。为防止客户端的连续请求，服务器可能会关闭连接。如果只是服务器暂时无法处理，则会包含一个Retry-After的响应信息

414 &emsp; Request-URI Too Large &emsp; 请求的URI过长（URI通常为网址），服务器无法处理

415 &emsp; Unsupported Media Type &emsp; 服务器无法处理请求附带的媒体格式

416 &emsp; Requested range not satisfiable &emsp; 客户端请求的范围无效

417 &emsp; Expectation Failed &emsp; 服务器无法满足Expect的请求头信息

500 &emsp; Internal Server Error &emsp; 服务器内部错误，无法完成请求

501 &emsp; Not Implemented &emsp; 服务器不支持请求的功能，无法完成请求

502 &emsp; Bad Gateway &emsp; 作为网关或者代理工作的服务器尝试执行请求时，从远程服务器接收到了一个无效的响应

503 &emsp; Service Unavailable &emsp;由于超载或系统维护，服务器暂时的无法处理客户端的请求。延时的长度可包含在服务器的Retry-After头信息中

504 &emsp; Gateway Time-out &emsp; 充当网关或代理的服务器，未及时从远端服务器获取请求

505 &emsp; HTTP Version not supported &emsp; 服务器不支持请求的HTTP协议的版本，无法完成处理

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

# let关键字
let可以让变量具有ES6中的**块级作用域**的属性
```js
{ 
    var x = 2; 
}
// 这里可以使用 x 变量

{ 
    let x = 2;
}
// 这里不能使用 x 变量
```
# HTTP方法
GET<br>
POST<br>
HEAD<br>
OPTIONS<br>
PUT<br>
DELETE<br>
TRACE<br>
CONNECT<br>

# \<link>和@import
链接方式（下面用 link 代替）和导入方式（下面用 **@import** 代替）都是引入外部的 CSS 文件的方式，下面我们来比较这两种方式，并且说明为什么不推荐使用 **@import**。

link 属于 HTML，通过 **\<link>** 标签中的 href 属性来引入外部文件，而 **@import** 属于 CSS，所以导入语句应写在 CSS 中，要注意的是导入语句应写在样式表的开头，否则无法正确导入外部文件；

**@import** 是 CSS2.1 才出现的概念，所以如果浏览器版本较低，无法正确导入外部样式文件；

当 HTML 文件被加载时，link 引用的文件会同时被加载，而 **@import** 引用的文件则会等页面全部下载完毕再被加载；