
# Leet code solutions

Welcome to my repository of solutions for LeetCode problems! Below you'll find a collection of my solutions to various coding challenges on [LeetCode](https://leetcode.com/). Feel free to explore, learn, and provide feedback.


![Logo](https://doodler.s3.eu-north-1.amazonaws.com/doodler-guy.png)


## About LeetCode

[LeetCode](https://leetcode.com/) is a platform where you can practice coding skills and prepare for technical interviews. It offers a vast array of coding problems across different difficulty levels and categories such as algorithms, data structures, and more.



## Solutions

- [35. Search Insert Position (JS)](#35-search-insert-position-js)
- [75. Sort Colors (JS)](#75-sort-colors-js)
- [136. Single Number (JS)](#136-single-number-js)
- [169. Majority Element (JS)](#169-majority-element-js)
- [228. Summary Ranges (JS)](#228-summary-ranges-js)
- [231. Power of Two (JS)](#231-power-of-two-js)
- [268. Missing Number (JS)](#268-missing-number-js)
- [342. Power of Four (JS)](#342-power-of-four-js)
- [344. Reverse String (JS)](#344-reverse-string-js)
- [367. Valid Perfect Square (JS)](#367-valid-perfect-square-js)
- [605. Can Place Flowers (JS)](#605-can-place-flowers-js)
- [945. Minimum Increment to Make Array Unique (JS)](#945-minimum-increment-to-make-array-unique-js)
- [1002. Find Common Characters (JS)](#1002-find-common-characters-js)
- [1122. Relative Sort Array (JS)](#1122-relative-sort-array-js)
- [1154. Day of the Year (JS)](#1154-day-of-the-year-js)
- [2974. Minimum Number Game (JS)](#2974-minimum-number-game-js)
- [3110. Score of a String (JS)](#3110-score-of-a-string-js)


### 35. Search Insert Position (JS)
Difficulty: Easy
```bash
var searchInsert = function(nums, target) {
    let i=0
    for(;nums[i]<=target;i++){
      if (nums[i]==target){
        return i
      }
    }
     return i
};
```
Binary search
```bash
var searchInsert = function(nums, target) {
    let low = 0
    let high = nums.length-1
    let mid;
    if(target<nums[0]){
         return 0
    }
    if(target>nums[nums.length-1]){
         return nums.length
    }
    while(low<=high){
      mid = Math.ceil((low+high)/2)
      if(nums[mid]==target){
        return mid
      }
      if(nums[mid]>target){
        high=mid-1
      }
      if(nums[mid]<target){
        low = mid+1
      }
    }
if(nums[mid]>target){
    return mid
} else
    return mid+1
};
```

### 75. Sort Colors (JS)
Difficulty: Medium
```bash
var sortColors = function(nums) {
      let num;
    for(let i=0;i<nums.length;i++)
    {
      for(let j=0;j<nums.length;j++)
      {
        if(nums[j]>nums[i]){
          num = nums[i]
          nums[i] = nums[j]
          nums[j] = num
        }
      }
    }
};
```

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

### 169. Majority Element (JS)
Difficulty: Easy
```bash
var majorityElement = function(nums) {
    if(nums.length>1){
nums.sort((a,b)=>a-b)
let num = Math.floor(nums.length/2)
return nums[num]}
    else return nums[0]
};
```

### 228. Summary Ranges (JS)
Difficulty: Easy
```bash
let line = ''
    const newAr = []
    for(let i=0;i<nums.length;i++){
                if(nums[i+1]!=nums[i]+1){
        line = line + nums[i]
        newAr.push(line)
        }
        if(nums[i+1]==nums[i]+1){
            line=nums[i] + '->'
            for(let j=i;j<nums.length;j++){
                if(nums[j+1]!=nums[j]+1)
                {
                    line+=nums[j]
                    newAr.push(line)
                    i=j
                    break
                }
            }
        }
        line=''
    }
    return newAr
```

### 231. Power of Two (JS)
Difficulty: Easy
```bash
var isPowerOfTwo = function(n) {
    if(n==1) return true
        if(n%2==0){
       if(Number.isInteger(Math.log2(n))){
         return true
       }
       else return false
    }
    else return false 
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

### 342. Power of Four (JS)
Difficulty: Easy
```bash
var isPowerOfFour = function(n) {
    if(n==1) return true
    if(n%4==0){
      if(Number.isInteger(Math.log2(n)/Math.log2(4)))
        return true
      else
       return false
    }
    else return false
};
```

### 344. Reverse String (JS)
Difficulty: Easy
```bash
var reverseString = function(s) {
    let elem1;
    let elem2;
    for(let i = 0;i<s.length/2;i++){
      elem1 = s[i]
      elem2 = s[s.length-1-i]
      s[i] = elem2;
      s[s.length-i-1] = elem1
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

### 605. Can Place Flowers (JS)
Difficulty: Easy
```bash
var canPlaceFlowers = function(flowerbed, n) {
let freePots = 0;
if(flowerbed.length==1){
          if(n==1&&flowerbed[0]==0||n==0&&flowerbed[0]==1||n==0&&flowerbed[0]==0) return true
          else return false} 
if(flowerbed.length==2){
          if((n==1&&flowerbed[0]==0&&flowerbed[1]==0)||n==0) return true
          else return false } 
if(flowerbed[0]==0&&flowerbed[1]==0) freePots++; 
if(flowerbed[flowerbed.length-1]==0&&flowerbed[flowerbed.length-2]==0)  freePots++;

for(let i=2;i<=flowerbed.length-3;i++){
    if(flowerbed[i]==0&&flowerbed[i-1]==0&&flowerbed[i+1]==0){
      freePots++;
      i+=1
    }
  }
if(freePots>=n) return true
else return false
};
```

### 945. Minimum Increment to Make Array Unique (JS)
Difficulty: Medium
```bash
var minIncrementForUnique = function(nums) {
    nums.sort((a,b)=>a-b)
    let count = 0
    for(let i=1;i<nums.length;i++)
    {
      if(nums[i]<=nums[i-1]){
        while(nums[i]<=nums[i-1]){
          nums[i]++
          count++;
        }
      }
    }
    return count
};
```

### 1002. Find Common Characters (JS)
Difficulty: Easy
```bash
const res = []
    let count = 0
    let newW
    for(let i=0;i<words[0].length;i++){   
      for(let j=1;j<words.length;j++){
          if(words[j].match(words[0][i]))
          {
           newW = words[j].replace(words[0][i],"")
           words[j] = newW
            count++
          }
      }
      if(count==words.length-1){
        res.push(words[0][i])
      }
      count = 0
    }
    return res
};
```

### 1122. Relative Sort Array (JS)
Difficulty: Easy
```bash
var relativeSortArray = function(arr1, arr2) {
        const newArray = []
    for(let i=0;i<arr2.length;i++){
        let elem = arr2[i]
        
        for(let j=0;j<arr1.length;j++){
            if(arr1[j]==elem){
                newArray.push(elem)
                arr1.splice(j,1)
                j--
            }
        }
    }
    arr1.sort((a,b)=>a-b)
    for(let i=0;i<arr1.length;i++){
        newArray.push(arr1[i])
    }
    return newArray
};
```


### 1154. Day of the Year (JS)
Difficulty: Easy
```bash
var dayOfYear = function(date) {
    let year = date.substr(0,4);
    let day1 = new Date(date)
    let day0 = new Date(year + '-01-01')
    let days = (day1-day0)/1000/60/60/24;
    return days+1
};
```

### 2974. Minimum Number Game (JS)
Difficulty: Easy
```bash
var numberGame = function(nums) {
        nums.sort((a,b)=>a-b)
    const resArray = []
    for(let i=0;i<nums.length;i=i+2){
      resArray.push(nums[i+1])
      resArray.push(nums[i])
    }
   return resArray
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

