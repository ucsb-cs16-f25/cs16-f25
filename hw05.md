---
layout: page
title: HW05
nav_order: 6
desc: "Array Lists and Dynamic Arrays"
assigned: 2023-02-23 13:00
due: 2023-03-08 23:59
num: hw05
published: true
---

# {{page.title}} - {{page.desc}}

## Goals of this assignment

The goal of this assignment is to get more practice with iterating through arrays and dynamically allocating memory. Continue to practice code tracing to reason about your code. We request that you **do not** ask the staff to debug your code. They have been specifically instructed not to debug for you, but rather to guide you in the process.

# Step-by-step instructions

## Step 1: Getting ready

1. Go to Github and find a repo for HW05 assigned to your GitHub ID.

2. Log on to your CSIL account.

3. Change into your `~/cs16` directory

4. Clone your empty `{{page.num}}` repo into your `~/cs16` directory.

5. In your empty repo, do `git checkout -b main` to establish that you are on the `main` branch as your default branch.


## Step 2: Obtain the starter code

The starter code is in this repo:

* <https://github.com/{{site.github_org}}/STARTER-{{page.num}}>

The URL for cloning this repo is this: `git@github.com:{{site.github_org}}/STARTER-{{page.num}}.git`

Previous assignments contain instruction for the process of:
* Adding a `starter` remote for this repo.
* Pulling the code from that `starter` remote into your own repo.

Please do those steps now, and then do a `git push origin main` to populate your own repo with the starter code.

If you need help with these steps:
* First, consult previous assignments for more detailed instructions.
* Then, if you are still having trouble, ask the staff for help during discussion section or office hours.

Once you've populated your repo, typing the `ls` command should show you the following files in your current directory

```
$ ls
Makefile		arrayFuncs.h		moreArrayFuncs.h
README.md		mafTest.cpp		tddFuncs.cpp
arrayFuncs.cpp		moreArrayFuncs.cpp	tddFuncs.h
$
```

## Step 3: Reviewing the files and what your tasks are

### Step 3a: Familiarize yourself with the big picture

Type `make tests` and you will see some tests pass, but some fail.
You are finished when all the tests pass.

There is only one file that you need to edit this week: `moreArrayFuncs.cpp`, which contains more functions that deal with arrays.

These are in addition to the `arrayFuncs.cpp` that you worked with before in HW03.

### Step 3b: Work on the array functions

There are 9 functions you will need to write for this assignment:

* `indexOfMax`
* `indexOfMin`
* `largestValue`
* `smallestValue`
* `sum`
* `copyElements`
* `copyOddOnly`
* `multiplyPairwise`
* `createArray`

Each one has a set of tests which can be found under its corresponding heading when you type `make tests`. For example, the `indexOfMax` tests look like this to start:

```
--------------INDEX_OF_MAX--------------
   FAILED: indexOfMax(fiveThrees,5)
     Expected: 0 Actual: -42
   FAILED: indexOfMax(zeros,3)
     Expected: 0 Actual: -42
   FAILED: indexOfMax(primes,1)
     Expected: 0 Actual: -42
   FAILED: indexOfMax(primes,5)
     Expected: 4 Actual: -42
   FAILED: indexOfMax(primes,10)
     Expected: 9 Actual: -42
   FAILED: indexOfMax(meaning,1)
     Expected: 0 Actual: -42
   FAILED: indexOfMax(mix1,10)
     Expected: 5 Actual: -42
   FAILED: indexOfMax(mix2,10)
     Expected: 5 Actual: -42
   FAILED: indexOfMax(mix1,3)
     Expected: 1 Actual: -42
   FAILED: indexOfMax(mix2,3)
     Expected: 1 Actual: -42
   FAILED: indexOfMax(mix2,1)
     Expected: 0 Actual: -42
   FAILED: indexOfMax(mix2,5)
     Expected: 4 Actual: -42
```

You should replace each function stub with the correct code for the function until all of the tests for each one pass. It is recommended that you work on the functions one at a time in the order that they are presented above. That is, get all the tests to pass for `indexOfMax` then `indexOfMin`, and so on. When all the tests pass, move on to the next step.

You must implement each function iteratively. For this assignment, you **cannot** implement the function with recursion. Any recursive implementations **will not receive credit for this assignment and be flagged for possible plagarism.** (Note: if you are unaware what a recursive implementation entails, do not worry, we have not covered this technique in class yet. This assignment should be completed using only using the techniques we learned in class.)

## Step 4: Checking your work before submitting

When you are finished, you should be able to type `make clean` and then `make tests` and see the following output:

```
$ make clean
/bin/rm -f mafTest *.o
$ make tests
clang++ -Wall -Wno-uninitialized   -c -o mafTest.o mafTest.cpp
clang++ -Wall -Wno-uninitialized   -c -o moreArrayFuncs.o moreArrayFuncs.cpp
clang++ -Wall -Wno-uninitialized   -c -o tddFuncs.o tddFuncs.cpp
clang++ -Wall -Wno-uninitialized   -c -o arrayFuncs.o arrayFuncs.cpp
clang++ -Wall -Wno-uninitialized  mafTest.o moreArrayFuncs.o tddFuncs.o arrayFuncs.o -o mafTest
./mafTest
--------------INITIALIZING--------------
PASSED: arrayToString(fiveThrees,5)
PASSED: arrayToString(zeros,3)
PASSED: arrayToString(empty,0)
PASSED: arrayToString(primes,5)
PASSED: arrayToString(primes,10)
PASSED: arrayToString(meaning,1)
PASSED: arrayToString(mix1,10)
PASSED: arrayToString(mix2,10)
PASSED: arrayToString(descending,5)
--------------INDEX_OF_MAX--------------
PASSED: indexOfMax(fiveThrees,5)
PASSED: indexOfMax(zeros,3)
PASSED: indexOfMax(primes,1)
PASSED: indexOfMax(primes,5)
PASSED: indexOfMax(primes,10)
PASSED: indexOfMax(meaning,1)
PASSED: indexOfMax(mix1,10)
PASSED: indexOfMax(mix2,10)
PASSED: indexOfMax(mix1,3)
PASSED: indexOfMax(mix2,3)
PASSED: indexOfMax(mix2,1)
PASSED: indexOfMax(mix2,5)
--------------INDEX_OF_MIN--------------
PASSED: indexOfMin(fiveThrees,5)
PASSED: indexOfMin(zeros,3)
PASSED: indexOfMin(primes,5)
PASSED: indexOfMin(primes,10)
PASSED: indexOfMin(meaning,1)
PASSED: indexOfMin(mix1,10)
PASSED: indexOfMin(mix2,10)
PASSED: indexOfMin(mix1,3)
PASSED: indexOfMin(mix2,3)
PASSED: indexOfMin(descending,5)
PASSED: indexOfMin(descending,1)
--------------LARGEST_VALUE--------------
PASSED: largestValue(fiveThrees,5)
PASSED: largestValue(zeros,3)
PASSED: largestValue(primes,5)
PASSED: largestValue(primes,10)
PASSED: largestValue(meaning,1)
PASSED: largestValue(mix1,10)
PASSED: largestValue(mix2,10)
PASSED: largestValue(mix1,3)
PASSED: largestValue(mix2,3)
PASSED: largestValue(descending,5)
PASSED: largestValue(descending,1)
--------------SMALLEST_VALUE--------------
PASSED: smallestValue(fiveThrees,5)
PASSED: smallestValue(zeros,3)
PASSED: smallestValue(primes,5)
PASSED: smallestValue(primes,10)
PASSED: smallestValue(meaning,1)
PASSED: smallestValue(mix1,10)
PASSED: smallestValue(mix2,10)
PASSED: smallestValue(mix1,3)
PASSED: smallestValue(mix2,3)
PASSED: smallestValue(descending,5)
PASSED: smallestValue(descending,1)
--------------SUM--------------
PASSED: sum(fiveThrees,5)
PASSED: sum(zeros,3)
PASSED: sum(primes,5)
PASSED: sum(primes,10)
PASSED: sum(meaning,1)
PASSED: sum(mix1,10)
PASSED: sum(mix2,10)
PASSED: sum(mix1,3)
PASSED: sum(mix2,3)
PASSED: sum(descending,5)
PASSED: sum(descending,1)
--------------COPY_ELEMENTS--------------
PASSED: arrayToString(primes,10)
PASSED: arrayToString(mix1,10)
PASSED: arrayToString(mix1,10)
PASSED: arrayToString(mix2,10)
PASSED: arrayToString(mix1,10)
PASSED: arrayToString(mix2,10)
--------------COPY_ODD_ONLY--------------
PASSED: copyOddOnly(a,descending,5)
PASSED: arrayToString(descending,5)
PASSED: arrayToString(a,3)
PASSED: copyOddOnly(a,mix2,10)
PASSED: arrayToString(mix2,10)
PASSED: arrayToString(a,5)
--------------MULTIPLY_PAIRWISE--------------
PASSED: arrayToString(fiveThrees,5)
PASSED: arrayToString(descending,5)
PASSED: arrayToString(a,5)
PASSED: arrayToString(primes,5)
PASSED: arrayToString(descending,5)
PASSED: arrayToString(a,4)
PASSED: arrayToString(primes,7)
PASSED: arrayToString(a,7)
--------------CREATE_ARRAY--------------
PASSED: arrayToString(oneElem, 1)
PASSED: arrayToString(threeElems, 3)
PASSED: arrayToString(fiveElems, 5)
PASSED: arrayToString(oneElem, 1)
PASSED: arrayToString(threeElems, 3)
PASSED: arrayToString(fiveElems, 5)
$
```

At that point, you are ready to try submitting on Gradescope.

## Step 5: Turn in your code on Gradescope

Submit all the `.cpp` and `.h` files to this assignment on Gradescope via your GitHub repo. Then visit Gradescope and check that you have a correct score.
You must check that you have followed these style guidelines:

1. **Indentation:** Ensure your code is neatly and consistently indented. Code inside braces (`{ }`) should be indented appropriately, and all code at the same level of nesting should follow a consistent indentation pattern. Refer to examples from lectures, sample code, and the textbook for guidance.
2. **Variable Names:** Use meaningful and descriptive variable names that reflect their purpose.
3. **Avoid Repetition:** Practice the DRY (Don’t Repeat Yourself) principle to identify and optimize repetitive or redundant sections for better efficiency and clarity.

Commit and push the latest version of your code on github.

**Graders will check your code to make sure it follows the coding style guidelines. Egregious violations to the coding style guidelines may result in a score reduction for your assignment grade.** If you are unsure whether your code exhibits good coding style, please ask a member of the course staff during assignment.
