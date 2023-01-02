## Sum All Odd Fibonacci Numbers

Given a positive integer num, return the sum of all odd Fibonacci numbers that are less than or equal to num.

The first two numbers in the Fibonacci sequence are 1 and 1. Every additional number in the sequence is the sum of the two previous numbers. The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5 and 8.

For example, sumFibs(10) should return 10 because all odd Fibonacci numbers less than or equal to 10 are 1, 1, 3, and 5.

## Solution

```js
function sumFibs(num) {
  let arr = [];
  let c = 0;
// Prints the "num" number of Fibonacci Numbers
  for(let i = 3; i<= num; i++){
   
    arr[0] = 0;
    arr[1] = 1;
    arr[2] = 1;
    arr.push(arr[i-1] + arr[i-2]);
    
    if (arr[i] <= num){
      c = i+1;
    }
  }

  let arr2 = arr.slice(0, c);
  let arr3 = arr2.filter((n) => n % 2 == 1);


  return arr3.reduce((a, b) => a + b, 0);
}

console.log(sumFibs(10000));

```
