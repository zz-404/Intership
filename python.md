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

前闭后开区间 ，从m数到n不包含n，但是每次的间隔是s

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

# 字符串
```python
在 Python 中，单引号（' '）和双引号（" "）在表示字符串时没有本质区别，
它们可以完全互换使用，表示的数据类型都是 str。
# 1. 字符串的格式化问题

name =input("请输入你的名字")
add=input("请输入你的住址")
age=int(input("请输入你的年龄"))

# %s 字符串占位
# %d 占位数字
s="我叫%s,我的住址%s,my age %d" % (name,add,age)
print(s)

s1="我叫{},我的住址{},my age {}".format(name,add,age)
print(s1)

s2=f"我叫{name},我的住址{add}，myage{age}" # fstring 更简单更方便
print(s2)

# 2.索引和切片
# 索引：按照某一个位置提取元素
s="我叫周杰伦"
#可以采用索引的方式提取某一个字符
print(s[3])
print(s[-1]) # 符号表示倒数 -1 倒数第一

#切片 提取一部分内容
s= "我叫周杰伦，你呢，你叫周润发吗"
print(s[3:6]) # 从索引3位置进行切片，切到6结束，不包含索引6

print(s[:1]) # 从开始开始切片，前面的数可以省略
print(s[1:]) # 截取到末尾，后面的数也可以省略

print(s[-3:-1]) # 从倒数第三个到倒数第一个

# 注意print(s[-1,-3]) 没有结果

s="我爱你"
# 可以给切片添加步长来控制切片的方向
print(s[::-1]) # 注意最后一个-1表示从右往左

# 解释一下步长
# 语法 s[start:end:step]从start切到end且每step个元素出来一个元素
s="aiuyiuiuysdfpoipopoi"
print(s[3:8:2])
# 符号是正的，从左往右分组就取左边的那个，是负号从右往左分组，且取出来的是右面的
# 而且注意如果改成负号的时候再切片最左边的索引就要从右面的位置开始取了
print(s[-1:-10:-3]) # 正确！
print(s[10:3:-2])   # 正确！
print(s[-10:-1:-3]) # 错误！


# 3.字符串的常规操作
# 字符串的操作一般不会对原字符串产生影响，但是会返回一个新的字符串
s="python"
s1= s.capitalize() # 让首字母变成大写， 原字符串不改变，但是会返回新的值

print(s1)
print(s)

s.title() #所有单词的首字母变成大写，不常用
s1=s.lower()

print(s1)

s=s.upper() # 忽略大小写来进行判断

print(s)

verify_code =input("请输入")
user_code="wGhj"
if verify_code.upper()==user_code.upper():
    print("right")
else :
    print("wrong")


# 替换和切割
# strip 函数,去掉字符串两端的空白符，例如空格和换行符，/t/n
s="      iop   oiu    "
s1=s.strip()
print(s1)
#iop oiu

username=input("请输入用户名： ").strip()
password=input("请输入密码： ").strip()
print(f"{username},{password}")

# replace(old,new)函数 注意还是同样的只提供返回值，不影响原来的数据
s="hello , my name is zhoujielun"
print(s.replace("zhoujielun","zz"))

print(s.replace(" ",""))

# 字符串的切割
# split(用什么切割) 字符串切割,切割之后的结果会放在列表当中
a="java_script_c#_c++"
lst=a.split("_")
print(lst)
lst=a.split("_c#")
print(lst)

# 注意用谁去切谁就会消失,注意列表里面用的是单引号不是双引号了

#replace split strip




# 查找和判断

# 查找
s="你好啊，我叫周润发"

# 1. find
ret=s.find("周润发")
print(ret)
# 如果找到了返回索引，如果没找到返回的是-1！

# 2. index
ret=s.index("周")
print(ret)
#注意index如果没找到会直接报错

# 3. in 更常见
print("周润发" in s)
print("周润发" not in s)
#注意 in可以做条件判断


# 判断
name=input("请输入你的名字")
if name.startswith("张"): #判断是否以某个字符开头，endwith()
    pass

money=input("money")
if money.isdigit(): # isdigit 判断字符串是否由整数组成 ，isdecimal小数
    money=int(money)
else:
    pass



# 其他
# 1. len()
len(s)
type(s)
print(len(s))

# 2. join()
lst=['a','b','c']
lst2=["a","b","c","d"]
print("-".join(lst),"_".join(lst2))
```

# 列表
```python
# 列表
# 定义 能装东西的东西
# 列表里的元素用逗号隔开
#python 中用[]来表示一个列表

lst=["金毛狮王",["acdc","acdc"],"bbb","ccc"]
# 特性：
# 1. 也像字符串一样有索引和切片
# 2. 索引如果超出范围会报错
# 3. 可以用for循环进行遍历
# 4. 可以用len知道列表的长度
#print(lst)
print(lst[0])
print(lst[1])

for item in lst:
    print(item)

# 列表的增删改查，★注意这些增删改查可以直接影响列表，而不只是单单提供返回值
lst=[]

#向列表中添加内容
# 1.append()
lst.append("zhangsan")
lst.append(["zhangsan","zhangwuji"])
print(lst)

# 2.insert()
lst.insert(0,"zhaomin")
print(lst)
#insert()必须指定位置

# 3.extend()
lst.extend(["wuzetian","yingzheng","machao"])
print(lst)
#extend可以将两个列表合并，批量添加


# 删除元素
# 1.pop()
ret=lst.pop(3)
print(ret)
# pop()返回被删除的元素并删除

#★★ 2.remove()
lst.remove("machao")
print(lst)
# 指定元素删除


# 修改元素
lst[2]="kai"
#直接用索引

# 查询
print(lst)
#直接用索引进行查询


# 小练习
# 把所有姓张的人改成姓王
lst=["张无忌","张绍刚","444"]


for item in lst:
    if item.startswith("张"):
        item.replace("张","王")
        newname="王"+item[1:]
        print(item)
        print(newname)
print(lst)
# 注意，问题来了
# 1. item.replace只提供返回值，并不直接修改元素
# 2. 在循环中直接修改item变量不会改变原列表中的元素，因为item是一个局部变量，item也由列表中的东西赋值
# 3. 看不到索引
# ★★★★★★★★所以必须通过索引修改元素★★★★★★★★
# ★★ 修改for循环，通过索引遍历

for i in range(len(lst)):
    if lst[i].startswith("张"):
        lst[i]="王"+lst[i][1:]

print(lst)



# 其他操作
# 排序
lst=["马化腾",1,2,3]
#列表是有序的

lst=["1234","123"]
lst.sort() #对列表进行升序排序,需要相同的数据类型
print(lst)
lst.sort(reverse=True)
print(lst)

#列表的嵌套
lst=[123,12,[123,[45,"spring"]]]
print(lst[2][1][1].upper())

#列表的循环删除
lst=["张无极","赵敏","张绍刚","张无忌","武则天"]
# for item in lst:
#     if item.startswith("张"):
#         lst.remove(item)
# print(lst)
#出现问题了，在删除的时候后面元素自动递补，但是索引并没有改变，因此错过了一个元素


temp=[]# 准备一个临时列表，存储即将要删除的东西
for item in lst:
    if item.startswith("张"):
        temp.append(item)

for item in temp:
    lst.remove(item)
# 安全稳妥的删除方式：将要删除的东西保存在新列表当中，循环新列表，删除老列表
print(lst)
```
# 元组和集合
```
# tuple 元组 特点：不可变的列表
t=("zhangwuji","zhaomin",123)

print(t)

print(t[1:3])

# t[0]="qiaofu"  TypeError: 'tuple' object does not support item assignment,元组不可变

print(t)

# 你固定了某些东西，不允许外界修改

# 元组如果只有一个元素★此时括号默认为优先级，默认不当成元组，想让他变成元组的话，需要在元素末尾添加一个逗号
t=("haha")
print(t)
print(type(t))

t=("haha",)
print(len(t))

t=("haha",["10",2,3,])
t[1].append("dadada")
print(t)
# 注意元组的不可变指的是：元组的某一层地址不可变，不可以被替换为其他地址
# 但是这个地址处的东西可以进行他自己的操作

# set集合
# ★重点特性：由于哈希存在，可以去除重复
s={1,2,3,"heheda",(1,2,3)}
# s={1,2,3,"heheda",[1,2,3]}    TypeError: unhashable type: 'list'
# 不可哈希：python中的集合进行数据存储的时候，需要对数据进行哈希计算，根据计算出的数据来进行存储
# 所以色图集合要求存储的数据必须是可以进行哈希计算的
# 可哈希的数据类型是不可变的数据值：纯数字，字符串，元组，布尔值
# 可变的值是不可哈希的，list,dict,set
print(type(s))
print(s)

s={}
print(type(s))# <class 'dict'>
# 想创建空集合，空元组
s=set()
t=tuple()
str=str()
lst=list()

# 集合的增删改查
# 增
s.add("hhh")
s.add("123")

# 删
# 集合没有索引
# s.pop()  #没有索引。pop()不能加参数，随机弹出一个
s.remove("hhh")

# 改
# 只能先删掉再加入
s.remove("123")
s.add("liua")

# 查
in关键字

# 集合的交并差
s1={"123","234","345"}
s2={"123","345","456"}

# 交
print(s1&s2)
print(s1.intersection(s2))

# 并
print(s1|s2)

# 差集
print(s1-s2)

# 去重
lst=["zhoujielun","kunling","caiyilin","zhoujielun","kunling","caiyilin"]
# set(lst) 可以把lst变成set
print(list(set(lst)))
```

# 字典
```
# 字典
# 首先，字典是以键值对的形式进行存储的
# 字典的表示方式：{key:value1,key2:value2,key3:value3}

# 字典的key必须是可哈希的数据类型，但是字典的value可以是任何数据类型

dic={"caicaidexiaoze":["chaochao","chenyang"]}

# 字典的增删改查
# 增
dic=dict()
dic["jay"]="zhoujielun"
dic[1]=123
dic["jay"]="kunling"
# 注意比c++更加的灵活，可以放入不同的东西
# 字典中的键只能有一个，所以
print(dic)

dic.setdefault("tom","hulatang")# 设置默认值，如果以前已经有tom了,则setdefault不再管用
dic.setdefault("tom","123")
print(dic)

# 删除
dic.pop("jay")


# 查找
# print(dic["jay"]) #如果key不存在，则程序会报错
# print(dic.get("jay")) #如果key不存在，返回null，当不确定key的时候可以用
in 关键字

# None
a=None #单纯的就是空，什么都没有
print(type(a))

dic={
    "zhaosi":"tebienengwaizui",
    "liuneng":"tebienenggaoduixiang",
    123:321,
    1234:4321

}
name=input("请输入你想知道的人的名字")
if dic.get(name) is None:# 注意is也可以
    print("no thisone")
else:
    print(dic.get(name))



# 字典如何进行循环遍历
# 1.for循环
for key in dic:
    print(key,dic[key])

# 2. 把所有的key全都把存在一个列表中,dic.keys()函数
print(dic.keys())
print(list(dic.keys()))

# 3.直接拿到字典中的key和value,dic.items()函数
print(dic.items()) #列表里放元组
print(list(dic.items())) #变成一个列表中放着元组

for item in dic.items():
    print(item)

a,b=(1,2) #元组或者列表都可以执行该操作，该操作叫做解构，或者解包
print(a)
print(b)

for item in dic.items():
    key,value=item # 解构
    print(key,value)

for key,value in dic.items(): # 在for循环中直接进行解构，非常关键★★★
    print(key,value)


# 字典的嵌套
n=123
wangfeng={
    "name":"wangfeng", #注意直接这么写是不行的，因为字典的键必须是一个值,不能是一个未定义的变量,但是可以是一个已定义的变量
    "wife":{
        "name":"zhangziyi",
        "hobby":"act"
    },
    "children":{
        "children1":{
            "name":"liu",
            "age":18,
        },
        "children2":{
            "name":"cai",
            "age":19,
        }
    },
    "assistant":[
        {
            "name":"liu",
            "age":18,
        },
        {
            "name":"cai",
            "age":19,
        }
    ]
}
print(wangfeng["children"]["children1"]["name"])

wangfeng["assistant"][1]["age"]+=12
print(wangfeng["assistant"][1]["age"])


dic={"大张伟":1,
     "大步走":2,
     "dasd":3
     }
# 循环删除
# 准备临时列表
temp=[]
# 字典循环自己又删自己是不允许的，但是循环别的东西去删字典也是ok的
for key in dic:
    if key.startswith("大"):
        # dic.pop(key) #dictionary changed size during iteration
        temp.append(key)

for item in temp:
    dic.pop(item)

print(dic)
```

# bytes
```
# 1. 字符集和编码
# 电脑如何存储文字信息？
#
# ascii码 128
# 没有中文的标点符号
# ANSI => 一套标准，每个字符16bit，2byte
#
# 到了中国，gb2312编码 国标  ->gbk编码（windows默认）
#
# 国际化组织：
# Unicode：万国码，统一码
# 早期unicode UCS-2 2bytes
# 进行了扩充，变成了4个字节
#
#
# utf: 是可变长度的unicode，可以进行数据的传输和存储
# utf-8(常用)  最短的位长度 8位
#         英文：8bit
#         欧洲文字：16bit
#         中文文字：24bit
# utf-16      最短的为长度 16位
#
# 总结：
# 最早的编码是ascii码，8位一字节
# gbk 16位，两字节   (windows默认)
# unicode 32bit，4字节
# utf-8:       mac默认
#     英文：8bit
#     欧洲：16bit
#     中文：24bit
#
# gbk和utf-8不能直接进行转化


#2.bytes
   #  程序员平时遇到的所有的数据最终单位都是字节byte
s="周杰伦"
bs1=s.encode("gbk")
print(bs1)
#b'\xd6\xdc\xbd\xdc\xc2\xd7' bytes类型
# 每个\x都是一个字节，共六个字节

bs2=s.encode("utf8")
print(bs2)

# 怎么把一个gbk的字节转化成一个utf-8的字节？
bs= b'\xd6\xdc\xbd\xdc\xc2\xd7'
#先变成文字符号（字符串）
s=bs.decode("gbk") # 解码
print(s)
bs2=s.encode("utf-8") # 重新编码
print(bs2)

# 1.str.encode("编码类型") 编码，得到bytes
# 2.bytes.decode("解码类型") 解码，得到str

s="你好abc呵呵哒"
print(s.encode("gbk"))
# b'\xc4\xe3\xba\xc3abc\xba\xc7\xba\xc7\xdf\xd5'
print(s.encode("utf8"))
# b'\xe4\xbd\xa0\xe5\xa5\xbdabc\xe5\x91\xb5\xe5\x91\xb5\xe5\x93\x92'
# 英文都还是原来的1位
```

# 运算符
```
# 运算符
# 1. 算数运算
# + - * / %  //(整除,地板除)
#
# 2. 比较运算符
# > < >= <= == !=
#
# 3. 赋值运算符
# = += *=
#
# 4. 逻辑运算
#     1. and 并且，左右两端同时成立
#     2. or 或
#     3. not
#
#     加括号规定好优先级 ，非与或
# 5. 成员运算
# in
# not in
a=10
b=3
print(int(a/b))
print(a//b)

# python中的swap
a,b=(b,a) # 解构，解包
print(a,b)
```

# 文件操作
```
# 文件操作
# 1. 找到这个文件，双击打开它
# open(文件路径，mode="",encoding="")
#     文件路径：
#         1.绝对路径
#             d:/test/xxx.txt(从磁盘的根目录开始读取，不安全，在开发人员处ok但无法项目迁移)
#         2.相对路径
#             相对于当前你的程序所在的文件夹

# mode:
#     r：read
#     w:write
#     a:append
#     b:读写非文本文件要加，此时可以不加encoding

# 正确的文件打开方式
# open("葫芦娃.txt")
# f=open("../为了演示文件操作而创建的外部文件",mode="r",encoding="utf8") #读写文本文件的时候一定要给encoding
#注意 f只是一个流管道

# 读
# 1. 全部读取
# content=f.read()
# print(content)

# 2.readline
# line=f.readline().strip()
# print(line)
# line=f.readline()
# print(line)
#
# 123456
#
# 123456789456
# print内部存在一个换行，但是文件里面也有一个换行符，隐藏在每行字符的末尾
# 加上strip可以把换行符干掉

# 3. readlines，读出来放到一个列表里
# content=f.readlines()
# print(content)

# 最重要的一种文本读取方式，必须掌握
# for line in f:
#     print(line.strip())
# f是可以循环和遍历的

# f.close()

# 写
# 1. mode="w"
# f=open("../通过python创建的一个文件",mode="w",encoding="utf8")
# w模式下，如果文件不存在，自动的创建一个文件
# w模式下，每一次open都会清空文件里的内容
# f.write("胡辣汤1\n")
#
# f.close() # 每次尽量关掉，确保数据从缓冲区写入磁盘


#
# f1 =open("../通过python创建的一个文件",mode="w",encoding="utf8")
# # f.close()
# lst=["aaa","bbb","ccc","ddd","eee"]
#
# for i in lst:
#     f1.write(i+"\n")
# # 注意每次的write实际上是预写，写在缓冲区里，还没彻底写进去，只有当close或者程序执行完之后才会生效，如果还未close的话后面的文件也读不出来
# f1.close()
#
#
# f2 =open("../通过python创建的一个文件",mode="r",encoding="utf8")
# for lin in f2:
#     print(lin.strip())
#
# f2.close()

#
# # 2.mode="a",append追加
# f=open("../通过python创建的一个文件",mode="a",encoding="utf8")
# f.write("胡辣汤2\n")
# f.close()

#
#
# # with 自动关闭文件
# with open("../通过python创建的一个文件",mode="r",encoding="utf8") as f: #f=open
#     for line in f:
#         print(line.strip())
#
# # f.read() # I/O operation on closed file.
#
#
# # 读取图片
# # 在读取非文本文件的时候要加上b
# # with open("../屏幕截图 2025-11-03 164326.png",mode="rb") as f:
# #     print(f.read())
#
#
#
# # 文件的复制：
# # 从源文件中读取内容，写入到新路径去
# # ，\表示下一行和这一行是同一行
# with open("../屏幕截图 2025-10-31 154831.png",mode="rb") as f1, open("../新图片.png",mode="wb") as f2:
#     for line in f1:
#         f2.write(line)
# 不需要考虑换行符，因为读取的时候已经能读出来换行符了


# 文件的修改
# 不能边读边写
# 从源文件中读，修改之后放到新文件里
# 把原来的文件删掉，把新文件再换成原文件
# 副本其实还在，原来的文件没了，副本变成了原来的文件

# import os 和操作系统相关的模块导入
import os #导入os模块
import time #导入时间模块
with open("../通过python创建的一个文件",mode="r",encoding="utf8") as f1 ,\
     open("通过_副本.txt",mode="w",encoding="utf8") as f2 :
    for line in f1:
        line=line.strip() # 去掉换行符
        if line.startswith("胡"):
            line=line.replace("胡","张")
        f2.write(line+"\n")

# 删除源文件
time.sleep(3) #让程序休眠3秒钟
os.remove("../通过python创建的一个文件")
time.sleep(3)
# 把副本文件重命名为源文件
os.rename("通过_副本.txt","../通过python创建的一个文件")
# 删除源文件
# 把副本文件重命名成源文件


```

# 函数上
```
# 函数
# 好处：封装功能，代码更简洁，更合理
# python里面形参不写类型,也不写返回值

def calculator(a,b,op):
    if op=='+':
        return a+b
    elif op=='-':
        return a-b
    elif op=='*':
        return a*b
    elif op=='/':
        if b==0:
            return None
        else:
            return a/b


print(calculator(1,2,"+"))
print(calculator(1,2,"-"))
print(calculator(1,2,"*"))

#
# 参数的分类
#     1. 形参，在函数定义的时候需要准备一些变量来接收信息
#     2. 实参，实际调用的时候传递的信息

# 实参传参方式
def chi(main,ast,soup):
    print(main,ast,soup)

#         1. 位置参数，按照位置进行传参
chi("大米","咸菜","粥")

#         2. 关键字参数，指定形参的名字进行传参
chi(main="大米",soup="粥",ast="咸菜")

#         3. 混合参数,位置参数在前面，关键字参数在后面，并且一定要保证
chi("大米","咸菜",soup="粥")



# 形参传参方式
# 1.位置参数，按照位置
# 2.默认值参数
#   默认参数必须从右向左连续设置

def classroom(main="1班",num=12,style="nb"):
    print(main,num,style)

# classroom()
# classroom("2班")
# # 注意默认值必须保证前面所有的参数全部写出
# classroom(13,style="nnn")

# 位置参数总是放在前面的
# 3.动态传参
#     1. *args ，表示接收所有的位置参数的动态传参
#     2. **kwargs ，表示接受所有的关键字参数的动态传参

# 顺序: 位置> *args >默认值>**kwargs
#           1.args
# def chi(*food): # * 表示位置参数的动态传参，*接受到的值会被统一放在一个元组里面
#     print(food)
#
# chi("123","456","789")
# chi("123","789")
# chi("123","456")

#           2. **kwargs,表示接受所有的关键字的动态传参
#
# def chi(**food):  # **表示接受关键字的动态传参，接收到的所有参数都会被处理成字典
#     print(food)
#
# chi(fu="糯米糍",des="深圳")


#      4.混合传参
def func1(a,b,c="哈哈",*args,**kwargs):
    print(a,b,c,args,kwargs)

func1(1,2,"123",4,5,6,7,8,9,hello=456,nihao=789)
# 何时能产生默认值
# 如果c的默认值生效，则args一定收不到任何值
# 如果args收到了值，则c的默认值yidingmie

def func2(a,b,*args,c="哈哈",**kwargs):
    print(a,b,c,args,kwargs)

func2(1,2,3,4,5,6,7,8,9,c=123,hello=456,nihao=789)

# args直接全部收走了
# 但是默认值参数可以通过关键字参数指定c的值

def func3(*arg,**kwargs): # 没有限制的接受任何参数
    print(arg,kwargs)



stulst=["123","456","789","101","102"]
def func4(*args):
    print(args)

func4(*stulst) # *在实参位置就是把列表打散成位置参数传递

dic={
    "abc":123
}
# **也可以打散


# 
# 关于 return
#     1.函数内部没有 return，默认返回none
#     2.函数内部只有return后面不跟数据，此时接收到的还是none
#     3. return 值1，值2，值3，此时返回的是一个元组，python函数可以返回好多个值


# 作用域：变量的访问权限

# a=10 #全局变量 --> 全局作用域
#
# def func():
#     b=10
#     print(a) 全局变量在函数内部可以访问
# print(b)  #局部变量外部不能访问

# # 局部变量外部不能访问

# 顶格声明的函数也可以认为是全局的，可以在各处调用
# 函数外部想访问函数内部只能用return

# # python中允许函数嵌套(不是函数的调用)
# def func1():
#     print(123)
#     def func2():  # 函数的嵌套，局部变量，局部函数
#         print(456)
#         def func3():
#             print(789)
#             def func4():
#                 print(78910)
#     print(3)
#     func2()
#     print(4)
#     # 函数内部访问局部函数是没问题的
#
# func1()


# 返回值是局部函数的情况，把函数当成一个变量返回
# def func():
#     def inner():
#         print(123)
#     print(inner) #<function func.<locals>.inner at 0x000001C1C2673920>
#     return inner #一定不能加括号，加括号返回的是返回值
#
# b1=func()
# b1()
# print(b1) #<function func.<locals>.inner at 0x0000025F4C483920>,b1就是这个inner
# b1就是inner



# # 函数的赋值
# def an():
#     return 123
# bn=an #注意不能加括号
# print(bn())


# 代理模式
# 函数可以作为实参进行传入
# def func1(an):
#     print(an())
#
# def tar():
#     return "123456tar"
#
# func1(tar)

# 综上：
# 1.函数可以作为参数返回
# 2.函数可以作为参数进行互相传递
# 函数实际上就是一个变量名


# global #在局部引入全局变量
# nonlocal #向外找一层，看看有没有该变量，如果有就引入，如果没有就继续向外找，直到全局（不包括）
# a=10
# def func():
#     # print(a) #还是全局变量，这个可以
#     # a=20 #创建一个全部变量，并没有去改变全局变量中的a
#     global a
#     a=20
#
# func()
# print(a)
#
#
# def func2():
#     a=10
#     def inner():
#         nonlocal a
#         a=12
#     inner()
#     print(a)
#
# func2()

# 闭包 ：本质，内层函数对外层函数的局部变量的使用，此时内层函数被称为闭包函数
# 1. 可以让一个变量长驻于内存，实现了全局变量的效果
# 2. 可以避免全局变量被修改
# 闭包语法：
b=10
def func():
    a=10
    def inner():
        # 这个a本身是一个局部变量，但是达到了全局变量的效果
        nonlocal a
        a+=1
        return a

    return inner

ret=func()
ret()
# ret的执行时间不确定，为了保证正常使用inner，必须保证inner所使用的东西是一直都存在的，即闭包所使用的东西必须一直常驻于内存

print(ret())
print(ret())


#
# 内容回顾：
# 1.函数可以作为参数进行传递 （还记得代理模式吗）
# 2.函数可以作为返回值进行返回
# 3.函数名称可以当成变量一样进行赋值操作

def func():
    print("我是函数")

def gggg(fn):
    fn()

gggg(func) #注意只传函数名字，括号啊参数啊都不传

def func2():
    def inner():
        print(123)
    return inner

ret=func2()
ret()

newfunc=func
newfunc()



# 装饰器  ->  要求记住最后的结论
# def play_dnf():
#     print("你好啊我叫赛利亚")
#
# def play_lol():
#     print("德玛西亚！")
#
# print("开挂")
# play_lol()
# print("关闭外挂")
#
# print("开挂")
# play_dnf()
# print("关闭外挂")
#
# def guanjia(game):
#     def inner():
#         print("开挂")
#         game()
#         print("关闭外挂")
#     return inner
#
# play_dnf=guanjia(play_dnf)  #让管家把游戏重新封装一边，再把原来的游戏给替换掉
# play_dnf() #此时运行的是管家给的内层函数inner

# # play_dnf=guanjia(play_dnf)  #如果再封装一次就变成两次开挂了
# play_dnf()


# def guanjia(game):
#     def inner():
#         print("开挂")
#         game()
#         print("关闭外挂")
#     return inner
#
#
# @guanjia
# def play_dnf():
#     print("你好啊我叫赛利亚")
#
# @guanjia
# def play_lol():
#     print("德玛西亚！")
#
# play_dnf()
# play_lol()
```
# 装饰器：
```
# 装饰器本质上是一个闭包
# 作用：
#     在不改变原有函数★调用★的情况下，给函数增加新的功能
#     直白：可以在函数前后添加新功能，但是不改原来的代码

# 雏形：
# def wrapper(fn):    wrapper:装饰器，fn:目标函数
#     def inner(*args,**kwargs):
#         # before
#         fn(*args,**kwargs) #执行目标函数
#         #after
#     return inner

# 通用
def wrapper(fn):    wrapper:装饰器，fn:目标函数
    def inner(*args,**kwargs):
        # before
         ret = fn(*args,**kwargs) #执行目标函数
         #after
        return ret
     return inner
# 通用装饰器

#
# def func1(fn):
#     fn()
#
# def func2():
#     print(123)
#
# func1(func2) # #把函数作为参数传递时一定只传函数名字，其他什么都不加

def guanjia(game):
    # 这里的*表示接受所有的元组和字典
    def inner(*args,**kwargs): #args 一定是元组
        print("开挂")
        # 这里的*表示把接收到的元组和字典再打散成参数传递进去
        game(*args,**kwargs)
        print("关闭外挂")
    return inner

#把函数作为参数传递时一定只传函数名字，其他什么都不加
@guanjia
def play_dnf(username,password):
    print("你好啊我叫赛利亚",username,password)

@guanjia
def play_lol(username,password,hero):
    print("德玛西亚！",username,password,hero)

play_dnf("123",123)
play_lol("oiu",456,"盖伦")

# 理解：inner它是最后封在外面的函数，他要无限制的接受，接收完之后再把接收到的东西打散成内层函数，让内层函数来执行，这个外层函数最后再赋值给内层函数，内层函数放心地执行即可，同时也说明内层函数只套了一层



# 一个函数可以被多个装饰器装饰
def wrapper1(func):
    def inner(*args,**kwargs):
        print("wrapper1 in")
        ret=func(*args,**kwargs)
        print("wrapper1 out")
        return ret
    return inner

def wrapper2(func):
    def inner(*args,**kwargs):
        print("wrapper2 in")
        ret=func(*args,**kwargs)
        print("wrapper2 out")
        return ret
    return inner


@wrapper1 #tar= wrapper1(wrapper2(tar))
@wrapper2 # tar=wrapper2(tar)
def func3():
    print("func3")

func3()
# 先装wrapper2，再装wrapper1，最后实现的状态有点类似于栈


# 员工系统实战
loginflag=0
def login(fn):
    def inner(*args,**kwargs):
        global loginflag
        if loginflag==0:
            username=input("uname")
            print("logining")
            loginflag=1
        ret=fn(*args,**kwargs)
        print("logining out")
        return ret
    return inner

@login
def add(name):
    print(f"录入{name}")

@login
def out(name):
    print(f"out {name}")

@login
def change(name):
    print(f"change {name}")

add("123")
out("123")
change("456")

```
# 函数下：
```
"""
for 变量 in 可迭代
    pass


iterable 可迭代的东西
iterator 迭代器
str，list，tuple，dict，set，open()

可迭代的数据类型都会提供一个叫迭代器的东西
这个迭代器可以帮我们把数据类型中的所有数据逐一的拿到

获取迭代器的两种方案：
    1. iter() 内置函数可以直接拿到迭代器
    2. __iter__()
从迭代器中拿到数据：
    1.next()
    2.__next__()

for 里面一定要拿迭代器，所以有不可迭代的东西不能用for循环
for循环里面一定有x__next__()

总结：迭代器统一了所有不同数据类型的遍历工作


迭代器本身也是可迭代的

迭代器本身的特性：
    1. 只能向前，不能反复
    2. 很省内存
    3. 惰性机制，只有调用的时候才往后挪一个，不调用就不改变位置，
"""
it=iter("你叫什么名字啊")

print(next(it))
print(next(it))
print(next(it))         # StopIteration:迭代停止了，拿不出，一次性，再想拿需要重新重新获取迭代器

it="heheda".__iter__()
print(next(it))
print(it.__next__())


# 模拟for循环的工作原理:
s = "123456"
it=s.__iter__()
while 1:
    try:
        data=it.__next__()
        print(data)
    except StopIteration:   #Stopiteration 是错误类型
        break


it="123456".__iter__()

for mm in it:
    print(mm)


# 字符串的改变可以用索引或切片
s="123456"
s=s[1:]
it=s.__iter__()
print(it.__next__())
# 出现了之前删除时发生过的问题,迭代器他只管所在的位置，不管数据有没有更改

"""
    生成器(generator)：
        生成器的本质就是迭代器
        
        创建生成器的两种方案：
            1.生成器函数
            2.生成器表达式
            
        生成器函数
            生成器函数关键字 yield
            生成器函数执行的时候，不会执行函数本体，得到的是一个迭代器
            生成器执行next的时候，才会执行函数本体，并返回一个可以迭代的返回值
            
            yield:只要函数中出现了yield，他就是一个生成器函数
                作用：
                    1.可以返回数据
                    2.可以分段的执行函数中的内容，通过__next__()执行到下一个yield的位置
                    3.每次从上一个yield的位置开始执行
                
            优势：
                用好了，特别的节省内存
"""
def func():
    print(123456)
    yield 999 #yield 也有返回的意思,但是只有执行到next的时候，才会返回数据
    print("2th")
    yield "hello"
ret=func()
print(ret)
ret.__next__()
print(ret.__next__())

#去工厂定制10000键一副
# def order():
#     lst=[]
#     for i in range(10000):
#         lst.append(f"衣服{i}")
#     return lst

# print(order())

def order():
    lst=[]
    for i in range(1,1000):
        lst.append(f"衣服{i}")
        if len(lst)==50:
            yield lst
            lst.clear()

ret=order()
print(ret.__next__())

print(ret.__next__())



# 列表推导式
"""
推导式：
    简化代码
    语法：
        列表推导式：[数据 for循环 if判断]    
        集合推导式：{数据 for循环 if判断}
        字典推导式：{k:v for循环 if判断}

    不要把推导式妖魔化
    
    元组不能新增数据，没有推导式
    (数据 for循环 if判断) ---> 生成器表达式
"""
lst=[i for i in range(1,10,2)]
print(lst)
lst=[i for i in range(10) if(i%2!=0)]
print(lst)

lst=[f"衣服{i}" for i in range(1,10,2)]
print(lst)

# 将如下列表中的所有英文字母改成大写
lst1=["abcd","yui","poi"]
lst2=[i.upper() for i in lst1]
print(lst2)

s={i for i in range(1,10,2)}
print(s)

# 4.改为字典，索引为key数据为value
lst1=["abcd","yui","poi"]
s={i:lst1[i] for i in range(len(lst1)) }
print(s)

s={i:j for i,j in enumerate(lst1) }
# enumerate 用于在遍历序列（如列表、元组、字符串）时，同时获取元素的索引和值,并组合成一个元组，再解构即可直接获得索引和值


"""
生成器表达式：
(数据 for循环 if判断)

"""
gen=(i**2 for i in range(10))
print(gen.__next__())
print(gen.__next__())

# 想把迭代器中的数据全拿出来，由于迭代器本身也可以被迭代
for it in gen:
    print(it)

# 注意是it不是it.__next__()

# 想把迭代器中的东西变成列表：
s="zhoujielun"
lst=list(s)
print(lst)
"""
因为小括号实际上是一项一项的拿出来，所以也在迭代，里面一定有list
"""
print(list(gen))
# [],生成器表达式是个一次性的东西


"""
    匿名函数：
        lambda表达式
        语法 ：
            变量 = lambda 参数1 ， 参数2 ， 参数3 ，：返回值
        注意lambda不要写return关键字
"""
fn = lambda a,b:a+b
print(fn)
print(fn(10,20))
```

# 内置函数
```
"""
内置函数：
直接能拿来用的函数


"""
s="123"
i=int(s)
b=bool(s)
f=float(s)

# bin,oct,hex 十进制转他进制
a=18
print(bin(a))
print(oct(a))
print(hex(a))

# 他进制转十进制
a=0o1101
print(int(a))

# sum,min,max,pow
print(pow(a,2))
print(a**2)

lst=[123,12,4,456,65]
print(max(lst))


# 数据结构相关
s={1,2,3,}
lst=list(s)  # list内置函数内部一定会有一个循环
print(lst)
# 逻辑：
for item in s:
    lst.append(item)


# 字符串相关
# format,ord,chr
# format 格式化
a=10
print(format(a,"b"))
print(format(a,"o"))
print(format(a,"x"))

print(format(a,"08b")) #自动补齐场宽

# ord
a="中" # python的内存中使用的是unicode（不是存储）
print(ord(a)) # 中 字在unicode中码位20013
# ord可以获取字符的ascii码
print(chr(20013)) # 把码位转换为字符
# for i in range(65536):
#     print(chr(i)+" ",end="")

# all
print(all([12,"hehe",0]))# 打印一堆东西的与，相当于and

lst=["",""]
print(any(lst))# 打印一堆东西的或，相当于or


# enumerate
ls=[123,45,16,7]
for i,j in enumerate(ls):
    print(i,j)

s="heheda"
print(hash(s)) # 做数学运算，成为一个数字，想办法转化成一个内存地址，然后进行数据的存储，成为哈希表
#每次执行都不一样
print(hash(s))
print(id(s)) #id是直接拿到内存地址，而哈希是进行计算，两者不同

print(help(str))# 针对数据类型
print(dir(s)) # 针对对象，当前这个对象可以执行哪些操作
# 返回源码，pycharm直接按control即可看源码，但是help或dir可以在控制台里看源码


# """
# zip：可以把多个可迭代内容进行合并
# """
# lst1=["驴打滚","芝麻球","咸肉粽"]
# lst2=[12,23,10]
# lst3=["辽宁","吉林","黑龙江"]
# result=[]
# # for i in range(len(lst1)):
# #     frist=lst1[i]
# #     second=lst2[i]
# #     third=lst3[i]
# #     result.append((frist,second,third))
# #
# # print(result)
#
# result=zip(lst1,lst2,lst3)
# print(dir(result))
# for item in result:
#     print(item)
#
# print(list(result)) #list 里面有for循环

#locals,globols
#locals
a=123
b=321
print(locals())# locals放在全局，看到的是全局
def func():
    a=987
    uio= 336
    print(locals())
    print(globals())

func()


"""
sorted :排序
"""
lst=[123,5,456,12]
sorted(lst,reverse=True) # 注意不改变原结果，只提供返回值
s=sorted(lst)
print(s)
lst=["zz","aaa","bbbbb"]
# sorted(lst,key=排序规则，reverse=)
# 排序规则会把每一项数据分别传递给排序函数，排序函数里面写规则
# sorted把每一项传递给排序函数，然后根据排序函数的返回值来进行排序
def cmp(a):
    return ord(a[0])
s=sorted(lst,key=cmp,reverse=True)
print(s)

s=sorted(lst,key=lambda a:ord(a[0]))
print(s)

lst=[
    {"id":1,
     "name":"aaa",
     "age":12
     },
    {"id":2,
     "name":"bbb",
     "age":13
     },
    {"id":3,
     "name":"aaa",
     "age":789
     },
    {"id":4,
     "name":"aaa",
     "age":1
     },
    {"id":5,
     "name":"aaa",
     "age":12311
     }
]
s=sorted(lst,key=lambda a:a["age"])
# 一定要写key关键字
print(s)

"""
filter:筛选
"""
lst=["123","321","1234567"]
f=filter(lambda x:x[0]=="1",lst)
print(list(f))


"""
map:映射
"""
lst=[1,2,3,4,5,6,7,8,9]
r=map(lambda x:x**2,lst)
print(list(r))


# python默认最大递归深度是1000
import sys
print(sys.getrecursionlimit())
sys.setrecursionlimit(2000)
# 优化算法
```
