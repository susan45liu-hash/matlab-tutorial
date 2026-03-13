# Chapter 1 MATLAB Basics

## 1.1 MATLAB Environment
### 1.1.1 MATLAB Execution Order / Search Path:
```mermaid
flowchart LR
A[Variable 变量] --> B[Built-in Function 内部函数]
B --> C[Program File 程序文件]
C --> D[Current Folder 当前文件夹]
C --> E[Search Path 搜索路径文件夹]
```
## 1.2 Numerical Data
### 1.2.1 Classification of numeric data types: Integer, floating-point, complex number
#### Function — to find the signed 8-digit integer format of a given decimal number: 
`int8`, `uint8`

`int16`, `uint16`

`int32`, `uint32`

`int64`, `uint64`

```matlab
x=int8(129) 
x =
127
```
```matlab
x=uint8(129)
x =
129
```
#### Functions to convert other data types to ...⭐matlab default: double
`single`-precision/`double`-precision floating-point data.
>> class(4)
   ans =
   double
>> class(single(4))
   ans =
   single
#### Both the real and imaginary parts of complex data are assumed to be double-precision type.
The imaginary（虚部） unit is represented by i or j.

Function `real`: Calculates the real part of a complex number.

Function `imag`: Calculates the imaginary part of a complex number.

```matlab
6+5i
ans =
6.0000 + 5.0000i
```
```matlab
6+5j
ans =
6.0000 +5.0000i
```
### 1.2.2 Output format of numerical data
format + 格式符format specifier

The `format` command only affects the output format of data; 

it does not affect data calculation or storage.
```matlab
>> format long
>> 50/3
  ans =
  16.666666666666668
```
```matlab
>> format
>> 50/3
  ans =
  16.6667
```
### 1.2.3 Commonly used mathematical functions
#### The function call format is as follows:
Function name (value)

During the operation, the function is applied to each element of the matrix, so the result is still a matrix.
#### Changes in common functions
1. Trigonometric functions.

In radians（弧度）: `sin()`

In degrees（角度）: `sind()`
```matlab
>>sin(pi/2)
ans =
     1
```
```matlab
>>sind(90)
ans =
     1
```
2. The `abs` function can calculate:

the absolute value of a real number（实数的绝对值）,

the modulus of a complex number（复数的模）, and the

ASCII code value of a string（字符串的ASCII码值）.
```matlab
>>abs(-4)
ans =
     4
```
```matlab
>>abs(3+4i)
ans =
     5
```
```matlab
>>abs('a)
ans =
     97
```
#### Take the integer
Truncate/Floor`floor()`: Remove the decimal part directly.
```matlab
>>floor(3.6)
ans =
     3
```
Rounding`round()`: to the nearest whole number.
```matlab
>>round(4.6)
ans =
     5
```
Ceiling`ceil()`: Carry over if there is a decimal.
```matlab
>>ceil(-3.6)
ans =
     -3
```
`fix`: Regardless of the sign, always take the integer closest to 0.
```matlab
>>fix(-3.6)
ans =
     -3
```
## 1.3 Variables and Operations

## 1.4 Matrix Representation

## 1.5 Accessing Matrix Elements

## 1.6 Basic Operations

## 1.7 String Processing
