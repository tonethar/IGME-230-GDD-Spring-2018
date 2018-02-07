# Instructor Notes

## Week 0
- in mycourses:
    - create gradebook, give everyone 100% (5/5) in attendance
    - post link to syllabus and schedule to mycourses welcome page
    - add a "links" module (i.e. folder) to the Content section, and add a hypertext link (that opens in a new window) to [schedule.md](../schedule.md)
    - email students welcoming them to the class, and send them the link to the course github repo, as well as the [Week 1A: Course Introduction](../weekly/Week-01A-notes.md) - request that they read this page and the [syllabus](syllabus.md) prior to attending class.
- set up mycourses dropboxes for:
  - [Custom 404 Authorization ICE](../exercises/week-1/Custom_404_Auth_start.zip)
  - [PHP-1](php-1.md)
  - [HW: php.ini](HW-php-ini.md)
  - [PHP-2](php-2.md)
  - [PHP-3](php-3.md)
  - [HW: PHP "Fact of the Day"](HW-php-fact-of-the-day.md)

## Week 1
### Day 1 - there is quite a bit to do today!
- introduce self and TA
- show the course link in mycourses, and the already extant mycourses dropboxes
- **Reminder:** *all code files (HTML, CSS, JavaScript) must be zipped when put in a dropbox, because otherwise mycourses strips out the JavaScript and CSS, and you will likely get a zero on the assignment*
- "Welcome to course"
- review [syllabus.md](../syllabus.md)
- review [schedule.md](../schedule.md)
- Review [Week 1A: Course Introduction](../weekly/Week-01A-notes.md)
    - there is a lot here, the instructor will summarize it, and the students are expected to read it themselves
    - review what the course is about, and show a few examples of previous projects 
    - cover pedagogy and emphasize there will be many (small) HW assignments, so keep an eye on the dropboxes!
    - review [http-protocol-intro.md](http-protocol-intro.md), discuss what a web server is, how you can program it (which we will do with .htaccess files next time, and PHP next week)
    - do the [http-protocol-demo.md](http-protocol-demo.md), highlight the request line, headers, and request/response, and then answer the review questions on the bottom of [http-protocol-intro.md](http-protocol-intro.md) together.
- time allowing, create a *hello.html* page and post it to banjo (some students might have forgotten the FTP and permissions part of posting to banjo)

### Day 2 
- "Anyone here who wasn't here last time?"
- "Any questions from last time?"
- recap HTTP protocol stuff from last time
- Review [Week 1B - Review of banjo.rit.edu & FTP](../weekly/Week-01B-notes.md)
   - review *hello.html* and FTP (FileZilla or similar)
   - do .htaccess presentation
   - show a page like this one - https://people.rit.edu/~acjvks/ - that `ModPagespeed` is compressing the styles and JS
   - use the Chrome web inspector to show headers - including the `ModPagespeed` header
   - walk through the [Fixing Banjo Exercise](../exercises/week-1/Fixing-Banjo.md) and then check the inspector to see that the `ModPagespeed` header is gone, and check the page to see that the styles and JS are no longer compressed 
   - let the students work on the [Auth and htaccess PDF](../docs/Auth_and_htaccess.pdf) exercise

## Week 2
### Day 1
- You probably want to post the PHP example files (from PHP-1 through PHP-4) to web prior to class
- Take attendance! from this day and all going forward
- Any .htaccess questions?
- Review [Week-02-notes.md](../weekly/Week-02-notes.md), give presentation, and do demos from presentation
- Demo upgrading to PHP 7 ->  https://www.rit.edu/webdev/php-7
- Demo editing php.ini file -> [HW-php-ini.md](HW-php-ini.md)
- Review [php-0.md](php-0.md)
- Review [php-1.md](php-1.md)
    - just the *Creating a valid HTML page with PHP* section as the rest is covered in the slides. Be sure to hilite PHP's string interpolation.
- Review [php-2.md](php-2.md)
    - time allowing, you may or may not want to demo each example, but be sure to mention the caching issue and .htaccess solution in Part IX

**Reminder: We are going to go through these demos very quickly. If a student is unable to keep up as we do all of these demos, they just need to go back and follow the written instructions.**

### Day 2
- Any questions from last time?
- Todays' demos will probably eat up all of our class time - `:-|`
- Review [php-3.md](php-3.md) - be sure to demo all of the associative array code and the `$_SERVER` example
- Review [php-4.md](php-4.md)
    - demo [php-mail-1.php](php-mail-1.php)
    - demo [php-mail-2.php](php-mail-2.php), and how form variables are passed based on the name of the field - change the form method to GET so that the variables are visible
    - the students can do the rest of this chapter on their own
- Demo the completed version of [php-4-HW.php](php-4-HW.php) and the two [HW-php-fact-of-the-day.md](HW-php-fact-of-the-day.md) files
- Time allowing, demo some debugging:
    - run a PHP script through the PHP parser on the command line to view the output. Also note how superglobals like `$_SERVER` don't exist in the command-line context
    - view the PHP error log at `abc1234/php_data/php.log`
  

## Week 3
### Day 1
- PHP Wrap up:
    - Demo the [File Lister Example](HW-php-file-lister.md)
    - Demo the Homework:
        - [php-3-HW.php](php-3-HW.php) - working with PHP associative arrays
        - [php-4-HW.php](php-4-HW.php) - adding a field to the mail form - be sure to show XSS attack in Firefox when we comment out the `sanitizeString()` code
        - [HW-php-fact-of-the-day.md](HW-php-fact-of-the-day.md) - random fact & fact of the day
    - Any PHP questions?
 - Intro to HTML - much of this is review from 110:
     - Weekly notes are here: [Week-03A-notes.md](../weekly/Week-03A-notes.md)
     - Go through at least one of the presentations - if you run out of time, the students can read the other one
     - Do the "It was a Dark & Stormy night" demo in class, by marking up the content and beginning to style it

### Day 2
- Intro to CSS
- Weekly notes are here: [Week-03B-notes.md](../weekly/Week-03B-notes.md)
- Finish "It was a Dark & Stormy night" demo in class - by adding styles

## Week 4
### Day 1
- Look at 230 home page submissions - most of them will probably not look great - but that's OK at this point
- Review [Project 1](../projects/project1.md) requirements and emphasize the first deliverable (Github content)
- Demo GitHub and Markdown syntax
- Finish Reviewing the CSS topics and Slides from [Week 3B](../weekly/Week-03B-notes.md)
- "Holmes" Single Column Layout Demo/ICE - just do the first part
- Review CSS Layout Demos

### Day 2
- Discuss Responsive Design and the "Mobile First" philosophy
- Do Part II of Holmes Demo/ICE
- Quick look at Bootstrap Template (it's responsive!)
- Responsive Design Slides
- ICE: "Darth"

## Week 5

## Week 6

## Week 7

## Week 8

## Week 9

## Week 10

## Week 11

## Week 12

## Week 13

## Week 14
