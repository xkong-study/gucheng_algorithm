#  JavaScript 面向对象编程（OOP）总结 ✨✨✨

JavaScript 是一种 基于原型 (Prototype-based) 的面向对象编程语言，但 ES6 引入了 class 语法，使其更接近传统 OOP 语言（如 Java、Python）。

本文总结了 JavaScript OOP 相关的 类、继承、多态、封装、属性访问控制、动态属性、方法重写等 重要知识点。

\---

## 1️⃣ JavaScript 类（Class） ✨✨✨

## ✅ 类的基本写法

📌 代码示例：

class Person {

constructor(name, age) {

this.name = name; // 实例属性

this.age = age;

}

greet() {

return Hello, my name is ${this.name}.;

}

}

const p = new Person("Alice", 25);

console.log(p.greet()); // ✅ "Hello, my name is Alice."

\---

## 2️⃣ 封装（Encapsulation）：私有属性 & 方法 ✨✨✨

## ✅ 方法 1：使用  号定义私有属性

📌 代码示例：

class Person {

# age; // 🔒 私有属性

constructor(name, age) {

this.name = name;

this.#age = age;

}

getAge() {

return this.#age;

}

}

const p = new Person("Alice", 25);

console.log(p.getAge()); // ✅ 25

console.log(p.#age); // ❌ 报错，外部不能访问私有属性

\---

## 3️⃣ 继承（Inheritance） ✨✨✨

📌 代码示例：

class Animal {

constructor(name) {

this.name = name;

}

speak() {

return ${this.name} makes a sound.;

}

}

class Dog extends Animal {

constructor(name, breed) {

super(name); // ✅ 调用父类构造函数

this.breed = breed;

}

}

\---

## 4️⃣ 多态（Polymorphism）：避免 switch-case ✨✨✨

📌 代码示例：

class Shape {

area() {

throw new Error("Method 'area' must be implemented.");

}

}

class Circle extends Shape {

constructor(radius) {

super();

this.radius = radius;

}

area() {

return Math.PI \* this.radius  2;

}

}

\---

## 5️⃣ 静态属性 & 方法（Static） ✨✨✨

📌 代码示例：

class MathUtils {

static add(a, b) {

return a + b;

}

}

console.log(MathUtils.add(2, 3)); // ✅ 5

\---

## 6️⃣ JavaScript 允许动态添加属性 ✨✨✨

## ✅ 实例可以动态添加属性

📌 代码示例：

class Person {

constructor(name) {

this.name = name;

}

}

const p = new Person("Alice");

p.age = 25; // ✅ 运行时动态添加属性

console.log(p.age); // ✅ 25

\---

| 特性         | Python                                | JavaScript                          |
|--------------|---------------------------------------|-------------------------------------|
| 变量声明     | 直接赋值                               | `let`, `const`, `var`               |
| 类 & 继承    | `__init__` + `super()`                 | `constructor()` + `super()`         |
| 私有变量     | `__var`（模拟）                        | `#var`（ES6 真实私有）              |
| 静态方法     | `@staticmethod`                        | `static method()`                   |
| 线程安全     | `threading.Lock()`                     | `async-mutex`                       |
| 异步处理     | `async def` + `await`                  | `async function` + `await`          |
| 异常处理     | `try-except`                           | `try-catch`                         |

🚀 JavaScript OOP 重点：封装、继承、多态、静态成员、动态属性

今日手写错误

```
class UserFactory {
    static createUser(type, name) {
        switch (type) {
            case "admin": return new Admin(name);
            case "user": return new User(name);
            case "guest": return new Guest(name);
            default: throw new Error("Invalid type");
        }
    }
}

```
不是
```
class factory{
    constructor(type,name){
        if(this.type == 'admin'){ return new Admin(this.name); }
}
```

```
乐观锁问题	this.version 需在 withdraw() 前检查 是 Files.version
```
```
在类里直接 new 另一个类	 可以	this.node = new ListNode();      
在构造函数里传入另一个类	 不推荐	constructor(ListNode, capacity) {...}       
在方法里创建另一个类的实例	可以	this.car = new Car("Tesla");     
```
catch() 语法错误（缺少参数）    
 
this 丢失	普通函数不绑定上下文	改用箭头函数 const process = () => {}                 
Math.random() 不变	写成 static，只生成一次	每次交易生成 ID，用 Date.now(), Math.random() 或  UID               
this.account undefined	Account 类里没有 this.account	应传 this 本身，代表当前账户              
我们不可以把this.#balance再构造器之外 如果之外就是#balance             
setTimeout不可以写在try catch里面 因为try catch 宏观事件 setTimeout是微事件 不可以在同时执行  try/catch 只捕获同步异常         
constructor只能初始化不能实现可以override的事件 不可以执行需要耗时或者可能失败的操作。      
不可以在构造器里面创建类 =》 不方便测试 不利于耦合 不方便扩展 通过依赖注入方式替代。       
execute() → 再内部调用 withdraw() or deposit() 更好！      
比起“直接调用 withdraw()”，这种做法在可读性、可维护性、扩展性、安全性上都更优秀。     

测试时无法注入替代实现      
比如你想测试 Logger 会不会正确调用 .write()，你就没法 mock 这个 ConsoleOutput        

除非你去 monkey patch 全局类，这非常 dirty：         
global.ConsoleOutput = TestOutput; // ❌ 超脏        
而如果你用依赖注入，就可以轻松 mock：          
const logger = new Logger(new TestOutput())        

 
“变的是行为？用组合”   
“变的是类型结构？才考虑继承”    
“组合注入 + 策略模式 + 依赖分离 = 企业级设计标准”   

class User {       
  #email;         

  constructor(email) {
    this.setEmail(email); // 利用已有逻辑，避免重复写规则         
  }

  getEmail() {        
    return this.#email;       
  }           
       
  setEmail(val) {         
    this.#email = val.toLowerCase(); // 一处封装，标准统一        
  }      
}         


async run() {        
  try {        
    await this.task(); // 支持 Promise/async 异步任务         
  } catch (e) {        
    console.log("Caught:", e); // 错误被 catch 到，不会炸崩系统        
  }       
}      
优势：        
async/await 能让 try/catch 捕获 Promise 中的异常
可读性强，结构清晰
可以扩展后续 retry、status 控制等逻辑

✅ 状态改我 → 方法挂我（如：post.publish()）  
✅ 字段归我 → 方法挂我（如：session.isExpired()）      
✅ 集合是我 → 方法挂我（如：cart.add()）      
✅ 是我发起 → 方法挂我（如：user.like()）      
✅ 是我调度 → 方法挂我（如：scheduler.schedule()）           
     
