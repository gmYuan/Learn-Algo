# LeetCode345- 反转字符串中的元音字符

# 题目描述

编写一个函数，以字符串作为输入，反转该字符串中的元音字母。

示例1:
```
输入: "hello"
输出: "holle"
```

示例2:
```
输入: "leetcode"
输出: "leotcede"
```

## 参考文档

[01 双指针实现](https://github.com/CyC2018/CS-Notes/blob/master/notes/Leetcode%20%E9%A2%98%E8%A7%A3%20-%20%E5%8F%8C%E6%8C%87%E9%92%88.md)


## 思维技巧

![双指针](https://s1.ax1x.com/2020/05/24/tpkLiF.png)

## 代码实现

```js
/**
 * @param {string} s
 * @return {string}
 */
var reverseVowels = function(s) {
  let temp = s.split('')
  let head = 0, tail = temp.length - 1
  const vowels = new Set(['a', 'e', 'i', 'o', 'u', 'A', 'E', 'I', 'O', 'U'])
  
  if (s.length <= 1) return s;
  while (head < tail) {
    if (!vowels.has(temp[head])) {
      head++
    }
    if (!vowels.has(temp[tail])) {
      tail--
    }

    if (vowels.has(temp[head]) && vowels.has(temp[tail])) {
      [temp[head], temp[tail]] = [temp[tail], temp[head]]
      head++
      tail--
    }
  }

  return temp.join('')
}
```