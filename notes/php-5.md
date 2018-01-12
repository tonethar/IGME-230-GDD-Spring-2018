# 5 - PHP Mail & Forms

## Contents
<!--- Local Navigation --->
I. [Overview](#section1)

## I. <a id="section1">Overview
Today we are going to look at creating a typical HTML contact form where a user can type in a message, and then click a button to send the message, without ever having to open up their email client. To accomplish this we will need to cover a few things today:
- how to utilize PHP `mail()` function
- how HTML forms can capture the user's message
- how data can be passed to PHP scripts


## II. The PHP `mail()` function

The PHP `mail()` function will send mail using the email program specified in our php.ini file. It's easy to use - go ahead run this code on banjo. You will need to replace `abc1234` with your RIT id.

**php-mail-1.php**

```
<?php
	$to = "abc1234@rit.edu";
	$from = "abc1234@rit.edu"
	$subject = "My subject";
	$message = "Hello world!";
	$headers = "From: $from" . "\r\n";

	// send the message!
	mail($to,$subject,$message,$headers);
?>
```



- https://www.w3schools.com/php/func_mail_mail.asp
- http://php.net/manual/en/function.mail.php


 




<hr><hr>

**[Previous Chapter <- PHP Functions (chapter 4)](php-4.md)**
