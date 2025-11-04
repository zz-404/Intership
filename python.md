# python基础语法

## 字面量
1. 数字
  bool Ture False
2. 字符串：
- 可以使用三个双引号“”“   ”“”来包含多行字符串
- 字符串可以相加，可以相乘
  - 例如 a*5 打印aaaaa

3. 列表
4. 元组
5. 集合
6. 字典

## 输入输出
```python
x = input("提示语")
print(type(a))
还可以把string强行转化为int
str=(int)str
★ print("the content:",content)
```
## 条件判断
```
if money >300:
    print(123)
    print(456)
print(789)
利用缩进来确定层级

if 条件：
    代码1
else:
    代码2


money = input("please input")
if money>10：
    print("yes")
else:
    print("yes")

if 条件：
    代码1
elif 条件2:
    代码2
elif 条件3：
    代码3
else:
    代码4
```
## 循环结构
```python
x=1
while x<=100:
    x++


break 让当前循环停止

for循环

for 变量 in 可迭代的东西：
把可迭代的东西的每一项内容拿出来，赋值给变量
例如：字符串可循环

for a in str:
    print(a)

for i in range(10):
    print(i)

for i in range(3,10):
    print(i)

for i in range(m,n,s):
    print(i)

从m数到n不包含n，但是每次的间隔是s

pass: 代码占位，防止报错
```

## 基础数据结构
### int,float,bool
**所有非空字符串都是True，非空列表都是ture，所有非零数都是true**
str(*****)

list(*****)

tuple(**)

set(*)

dict(*****)

bytes(****)

运算符(***)

文件操作(***)
