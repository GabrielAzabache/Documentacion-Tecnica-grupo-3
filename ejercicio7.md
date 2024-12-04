# Conexion a la base de datos MySQL

Para conectarte a una base de datos MySQL se puede usar PHP, pero para llegar a eso es necesario establecer una conexión usando la dirección del servidor MySQL teniendo en cuenta:
1) Tener instalado XAMPP y que funcione.
2) El servidor MySQL debe estar iniciado desde el Panel de Control de XAMP
3) Tiene que tener los siguientes datos:
   Host: Por defecto, será localhost.
   Usuario: Por defecto, root.
   Contraseña: Por defecto, está vacía (sin contraseña).
   Base de datos: Debemos asegurarnos de haber creado una base de datos en phpMyAdmin.

Una de las maneras de establecer una conexion con MySQL usando PHP es de la siguiente manera:
 ```bash
<?php
$servername = "localhost";
$database = "base_de_datos";
$username = "root";
$password = "";
// Create connection
$conn = mysqli_connect($servername, $username, $password, $database);
// Check connection
if (!$conn) {
    die("Connection failed: " . mysqli_connect_error());
}
echo "Connected successfully";
mysqli_close($conn);
?>
 ```
