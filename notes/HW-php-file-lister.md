# HW - PHP File Lister


```html
<?php
	// a function we will use to filter the directory array
	function myFilter($name){
		if (substr($name, 0, 2) == ".."){
			return true; // keep the parent directory link
		} 
		
		if ($name[0] == "."){
			return false; // get rid of files and folders that start with '.' - ex. .htaccess files
		} 
		
		if (is_dir($name)){
			return true; // keep if it is a directory
		}
		
		$ext = pathinfo($name, PATHINFO_EXTENSION); // grabs file extension
		if ($ext == "html" || $ext == "htm" || $ext == "php"){
			return true; // keep it if it ends in .html, .htm or .php
		}
		
		return false; // otherwise get rid of it
	}
	
	// get all the file names in the current directory
	$dir = scandir("./"); // $dir is an array
	
	// get rid of the file names we are not interest in
	$dir = array_filter($dir,"myFilter");
	
	// loop through array and create the HTML
	$html = "<ul>\n";
	
	foreach($dir as $name){
		if($name == ".."){
			$html .= "<li><a href='$name' class='parentDirectory'>Parent Directory</a></li>\n";	
		}elseif (is_dir($name)){
			$html .= "<li><a href='$name' class='directory'>$name</a></li>\n";	
		}else{
			$html .= "<li><a href='$name'>$name</a></li>\n";	
		}
		
	}
	
	$html .= "</ul>\n";
?>
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Directory listing</title>
	<style>
	/*
		Most of these styles are from a really old article!
		https://alistapart.com/article/taminglists
	*/
	#listing {
		width: 12em;
		border-right: 1px solid #000;
		padding: 0 0 1em 0;
		margin-bottom: 1em;
		font-family: 'Trebuchet MS', 'Lucida Grande',Verdana, Lucida, Geneva, Helvetica, Arial, sans-serif;
		background-color: #90bade;
		color: #333;
	}
 
 #listing ul {
		list-style: none;
		margin: 0;
		padding: 0;
		border: none;
  }
  
 #listing li {
		border-bottom: 1px solid #90bade;
		margin: 0 0 1px 0;
  }
  
  #listing li a {
		display: block;
		padding: 5px 5px 5px 0.5em;
		border-left: 10px solid #1958b7;
		border-right: 10px solid #508fc4;
		background-color: #2175bc;
		color: #fff;
		text-decoration: none;
		width: 100%;
  } 
  
  #listing li a {
  	width: auto;
  }
  
  #listing li a:hover {
		border-left: 10px solid #1c64d1;
		border-right: 10px solid #5ba3e0;
		background-color: #2586d7;
		color: #fff;
  }
  
   #listing .parentDirectory::before{
   	content: "<-- ";
   	color: #ffaaaa;
   }
  
   #listing .directory::after{
   	content: " --> ";
   	color: #ffaaaa;
   }
	</style>
</head>
<body>
<div id="listing">
<?php
	echo $html;
?>
</div>
</body>
</html>
```

![Screenshot](_images/php-file-lister-1.jpg)

![Screenshot](_images/php-file-lister-2.jpg)

![Screenshot](_images/php-file-lister-3.jpg)
