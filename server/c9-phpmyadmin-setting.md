#
C9.io


## PHP

### Using PHPMyAdmin with Cloud9
Here we'll explain how to install a PHPMyAdmin instance right in your workspace. Each workspace runs its own database and copy of PHPMyAdmin.

First, create a PHP workspace so you have PHP, MySQL, and Apache installed right away. You can then make sure you have MySQL installed by running:

```
$ mysql-ctl install
```
Then install phpMyAdmin:

```bash
$ phpmyadmin-ctl install
```

After the installation is complete you'll just want to make sure mysql is running once more:

```
mysql-ctl start
```

After installing phpMyAdmin, you were given a link to access PHPMyAdmin which will follow the pattern of: https://[workspacename]-[username].c9users.io/phpmyadmin. From that link, you can login with your Cloud9 username and a blank password.

### Creating a Database
You can create a database by clicking on the "Databases" tab up the top. On this page you'll see a "Create database" field where you can enter the name and create a new database.

If you'd like further help using the software please consult the official PHPMyAdmin docs167

### Security
Because MySQL has a blank password by default and phpMyAdmin uses the same credentials as MySQL, phpMyAdmin has a blank password by default as well. This is great because it makes setup significantly easier for users. Additionally, since developers generally don't (and often shouldn't) put sensitive/important data in a development environment like Cloud9, having no password on phpMyAdmin is rarely an issue.

If you do have sensitive data in the database in your workspace or if you feel safer locking down your database, you can simply change your MySQL password and lock down your database as you'd like to.

If my Cloud9 username is "myUser" then I can change my password to "test" by running:

```sql
SET PASSWORD FOR 'myUser'@'%' = PASSWORD('test');
```

From this point, I'll get into the CLI for MySQL by doing:

```
mysql -u myUser -p
```
Then I'll be prompted for my password.

https://community.c9.io/t/setting-up-phpmyadmin/1723

---

### PHP Connect DB C9

```php
<?php
//Connect to the database
$host = "127.0.0.1";
$user = "your_username"; //Your Cloud 9 username
$pass = ""; //Remember, there is NO password by default!
$db = "c9"; //Your database name you want to connect to
$port = 3306; //The port #. It is always 3306
$connection = mysqli_connect($host, $user, $pass, $db, $port)or die(mysql_error());



//And now to perform a simple query to make sure it's working
$query = "SELECT * FROM users";
$result = mysqli_query($connection, $query);

while ($row = mysqli_fetch_assoc($result)) {
echo "The ID is: " . $row['id'] . " and the Username is: " . $row['username'];
}

?>
```
