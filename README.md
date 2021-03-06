# javascript-study
原生javascript 的学习

## 内存空间

### 栈内存

- 存储的值 大小固定
- 空间较小
- 可以直接操作其保存的变量，运行效率高
- 由系统自动分配存储空间

### 堆内存

- 存储的值大小不定，可动态调整
- 空间较大，运行效率低
- 无法直接操作其内部存储，使用引用地址读取
- 通过代码进行分配空间

## 数据的类型

### 原始类型

- null
- undefined
- number
- string
- symbol ES6 唯一的值
- bigInt ES10

#### 特点

- 不可变性 值存放于栈内存，修改一个变量，相当于在栈内存重新开辟一处空间，并指向该空间
- 直接比较值，值相等则相等

### 对象类型

- objec

#### 特点

- 对象类型也称为引用类型，把具体的值存放在堆内存，栈中只存储了一个固定长度的地址。
- 比较引用地址，值相等，未必引用地址相等

## 值传递和引用传递

**ECMAScript 里所有的函数的参数都是按值传递**

## undefined 与Null

**null** 表示被赋值过的对象， 只是值为空

**undefined** 表示 一个变量 未赋值

**根本原因在于**：

JavaScript 是一门动态类型语言，成员除了表示存在的空值，还有可能根本就不存在（运行期才知道），这就是**undefined** 存在的意义，JAVA 强类型语言， 如有undefined 情况，会直接编译失败。

## Number类型的怪异

### 0.1+0.2 !== 0.3

- **精度丢失**

计算机中所有的数据都是以 **二进制** 存储，所以计算时，计算机要把数据先转换成 二进制 进行计算，再把结果 转换成 十进制。

然而，0.1+0.3时，二进制的计算发生精度丢失，导致再转换成 十进制 后， 与预计的结果不符合。

**更深度的探究**：

**JavaScript 对 二进制 小数的存储方式**

小数的 二进制 大多数是 无限循环的， ECMAScript中 Number类型遵循IEEE 754标准，使用固64位固定长度来表示。

若被省略的第一位是1，则末尾+1，反则省略。

## 数据类型的判断

- **typeof**

  可以判断基本类型 和function，但别的引用类型都会判定为 Object

  且 typeof null === ‘object’  // true

- **instanceof**

  判断一个引用类型具体是什么类型的对象

   **instanceof运算符**用于检测构造函数的 `prototype` 属性是否出现在某个实例对象的原型链上。

- **toString**

  Object.prototype.toString 可以判断所有数据类型。 

