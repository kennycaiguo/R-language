# R-language
R语言学习资料
## 简单语法
# R语言 函数
 
R语言函数
函数是一组组合在一起以执行特定任务的语句。 R语言具有大量内置函数，用户可以创建自己的函数。 在R语言中，函数是一个对象，因此R语言解释器能够将控制传递给函数，以及函数完成动作所需的参数。 该函数依次执行其任务并将控制返回到解释器以及可以存储在其他对象中的任何结果。

函数定义
使用关键字函数创建R语言的函数。 R语言的函数定义的基本语法如下

function_name <- function(arg_1, arg_2, ...) {
   Function body
}
函数组件
函数的不同部分

函数名称 -这是函数的实际名称。 它作为具有此名称的对象存储在R环境中。
参数 -参数是一个占位符。 当函数被调用时，你传递一个值到参数。 参数是可选的; 也就是说，一个函数可能不包含参数。 参数也可以有默认值。
函数体 -函数体包含定义函数的功能的语句集合。
返回值 -函数的返回值是要评估的函数体中的最后一个表达式。
R语言有许多内置函数，可以在程序中直接调用而无需先定义它们。我们还可以创建和使用我们自己的函数，称为用户定义的函数。

内置功能
内置函数的简单示例是seq()，mean()，max()，sum(x)和paste(...)等。它们由用户编写的程序直接调用。 您可以参考最广泛使用的R函数。

# Create a sequence of numbers from 32 to 44.
print(seq(32,44))

# Find mean of numbers from 25 to 82.
print(mean(25:82))

# Find sum of numbers frm 41 to 68.
print(sum(41:68))
当我们执行上面的代码，它产生以下结果

[1] 32 33 34 35 36 37 38 39 40 41 42 43 44
[1] 53.5
[1] 1526
用户定义的函数
我们可以在R语言中创建用户定义的函数。它们特定于用户想要的，一旦创建，它们就可以像内置函数一样使用。 下面是一个创建和使用函数的例子。

# Create a function to print squares of numbers in sequence.
new.function <- function(a) {
   for(i in 1:a) {
      b <- i^2
      print(b)
   }
}
调用函数
# Create a function to print squares of numbers in sequence.
new.function <- function(a) {
   for(i in 1:a) {
      b <- i^2
      print(b)
   }
}

# Call the function new.function supplying 6 as an argument.
new.function(6)
当我们执行上面的代码，它产生以下结果

[1] 1
[1] 4
[1] 9
[1] 16
[1] 25
[1] 36
调用没有参数的函数

# Create a function without an argument.
new.function <- function() {
   for(i in 1:5) {
      print(i^2)
   }
}

# Call the function without supplying an argument.
new.function()
当我们执行上面的代码，它产生以下结果 -

[1] 1
[1] 4
[1] 9
[1] 16
[1] 25
使用参数值调用函数（按位置和名称）

函数调用的参数可以按照函数中定义的顺序提供，也可以以不同的顺序提供，但分配给参数的名称。

# Create a function with arguments.
new.function <- function(a,b,c) {
   result <- a * b + c
   print(result)
}

# Call the function by position of arguments.
new.function(5,3,11)

# Call the function by names of the arguments.
new.function(a = 11, b = 5, c = 3)
当我们执行上面的代码，它产生以下结果 -

[1] 26
[1] 58
使用默认参数调用函数

我们可以在函数定义中定义参数的值，并调用函数而不提供任何参数以获取默认结果。 但是我们也可以通过提供参数的新值来获得非默认结果来调用这样的函数。

# Create a function with arguments.
new.function <- function(a = 3, b = 6) {
   result <- a * b
   print(result)
}

# Call the function without giving any argument.
new.function()

# Call the function with giving new values of the argument.
new.function(9,5)
当我们执行上面的代码，它产生以下结果 -

[1] 18
[1] 45
功能的延迟计算

对函数的参数进行延迟评估，这意味着它们只有在函数体需要时才进行评估。

# Create a function with arguments.
new.function <- function(a, b) {
   print(a^2)
   print(a)
   print(b)
}

# Evaluate the function without supplying one of the arguments.
new.function(6)
当我们执行上面的代码，它产生以下结果

[1] 36
[1] 6
Error in print(b) : argument "b" is missing, with no default
*************************************************************************************************************************************

# R语言 数据类型
R语言 基本语法R语言 变量
R语言数据类型
通常，在使用任何编程语言进行编程时，您需要使用各种变量来存储各种信息。 变量只是保留值的存储位置。 这意味着，当你创建一个变量，你必须在内存中保留一些空间来存储它们。
您可能想存储各种数据类型的信息，如字符，宽字符，整数，浮点，双浮点，布尔等。基于变量的数据类型，操作系统分配内存并决定什么可以存储在保留内存中。
与其他编程语言（如C中的C和java）相反，变量不会声明为某种数据类型。 变量分配有R对象，R对象的数据类型变为变量的数据类型。尽管有很多类型的R对象，但经常使用的是：

矢量
列表
矩阵
数组
因子
数据帧
这些对象中最简单的是向量对象，并且这些原子向量有六种数据类型，也称为六类向量。 其他R对象建立在原子向量之上。

数据类型	例	校验
Logical（逻辑型）	TRUE, FALSE	
v <- TRUE
print(class(v))
它产生以下结果 -

[1] "logical"
Numeric（数字）	12.3，5，999	
v <- 23.5
print(class(v))
它产生以下结果 -

[1] "numeric"
Integer（整型）	2L，34L，0L	
v <- 2L
print(class(v))
它产生以下结果 -

[1] "integer"
Complex（复合型）	3 + 2i	
v <- 2+5i
print(class(v))
它产生以下结果 -

[1] "complex"
Character（字符）	'a' , '"good", "TRUE", '23.4'	
v <- "TRUE"
print(class(v))
它产生以下结果 -

[1] "character"
Raw（原型）	"Hello" 被存储为 48 65 6c 6c 6f	
v <- charToRaw("Hello")
print(class(v))
它产生以下结果 -

[1] "raw"
在R编程中，非常基本的数据类型是称为向量的R对象，其保存如上所示的不同类的元素。 请注意，在R中，类的数量不仅限于上述六种类型。 例如，我们可以使用许多原子向量并创建一个数组，其类将成为数组。

Vectors 向量
当你想用多个元素创建向量时，你应该使用c()函数，这意味着将元素组合成一个向量。

# Create a vector.
apple <- c('red','green',"yellow")
print(apple)

# Get the class of the vector.
print(class(apple))
当我们执行上面的代码，它产生以下结果

[1] "red"    "green"  "yellow"
[1] "character"
Lists 列表
列表是一个R对象，它可以在其中包含许多不同类型的元素，如向量，函数甚至其中的另一个列表。

# Create a list.
list1 <- list(c(2,5,3),21.3,sin)

# Print the list.
print(list1)
当我们执行上面的代码，它产生以下结果

[[1]]
[1] 2 5 3

[[2]]
[1] 21.3

[[3]]
function (x)  .Primitive("sin")
Matrices 矩阵
矩阵是二维矩形数据集。 它可以使用矩阵函数的向量输入创建。

# Create a matrix.
M = matrix( c('a','a','b','c','b','a'), nrow = 2, ncol = 3, byrow = TRUE)
print(M)
当我们执行上面的代码，它产生以下结果

[,1] [,2] [,3]
[1,] "a"  "a"  "b"
[2,] "c"  "b"  "a"
Arrays 数组
虽然矩阵被限制为二维，但阵列可以具有任何数量的维度。 数组函数使用一个dim属性创建所需的维数。 在下面的例子中，我们创建了一个包含两个元素的数组，每个元素为3x3个矩阵。

# Create an array.
a <- array(c('green','yellow'),dim = c(3,3,2))
print(a)
当我们执行上面的代码，它产生以下结果

, , 1

     [,1]     [,2]     [,3]    
[1,] "green"  "yellow" "green"
[2,] "yellow" "green"  "yellow"
[3,] "green"  "yellow" "green"

, , 2

     [,1]     [,2]     [,3]    
[1,] "yellow" "green"  "yellow"
[2,] "green"  "yellow" "green"
[3,] "yellow" "green"  "yellow"
Factors 因子
因子是使用向量创建的r对象。 它将向量与向量中元素的不同值一起存储为标签。 标签总是字符，不管它在输入向量中是数字还是字符或布尔等。 它们在统计建模中非常有用。 使用factor()函数创建因子。nlevels函数给出级别计数。

# Create a vector.
apple_colors <- c('green','green','yellow','red','red','red','green')

# Create a factor object.
factor_apple <- factor(apple_colors)

# Print the factor.
print(factor_apple)
print(nlevels(factor_apple))
当我们执行上面的代码，它产生以下结果

[1] green  green  yellow red    red    red    yellow green
Levels: green red yellow
# applying the nlevels function we can know the number of distinct values
[1] 3
Data Frames 数据帧
数据帧是表格数据对象。 与数据帧中的矩阵不同，每列可以包含不同的数据模式。 第一列可以是数字，而第二列可以是字符，第三列可以是逻辑的。 它是等长度的向量的列表。 使用data.frame()函数创建数据帧。

# Create the data frame.
BMI <-  data.frame(
   gender = c("Male", "Male","Female"),
   height = c(152, 171.5, 165),
   weight = c(81,93, 78),
   Age = c(42,38,26)
)
print(BMI)
当我们执行上面的代码，它产生以下结果

gender height weight Age
1   Male  152.0     81  42
2   Male  171.5     93  38
3 Female  165.0     78  26

***************************************************************************************************************************************

# R语言变量
变量为我们提供了我们的程序可以操作的命名存储。 R语言中的变量可以存储原子向量，原子向量组或许多Robject的组合。 有效的变量名称由字母，数字和点或下划线字符组成。 变量名以字母或不以数字后跟的点开头。

变量名	合法性	原因
var_name2.	有效	有字母，数字，点和下划线
VAR_NAME％	无效	有字符'％'。只有点(.)和下划线允许的。
2var_name	无效	以数字开头
.var_name,
var.name	有效	可以用一个点(.)，但启动点(.)，不应该后跟一个数字。
.2var_name	无效	起始点后面是数字使其无效。
`_`var_name	无效	开头_这是无效的
变量赋值
可以使用向左，向右和等于运算符来为变量分配值。 可以使用print()或cat()函数打印变量的值。 cat()函数将多个项目组合成连续打印输出。

# Assignment using equal operator.
var.1 = c(0,1,2,3)           

# Assignment using leftward operator.
var.2 <- c("learn","R")   

# Assignment using rightward operator.   
c(TRUE,1) -> var.3           

print(var.1)
cat ("var.1 is ", var.1 ,"
")
cat ("var.2 is ", var.2 ,"
")
cat ("var.3 is ", var.3 ,"
")
当我们执行上面的代码，它产生以下结果 -

[1] 0 1 2 3
var.1 is  0 1 2 3
var.2 is  learn R
var.3 is  1 1
注 - 向量c（TRUE，1）具有逻辑和数值类的混合。 因此，逻辑类强制转换为数字类，使TRUE为1。

变量的数据类型
在R语言中，变量本身没有声明任何数据类型，而是获取分配给它的R - 对象的数据类型。 所以R称为动态类型语言，这意味着我们可以在程序中使用同一个变量时，一次又一次地更改变量的数据类型。

var_x <- "Hello"
cat("The class of var_x is ",class(var_x),"
")

var_x <- 34.5
cat("  Now the class of var_x is ",class(var_x),"
")

var_x <- 27L
cat("   Next the class of var_x becomes ",class(var_x),"
")
当我们执行上面的代码，它产生以下结果 -

The class of var_x is  character
   Now the class of var_x is  numeric
      Next the class of var_x becomes  integer
查找变量
要知道工作空间中当前可用的所有变量，我们使用ls()函数。 ls()函数也可以使用模式来匹配变量名。

print(ls())
当我们执行上面的代码，它产生以下结果 -

[1] "my var"     "my_new_var" "my_var"     "var.1"      
[5] "var.2"      "var.3"      "var.name"   "var_name2."
[9] "var_x"      "varname"
注意 - 它是一个示例输出，取决于在您的环境中声明的变量。

ls()函数可以使用模式来匹配变量名。

# List the variables starting with the pattern "var".
print(ls(pattern = "var"))
当我们执行上面的代码，它产生以下结果

[1] "my var"     "my_new_var" "my_var"     "var.1"      
[5] "var.2"      "var.3"      "var.name"   "var_name2."
[9] "var_x"      "varname"
以点(.)开头的变量被隐藏，它们可以使用ls()函数的“all.names = TRUE”参数列出。 print(ls(all.name = TRUE)) 当我们执行上面的代码，它产生以下结果

[1] ".cars"        ".Random.seed" ".var_name"    ".varname"     ".varname2"   
[6] "my var"       "my_new_var"   "my_var"       "var.1"        "var.2"        
[11]"var.3"        "var.name"     "var_name2."   "var_x"
删除变量
可以使用rm()函数删除变量。 下面我们删除变量var.3。 打印时，抛出变量错误的值。

rm(var.3)
print(var.3)
当我们执行上面的代码，它产生以下结果

[1] "var.3"
Error in print(var.3) : object 'var.3' not found
所有的变量可以通过使用rm()和ls()函数一起删除。

rm(list = ls())
print(ls())
当我们执行上面的代码，它产生以下结果

character(0)
***************************************************************************************************************************************

# R语言运算符
运算符是一个符号，通知编译器执行特定的数学或逻辑操作。 R语言具有丰富的内置运算符，并提供以下类型的运算符。

运算符的类型
R语言中拥有如下几种运算符类型：

算术运算符
关系运算符
逻辑运算符
赋值运算符
其他运算符
算术运算符
下表显示了R语言支持的算术运算符。 操作符对向量的每个元素起作用。

运算符	描述	例
+	两个向量相加	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v+t)
它产生以下结果 -

10.0  8.5  10.0
-	两个向量相减	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v-t)
它产生以下结果 -

-6.0  2.5  2.0
`*`	两个向量相乘	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v*t)
它产生以下结果 -

16.0 16.5 24.0
/	将第一个向量与第二个向量相除	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v/t)
当我们执行上面的代码，它产生以下结果 -

0.250000 1.833333 1.500000
%%	两个向量求余	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v%%t)
它产生以下结果 -

[1] 2.0 2.5 2.0
％/％	两个向量相除求商	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v%/%t)
它产生以下结果 -

[1] 0 1 1
^	将第二向量作为第一向量的指数	
v <- c( 2,5.5,6)
t <- c(8, 3, 4)
print(v^t)
它产生以下结果 -

[1]  256.000  166.375 1296.000
关系运算符
下表显示了R语言支持的关系运算符。 将第一向量的每个元素与第二向量的相应元素进行比较。 比较的结果是布尔值。

运算符	描述	例
>	检查第一向量的每个元素是否大于第二向量的相应元素。	
v <- c(2,5.5,6,9)
t <- c(8,2.5,14,9)
print(v>t)
它产生以下结果 -

FALSE  TRUE FALSE FALSE
<	检查第一个向量的每个元素是否小于第二个向量的相应元素。	
v <- c(2,5.5,6,9)
t <- c(8,2.5,14,9)
print(v < t)
它产生以下结果 -

TRUE FALSE  TRUE FALSE
==	检查第一个向量的每个元素是否等于第二个向量的相应元素。	
v <- c(2,5.5,6,9)
t <- c(8,2.5,14,9)
print(v == t)
它产生以下结果 -

FALSE FALSE FALSE  TRUE
<=	检查第一向量的每个元素是否小于或等于第二向量的相应元素。	
v <- c(2,5.5,6,9)
t <- c(8,2.5,14,9)
print(v<=t)
它产生以下结果 -

TRUE FALSE  TRUE  TRUE
> =	检查第一向量的每个元素是否大于或等于第二向量的相应元素。	
v <- c(2,5.5,6,9)
t <- c(8,2.5,14,9)
print(v>=t)
它产生以下结果 -

FALSE  TRUE FALSE  TRUE
!=	检查第一个向量的每个元素是否不等于第二个向量的相应元素。	
v <- c(2,5.5,6,9)
t <- c(8,2.5,14,9)
print(v!=t)
它产生以下结果 -

TRUE  TRUE  TRUE FALSE
逻辑运算符
下表显示了R语言支持的逻辑运算符。 它只适用于逻辑，数字或复杂类型的向量。 所有大于1的数字被认为是逻辑值TRUE。 将第一向量的每个元素与第二向量的相应元素进行比较。 比较的结果是布尔值。

运算符	描述	例
&	它被称为元素逻辑AND运算符。 它将第一向量的每个元素与第二向量的相应元素组合，并且如果两个元素都为TRUE，则给出输出TRUE。	
v <- c(3,1,TRUE,2+3i)
t <- c(4,1,FALSE,2+3i)
print(v&t)
它产生以下结果 -

TRUE  TRUE FALSE  TRUE
|	它被称为元素逻辑或运算符。 它将第一向量的每个元素与第二向量的相应元素组合，并且如果元素为真，则给出输出TRUE。	
v <- c(3,0,TRUE,2+2i)
t <- c(4,0,FALSE,2+3i)
print(v|t)
它产生以下结果 -

TRUE FALSE  TRUE  TRUE
!	它被称为逻辑非运算符。 取得向量的每个元素，并给出相反的逻辑值。	
v <- c(3,0,TRUE,2+2i)
print(!v)
它产生以下结果 -

FALSE  TRUE FALSE FALSE
逻辑运算符&&和|| 只考虑向量的第一个元素，给出单个元素的向量作为输出。

运算符	描述	例
&&	称为逻辑AND运算符。 取两个向量的第一个元素，并且只有两个都为TRUE时才给出TRUE。	
v <- c(3,0,TRUE,2+2i)
t <- c(1,3,TRUE,2+3i)
print(v&&t)
它产生以下结果 -

TRUE
||	称为逻辑OR运算符。 取两个向量的第一个元素，如果其中一个为TRUE，则给出TRUE。	
v <- c(0,0,TRUE,2+2i)
t <- c(0,3,TRUE,2+3i)
print(v||t)
它产生以下结果 -

FALSE
赋值运算符
这些运算符用于向向量赋值。

运算符	描述	例
<−

or

=

or

<<−

称为左分配	
v1 <- c(3,1,TRUE,2+3i)
v2 <<- c(3,1,TRUE,2+3i)
v3 = c(3,1,TRUE,2+3i)
print(v1)
print(v2)
print(v3)
它产生以下结果 -

3+0i 1+0i 1+0i 2+3i
3+0i 1+0i 1+0i 2+3i
3+0i 1+0i 1+0i 2+3i
->

or

->>

称为右分配	
c(3,1,TRUE,2+3i) -> v1
c(3,1,TRUE,2+3i) ->> v2
print(v1)
print(v2)
它产生以下结果 -

3+0i 1+0i 1+0i 2+3i
3+0i 1+0i 1+0i 2+3i
其他运算符
这些运算符用于特定目的，而不是一般的数学或逻辑计算。

运算符	描述	例
:	冒号运算符。 它为向量按顺序创建一系列数字。	
v <- 2:8
print(v)
它产生以下结果 -

2 3 4 5 6 7 8
%in%	此运算符用于标识元素是否属于向量。	
v1 <- 8
v2 <- 12
t <- 1:10
print(v1 %in% t)
print(v2 %in% t)
它产生以下结果 -

TRUE
FALSE
%*%	此运算符用于将矩阵与其转置相乘。	
M = matrix( c(2,6,5,1,10,4), nrow = 2,ncol = 3,byrow = TRUE)
t = M %*% t(M)
print(t)
它产生以下结果 -

      [,1] [,2]
[1,]   65   82
[2,]   82  117

**************************************************************************************************************************************
# R语言判断
决策结构要求程序员指定要由程序评估或测试的一个或多个条件，以及如果条件被确定为真则要执行的一个或多个语句，如果条件为假则执行其他语句。 以下是在大多数编程语言中的典型决策结构的一般形式



R提供以下类型的决策语句。 单击以下链接以检查其详细信息。

Sr.No.	声明和描述
1	if语句
if语句由一个布尔表达式后跟一个或多个语句组成。

2	if ... else语句
if语句后面可以有一个可选的else语句，当布尔表达式为false时执行。

3	switch语句
switch语句允许根据值列表测试变量的相等性。

if语句
if语句由一个布尔表达式后跟一个或多个语句组成。

语法
在R中创建if语句的基本语法是

if(boolean_expression) {
   // statement(s) will execute if the boolean expression is true.
}
如果布尔表达式的计算结果为true，那么if语句中的代码块将被执行。 如果布尔表达式的计算结果为false，那么第一组代码在if语句结束之后（在结束大括号之后）将被执行。

流程图
r if

例
x <- 30L
if(is.integer(x)) {
   print("X is an Integer")
}
当上面的代码被编译和执行时，它产生以下结果

[1] "X is an Integer"
If...Else语句
if语句后面可以是一个可选的else语句，当布尔表达式为false时执行。

语法
在R中创建if ... else语句的基本语法是 -

if(boolean_expression) {
   // statement(s) will execute if the boolean expression is true.
} else {
   // statement(s) will execute if the boolean expression is false.
}
如果布尔表达式的计算结果为真，则将执行if代码块，否则将执行代码块。

流程图
r if else

例
x <- c("what","is","truth")

if("Truth" %in% x) {
   print("Truth is found")
} else {
   print("Truth is not found")
}
当上面的代码被编译和执行时，它产生以下结果

[1] "Truth is not found"
这里“Truth”和“truth”是两个不同的字符串。

if ... else if ... else语句
if语句后面可以跟一个可选的else if ... else语句，这对于使用single if ... else if语句测试各种条件非常有用。

当使用if，else if，else语句有几点要记住。

如果可以有零或一个else，它必须在任何其他if之后。
一个if可以有0到许多else if和它们必须在else之前。
一旦一个else如果成功，没有任何剩余的else if或else将被测试。
语法
在R中创建if ... else if ... else语句的基本语法是 -

if(boolean_expression 1) {
   // Executes when the boolean expression 1 is true.
} else if( boolean_expression 2) {
   // Executes when the boolean expression 2 is true.
} else if( boolean_expression 3) {
   // Executes when the boolean expression 3 is true.
} else {
   // executes when none of the above condition is true.
}
例
x <- c("what","is","truth")

if("Truth" %in% x) {
   print("Truth is found the first time")
} else if ("truth" %in% x) {
   print("truth is found the second time")
} else {
   print("No truth found")
}
当上面的代码被编译和执行时，它产生以下结果

[1] "truth is found the second time"
Switch语句
switch语句允许根据值列表测试变量的相等性。 每个值都称为大小写，并且针对每种情况检查打开的变量。

语法
在R中创建switch语句的基本语法是

switch(expression, case1, case2, case3....)
以下规则适用于switch语句：

如果expression的值不是字符串，那么它被强制为整数。
在交换机中可以有任意数量的case语句。 每个案例后面都跟要比较的值和冒号。
如果整数的值在1和nargs() - 1（参数的最大数目）之间，则对case条件的相应元素求值并返回结果。
如果表达式求值为字符串，那么该字符串与元素的名称匹配。
如果有多个匹配，则返回第一个匹配元素。
无默认参数可用。
在没有匹配的情况下，如果有一个未命名的元素...它的值被返回。 （如果有多个这样的参数，则返回错误。）
流程图
r switch

例
x <- switch(
   3,
   "first",
   "second",
   "third",
   "fourth"
)
print(x)
当上面的代码被编译和执行时，它产生以下结果

[1] "third"

***************************************************************************************************************************************
# R语言包
R语言的包是R函数，编译代码和样本数据的集合。 它们存储在R语言环境中名为“library”的目录下。 默认情况下，R语言在安装期间安装一组软件包。 随后添加更多包，当它们用于某些特定目的时。 当我们启动R语言控制台时，默认情况下只有默认包可用。 已经安装的其他软件包必须显式加载以供将要使用它们的R语言程序使用。
所有可用的R语言包都列在R语言的包。
下面是用于检查，验证和使用R包的命令列表。

检查可用R语言的包
获取包含R包的库位置

.libPaths()
当我们执行上面的代码，它产生以下结果。 它可能会根据您的电脑的本地设置而有所不同。

[2] "C:/Program Files/R/R-3.2.2/library"
获取已安装的所有软件包列表
library()
当我们执行上面的代码，它产生以下结果。 它可能会根据您的电脑的本地设置而有所不同。

Packages in library ‘C:/Program Files/R/R-3.2.2/library’:

base                    The R Base Package
boot                    Bootstrap Functions (Originally by Angelo Canty
                        for S)
class                   Functions for Classification
cluster                 "Finding Groups in Data": Cluster Analysis
                        Extended Rousseeuw et al.
codetools               Code Analysis Tools for R
compiler                The R Compiler Package
获取当前在R环境中加载的所有包

search()
当我们执行上述代码时，它产生了以下结果。它会根据你的个人电脑的本地设置而异。

[1] ".GlobalEnv"        "package:stats"     "package:graphics"
[4] "package:grDevices" "package:utils"     "package:datasets"
[7] "package:methods"   "Autoloads"         "package:base"
安装一个新的软件包
有两种方法来添加新的R包。 一个是直接从CRAN目录安装，另一个是将软件包下载到本地系统并手动安装它。

直接从CRAN安装

以下命令直接从CRAN网页获取软件包，并将软件包安装在R环境中。 可能会提示您选择最近的镜像。 根据您的位置选择一个。

安装一个新的软件包

有两种方法来添加新的R包。 一个是直接从CRAN目录安装，另一个是将软件包下载到本地系统并手动安装它。
直接从CRAN安装

以下命令直接从CRAN网页获取软件包，并将软件包安装在R环境中。 可能会提示您选择最近的镜像。 根据您的位置选择一个。
手动安装包

转到链接R Packages下载所需的包。 将包作为.zip文件保存在本地系统中的适当位置。
现在您可以运行以下命令在R环境中安装此软件包。

install.packages(file_name_with_path, repos = NULL, type = "source")

# Install the package named "XML"
install.packages("E:/XML_3.98-1.3.zip", repos = NULL, type = "source")
装载包到库中
在包可以在代码中使用之前，必须将其加载到当前R环境中。 您还需要加载先前已安装但在当前环境中不可用的软件包。
使用以下命令加载包：

library("package Name", lib.loc = "path to library")

# Load the package named "XML"
install.packages("E:/XML_3.98-1.3.zip", repos = NULL, type = "source")

****************************************************************************************************************************************
# R语言循环
可能有一种情况，当你需要执行一段代码几次。 通常，顺序执行语句。 首先执行函数中的第一个语句，然后执行第二个语句，依此类推。
编程语言提供允许更复杂的执行路径的各种控制结构。
循环语句允许我们多次执行一个语句或一组语句，以下是大多数编程语言中循环语句的一般形式



R编程语言提供以下种类的循环来处理循环需求。 单击以下链接以检查其详细信息。

Sr.No.	循环类型和描述
1	repeat循环
多次执行一系列语句，并简化管理循环变量的代码。

2	while循环
在给定条件为真时，重复语句或语句组。 它在执行循环体之前测试条件。

3	for循环
像while语句，不同之处在于它测试在循环体的端部的条件。

R语言 Repeat循环
Repeat循环重复执行相同的代码，直到满足停止条件。

语法
在R中创建Repeat循环的基本语法是

repeat {
   commands
   if(condition) {
      break
   }
}
流程图
r repeat

例
v <- c("Hello","loop")
cnt <- 2

repeat {
   print(v)
   cnt <- cnt+1

   if(cnt > 5) {
      break
   }
}
当上面的代码被编译和执行时，它产生以下结果

[1] "Hello" "loop"
[1] "Hello" "loop"
[1] "Hello" "loop"
[1] "Hello" "loop"
R语言 While循环
While循环一次又一次地执行相同的代码，直到满足停止条件。

语法
在R中创建while循环的基本语法是

while (test_expression) {
   statement
}
流程图
r while

while循环的关键点是循环可能永远不会运行。 当条件被测试并且结果为false时，循环体将被跳过，while循环之后的第一条语句将被执行。

例
v <- c("Hello","while loop")
cnt <- 2

while (cnt < 7) {
   print(v)
   cnt = cnt + 1
}
当上面的代码被编译和执行时，它产生以下结果

[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
[1] "Hello"  "while loop"
R语言 For循环
For循环是一种重复控制结构，允许您有效地编写需要执行特定次数的循环。

语法
在R中创建一个for循环语句的基本语法是

for (test_expression) {
   statement
}
流程图
r for

R的for循环是特别灵活的，因为它们不限于整数，或者输入中的偶数。 我们可以传递字符向量，逻辑向量，列表或表达式。

例
v <- LETTERS[1:4]
for ( i in v) {
   print(i)
}
当上面的代码被编译和执行时，它产生以下结果

[1] "A"
[1] "B"
[1] "C"
[1] "D"
循环控制语句
循环控制语句从其正常序列改变执行。 当执行离开作用域时，在该作用域中创建的所有自动对象都将被销毁。
R语言支持以下控制语句。 单击以下链接以检查其详细信息。

Sr.No.	控制语句和描述
1	break语句
终止循环语句，并将执行转移到循环后立即执行的语句。

2	next语句
next语句模拟R语言switch语句的行为。

break语句
R语言中的break语句有以下两种用法：

当在循环中遇到break语句时，循环立即终止，并且程序控制在循环之后的下一语句处恢复。 它可以用于终止switch语句中的情况（在下一章中讨论）。

语法
在R中创建break语句的基本语法是

break
流程图
r break

例
v <- c("Hello","loop")
cnt <- 2

repeat {
   print(v)
   cnt <- cnt + 1

   if(cnt > 5) {
      break
   }
}
当上面的代码被编译和执行时，它产生以下结果

[1] "Hello" "loop"
[1] "Hello" "loop"
[1] "Hello" "loop"
[1] "Hello" "loop"
next语句
R语言存在next语句，当我们想跳过循环的当前迭代而不终止它时便可使用next。 遇到next时，R解析器跳过本次迭代，并开始循环的下一次迭代。

语法
在R中创建Next语句的基本语法是

next
流程图
r next

例
v <- LETTERS[1:6]
for ( i in v) {

   if (i == "D") {
      next
   }
   print(i)
}
当上面的代码被编译和执行时，它产生以下结果

[1] "A"
[1] "B"
[1] "C"
[1] "E"
[1] "F"

# 更多语法，查看http://codingdict.com/article/2830

 
