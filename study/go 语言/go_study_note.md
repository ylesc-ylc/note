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

