学习笔记

1、三元运算符可多条件判断
```$xslt
cell.innerText = pattern[i][j] ==2?"❌":pattern[i][j]==1?"⭕️": ''
```
2、ife是什么?

3、使用{}反复使用一个let 声明的变量

4、跳出两层循环
```$xslt
outer:for (let i = 0; i < 3; i++) {
            for (let j = 0; j < 3; j++) {
                if (条件) {
                    break outer
                }

            }
        }
```

5、二维数组改一维数组
> [i,j] => i*3+ j

一个好处：
* 二维数组克隆
```$xslt
JSON.parse(JSON.stringify(pattern))
```
* 一维数组克隆
```$xslt
Object.create(pattern)
```

6、
