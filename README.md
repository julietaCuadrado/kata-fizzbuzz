FizzBuzz kata in the TDD way

I'm trying to have the TDD habit while developing.
Therefore, I'm developing some katas with TDD style in order to learn and interiorize it has my daily routine.

This one is FizzBuzz, it is simple, and then some one needs to modify it and you have a set of requirements wich makes you change the code in each iteration

FizzBuzz MVP
Write a program that prints the numbers from 1 to 100. But for multiples of three print “Fizz” instead of the number and for the multiples of five print “Buzz”. For numbers which are multiples of both three and five print “FizzBuzz “.

---
## How to use

To run the app, you don't really need to run composer, but if you want to run the tests:
```
$ composer update
```

app.php is an entrypoint to run and configure the application, to run FizzBuzz:
```
$ php app/app.php
```

finally to run the tests
```
$ php vendor/bin/phpunit test
```

---

## How was it done:

To make it clear how TDD goes, I've chosen to make branches with the followed steps. Branches will therefore be merged to master, but not deleted from the repo.

Also a new section will be added to this README.md in each branch together with a brief description on what was done and the things I've learn or I think I should hightlight.

---
## step-1 configure
### gitignore

In your gitignore folder, first thing should be vendors folder. Is there a reason for pushing vendors to the repo? Well, sometimes you just have to, but if you are forced to consider that option, probabily your day-to-day has a lot to do with legacy code an bad practices.

About composer.lock being added to your gitignore, someones says yes, someones says no. 
Why? The ones saying 'yes, git should ignore composer.lock' are the ones attaching dependecies to composer json one by one, including version to the letter.
It can be done but is really exausting, and the process is slow.
I think it should be commited.

_Resources_
* gitignore documentation:
https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository#_ignoring

* gitignore scheletons: https://github.com/github/gitignore

### Composer 

I will follow PSR4 for autoloading classes.
Tests are also part of my namespace (they are part of my codebase!)

I am using phpunit to test. 

It is recomended as a good practice to use require-dev to specify the dependecy with phpUnit instead of require.

## step-2 check that tests run and pass
Just to double-check that test properly run, first test does test 1 equals 1 
