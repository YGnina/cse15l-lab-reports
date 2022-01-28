
## [First bug](https://github.com/YGnina/markdown-parse/blob/main/MarkdownParse.java)
![Image](/pictures/lab2pic1.jpg)
![Image](/pictures/lab2bug1.jpeg)

In this part, there is an `ArrayIndexOutOfBoundsException` as is shown in the terminal, which clearly is the symptom. It gets an unexpected result 0, which is out of the bounds. In order to solve this problem, we added an `if` statement to print out the invalid input and break the `while` loop.


## [Second bug](https://github.com/YGnina/markdown-parse/blob/main/MarkdownParseTest.java)
![Image](/pictures/lab2pic2.jpg)
![Image](/pictures/lab2bug2.jpg)

In this part, lots of symbols cannot be found. As is shown in the terminal, those symbols only appear in a specific class. For example, `ArrayList<>` can only befound in `ArrayList` class instead of the class we created. In order to solve this, we import the required packages.

## [Third bug]()
