# Week 1B - Review of *banjo.rit.edu* & FTP

## Topics
- FTP review
- Setting up your `230` directory
- Scripting the server with `.htaccess` files

## Demo
FTP demo and review (we will do this together in class):
   - Create a local 230 directory, and put a hello.html file in it:

**hello.html**
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Hello Page</title>
</head>
   <body>
      <h1>Week 1 in 230!</h1>
      <p>I am stoked about this class!</p>
   </body>
</html>
```
 
   - **Reminder:** keep backups, bring a flash drive to class; the 230 folder is where course work will often be posted.
   - Connect to Banjo (`banjo.rit.edu`, port 22) and upload the 230 directory to have it there for when we need it. Use a FTP client like FileZilla.
   - Review permissions (at this point, you shouldn't need to change these, but just in case)
   - **Reminder:** `banjo.rit.edu` is the FTP name, while the browser accesses people.rit.edu
   - Navigate to that directory via browser, and you should see our *hello.html* page

## Presentations
- [Auth and htaccess PDF](../docs/Auth_and_htaccess.pdf)

## Exercises
- ["Fixing Banjo" instructions](../exercises/week-1/Fixing-Banjo.md)
- [Custom 404 Pages and Authentication files (ZIP)](../exercises/week-1/Custom_404_Auth_start.zip)


## Reference
- Banjo Authentication Docs: https://www.rit.edu/webdev/authenticating-and-authorizing-rit-users
- Advanced Scripting with .htaccess files: https://www.askapache.com/htaccess/

