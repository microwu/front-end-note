# js数据类型
基本类型：String Number Boolean Null Undefined Symbol(es6新增 表示独一无二的值) 

引用类型：Object Array Function

# 获取元素
通过ID获取（getElementById）

通过name属性（getElementsByName）

通过标签名（getElementsByTagName）

通过类名（getElementsByClassName）

获取html的方法（document.documentElement）

获取body的方法（document.body）

通过选择器获取一个元素（querySelector）

通过选择器获取一组元素（querySelectorAll）

# HTTP Code
200：请求被正常处理 

204：请求被受理但没有资源可以返回 

206：客户端只是请求资源的一部分，服务器只对请求的部分资源执行GET方法，相应报文中通过Content-Range指定范围的资源。 

301：永久性重定向 

302：临时重定向 

303：与302状态码有相似功能，只是它希望客户端在请求一个URI的时候，能通过GET方法重定向到另一个URI上 

304：发送附带条件的请求时，条件不满足时返回，与重定向无关 

307：临时重定向，与302类似，只是强制要求使用POST方法 

400：请求报文语法有误，服务器无法识别 

401：请求需要认证 

403：请求的对应资源禁止被访问 

404：服务器无法找到对应资源 

500：服务器内部错误 

502：服务器挂了

503：服务器正忙