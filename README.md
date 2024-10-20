# LAMP-Stack
Sure! Here’s a simple guide for creating a basic LAMP stack project, along with a sample README file for your GitHub portfolio.

### Basic LAMP Stack Project

**LAMP** stands for Linux, Apache, MySQL, and PHP. This stack is commonly used for web development.

#### Prerequisites

1. **Linux** (Ubuntu preferred)
2. **Apache** web server
3. **MySQL** database
4. **PHP** programming language

### Step 1: Install LAMP Stack

You can install the LAMP stack using the following commands:

```bash
sudo apt update
sudo apt install apache2
sudo apt install mysql-server
sudo apt install php libapache2-mod-php php-mysql
```

### Step 2: Start and Enable Services

Make sure that Apache and MySQL are running:

```bash
sudo systemctl start apache2
sudo systemctl start mysql
sudo systemctl enable apache2
sudo systemctl enable mysql
```

### Step 3: Test Apache

Open your web browser and type `http://localhost`. You should see the Apache2 Ubuntu Default Page.

### Step 4: Test PHP

Create a PHP info file to test PHP:

```bash
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
```

Now visit `http://localhost/info.php`. You should see a page displaying PHP configuration information.

### Step 5: Set Up MySQL

Secure your MySQL installation:

```bash
sudo mysql_secure_installation
```

Follow the prompts to set up a root password and secure your MySQL server.

### Step 6: Create a Simple PHP Application

1. **Create a database:**
   ```bash
   sudo mysql -u root -p
   CREATE DATABASE mydatabase;
   EXIT;
   ```

2. **Create a PHP file to connect to the database:**

Create a new PHP file:

```bash
sudo nano /var/www/html/db.php
```

Add the following code:

```php
<?php
$servername = "localhost";
$username = "root"; // or your MySQL username
$password = "yourpassword"; // your MySQL password
$dbname = "mydatabase";

// Create connection
$conn = new mysqli($servername, $username, $password, $dbname);

// Check connection
if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
echo "Connected successfully";
?>
```

### Step 7: Test the Database Connection

Visit `http://localhost/db.php` to test the database connection.

### README.md

Here’s a sample README file for your GitHub portfolio:

```markdown
# Basic LAMP Stack Project

## Description

This project demonstrates a basic LAMP (Linux, Apache, MySQL, PHP) stack setup. It includes installation instructions, basic configuration, and a sample PHP application that connects to a MySQL database.

## Prerequisites

- Ubuntu (or any other Linux distribution)
- Basic knowledge of terminal commands

## Installation

1. **Install LAMP Stack**: Follow the instructions below to install Apache, MySQL, and PHP.
   ```bash
   sudo apt update
   sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql
   ```

2. **Start Services**:
   ```bash
   sudo systemctl start apache2
   sudo systemctl start mysql
   sudo systemctl enable apache2
   sudo systemctl enable mysql
   ```

3. **Test Apache**: Visit `http://localhost` in your browser.

4. **Test PHP**: Create a PHP info file to verify PHP is working:
   ```bash
   echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
   ```

5. **Set Up MySQL**: Secure your MySQL installation:
   ```bash
   sudo mysql_secure_installation
   ```

6. **Create a Database**: Access MySQL and create a new database.
   ```sql
   CREATE DATABASE mydatabase;
   ```

7. **Connect to MySQL with PHP**: Create a `db.php` file to test the connection.

## Usage

- Visit `http://localhost/info.php` to see PHP info.
- Visit `http://localhost/db.php` to test the database connection.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- Inspired by LAMP Stack tutorials and documentation.
```

Feel free to modify any part of this guide or README to suit your specific project needs!
