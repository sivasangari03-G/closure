closure:

//Create a function called toggler using closures

function toggler() {
    let num1 = 1;
    function toggler1() {
        console.log(num1);
        let num2 = 2
        function toggler2() {
            console.log(num2);
            let num3 = 3
            function toggler3() {
                console.log(num3);
            }
            return toggler3
        }
        return toggler2
    }
    return toggler1
}

const toggle = toggler();
toggle()()();


2)  What are IIFE?
	 An IIFE (Immediately Invoked Function Expression) is a JavaScript function that runs as soon as it is defined.

example: index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="another.js"></script>

    <script src="core.js"></script>

</head>
<body>
    
</body>
</html>

code.js:-
(function (word) {
    let prefix = "code js"
    console.log(prefix+word);
})("hello world")

var prefix = "code prefix"
console.log(prefix);

another.js:-
var prefix = "another js"

3)What is currying?
	currying is when a function — instead of taking all arguments at one time — takes the first one and returns a new function, which takes the second one and returns a new function, which takes the third one, etc. until all arguments are completed.
  Currying is helpful when we have to frequently call a function with a fixed argument.
  It can be done using bind method or closure.

Examples:
let multiple = function (x,y) {
    return x*y
}
let multipleByThree = multiple.bind(this, 3)
console.log(multipleByThree(2));

const sendRequest = (greet) => (name) => (message) =>
	`${greet} ${name}, ${message}`;
console.log(sendRequest("Hello")("John")("Please can you add me to your Linkedin network?"));

let mul = function (x) {
	return function (y) {
		return x * y;
	};
};
let multiplyByTwo = mul(2);
console.log(multiplyByTwo(3))


4)  Write a program to throttle using closures?
function throttling(func, delay) {
		let flag = true;
		return function () {
			if (flag) {
				func();
				flag = false;

				setTimeout(function () {
					flag = true;
				}, delay);
			}
		};
	}
