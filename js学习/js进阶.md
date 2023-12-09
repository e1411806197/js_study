## js进阶

### 作用域和闭包

* 作用域  

  全局作用域

  语句作用域

  块作用域

  全局作用域>语句作用域>块作用域

  查找优先级：

  块->语句->全局

  ``` js
  let a=20
  function test(){
       var a=50
      console.log(a)
  }
  
  
  
  test()
  console.log(a)
  
  50
  20
  
  ```

  

* 闭包（外部函数无法访问内部函数）

  ``` js
  let s=function outer(){
      function inner(){
          console.log('i am inner')
      }
      console.log('i am outer')
      return inner
  }
  s()()
  
  //访问外部函数中的内部函数
  i am outer
  i am inner
  
  ```



### 创建实例对象

原型与原型链 prototype与_proto_方法

``` js
function Teacher(name,age,major){
    this.name=name
    this.age=age
    this.major=major
    this.teach=function (){

        console.log('hhhhhhhh')
    }

}
perry=new Teacher('hhhee',18,'computer')
Teacher.prototype.sport=function (hobby){this.hobby=hobby}
Teacher.prototype.play=function (){console.log('i am playing')}

console.log(perry.__proto__)
console.log(perry.__proto__.__proto__)
console.log(perry.__proto__===Teacher.prototype)

console.log(Teacher.prototype.__proto__)
console.log(Object.prototype.__proto__)


//实例化对象类的__proto__方法指向构造函数的prototype属性 构造函数的prototype属性继承了object的prototype属性

{ sport: [Function (anonymous)], play: [Function (anonymous)] }
[Object: null prototype] {}
true
[Object: null prototype] {}
null


```

### this指向

this指向浏览器环境与nodejs环境

``` js
var t={name:'hhh',age:18,hoppy:function (){console.log(this)}}
t.hoppy()
//指向t本身

```

this指向：

* 浏览器  全局-window 

  方法-window

  对象-指向对象本身

* nodejs环境 全局-空对象

  方法-global

  对象-指向对象本身



### 常见js相关方法

call与apply

``` js
function aa(ff){

    console.log('hhhhh',this.name,ff)
}
var ss={name:'alibaba'}
// call与apply主要功能是修改this指向的对象类型
aa.call(ss,'ppp')

aa.apply(ss,['apppp'])
let ss='console.log("hhhhhh")'
eval(ss)

hhhhh alibaba ppp
hhhhh alibaba apppp
hhhhhh


```

### 函数的相关声明方式

箭头函数es6

```js
//常用箭头函数
a=function (){console.log('jjjj')}
b=()=>{console.log('woshi jiantouhanshu')}
c=(a,b)=>{console.log(a+b)}
a()
b()
c(3,4)

jjjj
woshi jiantouhanshu
7

箭头函数中调用this指向的是外部作用域的对象
```

### 定时器

``` js
// 定时器 执行一次
x=setTimeout(()=>{console.log('hhhhhh')},200)


// 间隔一段时间就执行
y=setInterval(()=>{console.log('i am interval')},200)

```



### ajax

一种异步的js和xml

可以在不加载页面的情况下与服务器交换数据进行内容的更新

### axios

axios中主要使用提供的拦截器 可以在数据传输过程中进行加密解密等相关操作，

数据<-解密<-axios

Axios->加密->send