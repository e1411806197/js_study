# js基础

## 1.js变量

### js的基础数据类型以及定义变量

```js
var a=1
var b
var c=null
var d='hello'
var aa,bb,cc,dd=100
var nn=[1,2,3]
console.log(a,typeof a)
console.log(b,typeof b)
console.log(c,typeof c)
console.log(d,typeof d)
console.log(nn,typeof nn)
//可以先进行声明不给值


1 number
undefined undefined
null object
hello string
[ 1, 2, 3 ] object

```

Undefine  未声明  null 空指针  逻辑（null）=false undefine =false 

逻辑上相同（undefine=null）

```js

const a=100
ss=''
aa='eswafda'
a_=Boolean(aa)
s_=Boolean('')
console.log(a_,s_)


console.log(Boolean(undefined))

console.log(Boolean(null))
console.log(Boolean(0))
console.log(Boolean(1))

true false
false
false
false
true

```

###  数字类型 number



```js
var a=1/0
console.log(a)
//无穷大

var b=0/0
console.log(b)
//异常捕获
nan

var aa=0xfff
var bb=0b1001001
console.log(aa,bb)

var ap='123.456'
console.log(Number(ap),parseInt(ap),parseFloat(ap))


Infinity
NaN
4095 73
123.456 123 123.456

```

### 字符串

字符串拼接	

```js
var a='helloworld'
var c='hhppp'
var d=123
var z=56

zz=a+c
pp=a+d
nn=z+d+c
qq=c+d+z
console.log(zz,pp,nn,qq)

var ss=[1,2,3]
console.log(''+ss)


var pp=null
console.log(''+pp)

var kk=undefined
console.log(''+kk,typeof (''+kk))
console.log(''+true,typeof (''+true))

helloworldhhppp helloworld123 179hhppp hhppp12356
1,2,3
null
undefined string
true string
```

字符串常用

* tostring（）

  ```js
  var a='helloworld'
  var c='hhppp'
  var d=123
  var z
  var p=null
  
  console.log(a.toString())
  console.log(d.toString())
  // console.log(z.toString()) 无法转换
  console.log(true.toString())
  
  helloworld
  123
  true
  
  ```


字符串常用函数

``` js
var a='heLPloworld'
var c='h,h,ppp'
// 切片
console.log(a.substring(0,2))
console.log(a.substr(1,3))
// 分割
console.log(c.split(','))
//查询
console.log(a.indexOf('ll'))
console.log(a.lastIndexOf('l'))
// 字符串长度
console.log(a.length)
// 全大写
console.log(a.toUpperCase())
// 全小写
console.log(a.toLowerCase())


// 找到字符串中指定索引位置的内容并返回
console.log(a.charAt(0))

// 返回指定字符unicode编码
console.log(a.charCodeAt(0))


he
eLP
[ 'h', 'h', 'ppp' ]
-1
9
11
HELPLOWORLD
helploworld
h
104

```

### 数组常用相关方法

``` js
// 创建数组
aa=[1,34,45,'hhhrl']
console.log(aa,typeof aa)

b=new Array()
console.log(b)
// 从栈的尾部进行添加以及删除元素
aa.pop()
aa.push('kkkk')
console.log(aa)

// 从栈的头部进行添加以及删除元素
aa.shift()
aa.unshift(999)
console.log(aa)

var pp=[1,2,3,4,5,6,7,8]
var number=[]
pp.forEach(function (a,b){
    if (b%2==0){
        number.push(a)

    }
})

console.log(number)
console.log(pp.length)


提取数组中的一部分内容
let aa=[1,2,3,4,5]

b=aa.slice(0,3)
console.log(aa,'\n',b)


删除其中的某几个元素 并使用其他参数进行替换
zz=aa.splice(1,2,5,76)
console.log(aa)

aa=[1,2,3,4,5]
zz=aa
zz.splice(0,3,4,5,9)
console.log(aa)


进行数组的连接
ss=[10,20]
pp=[20,30,40]
cc=[100]
nn=ss.concat(pp).concat(cc)
console.log(nn)

a=[10,20,30,40]
pp=a.join('')
console.log(pp)

let pp=[10,20,30,'jhh']
ss=pp.indexOf('jhhp')
console.log(ss)


sort 函数
默认按照第一个数字进行排列
aa=[10,25,2,3,17]
bb=['zaas','baa','abz','aaaaa']
bb.sort()
console.log(bb)
aa.sort()
console.log(aa)


// 升序
nn=[100,25,30,20,14,5]
nn.sort(function (a,b){return a-b})
console.log(nn)

// 降序
pp=nn
pp.sort(function (a,b){return b-a})
console.log(nn)

aa=[1,2,3,4,5,6]
zz=aa.map(function (x){return x+20})
console.log(zz)


pp=aa.filter(function (x){ return x%2==0})
console.log(pp)
```

### 函数

函数与自运行函数

``` js
arguments采集相应的
let ss=function aa(x=20,y){
    zz=arguments
    console.log(zz)

}

ss(30,50)



自执行函数
(function sss(){console.log('aaaaa')})()

(function aaa(){console.log('bbbbb')}())

!function (){console.log('ssss')}()


```

### 循环

``` js
while  do while
//循环的两种形式

aa=[10,20,30,'hhh','xxxx']
for(i=0;i<aa.length;i++){

    console.log(aa[i])
}


// i为循环元素的序列号
zz=[10,20,30,40,50]
for (i in zz){

    console.log(zz[i])
}


kk=[10,20,30,40,50]
let i=0
while (i<kk.length){

    console.log(kk[i])
    i++
}

i=0
do{
    console.log('hhhhhhh')
    i++
}
while (i>1)
```

### 条件判断

``` js
let zz=function t(s){
    switch (s){
        case 1:
        case 2:
        case 3:
        case 4:{
            console.log('tttt')
            break

        }

        default:
            console.log('default')

    }
}

zz(10)
```

其余条件判断if else 与python相同 

### 创建日期时间

``` js
// 创建时间 utc时区
var d=new Date()
console.log(d)

f=new Date(Date.UTC(2024,1,2))
console.log(f)


// 创建时间戳 毫秒级别
var t=Date.now()
console.log(t)

var p=new Date().getTime()
console.log(p)


2023-12-08T12:54:08.750Z
2024-02-02T00:00:00.000Z
1702040048763
1702040048763

```

逻辑运算符

% ++ -- == === && ||相关逻辑运算符和在python中使用相类似

三元运算符

t=a>100?'大于'："小于"

### 对象

对象=数据（变量）+方法（函数）

``` js
var t={name:'perry',age:18,
    hobby:function (){console.log('hobbysss')}}

console.log(t.hobby())

let s=t
s.age=22
console.log(t)
//基础类型传值 引用类型传地址

hobbysss
undefined
{ name: 'perry', age: 22, hobby: [Function: hobby] }

```

