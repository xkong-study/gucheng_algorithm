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
Math.random() 不变	写成 static，只生成一次	每次交易生成 ID，用 Date.now(), Math.random() 或 UUID             
this.account undefined	Account 类里没有 this.account	应传 this 本身，代表当前账户            
我们不可以把this.#balance再构造器之外 如果之外就是#balance         
setTimeout不可以写在try catch里面 因为try catch 宏观事件 setTimeout是微事件 不可以在同时执行      
constructor只能初始化不能实现可以override的事件 不可以执行需要耗时或者可能失败的操作。    
不可以在构造器里面创建类 =》 不方便测试 不利于耦合 不方便扩展 通过依赖注入方式替代。     
execute() → 再内部调用 withdraw() or deposit() 更好！
比起“直接调用 withdraw()”，这种做法在可读性、可维护性、扩展性、安全性上都更优秀。   

