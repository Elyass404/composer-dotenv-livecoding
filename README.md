# composer-dotenv-livecoding
Hello everyone, in this repo you will find the steps to install the PHP package manager "COMPOSER", and also how to use "vlucas" in order to benifit from the dotenv file.

## step 1: Install composer

#### 1.1 Download the composer package manager

check the folder called "download composer" in this repository

### 1.2 Install the composer 

    1- Go to downloads folder in your machine, and chack for the composer installer.

    2- Double click on it and follow the installation guide.

    3-complete the installing process.

## step 2: Install vlucas/phpdotenv package into your project directory

    1- open command line.

    2-Head to your project local directory, by writing this command => cd "path to the project",
    
    Example : cd C:\xampp\htdocs\web-application-project

    3-install the vlucas/dotenv package with this command => composer require vlucas/phpdotenv 

    4- Go check you project, if the package has been installed with success, then youl will find new files and a vendor folder got added in your project directory (like in the picture located in "package installed" folder in this repository)

    4-congratulations, now the vlucas/phpdotenv has been installed to your project, 

## step 3: add dotenv file to the root of your project and declare the eviroment varibales

This is the file where we wil put out enviroment variables, (server name, database name, database password, and username )

    1- Create ".env" file to the root of your project check photo named "create env file" in the "env" folder in this repository 

    2-Add your eviroment varibales and give with the correct information check photo "add variables to env" in the "env" folder in this repository 

    Note: No need for quotes or semi columns in the dot env file 

    3- Now Create ".example.env" file also to the root of the project like the ".env" file . In this file you will declare the eviroment varibales as you did in the ".env" file, but it will remain empty, check the "create dot example dot env file" in the "env" folder in this repository

    4-Now that you created the "dot example dot env file" declare the enviroment variables and leave them empty, check the "add varibales to dot example dot env file" in the "env" folder in this repository

## step 4: create the connection file and call the variables from the dot env file

now that we declared the variables inside the dot env file, we can move to and call them in the connection file so we can connect the database with our project.

    1- Create a file that we will contain the code to connect the database with the pages in our project, you can call it what ever you want (connection.php, config.php ...etc) check the photo "create connection file" in the "connecting project" folder in this repository.

    2- copy this code and adapt the enviroment variables to the ones you wrote in the dot env file
    HERE IS THE CODE: 

    Note: check the photo "connection code" in the "connecting project" folder in this repository.
    Note 2 : follow the comments in the code to make sure the code works for you

    
        <?php
        use Dotenv\Dotenv;

        require '../vendor/autoload.php'; // Composer autoloader 
        //make sure to give the right path to the autoloader file.

        // Load .env file from the root of your project
        $dotenv = Dotenv::createImmutable(dirname(__DIR__));
        $dotenv->load();


        /*Connect to the database using the enviroment variables you declared in the .eenv file, with
        the help of $_ENV super global variable */
        $con = mysqli_connect($_ENV['DB_SERVER'],$_ENV['DB_USERNAME'],$_ENV['DB_PASSWORD'],$_ENV['DB_NAME']);


        if($con){
        echo"Connected successfully";
        }
        ?>
    

    3- Include the connection file into the pages you want to connect with the data base using: 
    inlude("file_name"); check the photo "include connction file" in the "connecting project" folder in this repository.

## step 5: Create .gitignore file and include the files you don't want to be pushed

Now that you finished creating dotenv file, and included the enviroment variables, you should not push those sensitive information and got them seen from other people. that's why you should include that file into the
.gitignore file.

you should also add vendor folder to the .gitignore file.

    1- Create a .gitignore file check the photo "create gitignore file" in the "git ignore" folder in this repository.

    2-add the files and foleders you don't want to push, check the image "add files to git ignore" in the "git ignore folder" in this repository.

    3- DONE.

 ## Conclusion

 I hope I explained the process clearly so anyone can do it without any confusion.

 Have a nice coding session buddies!!

 #### written by Ilyass Mar.











