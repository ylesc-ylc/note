## 一些工具
`go fmt`格式化代码，只在语法层面上更改
`god oc`生成代码文档
`go instal`安装额外的包

## 基本结构和基本数据类型

保留关键字
```go
break default func interface select case defer go map struct chan else goto package switch const fallthrough if range type continue for import return var
```

36 个预定义标识符
```go
append bool byte cap close complex complex64 complex128 copy false float32 float64 imag int int8 int16 int32 int64 iota len make new nil panic print println real recover string true uint uint8
```

类型转换
```go
valueOfTypeB = typeB(valueOfTypeA)
a := 5.0 
b := int(a)
```
`:=`是go语言的一个语法糖
`:=` 是一种简洁的变量声明和赋值语法，通常用于在函数或局部作用域中声明和初始化变量

在go语言中，赋值的值类型在变量后面
```go
var n int = 5
//变量
const n int = 5
//常量
```
就像上面那样

枚举iota
```go
const （
	a = iota
	b = iota
	c
	d
）
//一般使用形式，会从0开始进行加1赋值
```
上面只是iota简单用法

go语言中一般遵循驼峰命名法

虽然go语言的编译器能够在编译时推断变量的类型，但最好还是对变量进行显式声明

声明包级别的变量时应该使用较为完整的声明形式，但是声明函数体内的局部变量时应该使用`:=`语法糖

变量除了可以在全局声明中初始化，也可以在 init 函数中初始化。这是一类非常特殊的函数，它不能够被人为调 用，而是在每个包完成初始化后自动执行，并且执行优先级比 main 函数高。
```go
package main

import "math"

var Pi float64

func init() {
	Pi = 4 * math.Atan(1)
}
//函数一般使用方法
```


go语言的变量类型大致贴近C，逻辑运算也和C类似，不论是一元运算符还是二元运算符


go语言拥有复数
```go
complex64 //32位实数和虚数
complex128 //64位实数和虚数

//复数使用re+imi来表示
var a complex64 = 5 + 10I
//如果实数和虚数都是float32
a = complex（re， mi）

//函数
real（a） imag（a）
//分别获得相应的实数和虚数
```


按位补足//使用的符号和异或符号相同
```go
//该运算符与异或运算符一同使用，即 m^x ，对于无符号 x 使用“全部位设置为 1”，对于有符号 x 时使用 m=-1 
^2 = ^10 = -01 ^ 10 = -11
```

格式化说明符 `%c` 用于表示字符；当和字符配合使用时， `%v` 或 `%d` 会输出用于表示该字符的整数； `%U` 输出格式为 U+hhhh 的字符串

使用双引号括起来，其中的相关的转义字符将被替换，这些转义字符包括：
```go
\n ：换行符
\r ：回车符 
\t ：tab 键 
\u 或 \U ：Unicode 字符 
\\ ：反斜杠自身
```
如果不使用双引号包括，那么转义字符不会起作用

在go中，字符串可以使用`+`拼接
```go
str := "Beginning of the string " +  
	"second part of the string"
//其中+号必须写在第一行

//也可以使用
srt + = "world"
```


> strings 和 strconv 包

[[《Go 入门指南》.pdf#page=91&selection=193,4,199,1|《Go 入门指南》, 页面 91]]
上面是关于strings和strconv包的使用，是对于字符串操作的包


> 时间和日期

[[《Go 入门指南》.pdf#page=98&selection=246,0,246,5|《Go 入门指南》, 页面 98]]
go语言提供了一些可用于获得时间的函数


## 控制结构

if和else
关键字 if 和 else 之后的左大括号 { 必须和关键字在同一行，如果你使用了 else-if 结构，则前段代码块 的右大括号 } 必须和 else-if 关键字在同一行。这两条规则都是被编译器强制规定的。
```go
if x {

}
else {

}
//上面的代码无效
```

