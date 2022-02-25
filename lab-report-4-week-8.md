[My markdown-parse](https://github.com/YGnina/markdown-parse)

[Viewed markdown-parse](https://github.com/BenX-64/markdown-parse) 

## Snippet 1
```
`[a link`](url.com)

[another link](`google.com)`

[`cod[e`](google.com)

[`code]`](ucsd.edu)
```

The expected output is ```[`google.com, google.com, ucsd.edu]```

To test it, I write a test method as below:

![Image](/pictures/lab4test1.jpg)

However, my output is `AssertionError`

![Image](/pictures/lab4my1.jpg)

The other one gets

![Image](/pictures/lab4o1.jpg)

In this case, I think it doesn't check if there's any symbols before the brackets. Since it's hard to know if there's anything before `[`, the code would consider it as a valid link and print it out anyway. I think I can create a method to check if it's empty before the brackets.

## Snippet 2

```
[a [nested link](a.com)](b.com)

[a nested parenthesized url](a.com(()))

[some escaped \[ brackets \]](example.com)
```

The expexted output is `[a.com, a.com(()), example.com]`

To test it, I write a test method as below:

![Image](/pictures/lab4test2.jpg)

However, my output is `AssertionError`

![Image](/pictures/lab4my2.jpg)

The other one gets

![Image](/pictures/lab4o2.jpg)

In this case, the difference is actually very little. It is unable to check nested parentheses. I think I can add more variable or something to check and get all the parentheses.


## Snippet 3

```
[this title text is really long and takes up more than 
one line

and has some line breaks](
    https://www.twitter.com
)

[this title text is really long and takes up more than 
one line](
    https://ucsd-cse15l-w22.github.io/
)


[this link doesn't have a closing parenthesis](github.com

And there's still some more text after that.

[this link doesn't have a closing parenthesis for a while](https://cse.ucsd.edu/



)

And then there's more text
```

The expected ouput is `[https://ucsd-cse15l-w22.github.io/]`

To test it, I write a test method as below:

![Image](/pictures/lab4test3.jpg)

However, my output is `AssertionError`

![Image](/pictures/lab4my3.jpg)

The other one gets

![Image](/pictures/lab4o3.jpg)

In this case, the output is quite different with expected somehow. It should only print out the link of github, but it considers everything as a link. Though it looks horrible, usually it's easier to fix. I think it can check if there are any bracket between a pair of parentheses and the spaces to fix this issue.
