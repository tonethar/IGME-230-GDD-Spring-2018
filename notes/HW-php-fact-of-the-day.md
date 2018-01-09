# Homework: PHP: "Fact Of The Day" page

## Overview
In this assignment you will create a PHP-driven "random fact" page, and a PHP-driven "fact of the day" page.

To do this assignment, you should have completed at least the [3rd PHP Tutorial - Arrays](php-3.md)

Here are screen shots of the completed examples:

### PHP Random Facts Page
![Screenshot](_images/php-fact-of-the-day-HW-1.jpg)

### PHP Fact of the Day Page
![Screenshot](_images/php-fact-of-the-day-HW-2.jpg)

![Screenshot](_images/php-fact-of-the-day-HW-3.jpg)

## Instructions
**HW-random-fact.php**
1. The outputted page will be valid HTML5.
1. You must spend some time designing the page, and have at least 3 CSS rules. Your design should look no worse than the minimal example above, and ideally better! Above, I set (in CSS) the `width` and `height` of the main &lt;div> to 600 x 400, and used `margin-left:auto;` and `margin-right:auto;` to center it.
1. Create an array of at least 7 "facts". The example uses jokes, but the facts could be a random quote, vocabulary word, trivia, a Magic 8-ball type fortune, or whatever.
1. Pull a random fact out of the array every time the page is loaded or re-loaded, and display it. There are a couple of ways to do this - you can look here: http://php.net/manual/en/ref.array.php and here: http://php.net/manual/en/function.rand.php
1. Submission: When you are done, post the page to `banjo.rit.edu`, zip and post your files to the appropriate dropbox, and put the link in the dropbox comments field.

**HW-fact-of-the-day.php**
1. The requirements are the same as above, except that you will display a different fact depending on what day of the week it is. If it is Sunday, then the same fact will be shown for the whole day; if it is Monday, then another fact will be shown for the whole day, and so on.
1. You will also display to the user what day of the week it is (DO NOT display other time or date information other than the day of the week)
1. There are a number of way to get this information:
    - `date()` - http://php.net/manual/en/function.date.php
    - `jddayofweek(0)` - http://php.net/manual/en/function.jddayofweek.php - which gives an integer of 0-6 depending on what day it is
1. Submission: When you are done, post the page to `banjo.rit.edu`, zip and post your files to the appropriate dropbox, and put the link in the dropbox comments field.
