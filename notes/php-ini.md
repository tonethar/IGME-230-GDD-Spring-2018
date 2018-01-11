# php.ini

## Overview

A configuration file - `php.ini` - that is read when PHP starts up.

This file is located on your banjo account, and controls certain capabilities of how PHP runs for you gibson. In this exercise we are going to make two small changes to this file. 

A reference to what all of these PHP directives mean can be found at: http://www.php.net/manual/en/ini.list.php


Fetch your php.ini file, and make a back-up copy

1)	Download your gibson php.ini file to your local computer. It is located in your login directory on gibson at abc1234/php_data/php.ini

2)	Now that you have a copy of the php.ini file on your computer, change the name of the original file on the gibson server from php.ini to php.ini_bak

Note : php.ini_bak should be kept as a backup copy that you can always go back to in case there is a problem with the changes you are going to make to php.ini


Now let’s make some changes to your php.ini file

3)	First we will turn on error reporting so that you can see php errors printed to the browser window. This is a great option to have turned on during PHP development. Locate the line that looks like: 

display_errors = Off 

(it should be around line # 355) and change it to:

 display_errors = On


4)	Second, we will give PHP the ability to download files from other domains. We will need this ability later in the course when we are downloading web pages to scrape, and JSON/XML files to parse. Locate the line that looks like: 

allow_url_fopen = Off

(it should be around line # 578) and change it to:

 allow_url_fopen = On


5)	Save your changes, and transfer this updated php.ini file back to the directory that you got it from.


Test the changes you have made

6)	Create a script named broken.php to test error display and upload it to Gibson in a folder 431/day2/  - run it in the browser, you should see “Parse error” message in the browser window when the page is loaded.

<?php
	
echo "Welcome!!!!  // missing closing quote and semicolon

?>


The corrected version is here:

<?php
	
echo "Welcome!!!!”;  // all good!

?>



7)	Another way to see error messages is to run PHP scripts on the command line. You can do this by establishing an ssh session with Gibson, then cd to the folder with broken.php in it, and then typing:

php broken.php

Which runs broken.php through the command-line PHP parser and should display the error message as well


8)	Can you fix broken.php right here on the command line with a text editor like pico? Make it so!


9)	Another place to see error messages is in the PHP error log file on Gibson at abc1234/php_data/php.log 

 

10)	 Now we will check to see if we can open a file on another server with the following script which you can name open.php and put in your 431/day2/  folder.


<?php
	$data = file_get_contents("http://www.gop.com");

	echo "<h1>Here's your data!!</h1>\n" . $data;

// The dot above is used to concatenate the strings
 ?>


11)	 Test this in the browser by loading open.php The script should load the default page for www.cnn.com and display it. 


12)	 Test this on the command line by typing php open.php from the correct directory. You should see the default page for www.cnn.com dumped to the terminal.


13)	 Another capability that PHP has is to change these ini setting on a per-script basis. See the documentation for the PHP ini_set() function at:
http://php.net/manual/en/function.ini-set.php
