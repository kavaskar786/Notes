1. req
	1. html
	2. php
2. versions
3. installation
	1. zip
	2. c:/xampp/htdocs/(extract)
4. need to change the base url with the application name (c:xampp/htdocs/applicaionname/application/config/config.php)
5. need to give the database username(usally root), pass and db name in c:xampp/htdocs/applicaionname/application/config/database.php
6. like wise create one db in phpmyadmin page
7. create one .htaccess file in 
	1. ```perl
	RewriteEngine on
	RewriteCond $1 !^(index\.php|resources|robots\.txt)
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule ^(.*)$ index.php?/$1 [L,QSA]
8. to access the controllers without the help of the index.php
9. sdf


	
