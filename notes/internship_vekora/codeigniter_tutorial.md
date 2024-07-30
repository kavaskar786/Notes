1. MVC frame work
2. Requirements
	1. HTML
	2. PHP
3. history of codeigniter
	1. ELLISLAB
	2. british columbia  institute of tecnology (project)
4. versions
	1. version-3 most famous
		2. 3.1.11
	2. verstion-4 
5. how to work with the codeigniter
	1. download the zip from the official code igniter website
	2. and extract the zip file
	3. in the application_fold -> config fold -> config.php -> change the base_url as http://localhost/project_name
	4. go to the database.php file and change the username(root) and pass(nothing) and database name
	5. change the project name according to the config file
	6. open the xampp or wamp and start the admin and mysql servers
	7. finally open the browser and enter the http://localhost/project_name to see the welcome page of the code igniter
6. how to remove the index.php from the url
	1. to access a controller you have to put index.php in the url it is annoying so to remove that we need to 
		1. create the .htaccess and need to enter the following code in it
			1. 1. ```perl
				RewriteEngine on
				RewriteCond $1 !^(index\.php|resources|robots\.txt)
				RewriteCond %{REQUEST_FILENAME} !-f
				RewriteCond %{REQUEST_FILENAME} !-d
				RewriteRule ^(.*)$ index.php?/$1 [L,QSA]
		2. and in the browser now enter the url like http://local/project_name/controller_name
		3. so that finally the index.php is fully removed
7. how to load a view
	1. inside the welcome class
	2. write the public index function
	3. from this function only the actual code will starts to execute
	4. to call the view use this inbuilt function $this->load->view('view_name');
	5. with that same view_name the view file need to be there in the views fold of the application
	6. and in the browser now enter the url like http://local/project_name/controller_name
	7. and the user can able to see the view in the browser
8. how to add mutiple views in controller
	1. inside the index funtion
	2. first add the header view above the all contents like this $this->load->view('header_view_name'); like this
	3. first add the footer view below the all contents like this $this->load->view('footer_view_name'); like this
9. how to store information with session
	1. to start the session
	2. we need to first load the session library with this command
		1. $this->load->library('session');
	3. created the form with meth post and action with the php code like this
		1.  form method="post" action="<?= base_url('welcome/save') ?>"
	4. two inputs like this
		1. input type="text" name="name"
		2. input type="submit" value="save"
	5. the form is calling the save function inside the welcome controller using the base_url function
		1. to work with this function we need to include the helpler like this
			1. $this->load->helper('url') ;
	6. to work with session we need to first include the session library as mentioned above
	7. and we need to get the data from the post method like this
		1. $name = $this->input->post('name');
			1. checks the name in the html code
	8. to set that value into the session the following syntax will be used
		1. $this -> session ->set_userdata('name',dollarsymbolvalue);
			1. first param is key and the secondone is value to that particular key
	9. to use the setted data from the session id
		1. $this -> session -> userdata('name');
			1. here name is the key value of the setted data
	10. finally redirect to the actual controller to rerender and to see the updated session information
	11. to check whether the data is available in the session or not we will use the following code
		1. $this->session->has_userdata('name');
			1. here name is key
	12. to remove the session data
		1. $this->session->unset_userdata('name');
			1. here name is key
10. how to connect with the database
	1. two ways to connect
		1. automatic
		2. manual
	2. automatic
		1. application fold -> config -> libraries = array('database');
	3. manual
		1. $this->load->database();
11. how to configure database
	1. go application fold config fold in that database.php
	2. in default change
		1. hostname as localhost
		2. username as root
		3. pass nothing
		4. database as db_name
		5. dsn - values with string
	3. gen info
		1. hostname - name of the server
		2. dbdriver
		3. dbprefix - used for stimultaneous use of database
		4. pconnect - continous connection
		5. db_debug
		6. chache
		7. char_set
		8. dbcollat
		9. swap_pre
		10. encrypt
		11. compress
		12. strcton
		13. failover
		14. save_queries
12. how to insert into database
	1. create the table in the database of the xampp first
	2. create three files they are
		1. crud.php - controller
		2. crud_model.php - model
		3. insert.php - view
	3. create the controller first
	4. extend the CI_controller
	5. create the __construct() function
			1. by calling this function only will give the all properties
	6. load the database
	7. load the model using
			1. $this->load->model('model_name')
	8. to insert the data into database by using the the below method
		1. $this->db->insert('table_name',data)
		2. 
	9.  
	10. 
		
	
