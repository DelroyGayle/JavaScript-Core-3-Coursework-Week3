# Code reading

## Question 1

Take a look at the following code:

```
1    let x = 1;
2    function f1()
3    {
4        let x = 2;
5        console.log(x);
6    }
7    console.log(x);
```

Explain why line 4 and line 7 output different numbers.
Because x is block local to the function f1 whilst 'x' in line 7 is a global variable as defined in 1

## Question 2

Take a look at the following code:

```
let x = 10

function f1()
{
    console.log(x)
    let y = 20
}

console.log(f1())
console.log(y)
```

What will be the output of this code. Explain your answer in 50 words or less.
Answer:

10
undefined

x is a global variable so it is available to the entire program including f1()
In contrast y is a local variable available only in the function scope of f1()
So there is no defined variable 'y' at global level; hence undefined.

## Question 3

Take a look at the following code:

```
const x = 9;

function f1(val) {
  val = val + 1;
  return val;
}

f1(x);
console.log(x);

const y = { x: 9 };

function f2(val) {
  val.x = val.x + 1;
  return val;
}

f2(y);
console.log(y);
```

What will be the output of this code. Explain your answer in 50 words or less.
Answer:

9
{ x: 10 }

x is a 'const' which cannot be redefined.
It is passed as a parameter. The parameter has function scope local solely to f1.
So x is never affected at all hence 9

Objects are 'called by reference' unlike primitive values such as numbers and booleans.
That is, even when used as a parameter to a function, whatever is done to an object within a function will affect the object globally
So val.x is incremented globally so it has the value 10.

