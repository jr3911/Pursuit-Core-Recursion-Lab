# Recursion Exercises

- ### Sum of all from 1 to n

Write a function that takes in a number as input and recursively finds the sum of all numbers up to and including that number.

```swift
input: 6
output: 21

//21 = 6 + 5 + 4 + 3 + 2 + 1

func sumAllFromOneToN(n: Int) -> Int {
    var sum = n

    //Base Case
    if n <= 0 { return 0 }

    //Recursive Call
    return sum + sumAllFromOneToN(n: n - 1)
}

```


- ### Multiply array

Write a function called `multArr` that takes in an array of numbers as an argument and recursively multiplies together all of the values in the array.

```swift
multArr([2, 3, 5]); // returns 30
multArr([5, 5, 1, 2]); //returns 50

func multArr(array nums: [Int]) -> Int {
    //Base Case
    if nums.count == 1 { return nums[0] }

    //Recursive Call
    let firstElement = nums[0]
    let remainingElements = Array(nums[1...])
    return firstElement * multArr(array: remainingElements)
}
```

- ### Concatenate array

Write a function called `concatArr` that takes in an array of strings as an argument and recursively concatenates the strings together into a single string, with spaces between each original string.

```swift
concatArr(['is', 'it', 'tomorrow']); // returns 'is it tomorrow'
concatArr(['or', 'just', 'the', 'end', 'of', 'time']); //returns 'or just the end of time'

func concatArr(_ arr: [String]) -> String {
    //Base Case
    if arr.count == 1 { return arr[0] }

    //Recursive Call
    let firstElement = arr[0]
    let remainingElements = Array(arr[1...])
    return "\(firstElement) \(concatArr(remainingElements))"
}
```

- ### Sum evens

Write a function called `sumEvens` that takes in an array of numbers as an argument and recursively sums only the even numbers in the array.

```swift
sumEvens([2, 3, 5, 6]); // returns 8
sumEvens([10, 5, 1, 2, 12]); //returns 24

func sumEvens(_ arr: [Int]) -> Int {
    //Base Case
    if arr.count == 1 {
        if arr[0] % 2 == 0 { return arr[0] }
        else { return 0 }
    }

    //Recursive Call
    let firstElement = arr[0] % 2 == 0 ? arr[0] : 0
    let remainingElements = Array(arr[1...])
    return firstElement + sumEvens(remainingElements)
}
```

- ### Recursive range

Write a function called `range` which takes in two numbers (num1, num2) as arguments. The function should return an array of numbers between num1 and num2.

```swift
range(2,10); // returns [2, 3, 4, 5, 6,7, 8, 9, 10]
range(17,20); // returns [17, 18, 19, 20]

func range(_ num1: Int, _ num2: Int) -> [Int] {
    //Base Case
    if num1 == num2 { return [num1] }

    //Recursive Call
    return [num1] + range(num1 + 1, num2)
}
```


- ### Triple Step

A child is running up a staircase with n steps and can hop either 1 step 2 steps or 3 steps at a time. Write a function called 'tripleStep', that takes in an argument `n` that represents the number of steps in the staircase, and returns a count of how many possible ways the child can run up the stairs.

```swift
tripleStep(3); //returns 4
tripleStep(4); //returns 7
tripleStep(5); //returns 13
tripleStep(10); //returns 274

func tripleStep(_ n: Int) -> Int {
    //Base Case
    if n == 0 || n == 1 { return 1 }
    else if n == 2 { return 2 }

    //Recursive Call
    return tripleStep(n-3) + tripleStep(n-2) + tripleStep(n-1)
}
```

Source: Cracking the Coding Interview

- ### Coin Combos

Given an infinite number of quarters, dimes, nickels, and pennies, write code to calculate the number of possible ways of giving exact change for `n` cents.

In other words, write a function called `coinCombos` that takes in one argument: `n`, which represents the total amount of money (in cents) that you need to make change for. Your function should return the amount of possible combinations you can make to return that exact amount of change.

For example:
```swift
coinCombos(5); //returns 2
coinCombos(10); //returns 4
coinCombos(25); //returns 13
coinCombos(60); //returns 73
```

Source: CTCI

# Resources
- [JavaScript Recursion Exercises](http://www.w3resource.com/javascript-exercises/javascript-recursion-functions-exercises.php)
- [Swift Recursion Exercises](https://www.weheartswift.com/recursion/)
