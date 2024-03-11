<img width="867" alt="截屏2024-03-11 20 13 21" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/4f5d2495-c01c-4bd0-ae08-8b7697c6ccfd">

<img width="886" alt="截屏2024-03-11 20 18 03" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/30a29ecf-e153-441c-ac69-22ccb74488d2">

在 Java 中，String.charAt(int index) 方法和使用数组下标访问方式（比如 str[index]）来获取字符串中的字符也有区别，但是主要的区别在于 Java 不允许使用 str[index] 这样的语法来直接访问字符串中的字符。这是因为字符串在 Java 中是通过 String 类表示的，而不是像在某些其他语言中那样直接作为字符数组来处理。       

String.charAt(int index)          
在 Java 中，要获取字符串中指定位置的字符，你需要使用 charAt(int index) 方法。这个方法返回字符串中给定位置的字符。如果索引超出范围（index 小于 0 或大于等于字符串的长度），则会抛出 StringIndexOutOfBoundsException。      

```code
String str = "Hello";
char ch = str.charAt(2); // 'l'
```

使用数组下标访问         
如果你想通过下标来访问字符串中的每个字符，你需要首先将字符串转换为字符数组。在 Java 中，可以使用 String 类的 toCharArray() 方法实现这一点，然后就可以使用数组下标来访问字符了。       

```code
String str = "Hello";
char[] chars = str.toCharArray();
char ch = chars[2]; // 'l'
```

总结       
Java 中不能直接使用 str[index] 这样的语法来访问字符串中的字符，因为 String 类型不是数组。     
要在 Java 中访问字符串的特定字符，需要使用 charAt(int index) 方法。      
如果你确实需要像访问数组那样访问字符串中的字符，可以先将字符串转换为字符数组（使用 toCharArray() 方法），然后使用数组下标访问。     
这些区别反映了 Java 对象和基本数据类型处理方式之间的一般差异，以及 Java 在设计上对字符串不可变性（String 类型是不可变的）的强调。       

<img width="881" alt="截屏2024-03-11 21 06 35" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/ac458990-a047-4a81-b9a0-08a22b1169d2">

```code
class ListNode(){
int val;
ListNode next;
public ListNode(int val){
this.val = val;
 }
}
```

<img width="881" alt="截屏2024-03-11 21 26 54" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/4cb9ccd1-0d9d-40b1-8fa0-6b07c0f7e4ac">

<img width="853" alt="截屏2024-03-11 21 34 41" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/f6b003a3-2bbb-4c95-89de-65cccb639691">
字典树是n叉树。   

<img width="872" alt="截屏2024-03-11 22 22 27" src="https://github.com/xkong-study/gucheng_algorithm/assets/100473178/f3ec1423-214a-4c63-8b19-b883aebee825">

