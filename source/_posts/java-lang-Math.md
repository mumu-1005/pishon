---
title: java sdk 1.8 java.lang.Math
categories:
  - Java
tags:
  - Math
comments: false
date: 2017-08-19 14:08:06
updated: 2017-08-19 14:08:06
img:
---
### 1、求绝对值abs()
``` java
//返回double变量的绝对值
abs(double a){return the absolute value of a double value}
//返回float变量的绝对值
abs(float a){return the absolute value of a float value}
//返回int变量的绝对值
abs(int a){return the absolute value of a int value}
//返回long变量的绝对值
abs(long a){return the absolute value of long value}
```

### 2、三角函数
``` java
//返回角的反余弦,范围在 0.0 到 pi 之间。
acos(double a){return  the arc cosine of a value; the returned angle is in the range 0.0 through pi }
//返回角的反正弦，范围在 -pi/2 到 pi/2 之间。
asin(double a){return   the arc sine of a value; the returned angle is in the range -pi/2 through pi/2. }
//返回角的反正切，范围在 -pi/2 到 pi/2 之间。
atan(double a){return the arc tangent of a value; the returned angle is in the range -pi/2 through pi/2. }
//返回角的三角余弦
cos(double a){return the trigonometric cosine of an angle. }
//返回角的三角正弦
sin(double a){return the trigonometric sine of an angle. }
//返回角的三角正切
tan(double a){return the trigonometric tangent of an angle. }
```

### 3、双曲线函数
``` java
//返回double变量的双曲线余弦
cosh(double x){return the hyperbolic cosine of a double value.}
//返回double变量的双曲线正弦
sinh(double x){return the hyperbolic sine of a double value.}、
//返回double变量的双曲线正切
tanh(double x){return the hyperbolic tangent of a double value.}、
```

### 4、算术溢出处理函数
``` java
//返回两个int类型变量的求和结果,溢出处理 抛出异常ArithmeticException
addExact(int x,int y){return the sum of its arguments, throwing an exception if the result overflows a int.
//返回两个long类型变量的求和结果,溢出处理 抛出异常ArithmeticException
addExact(long x,long y){return the sum of its arguments, throwing an exception if the result overflows a long.
//返回int参数值减1，如果结果溢出，抛出例外
decrementExact(int a){return  the argument decremented by one, throwing an exception if the result overflows an int.}
//返回long参数值减1，如果结果溢出，抛出例外
decrementExact(long a){return  the argument decremented by one, throwing an exception if the result overflows an long.}
//返回int参数值加1，如果结果溢出，抛出例外
incrementExact(int a){return  the argument incremented by one, throwing an exception if the result overflows an int.}
//返回long参数值加1，如果结果溢出，抛出例外
incrementExact(long a){return  the argument incremented by one, throwing an exception if the result overflows a long.}
//返回两个数的乘积，结果溢出会抛出例外
multiplytExact(int x, int y){return  the product of the arguments, throwing an exception if the result overflows an int.}
//返回两个数的乘积，结果溢出会抛出例外
multiplyExact(long x, long y){return the product of the arguments, throwing an exception if the result overflows a long.}
//返回int参数值的相反数
negateExact(int a){return  the negation of the argument, throwing an exception if the result overflows an int.}
//返回long参数值的相反数
negateExact(long a){return the negation of the argument, throwing an exception if the result overflows a long.}
//返回两个数之差，如果溢出，抛出例外
subtractExact(int x, int y){return  the difference of the arguments, throwing an exception if the result overflows an int.}
//返回两个数之差，如果溢出，抛出例外
subtractExact(long x, long y){return  the difference of the arguments, throwing an exception if the result overflows a long.}
//长整数转换成整数，如果溢出，抛出例外
toIntExact(long value){return the value of the longargument; throwing an exception if the value overflows an int.}
```
### 5、坐标函数
``` java
//将矩形坐标转化为极坐标（r，theta）
atan2(double y, double x){return the angle theta from the conversion of rectangular coordinates (x, y) to polar coordinates (r, theta).}
```

### 6、数值运算函数
``` java 
//返回double变量的立方根
cbrt(double a){return  the cube root of a double value.}
//返回欧拉数e的double变量次幂的值
exp(double a){return "Euler's number" eraised to the power of adouble value.}
//返回ex -1
expm1(double x){return ex -1}
//返回 sqrt(x2 +y2)，没有中间溢出或下溢
hypot(double x, double y){return  sqrt(x2 +y2) without intermediate overflow or underflow.}
//按照 IEEE 754 标准的规定，对两个参数进行余数运算
IEEEremainder(double f1, double f2){Computes the remainder operation on two arguments as prescribed by the IEEE 754 standard.}
//返回（底数是 e）double 值的自然对数
log(double a){return the natural logarithm (base e) of a double value.}
//返回 double 值的底数为 10 的对数
log10(double a){Returns the base 10 logarithm of a double value.}
//返回参数与 1 的和的自然对数
log1p(double x){return  the natural logarithm of the sum of the argument and 1.}
//返回第一个参数的第二个参数次幂的值
pow(double a, double b){return  the value of the first argument raised to the power of the second argument.}
//返回带正号的 double 值，大于或等于 0.0，小于 1.0
random(){return a double value with a positive sign, greater than or equal to 0.0 and less than 1.0.}
//返回正确舍入的 double 值的正平方根
sqrt(double a){return the correctly rounded positive square root of a double value.}
//返回double表示形式中使用的无偏指数
getExponent(double d){return the unbiased exponent used in the representation of a double.}
//返回float表示形式中使用的无偏指数
getExponent(float f){return the unbiased exponent used in the representation of a float.}
//返回double 变量d乘以2的scaleFactor次幂
scalb(double d, int scaleFactor){return  d × 2scaleFactorrounded as if performed by a single correctly rounded floating-point multiply to a member of the double value set.}
//返回float变量d乘以2的scaleFactor次幂
scalb(float d, int scaleFactor){return  d × 2scaleFactorrounded as if performed by a single correctly rounded floating-point multiply to a member of the double value set.}
```

### 7、求接近值函数
``` java
//返回最小的（最接近负无穷大）double 值，该值大于或等于参数，并且等于某个整数
ceil(double a){return the smallest (closest to negative infinity) doublevalue that is greater than or equal to the argument and is equal to a mathematical integer.}
//返回最大的（最接近正无穷大）double 值，该值小于或等于参数，并且等于某个整数
floor(double a){return  the largest (closest to positive infinity) doublevalue that is less than or equal to the argument and is equal to a mathematical integer.}
//返回等于或小于代数商的最大整数值
floorDiv(long x, long y){return the largest (closest to positive infinity) longvalue that is less than or equal to the algebraic quotient.}
//返回int整数的最小模数
floorMod(int x, int y){return  the floor modulus of the int arguments.}
//返回long整数的最小模数
floorMod(long x, long y){return  the floor modulus of the long arguments.}
//返回第一个doublel类型参数的值，该值的符号使用第二个参数的符号
copySign(double magnitude, double sign){return the first floating-point argument with the sign of the second floating-point argument.}
//返回第一个float类型参数的值，该值的符号使用第二个参数的符号
copySign(float magnitude, double sign){return the first floating-point argument with the sign of the second floating-point argument.}
//返回两个参数之间和第一个参数相邻的浮点数
nextAfter(double start, double direction){return the floating-point number adjacent to the first argument in the direction of the second argument.}
//返回两个参数之间和第一个参数相邻的浮点数
nextAfter(float start, double direction){return the floating-point number adjacent to the first argument in the direction of the second argument.}
//返回参数值和负无穷大之间和参数值相邻的浮点数
nextDown(double d){return  the floating-point value adjacent to d in the direction of negative infinity.}
//返回参数值和负无穷大之间和参数值相邻的浮点数
nextDown(float f){return the floating-point value adjacent to f in the direction of negative infinity.}
//返回参数值和正无穷大之间和参数值相邻的浮点数
nextUp(double d){return  the floating-point value adjacent to d in the direction of positive infinity.}
//返回参数值和正无穷大之间和参数值相邻的浮点数
nexUp(float f){return  the floating-point value adjacent to f in the direction of positive infinity.}
//返回其值最接近参数并且是整数的 double 值
rint(double a){return the double value that is closest in value to the argument and is equal to a mathematical integer.}
```

### 8、比较函数
``` java 
//返回两个 double 值中较大的一个
max(double a, double b){return the greater of two double values.}
//返回两个 float 值中较大的一个
max(float a, float b){return the greater of two float values.}
//返回两个 int值中较大的一个
max(int a , int b){return the greater of two int values.}
//返回两个 long 值中较小的一个
max(long a , long b){return the greater of two long values.}
//返回两个 double 值中较小的一个
min(double a, double b){return the smaller of two double values.}
//返回两个 float 值中较小的一个
min(float a, float b){return the smaller of two float values.}
//返回两个 int 值中较小的一个
min(int a, int b){return the smaller of two int values.}
//返回两个 long 值中较小的一个
min(long a, long b){return the smaller of two long values.}
//返回参数的符号函数；如果参数是零则返回零；如果参数大于零，则返回 1.0；如果参数小于零，则返回 -1.0
signum(double d){return the signum function of the argument; zero if the argument is zero, 1.0 if the argument is greater than zero, -1.0 if the argument is less than zero.}
//返回参数的符号函数；如果参数是零则返回零；如果参数大于零，则返回 1.0；如果参数小于零，则返回 -1.0
signum(float f){return the signum function of the argument; zero if the argument is zero, 1.0f if the argument is greater than zero, -1.0f if the argument is less than zero.}
//返回double参数的 ulp 大小
ulp(double d){return  the size of an ulp of the argument.}
//返回float参数的 ulp 大小
ulp(float f){return the size of an ulp of the argument.}
```

### 9、角转换函数
``` java 
//将用弧度测量的角转换为近似相等的用度数测量的角
toDegrees(double angrad){converts an angle measured in radians to an approximately equivalent angle measured in degrees.}
//将用度数测量的角转换为近似相等的用弧度测量的角
toRadians(double angdeg){converts an angle measured in degrees to an approximately equivalent angle measured in radians.}
```