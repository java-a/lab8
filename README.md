# Lab 8
> 1. 复习巩固所学知识
> 2. 学习编写项目文档
> 3. 课程及Project答疑

## Lab 7 Code Review

传送门：https://github.com/java-a/lab7/issues/2 。

> 阅读样例代码，完成思考题。

> 提交：将所有回答写在同一个文档中，以学号+姓名命名，如16302010002李云帆.txt、16302010063郭涵青.docx。上传至 FTP WORK_UPLOAD > CodeReview > lab7 目录。

> Deadline: 2016.11.08 23:59:59 (UTC+8)

## Problem 1: Concept

1. The data types of the Java programming language are divided into two categories:  ( ) and ( ).
2. 017 = 0x( )
3. The ( ) is optional in Switch Statement, and can be used to perform actions when none of the specified cases matches the switch-expression.

## Problem 2: Lottery(彩票)

> 考试题是完整的程序编写，为节省时间，lab课上只需填空

Software school will establish the SS Lottery. And you are required to finish the lottery program. According to the discussion, your program should randomly generate a “Winning Number”, an integer in [0, 99]. And then the player will input two digits from 0 to 9. Below are the winning rules:

1)        1st Prize: all the two player digits match the digits in the Winning Number.

2)        2nd Prize: only one player digit matches a digit in the Winning Number.

3)        3rd Prize: the sum of the player digits equals the sum of the Winning Number digits.

For example, the Winning Number is 72 (we thinkthe Winning Number digits are 7 and 2). And then player A selects 7 and 2; player B selects 0, 2; player C selects 4, 5. So player A wins the 1st prize, player B wins the 2nd prize, and player C wins the 3rd prize. 

Moreover, if the Winning Number is from 0 to 9, we think 0 is also a Winning Number digit. For instance, if the Winning Number is 9, then the Winning Number digits are 0 and 9.

Please fill the blanks below

```java
import java.util.Scanner;

public class Lottery {
    public static boolean firstPrize(int[] player, int[] winner) {
       if (___________(1)___________) {
            return true;
        } else {
            return false;
        }
    }

    public static boolean secondPrize(int[] player, int[] winner) {
        if (___________(2)___________) {
            return true;
        } else {
            return false;
        }
    }

    public static boolean thirdPrize(int[] player, int[] winner) {
        int playerSum = 0;
        int winnerSum = 0;
        for (int i = 0; i < player.length; i++) {
          ___________(3)___________;
        }

        for (int i = 0; i < winner.length; i++) {
          ___________(4)___________;
        }

        return playerSum == winnerSum;
    }

    public static void main(String[] argv) {
        int digitSize = 2;

        // Generate the Winning Number
        double randomNumber = ___________(5)___________;
        int winningNumber = (int) Math.floor(randomNumber);
        int winningDigits[] = new int[digitSize];
        winningDigits[0] = ___________(6)___________;
        winningDigits[1] = ___________(7)___________;

        // Waiting the player to input
        int counter = 0;
        int playerDigits[] = new int[digitSize];
        Scanner input = new Scanner(System.in);
        while (___________(8)___________) {
            System.out.println("Please input a digit from 0 to 9:");
            String digit = input.next();
            if (digit.length() == 1 && digit.charAt(0) >= '0' && digit.charAt(0) <= '9') {
                playerDigits[counter++] = ___________(9)___________;
            }
        }

        // Compare the digits
        String result = "";
        if (___________(10)___________) {
            result = "You win the first prize.";
        } else if (secondPrize(playerDigits, winningDigits)) {
            result = "You win the second prize.";
        } else if (thirdPrize(playerDigits, winningDigits)) {
            result = "You win the third prize.";
        } else {
            result = "Thanks for your playing.";
        }

        // Print the result
        System.out.println(“the winning number is ” + winningNumber);
        System.out.println(result);
    }
}
```

## Project 文档指导

期中project只要求编写程序设计文档，请参考[设计文档要求](https://github.com/java-a/project1/issues/4)
