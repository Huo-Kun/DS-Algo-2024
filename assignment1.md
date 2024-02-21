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
def IsPrime(n):
    if n <= 1 or n % 2 == 0 and n != 2:
        return False
    elif n == 2:
        return True
    for i in range(3, int(n ** 0.5) + 1, 2):
        if n % i == 0:
            return False
    return True

def main():
    s = int(input())
    if s % 2 == 1:
        print(2, s - 2)
    else:
        for i in range(3, int(s/2) , 2):
            if IsPrime(i) and IsPrime(s - i):
                print(i, s - i)
                break

main()

```



![image](https://github.com/Huo-Kun/DS-Algo-2024/assets/142503647/da41702f-8510-4ab8-89d7-6b7a8ba2cc0b)






### 23563: 多项式时间复杂度

http://cs101.openjudge.cn/practice/23563/



思路：当我们使用正则表达式 r'(\d*)n\^(\d+)' 对输入字符串 input_str 进行匹配时，它会寻找满足以下条件的子字符串：

    包含一个可选的数字（0个或多个数字）作为系数。
    包含字母 "n"。
    包含一个或多个数字作为幂次。
这个正则表达式中的括号 (\d*) 和 (\d+) 是用来捕获匹配的数字部分的。具体解释如下：

    (\d*)：匹配0个或多个数字。这个括号中的 \d 表示一个数字字符，而 * 表示匹配前面的模式零次或多次。
    n\^：匹配字母 "n" 后面紧跟的字符 "^"。
    (\d+)：匹配一个或多个数字。这个括号中的 \d 表示一个数字字符，而 + 表示匹配前面的模式一次或多次。
当 re.findall() 函数被调用时，它会返回一个列表，其中包含所有满足正则表达式模式的匹配项。每个匹配项都是一个元组，其中第一个元素是系数部分的字符串，第二个元素是幂次部分的字符串。

例如，对于输入字符串 2n^3 + 5n^2 - 4n^1 + 7，re.findall() 函数将返回以下列表：[('2', '3'), ('5', '2'), ('-4', '1')]。



##### 代码

```python
import re

def calculate_time_complexity(input_str):
    terms = re.findall(r'(\d*)n\^(\d+)', input_str)
    max_power = 0
    for term in terms:
        coefficient = int(term[0]) if term[0] else 1
        power = int(term[1])
        if power > max_power and coefficient != 0:
            max_power = power
    if max_power == 0:
        return "n^0"
    else:
        return f"n^{max_power}"

# Input processing
input_str = input().strip()

# Calculate and output time complexity
result = calculate_time_complexity(input_str)
print(result)

```



![image](https://github.com/Huo-Kun/DS-Algo-2024/assets/142503647/b6eb2582-a8d8-4328-bc77-326d6f084f1c)






### 24684: 直播计票

http://cs101.openjudge.cn/practice/24684/



思路：使用了字典的 get() 方法来获取选项的得票数，如果选项在字典中不存在，则返回默认值0。然后，使用 max() 函数找出字典中的最大值，即得票数最多的选项的得票数。最后，使用列表推导式和 sort() 方法找出所有得票数最多的选项，并按编号从小到大排序。最后，使用 join() 方法将选项编号拼接成一个字符串，用空格隔开



##### 代码

```python
def find_winner(input_str):
    votes = input_str.split()  # 将输入的字符串按空格分割成一个列表
    counters = {}  # 用于记录每个选项的得票数的字典

    # 遍历列表中的每个数字，将其作为选项编号，并将其在字典中对应的值加1
    for vote in votes:
        counters[vote] = counters.get(vote, 0) + 1

    max_votes = max(counters.values())  # 找出得票数最多的选项的得票数

    # 按编号从小到大输出得票数最多的选项
    winners = [option for option, count in counters.items() if count == max_votes]
    winners.sort(key=int)  # 按编号从小到大排序
    return " ".join(winners)

input_str = input()
print(find_winner(input_str))

```



![image](https://github.com/Huo-Kun/DS-Algo-2024/assets/142503647/b4cb87fd-b95e-44b7-9b18-24a3ae43affa)






## 2. 学习总结和收获

==如果作业题目简单，有否额外练习题目，比如：OJ“数算pre每日选做”、CF、LeetCode、洛谷等网站题目。==





