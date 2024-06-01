
# Leet code solutions

Welcome to my repository of solutions for LeetCode problems! Below you'll find a collection of my solutions to various coding challenges on [LeetCode](https://leetcode.com/). Feel free to explore, learn, and provide feedback.


![Logo](https://doodler.s3.eu-north-1.amazonaws.com/doodler-guy.png)


## About LeetCode

[LeetCode](https://leetcode.com/) is a platform where you can practice coding skills and prepare for technical interviews. It offers a vast array of coding problems across different difficulty levels and categories such as algorithms, data structures, and more.



## Solutions

- [136. Single Number (JS)](#136-single-number-js)
- [268. Missing Number (JS)](#268-missing-number-js)
- [367. Valid Perfect Square (JS)](#367-valid-perfect-square-js)
- [3110. Score of a String (JS)](#3110-score-of-a-string-js)

### 136. Single Number (JS)
Difficulty: Easy
```bash
var singleNumber = function(nums) {
  const numsNew = [...nums.sort()]
    for(let i=0;i<numsNew.length;i+=2){
      if(i===numsNew.length-1){
        return numsNew[i]
      } 
        if(numsNew[i]!=numsNew[i+1]){
        return numsNew[i]
      }
    }  
};
```

### 268. Missing Number (JS)
Difficulty: Easy
```bash
var missingNumber = function(nums) {
    nums.sort((a, b) => a - b);
    for(let i=0;i<=nums.length;i++){
        if(nums[i]!=i){
        return i
      }
    }  
};
```

### 367. Valid Perfect Square (JS)
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

### 3110. Score of a String (JS)
Difficulty: Easy
```bash
var scoreOfString = function(s) {
      let sum = 0;
  for(let i=0;i<s.length-1;i++){
    if((s[i+1].charCodeAt(0)-s[i].charCodeAt(0))<0){
        sum+=(s[i+1].charCodeAt(0)-s[i].charCodeAt(0))*(-1)
    }
    else{
        sum+=s[i+1].charCodeAt(0)-s[i].charCodeAt(0)
    }
  }
  return sum
};
```

