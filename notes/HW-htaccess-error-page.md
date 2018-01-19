# HW - Creating a custom error page using htaccess

## Overview
.htaccess files allow you to script web server on a per-directory basis

## I. Get ready
Set up your 230 Directory (if you haven’t done so already)

1.	On your PC, create a directory called 230. This is where all the work you do from now on will be stored.

2.	Make sure to save this to a flash drive, your myCourses locker, GitHub, a remote disk, or some other means of backup. Be sure to keep 2 backups, on a removable device (for instance) and some other means in case something happens to that one.

3.	Connect to Banjo using filezilla or another FTP client

4.	Drag your 230 folder into your www folder on Banjo. Make sure it has the right permissions (right-click > File Attributes… > Numeric Value: 755)

Now let’s go back to the starter files you downloaded for this exercise.

5.	Open error.html in a web browser. This will be our custom error page any time the server does not find a page.

6.	Open noterror.html in a browser. This will be used as a test page that will not give us an error.

7.	Connect to Banjo using filezilla or another FTP client

8.	In your 230 folder, create a new folder called error. 

9.	Add the starter files from the error_start folder to the new error folder you created. Your error folder should only contain 3 files.

10.	Make sure you can reach the error.html page and the noterror.html pages from a browser. Correct any permissions issues if you need to.

11.	Now create a new file called .htaccess . The dot at the beginning of the file name is critical. The dot at the beginning tells unix machines that this is a hidden file. 

Apache servers look for hidden server configuration files called .htaccess.

The .htaccess file allows you to set custom configurations for a folder or sub-folders. 

Apache looks for one .htaccess file per folder. That sets the configuration for that folder and any sub-folder. Having .htaccess files in sub-folders overrides .htaccess files in above folders. 
12.	Now we will add the Apache commands to set up the custom 404 page when 404 errors occur. 

We will use the ErrorDocument directive. Apache’s ErrorDocument directive tells Apache how to handle specific errors. It takes an HTTP status code and a response to send.

The status code we will be handling is 404 – the file not found status code. 

You can find more status codes here: http://en.wikipedia.org/wiki/List_of_HTTP_status_codes 

     For a response, we will give Apache the path of an HTML file to send. The file path 
     for this directive is similar to your people.rit.edu path in a browser. You start with 
     /abc1234 (where abc1234 is your RIT ID), which is automatically linked to your www 
     folder. After that, it’s just the path to your file inside of the www folder. 

     Inside of your .htaccess file, add the following line. Replace abc1234 with your ID. 

ErrorDocument 404 /abc1234/230/error/error.html


13.	Transfer this file to the error folder you made on Banjo. 


14.	 Test your new 404 error page . Go to the noterror.html page on Banjo. Make sure you can get to that page. 


Once you get to that page, try a non-existent page in the error folder. Change the browser URL from noterror.html to maybe notreal.html.

You should automatically be sent to the 404 page you added any time you type in an address that does not exist in the error folder. 

This only affects the error folder and any folders inside of it because that is where the htaccess file is. If you test any non-existent pages above the error folder, you should still get the normal RIT 404 page.


     Note: If this does not work, check the name & capitalization of the .htaccess 
     file. Then inside of the .htaccess file, check the path to your error.html file. It 
     must be exact or else Apache will give you a default error page.
