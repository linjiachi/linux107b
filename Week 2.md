# 第二週筆記
## 通配符意義
* 通配符通常是 Shell 做 Pathname Expansion 時用到的。說白了一般只用於文件名匹配，它是由 Shell 解析的，舉例來說像是 `find`、`ls`、`cp`、`mv`等指令。

## 常見的通配符
| 通配符 | 匹配 | 指令 | 結果 |
| ----- | ----- | ----- | ---- |
| * | 0或多個字符 | `a*b` | `aabcb`、`axyzb`、`ab`|
| ? | 任意一個字符 | `a?b` | `abb`、`acb`、`a0b` |
| [list] | list 中任意單一字符 | `a[xyz]b` | `axb`、`ayb`、`azb` |
| [!list]<br>[^list] | 除 list 中的任意單一字符 | `a[!0-9]` | `axb`、`ayb`、`azb` |
| [c1-c2] | c1-c2 中的任意單一字符 | `a[0-9]b` | `a0b`、`a1b`、`a2b` |
| [!c1-c2]<br>[^c1-c2] | 不在 c1-c2 中的任意字符 | `a[!0-9]b` | `acb`、`adb` |
| {string1,string2,...} | string1 或 string2 其一字符串 | `a{abc,xyz,123}b` | `aabcb`、`axyzb`、`a123b` |

## 延伸學習
1. [51CTO博客 / linux通配符和正则表达式](https://blog.51cto.com/qibingtuan/1970593)