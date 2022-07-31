1.
function fun(num){
    return new Promise(function(resolve,reject){
        if(num>20)
            resolve("Greater than 20")
        else
            reject("Less than 20")
    })
}

var input = prompt("Enter the number :")

fun(input).then(
    function(v){
        alert(v)
    }).catch(
        function(error){
            alert(error)
        }
    );

2.
let val = new Promise(
    function(resolve,reject){
        alert = false
        if(!alert)
        resolve("The promise is resolved")
        else
        reject("The promise is not reslove")
    })

val.then(function Sucessvalue(result){
    document.write(result)
}).catch(function Sucessvalue(){
    document.write("Hello")
}).then(function Sucessvalue(){
    alert("done")
    document.write("Hi")
})

3.
var n = prompt("Enter the n0. of items in set :")

var x = new Set()

for(let i=0;i<n;i++)
{
    x.add(prompt("Enter element :"+i+1))
}

x.forEach(function(value){
    document.write(value)
})

4.
var n = prompt("Enter the n0. of items in set :")
var x = new Map()
for(let i=0;i<n;i++)
{
    x.set(i,prompt("Enter element :"+i+1))
}
x.forEach(function(value,key){
    document.write("Key : "+key+" Value : "+value+"<br>")
})

5.
var n = prompt("Enter the n0. of items in set :")
var arr = new Array()
let arr1 = new Array()
for(let i=0;i<n;i++)
{
    arr[i]=prompt("Enter element :"+i+1)
    arr1[i]=arr[i]
}
let m = prompt("Enter the Index : ")
let o = prompt("Enter the no of elementd to be deleted : ")
let p = prompt("Enter the element to be inserted : ")
arr.splice(m,o,p)
document.write("Old array : "+arr1+"<br> New array : "+arr+"<br>")

6.
<body>
    <input type="string" id="s1" />
    <button id="btn">click me</button>
    <script>
        document.getElementById("btn").addEventListener("click", fun);
        function fun(){
        let x=document.getElementById("s1").value;
        x = x.split("")
        x.sort()
        let r=""
        for(let i=0;i<x.length;i++)
        r+=x[i];        
        document.getElementById("demo").innerHTML=r;
    }
    </script>
    <p id="demo"></p>
</body>

7.
let n = parseInt(prompt("Enter the no."));
let fun = (n) => {
    let rev = 0;
    while (n != 0) {
        rev = rev * 10 + n % 10;
        n = parseInt(n / 10);
    }
    return rev;
}
alert("the reverse of " + n + " is " + fun(n));

8.
var evenSum =(a) =>{
    sum=0
    for(i=0;i<a.length;i++){
        if(a[i]%2==0)
            sum+=parseInt(a[i]);
    }
    return sum
}
var input = prompt("Enter the input : ")
var a = input.split(",")
document.write("Sum of Even Numbers is : "+evenSum(a))

9.
let jumpSearch = (arr, x, n) => {
    // Finding block size to be jumped
    let step = Math.sqrt(n); // Finding the block where element is
    // present (if it is present)
    let prev = 0;
    while (arr[Math.min(step, n) - 1] < x) {
        prev = step;
        step += Math.sqrt(n); 
        if (prev >= n)
            return -1;
    }
    // Doing a linear search for x in block
    // beginning with prev.
    while (arr[prev] < x) {
        prev++; // If we reached next block or end of
        // array, element is not present.
        if (prev == Math.min(step, n)) 
        return -1;
    }
    // If element is found
    if (arr[prev] == x)
        return prev;
    return -1;
}
// Driver program to test function
let arr = [0, 1, 1, 2, 3, 5, 8, 13, 21,
    34, 55, 89, 144, 233, 377, 610]; let x = 55;
let n = arr.length;
// Find the index of 'x' using Jump Search
let index = jumpSearch(arr, x, n); // Print the index where 'x' is located
document.write(`Number ${x} is at index ${index}`)

10. 
//175 - true

let disarium=(n)=>{
    let a = n.split("")
    let sum = 0
    for(var i=0;i<a.length;i++)
        sum += Math.pow(parseInt(a[i]),i+1)
    return n==sum
}
for(let i=1;i<=100;i++){
    if(disarium(i.toString()))
        document.write(i+"<br>")
}

11.
let encrypt = (text, s) => {
    let result = "";
    for (let i = 0; i < text.length; i++) {
        let char = text[i]; 
        if (char.toUpperCase()) {
            let ch = String.fromCharCode((char.charCodeAt(0) + s - 65) % 26 + 65); 
            result += ch;
        } else {
            let ch = String.fromCharCode((char.charCodeAt(0) + s - 97) % 26 + 97); 
            result += ch;
        }
    } 
    return result;
}
let text = prompt("Enter the Plain Text : ")
let s = prompt("Enter the shift : ")
document.write("Text :" + text + "<br>"); 
document.write("Shift :" + s + "<br>"); 
document.write("Cipher :" + encrypt(text, s) + "<br>");


12. Write a JavaScript function. a. to capitalize the first letter of each word in a string. b. to insert a string within a string at a particular position c. to check whether an `input` is a string or not d. to split a string and convert it into an array of words

const s = prompt("Enter the String : ")

let f1 = () => {
    // let s = prompt("Enter the string : ");
    document.write("<br>1.<br>")
    if (s[0] >= "a" && s[0] <= "z") {
        let r = s.charCodeAt(s[0]) - 97;
        document.write("After updating string is : " + String.fromCharCode(65 + r) + s.slice(1));
    }
    else
    document.write("After updating string is : " + s);
};
let f2 = () => {
    document.write("<br>2.<br>")
    // let s = prompt("Enter the string : ");
    document.write(s + " string after inserting a string in between : " + s.slice(0, 3) + "bar" + s.slice(3));
};
let f3 = () => {
    document.write("<br>3.<br>")
    // let s = prompt("Enter the string : "); 
    for (let i = 0; i < s.length; i++) {
        if (!(s[i] >= "A" && s[i] <= "Z") && !(s[i] >= "a" && s[i] <= "z")) {
            document.write("Not a string"); 
            return;
        }
    } document.write("Is a string");
};
let f4 = () => {
    document.write("<br>4.<br>")
    // let s = prompt("Enter the string : ");
    let array = s.split(" ");
    document.write(s + " after splitting :" + array);
};
f1();
f2();
f3();
f4();

13.
let multiply = (arr) => {
    let mul = arr.map((num) => num * 10);
    return mul;
}
let size = parseInt(prompt("Enter the size of the array:"))

let arr = new Array(size);

for (let i = 0; i < size; i++) {
    arr[i] = parseInt(prompt(i + 1 + "number"));
}
document.write(arr + " <br>-> Array after multiplying -> " + multiply(arr));

14.
var Student={
    Name: "Mohan Kumar",
    Dept: "ISE",
    id : 056
};
document.write(Object.values(Student))