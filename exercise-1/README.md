# Exercise 1 - Pomodoro-style :tomato: pairing

This exercise will focus on Pomodoro-style :tomato: pairing using the fizz buzz kata.

![alt pomodoro-method](https://media.hswstatic.com/eyJidWNrZXQiOiJjb250ZW50Lmhzd3N0YXRpYy5jb20iLCJrZXkiOiJnaWZcL3BvbW9kb3JvMy5qcGciLCJlZGl0cyI6eyJyZXNpemUiOnsid2lkdGgiOjgyOH19fQ==)

## 0.0 Dev environment setup

:exclamation: In this workshop we are going to use Node.js and the Jest framework to run JavaScript code and tests from the command line.

### 0.1 Install Node.js/npm

:pencil2: After installing [Node.js](https://nodejs.org), open up a command line window (Command Prompt or Powershell in Windows or Terminal in macOS) and type `node -v`, you should see a version number:

```bash
$ node -v
v18.12.1
```

:pencil2: Verify that [npm](http://npmjs.com/) (Node Package Manager) was installed by typing `npm -v`, you should see a version number:

```bash
$ npm -v
9.1.3
```

### 0.2 Install dependencies

:pencil2: While still in the command line window, change the current working directory to the location where you cloned this repository (where `package.json` is located). Then type `npm install`:

```bash
$ npm install
...
added 515 packages in 8.219s
```

If you see warnings of vulnerabilities don't worry. We only run our code locally, the vulnerabilities are of no concern to us during these exercises.
If you want to you can run `npm audit fix` and it will try to fix the vulnerabilites for you.

### 0.3 Running tests

:book: We are going to use the [Jest framework](https://facebook.github.io/jest/) for writing and running tests.

:pencil2: While still in the command line window, make sure the current working directory is the location where you cloned this repository (where `package.json` is located).
Then type `npm test -- exercise-1`:

```bash
$ npm test -- exercise-1
...
Ran all test suites matching /exercise-1/i.
```

This command runs the `test` script defined in `package.json`, which in turn calls the `jest` command with the parameter `exercise-1`. Jest then runs all tests found in the `exercise-1` directory.

:bulb: Please refer to the [Jest documentation](https://facebook.github.io/jest/docs/en/getting-started.html) if you have any questions not covered here regarding the framework.

### 0.4 Writing tests using Jest

:bulb: Note that there is no coding in this sub-section. This is an introduction to jest as a test-framework. The content of this section may be a useful reference when you are writing your tests.

#### 0.4.1 Declaring test functions

:book: To declare a test use the `test` function:

```js
test("did not rain", () => {
  expect(inchesOfRain()).toBe(0);
});
```

The first parameter sets the test name ("did not rain"), the second parameter is a function containing one or more asserts.

#### 0.4.2 Asserts / "matchers"

:book: Jest has several _assert_ functions available. Jest calls them "matchers". Here is a simple example:

```js
test("two plus two is four", () => {
  expect(2 + 2).toBe(4);
});
```

:book: `expect(2 + 2)` returns an object called an "expectation" object. These are used to call matchers on, like `toBe(4)`.

:book: `toBe` uses Javascripts built in [`Object.is`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/is) function to test exact equality.

:book: To check the value of an object, use `toEqual` instead:

```js
test("the shipping list is correct after adding brunost", () => {
  let shoppingList = ["melk"];
  shoppingList.push("brunost");
  expect(shoppingList).toEqual(["melk", "brunost"]);
});
```

:book: `toEqual` recursively checks every field of an object or array.

:bulb: Read more about using matchers in the [Jest matchers documentation](https://facebook.github.io/jest/docs/en/using-matchers.html).

#### 0.4.3 Grouping tests using `describe`

Tests can be grouped together using the `describe` function:

```js
const shoppingList = ["melk", "brunost"];

describe("shopping list", () => {
  test("is 2 items long", () => {
    expect(shoppingList.length).toBe(2);
  });

  test("has brunost in it", () => {
    expect(shoppingList).toContain("brunost");
  });
});
```

## 1.1 Fizz buzz kata

:book: [Fizz buzz](https://en.wikipedia.org/wiki/Fizz_buzz) is a word game designed teach children about division. Players take turns to count upwards from 1, replacing any number divisible by three with the word "Fizz", and any number divisible by five with the word "Buzz".

* Write a program that prints the numbers from 1 to 100
* For numbers which are multiples of three print "Fizz" instead of the number
* For numbers which are multiples of five print "Buzz"
* For numbers which are multiples of both three and five print "FizzBuzz"

Example output:

```shell
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
17
Fizz
19
Buzz
... etc up to 100
```

## 1.2 Pair programming session

> :exclamation: **Session length:** One pomodoro :tomato: - 25 minutes

:pencil2: Run through the Fizz buzz kata described above in pairs. Use Test Driven Development.

:pencil2: Use [pomodoro](https://en.wikipedia.org/wiki/Pomodoro_Technique)-style :tomato: pairing: The _Driver_ (writes the code) and the _observer_ (helps, reviews and remembers things you need to do later on).

:pencil2: _Rotate every 5-6 minutes_ by swapping seats (the _driver_ becomes the _observer_, and vice versa). Use the same computer.

:bulb: Skeleton functions are created in the exercise files. The function `fizzBuzzRange` takes in one argument `max`, which will be the length of the fizzBuzz-range you are creating. The function should return an array of elements, where each element is either a number, "Fizz", "Buzz" or "FizzBuzz". 
`fizzBuzzRange(5)` should return `[1, 2, "Fizz", 4, "Buzz"]`.

:bulb: You will see some tests already present in the tests-file. You are welcome to delete these tests, as they only serve a demonstrative purpose until you write your own tests.

### [Go to exercise 2 :arrow_right:](../exercise-2/README.md)
