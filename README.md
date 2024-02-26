Javascript Questions
Synchronous vs Asynchronous in javascript
What is the difference between var, let, and const.
Deep copy vs shallow copy give example
Why we use JSON.Parse and JSON.stringfy
Explain what the callback function is and provide a simple example.
Primitive vs no primitivism data types
How can we handle Asynchronous in javascript
Event Loop
Call Stack vs Heap
Object Prototyping with an example (.toString () method is an example)
libuv library for async
Event bubbling, event capturing/trickling, and event delegation
Explain this keyword
Normal function vs arrow function
The difference of this in normal function vs arrow function
Strict mode in Javascript
Hoc function in javascript
SOLID principles
What is hoisting? Explain with example
Temporal Dead Zone?
Difference between call, apply, and bind. Give exámple.
What is closure and what are the advantages of using closure?
JS engine architecture.
Problem Solving javascript
Let objA={name: “test”, value:2}
Let objB={name: “test”, value:2}
Console. Log(objA==objB)
Explain this also
How can we test whether these two objects are the same or not write a function?
Reactjs Interview Questions
Strict mode in reactjs
virtual dom vs shadow dom
Design patterns
reconciliation
dependency injection in reactjs
Can we change the value of props?
Jest with React testing library
Micro-Frontend
HOC Component with example
Pure component
Pure function
Context vs Redux
can context replace redux?
Redux logger middleware
How to handle protected vs public routes
How to handle User based permission from frontend
And how will you handle role based permission from frontend
function isPrime(n) {
  if (n <= 1) return false;
  if (n <= 3) return true;
  if (n % 2 === 0 || n % 3 === 0) return false;
  let i = 5;
  while (i * i <= n) {
    if (n % i === 0 || n % (i + 2) === 0) return false;
    i += 6;
  }
  return true;
}
function PrimeChecker(num) {
  // Convert num to a string to work with its digits
  const numStr = num.toString();
  // Generate all permutations of the digits
  const permutations = [];
  function permute(arr, index) {
    if (index === arr.length) {
      const permutationNum = parseInt(arr.join(""), 10);
      permutations.push(permutationNum);
      return;
    }
    for (let i = index; i < arr.length; i++) {
      [arr[index], arr[i]] = [arr[i], arr[index]];
      permute([...arr], index + 1);
      [arr[index], arr[i]] = [arr[i], arr[index]];
    }
  }
  permute([...numStr], 0);
  // Check if any of the permutations are prime
  for (const permutation of permutations) {
    if (isPrime(permutation)) {
      return 1;
    }
  }
  return 0;
}
// keep this function call here
console.log(PrimeChecker(readline()));
function DataList(props) {
  // Destructure the 'data' prop from props
  const { data } = props;
  return (
    <ul>
      {data.map((person, index) => (
        <li key={index}>
          <span>{person.name}</span> <span>{person.age}</span>
        </li>
      ))}
    </ul>
  );
}
