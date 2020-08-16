本章主要介绍了学习一门编程语言应该从哪些方面进行学习。

# 1 变量

在大部分的编程语言中都存在变量这一个概念。在程序中我们使用变量来表示我们要处理的某一个数据。例如我们想要使用程序表达这么一句话：“张三是清华大学的一名学生，今年20岁了”。

```python
name = "zhangsan"
school = "清华大学"
role = "student"
age = 20
```

上面的Python代码中的`name`, `school`, `role`, `age`就是变量。一个变量应该是有类型的，并且应该被赋值。

## 1.1 变量的类型

**基础类型**有数值，字符串，bool等;在基础类型的基础上每种语言会扩展出不同的**复合类型**。例如c语言中的array, struct, union; Python语言的list，tupe，dict, set; Go语言的struct, array, slice, map等

为什么要有数据类型呢？因为我们现实中处理的数据基本上就是数字和字符串, 使用数字我们能够定量的描述一个东西或者一件事情，使用字符串我们能够形象的描述。

## 1.2 变量的定义

知道了变量是具有类型的这一概念之后，我们来看一下如何定义一个变量。变量的定义实际是分为两个过程的：变量的声明和变量的赋值。变量的声明相当于给某个变量在内存中开辟一块内存空间，变量的赋值相当于在开辟的这个内存空间中放入我们希望的值。在不同的语言中，定义一个变量的语法是不同的，在有些编程语言中，变量在使用前必须先声明，而在有些语言中则不必如此，以在直接使用。下面就几种编程语言编码说明一下变量的定义和使用。

变量定义的三个要素：变量类型，变量名，变量的值。

C语言中如下：
```c
# incdlude <stdio.h>
// 在C语言中使用必须先声明一个变量
int main(int argcm, char *argv[]) 
{
    char *name = "xiaolele";  // 或者分开：char *name; name = "xiaolele";
    printf("%s\n", name);
}
```

Python中如下：

```python
# Python中变量的定义和使用，无需事先声明，也无需指明类型
def main():
    name = "xiaolele"
    printf(name)

if __name__ == "__main__":
    main()
```

Go语言中如下：

```go
package main

import "fmt"

func main() {
    // 方式1
    var name string   // 先声明变量
    name = "xiaolele" // 再赋值
    fmt.Println(name)

    // 方式2
    name := "xiaolele"  // 声明和赋值同时进行，但是无需指明类型，go语言会自动类型推导
    fmt.Println(name)
}
```

Java中如下：

```java
package com.xiaolele.demo;

public class Main {
    public static void main(String[] args) {
        String name = "xiaolele";
        System.out.println(name);
    }
}
```

JavaScript中如下：

```js
// 使用var关键字
var name = "xiaolele";
console.log(name);

// 使用let关键字
let name = "xiaolele";
console.log(name);
```

# 2 逻辑控制

## 2.1 条件控制语句

if-else

switch-case

## 2.2 循环控制语句

while 

for

# 3 函数

函数就是一段封装了指定功能的代码片段，目的是为了复用。

## 3.1 函数的定义

函数定义的三要素：函数名、参数、返回值，其中函数的入参和返回值决定了函数的类型

```c
// 函数名为add
// 入参有两个，类型都是int
// 返回值是int
int add (int a, int b) 
{
    return a + b;
}
```

```python
def add(a, b):
    return a + b
```

```go
func add(a, b int) int {
    return a + b
}
```

```java
package com.xiaolele.demo;

public class Main {
    public int add(int a, int b) {
        return a + b;
    }
}
```

```js
function add (a, b) {
    return a + b;
}
```

# 4 面向对象

因为C语言是面向过程的语言，在本节不讨论C语言。

用类来封装现实中的物体。封装类的三要素：成员变量，成员方法，成员变量和方法的属性（私有或者公有）。在成员方法中有一个特殊的函数称为**构造函数**。公有和私有指的是类外不可见，只在类内部是可见的，在go中可见性是对包而言的。

构造函数是为了给对象的属性赋初值。

## 4.1 成员变量

成员变量用来描述对象的属性。如何定义成员的属性，不同的语言有不同的表示方法。在Python中使用`_`来表示成员变量的属性。在java中是通过`private`和`public`这种关键字来表示。在Go语言中通过成员变量的首字母的大小写来表示成员变量的属性。

## 4.2 成员方法

成员方法用来描述对象的行为。

## 4.3 示例代码

```python
class Person:
    # 构造函数
    def __init__(self, name, age):
        # 成员变量
        self._name = name
        self._age = age
    
    # 成员方法
    def eat(self):
        print(self._name, self._age, "吃东西")
```
Java中的面向对象
```java
package com.xiaolele.demo;

class Person {
    // 成员变量
    private String name;
    private int age;

    // 构造函数
    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }
    // 成员方法
    public void eat() {
        System.out.println(this.name + this.age + "吃东西")
    }
}
```
go语言中的面向对象，其中go语言的面向对象是无侵入的，所谓的无侵入就是如果我们已经将一个类封装好了之后，如果我们想要给这个类添加一个新的方法，如果在java中我们需要使用extend继成一个新的类，或者直接修改已经封装好的类；但是在go中我们直接添加一个函数就可以，为此称为无侵入的。
```go
package person

type Person struct {
    name string
    age  int 
}

func (p *Person) eat() {
    fmt.Println(p.Name, p.Age, "吃东西")
}
```