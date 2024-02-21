# Assignment #1: 拉齐大家Python水平

Updated 0940 GMT+8 Feb 21, 2024

2024 spring, Complied by 王宇轩 信科



**说明：**

1）数算课程的先修课是计概，由于计概学习中可能使用了不同的编程语言，而数算课程要求Python语言，因此第一周作业练习Python编程。如果有同学坚持使用C/C++，也可以，但是建议也要会Python语言。

2）请把每个题目解题思路（可选），源码Python, 或者C++（已经在Codeforces/Openjudge上AC），截图（包含Accepted），填写到下面作业模版中（推荐使用 typora https://typoraio.cn ，或者用word）。AC 或者没有AC，都请标上每个题目大致花费时间。

3）课程网站是Canvas平台, https://pku.instructure.com, 学校通知3月1日导入选课名单后启用。**作业写好后，保留在自己手中，待3月1日提交。**

提交时候先提交pdf文件，再把md或者doc文件上传到右侧“作业评论”。Canvas需要有同学清晰头像、提交文件有pdf、"作业评论"区有上传的md或者doc附件。

4）如果不能在截止前提交作业，请写明原因。



**编程环境**


操作系统：Windows 11

Python编程环境：VS Code, PyCharm 2023.1.4




## 1. 题目

### 20742: 泰波拿契數

http://cs101.openjudge.cn/practice/20742/



思路：刚上手python且上学期计概学的C++忘得干干净净，照着书现看了一下py里列表和for的使用方法捏



##### 代码

```python
n = int(input())
list = [0, 1, 1]
for i in range(3, n+1):
    x = list[i - 1] + list[i - 2] + list[i - 3]
    list.append(x)
print(list[n])
```





![image](https://github.com/Huo-Kun/DS-Algo-2024/assets/142503647/32fa0c2c-d81c-4dc6-bcb4-8838aeef5750)


### 58A. Chat room

greedy/strings, 1000, http://codeforces.com/problemset/problem/58/A



思路：定义一个状态参数n，按照符合情况做判定



##### 代码

```python
s = input()
num = 0
for i in range(0, len(s)):
    if num == 0:
        if s[i] == 'h':
            num = num + 1
            continue
        else:
            continue
    if num == 1:
        if s[i] == 'e':
            num = num + 1
            continue
        else:
            continue
    if num == 2:
        if s[i] == 'l':
            num = num + 1
            continue
        else:
            continue
    if num == 3:
        if s[i] == 'l':
            num = num + 1
            continue
        else:
            continue
    if num == 4:
        if s[i] == 'o':
            num = num + 1
            continue
        else:
            continue
if num == 5:
    print('YES')
else:
    print('NO')

```



![image](https://github.com/Huo-Kun/DS-Algo-2024/assets/142503647/0a2f6045-c17b-4f53-81c1-3222ab673e33)






### 118A. String Task

implementation/strings, 1000, http://codeforces.com/problemset/problem/118/A



思路：py里的字符串不能直接修改元素，但是可以通过转换为list操作之后再用.join()函数将其复原，且利用了条件判断中"in/not in"的用法



##### 代码

```python
s = input()
s1 = list(s)
s2 = []
for i in range(0, len(s)):
    s1[i] = s1[i].lower()
for i in range(0, len(s)):
    if s1[i] not in 'aoyeui':
        s2.append('.')
        s2.append(s1[i])
s = ''.join(s2)
print(s)

```



![image](https://github.com/Huo-Kun/DS-Algo-2024/assets/142503647/a9304bf6-5a24-4eb7-b4a3-c35a9f3699e1)






### 22359: Goldbach Conjecture

http://cs101.openjudge.cn/practice/22359/



思路：



##### 代码

```python
# 

```



代码运行截图 ==（AC代码截图，至少包含有"Accepted"）==





### 23563: 多项式时间复杂度

http://cs101.openjudge.cn/practice/23563/



思路：



##### 代码

```python
# 

```



代码运行截图 ==（AC代码截图，至少包含有"Accepted"）==





### 24684: 直播计票

http://cs101.openjudge.cn/practice/24684/



思路：



##### 代码

```python
# 

```



代码运行截图 ==（AC代码截图，至少包含有"Accepted"）==





## 2. 学习总结和收获

==如果作业题目简单，有否额外练习题目，比如：OJ“数算pre每日选做”、CF、LeetCode、洛谷等网站题目。==





