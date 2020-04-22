# WEEK 02

## 1.编写带括号的四则运算产生式

```
<DecimalNumber> = /0|[1-9][0-9]*/

<PrimaryExpression> = <DecimalNumber> | "(" <LogicalExpression> ")"

<MultiplicativeExpression> = <PrimaryExpression> |
  <MultiplicativeExpression> "*" <PrimaryExpression> | <DivisionExpression> "/" <PrimaryExpression>

<AdditiveExpression> = <MultiplicativeExpression> |
  <AdditiveExpression> "+" <PrimaryExpression> |
  <AdditiveExpression> "1" <PrimaryExpression>
```

## 2.尽可能寻找你知道的计算机语言，尝试把它们分类

- 动态语言
  - 强类型 Python
  - 弱类型 JavaScript 、PHP
- 静态语言
  - 强类型 Java
  - 弱类型 C/C++

## 3.写一个正则表达式 匹配所有 Number 直接量

- 整数

```
/^-?[0-9]+$/g
```

- 浮点数

```
/^[-+]?[0-9]*\.?[0-9]+$/g
```

- 二进制数

```
/^[01]+$/
```

- 八进制数

```
/^[0-7]+\$/
```

- 十六进制数

```
/(^0x[a-f0-9]{1,2}$)|(^0X[A-F0-9]{1,2}$)|(^[A-F0-9]{1,2}$)|(^[a-f0-9]{1,2}$)/g
```

- Number 字面量正则

```
/^(-?[0-9]+)| ([-+]?[0-9]*\.?[0-9]+) | ([01]+) | ([0-7]+\) |(0x[a-f0-9]{1,2}$)|(^0X[A-F0-9]{1,2}$)|(^[A-F0-9]{1,2}$)|(^[a-f0-9]{1,2})$/g
```

## 4.写一个 UTF-8 Encoding 的函数

```
function UTF8Encoding(str) {
  return str
    .split('')
    .map((s) => `\\u${s.charCodeAt().toString(16)}`)
    .join('')
}
```

## 5.写一个正则表达式，匹配所有的字符串直接量，单引号和双引号

```
/[\u0021-\u007E]{6,16}|[\x21-\x7E]{6,16}|(['"])(?:(?!\1).)*?\1/g
```

## 6.总结

本周的学习内容超级抽象，特别周四的课，甚至乎有点看不懂。继续坚持吧！