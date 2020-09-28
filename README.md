# 2020.9.28———整数转罗马数字
## 题目
罗马数字包含以下七种字符： I， V， X， L，C，D 和 M。
```
字符          数值
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```
例如， 罗马数字 2 写做 II ，即为两个并列的 1。12 写做 XII ，即为 X + II 。 27 写做  XXVII, 即为 XX + V + II 。

通常情况下，罗马数字中小的数字在大的数字的右边。但也存在特例，例如 4 不写做 IIII，而是 IV。数字 1 在数字 5 的左边，所表示的数等于大数 5 减小数 1 得到的数值 4 。同样地，数字 9 表示为 IX。这个特殊的规则只适用于以下六种情况：

I 可以放在 V (5) 和 X (10) 的左边，来表示 4 和 9。

X 可以放在 L (50) 和 C (100) 的左边，来表示 40 和 90。 

C 可以放在 D (500) 和 M (1000) 的左边，来表示 400 和 900。

给定一个整数，将其转为罗马数字。输入确保在 1 到 3999 的范围内。

示例 1:
```
输入: 3
输出: "III"
```
示例 2:
```
输入: 4
输出: "IV"
```
示例 3:
```
输入: 9
输出: "IX"
```
示例 4:
```
输入: 58
输出: "LVIII"
解释: L = 50, V = 5, III = 3.
```
示例 5:
```
输入: 1994
输出: "MCMXCIV"
解释: M = 1000, CM = 900, XC = 90, IV = 4.
```
## 解题
### 语言
java
### 思路

贪心算法，首先将所有符号都写出来，如下

![](https://img-blog.csdnimg.cn/2020041410522079.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTEzOTUwNQ==,size_16,color_FFFFFF,t_70)

查找每一个符号的时候，我们都会寻找能够匹配的最大值

![](https://img-blog.csdnimg.cn/20200414105438254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl8zOTEzOTUwNQ==,size_16,color_FFFFFF,t_70)
![](https://img-blog.csdnimg.cn/20200414105536370.png)

其中两个为 X 值 10，一个 XL 值 40。因为 XL 更大，所以我们采用这种表示法。因此，140 的表示是 CXL。

好了我们直接上图，简单粗暴：（下面是以478为例子）

![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTEuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTIuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTMuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTQuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTUuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTYuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTcuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTguUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTkuUE5H?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTEwLlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTExLlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTEyLlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTEzLlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTE0LlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTE1LlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTE2LlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTE3LlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTE4LlBORw?x-oss-process=image/format,png)
![](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9waWMubGVldGNvZGUtY24uY29tL0ZpZ3VyZXMvMTIvZ3JlZWR5X2FuaW1hdGlvbi9TbGlkZTE5LlBORw?x-oss-process=image/format,png)

然后问题就这么解决啦！

### 代码
```java
class Solution {
   int[] values = {1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1};    
    String[] symbols = {"M","CM","D","CD","C","XC","L","XL","X","IX","V","IV","I"};

    public String intToRoman(int num) {
        StringBuilder sb = new StringBuilder();
        for (int i = 0; i < values.length && num >= 0; i++) {
            while (values[i] <= num) {
                num -= values[i];
                sb.append(symbols[i]);
            }
        }
    return sb.toString();
    }

}
```
