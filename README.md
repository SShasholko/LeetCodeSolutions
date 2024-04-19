
# Leet_code_solutions

Welcome to my repository of solutions for LeetCode problems! Below you'll find a collection of my solutions to various coding challenges on [LeetCode](https://leetcode.com/). Feel free to explore, learn, and provide feedback.


![Logo](https://doodler.s3.eu-north-1.amazonaws.com/doodler-guy.png)


## About LeetCode

[LeetCode](https://leetcode.com/) is a platform where you can practice coding skills and prepare for technical interviews. It offers a vast array of coding problems across different difficulty levels and categories such as algorithms, data structures, and more.



## Solutions

- [367. Valid Perfect Square](#367-valid-perfect-square)

### 367. Valid Perfect Square
Difficulty: Easy
```bash
  var isPerfectSquare = function(num) {
    if(num<=15){
        if(num===1||num===4||num===9){ return true } 
        else{ return false }
    }
    for(i=1;i<=num/4;i++){
        if(i*i>num){ return false }
        if(i*i===num){ return true }
    }
};
```


