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

# 集合
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
```
