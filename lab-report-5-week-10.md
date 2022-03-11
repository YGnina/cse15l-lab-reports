In this lab, we explore the difference between our implementation and the implementation provided for lab 9. 
In order to do this, I use `diff` to show the difference. We can find the lines where differences exist in the `results.txt` but don't know which test exactly, so I seach it manually.

We got 5 differences by running `diff` on the files in our group.
```
270c270
< [/bar\* "ti\*tle"]
---
> []
492c492
< []
---
> [/f&ouml;&ouml; "f&ouml;&ouml;"]
692c692
< []
---
> [url &quot;tit&quot;]
866,867c866
< [<foo
< bar>]
--
> []
869c869
< []
---
> [<foo
bar>]

```


## 270 --> 22.md
![Image](/pictures/lab5pic1.png)

![Image](/pictures/lab5pic2.jpg)

![Image](/pictures/lab5exp1.jpg)

As we use [CommonMark](https://spec.commonmark.org/dingus/) to check, the expected output should be a valid link. My implementation returns the correct result while the instructor's gets a differet one.


The instructor's gives an empty link, which might because it has problem identifying links when it has extra symbols.
When we check the given code as below, we notice in the `if` statement, it won't add the link if it contains space or newline. This makes 22.md fail. 
We should consider more possibilities so that even if the link has space it can be valid.

![Image](/pictures/lab5c1.jpg)

## 866 --> 489.md
![Image](/pictures/lab5pic4.png)

![Image](/pictures/lab5pic3.jpg)

![Image](/pictures/lab5exp2.jpg)

Again, as we use [CommonMark](https://spec.commonmark.org/dingus/) to check, the expected output should be `[link](foo bar)`, which is not a valid link. It seems that the instructor's is correct while mine is not.
Ours identify it as a valid link. When we check our code as below, we notice it's too simple to check the spaces or newlines. So we should add more details before the `while` loop.

![Image](/pictures/lab5c2.jpg)
