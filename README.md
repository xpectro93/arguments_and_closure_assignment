# Exercises

1. Create two functions: `double` and `square`.
`double` should take a number and return the number times two.
`square` should take a number and return the number squared.

const double = (aNumber) => {
  return aNumber*2
}

const square =(num) => {
  return Math.pow (num, 2)
}
const doubleSquare =(daNum) => {
   return square(double(daNum));

}
console.log(doubleSquare(2.5))

 * Create a third function `doubleSquare` that uses both of the functions to return a number that is first doubled and then squared.

2. Create a function `classyGreeting` that takes as input the strings `firstName`  and `lastName`,
and returns a string with a greeting using the two.

const classyG = (firstName, lastName) => {
  return `Hello there, ${firstName} ${lastName}`
}

  * Create a second function `yell`  that takes string as input and returns the string in all capitalized letters.

    const yell = (aString) => {
      let upperCase =""
      for(let i = 0; i < aString.length; i++){

        upperCase += aString[i].toUpperCase()
        //upperCase.push(aString[i].toUpperCase());

      }
     return upperCase
    }

  * Create a third function  `yellGreeting`  that will take the `firstName`  and `lastName`  as inputs and yell a greeting using the two.

  const yellGreeting = (first = "Random", last = "Stranger") => {
   let screaming ="";
   screaming = yell(classyG(first, last));
  return screaming;
  }
  console.log(yellGreeting())




3. The [concat](https://www.w3schools.com/jsreF/jsref_concat_array.asp) array method is used to merge two (or more) arrays.
Write a `removeDupes` function that takes an array as an argument and returns a copy without any duplicate elements.
Then, write a function `concatAndRemoveDupes`  that combines two arrays and removes any duplicates.

  _Hint:_ Use the array method `includes`, an object, or a Set. Or the spread operator instead of concat.
  [1, 2, 3].includes(1) ==> true  

  let testarr = [1,2,3,3,3,4];
  let testarr2 =[1,2,3,4,4,4,5]

  const remDup = (testArr) => {
    let noDupess = [...new Set(testArr)]
   return noDupess
  }

    remDup()

  const concatAndRemoveDupes = (arr1,arr2) => {
      let arr3 =(arr1.concat(arr2));
      let combArr = [...new Set(arr3)];

      return combArr

    }
  console.log(concatAndRemoveDupes(testarr, testarr2))

4. Given a list of grades, we can get the median grade by sorting the list and taking the middle element, or the average of the two middle elements.
Create the functions `sort` and `middleElement`, and then use them to create the functions `median`.

let gradess= [91, 85, 100, 92, 88];

console.log(median(grades)); // Should log 91

const sort = (rades) => {
  let sorted [];
  sorted =(rades.sort(function(a, b){return a-b}))
return sorted
};
const middleElement = (middlee) => {
  let sorted = sort(middlee);
  let answer = 0;
  let middle = 0;
  if(sorted.length%2===1){
    console.log(Math.floor(sorted.length/2))
     middle = answer = sorted[Math.floor(sorted.length/2)]

  }else {
    console.log(sorted.length/2)
    answer = (sorted[sorted.length/2] + (sorted[sorted.length/2]-1))/2
  }
 return answer
}


5. Write a function called `repeat` that takes in a string and numberOfTimes. The function should log to the screen the string however
many times as numberOfTimes. If the user does not enter a numberOfTimes it should default to 2.

let aString = "Can u hear me now?!?..how about now?!"
const repeat = (leString,numOtimes = 2) =>{
  for(var i = 0; i < numOtimes; i++){
    console.log(`${leString} has appeared ${i + 1} times`)

  }
}
repeat(aString, 4)


6. Using the spread operator, write a function that can take any number of arguments and return the sum of all of them.
let testArg = "12345"

const addArg = (...arg) => {
  let sum = 0;
  for(var i = 0; i < arg.length; i++){
  sum += arg[i]
}
return sum
}

7. Write a function called `adder` takes in one number and returns a function that will add that number with another number.
Using `adder` create an `add5` and an `add9` function. Hint: Closures!
