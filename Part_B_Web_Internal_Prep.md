1. Show how map is different from object to store key value pairs with coding example and prove Maps perform better than objects in most of the scenarios involving addition and removal of keys

let obj = {};
let map = new Map();
let userslist = ['john','stephen','ruth','sharon','malliga'];

for(let i=0;i<userslist.length;i++)
{
    obj[i] = userslist[i];
    map.set(i,userslist[i]);
}

let result1;
console.log(obj);
console.log(map);

console.time('Object');
result1 = obj.hasOwnProperty(3);
console.log(result1);
console.timeEnd('Object');


console.time('Map');
let result2;
result2 = map.has(2);
console.log(result2);
console.timeEnd('Map')

 
2. Show how set is different from array to store the value with coding example and prove Sets perform better than Arrays in most of the scenarios involving searching values present in it


let arr = []
let set = new Set();
let userlistname = ['john','stephen','sharon','malliga','ruth'];

for(let i=0;i<userlistname.length;i++)
{
    arr.push(userlistname[i]);
    set.add(userlistname[i]);
}
console.log(arr);
console.log(set);

let result1,result2;

console.time('Array');
result1 = arr.indexOf('stephen') !== -1;
console.log(result1);
console.timeEnd('Array')

console.time('Set');
result2 = set.has('stephen');
console.log(result2);
console.timeEnd('Set')

 


3. Implement a JavaScript promise to perform arithmetic operations. Display result for each operation synchronously using await () method. (Give delay in each promise object using settimeout() method)

const add = (n1,n2) => {
    return new Promise((resolve,reject) => {
        setTimeout(function(){
            resolve("Adding the two Numbers : " + (n1+n2));
        },3000)
    })
}

const sub = (n1,n2) => {
    return new Promise((resolve,reject) => {
        setTimeout(function() {
            resolve("Subtraction os the two Numbers : " + (n1 - n2));
        },3000)
    })
}

const mul = (n1,n2) => {
    return new Promise((resolve,reject) => {
        setTimeout(() => {
            resolve("Multiplication of the two Numbers : " +(n1*n2));
        }, 3000);
    })
}
const div = (n1,n2) => {
    return new Promise((resolve,reject) => {
        setTimeout(() => {
            resolve("Division of the two Numbers : " +(n1/n2));
        }, 3000);
    })
}

let n1 = parseInt(prompt("Enter the first Number: "));
let n2 = parseInt(prompt("Enter the second Number: "));

add(n1,n2).then(function(res) {
    console.log(res);
})
sub(n1,n2).then(function(res) {
    console.log(res);
})
mul(n1,n2).then(function(res) {
    console.log(res);
})
div(n1,n2).then(function(res) {
    console.log(res);
})


4. Write a Javascript program where user passes the location and a function is called which returns a promise, if the location passed is Paris Below is the output expected: "Let's take a trip to Paris" If the location is other than Paris, show the error message "Invalid Location"

let fun=(str)=>{
    return new Promise((resolve,reject)=>{
        let pattern = /Paris/i
        let result = str.match(pattern)
        if(result)
        {
            resolve("Let's take a trip to Paris")
        }
        else
            reject("Invalid Location")
    })
}

let input = prompt("Enter the String : ")

fun(input).then(function(res){
    document.write(res)
}).catch(function(err){
    document.write(err)
})

5. Write a JavaScript program to book a hotel only after booking a flight. [Hint: To achieve this, the promise returned from the bookHotel function is resolved only after resolving the promise from bookFlight function. If the promise gets rejected from bookflight then it won't execute the second function.]


let bookflight = (string) => {
    return new Promise((resolve,reject) => {
        let pattern = /book-flight/i;
        let result = string.match(pattern);

        if(result)
        {
            resolve("Your flight is Booked");
        }
        else
        {
            reject("Flight not Booked");
        }
    })
}

let bookhotel = (string) => {
    return new Promise((resolve,reject) => {
        let pattern = /book-hotel/i;
        let result = string.match(pattern);

        if(result)
        {
            resolve("Your flight is Booked");
        }
        else
        {
            reject("Flight not Booked");
        }
    })
}

let string = prompt("Want to book a flight enter book-flight");
bookflight(string).then(function(res){
    alert(res);
})
let string1 = prompt("Want to book a hotel enter book-hotel");
bookhotel(string1).then(function(res){
    alert(res)
}).catch(function(err){
    alert(res);
})


6.
let check = (kg) => {
    let lbs = 2.2 * kg;
    if (lbs < 100)
        return "underweight";
    else if (lbs >= 100 && lbs <= 150)
        return "you are ok";
    else
        return "obese";
}
let kg = parseInt(prompt("Enter the Weight in kg :")); 
document.write("The person with " + kg + "kg weight is : " + check(kg));


7.
var v = prompt("Enter virus composition");
var b = prompt("Enter blood composition");
var i = 0, j = 0;
var count = 0;
while (i < v.length && j < b.length) {
    if (v[i] == b[j]) {
        i++;
        j++;
        count++;
    } 
    else
        i++;
}
if (count == b.length)
    document.write("Positive");
else
    document.write("Negative");
