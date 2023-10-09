**Basic Syntax:**

```php
<?php
    // PHP code here
?>
```

**Variables and Data Types:**

```php
$variable_name = value; // Declare a variable
$string = "Hello, World!";
$integer = 42;
$float = 3.14;
$boolean = true;
$array = array(1, 2, 3);
```

**Output:**

```php
echo "Output text"; // Outputs text
print("Output text"); // Also outputs text
```

**Operators:**

```php
+  -  *  /  %  //  **  ==  ===  !=  !==  <  >  <=  >=  &&  ||  !
```

**Conditional Statements:**

```php
if (condition) {
    // Code to execute if condition is true
} elseif (another_condition) {
    // Code to execute if another_condition is true
} else {
    // Code to execute if neither condition is true
}
```

**Loops:**

```php
for ($i = 0; $i < 5; $i++) {
    // Loop code here
}

foreach ($array as $value) {
    // Loop code here
}

while (condition) {
    // Loop code here
}
```

**Functions:**

```php
function functionName($parameter1, $parameter2) {
    // Function code here
    return $result;
}
```

**Arrays:**

```php
$myArray = array("apple", "banana", "cherry");

// Accessing array elements
$firstElement = $myArray[0];

// Associative arrays
$assocArray = array("name" => "John", "age" => 30);
$value = $assocArray["name"];
```

**Super Globals:**

```php
$_GET['parameter']; // Access data sent via GET method
$_POST['parameter']; // Access data sent via POST method
$_SESSION['variable']; // Access session variables
```

**File Operations:**

```php
$file = fopen("filename.txt", "r"); // Open a file for reading
$data = fread($file, filesize("filename.txt")); // Read file content
fclose($file); // Close the file

$file = fopen("newfile.txt", "w"); // Open a file for writing
fwrite($file, "Hello, PHP!"); // Write to file
fclose($file);
```

**Database Connection (MySQL):**

```php
$servername = "localhost";
$username = "username";
$password = "password";
$dbname = "database_name";

$conn = new mysqli($servername, $username, $password, $dbname);

if ($conn->connect_error) {
    die("Connection failed: " . $conn->connect_error);
}
```

**Error Handling:**

```php
try {
    // Code that may throw an exception
} catch (Exception $e) {
    // Handle the exception
}
```

