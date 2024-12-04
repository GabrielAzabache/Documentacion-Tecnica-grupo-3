# DEMO: Ingreso de datos (ID, Nombre, Apellido, Sueldo)

Para crear el ejercicio planteado se decidio crear una base de datos en phpmyadmin, un html, php, javascript y css

### Base datos "demo" y tabla "empleados":
```bush
CREATE DATABASE demo;

CREATE TABLE empleados (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(50) NOT NULL,
    apellido VARCHAR(50) NOT NULL,
    sueldo DECIMAL(10, 2) NOT NULL
);

```

index.html
```bush
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ingreso de Datos</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <div class="contenedor">
        <h1>Ingreso de Datos</h1>
        <form id="formulario" action="procesar.php" method="POST">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" placeholder="Ingresa el nombre" required>
            
            <label for="apellido">Apellido:</label>
            <input type="text" id="apellido" name="apellido" placeholder="Ingresa el apellido" required>
            
            <label for="sueldo">Sueldo:</label>
            <input type="number" id="sueldo" name="sueldo" placeholder="Ejemplo: 1300.50" required>
            
            <button type="submit">Guardar</button>
        </form>
    </div>
    <script src="script.js"></script>
</body>
</html>
```


estilos.css:

```bush
/* Reseteo básico */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Estilos del cuerpo */
body {
    font-family: Arial, sans-serif;
    background-color: #f3f4f6;
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
}

/* Contenedor principal */
.contenedor {
    background: #ffffff;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px #0000001a;
    max-width: 400px;
    width: 100%;
    margin: 20px;
}

/* Título */
h1 {
    text-align: center;
    font-size: 1.8rem;
    color: #333;
    margin-bottom: 20px;
}

/* Estilos de formulario */
form {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

/* Etiquetas */
label {
    font-size: 0.9rem;
    font-weight: bold;
    color: #555;
}

/* Campos de entrada */
input {
    padding: 10px;
    font-size: 1rem;
    border: 1px solid #ccc;
    border-radius: 5px;
    outline: none;
    transition: border-color 0.3s ease;
}

input:focus {
    border-color: #007bff;
}

/* Botón */
button {
    padding: 12px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
    font-size: 1rem;
    cursor: pointer;
    transition: background-color 0.3s ease;
}

button:hover {
    background-color: #0056b3;
}

/* Adaptación móvil */
@media (max-width: 768px) {
    .contenedor {
        padding: 15px;
        margin: 10px;
    }

    h1 {
        font-size: 1.5rem;
    }

    button {
        font-size: 0.9rem;
    }
}
```
script.js

```bush
document.getElementById('formulario').addEventListener('submit', function (e) {
    const nombre = document.getElementById('nombre').value.trim();
    const apellido = document.getElementById('apellido').value.trim();
    const sueldo = parseFloat(document.getElementById('sueldo').value);

    if (nombre === '' || apellido === '' || isNaN(sueldo) || sueldo <= 0) {
        alert('Por favor, completa todos los campos correctamente.');
        e.preventDefault(); // Evita el envío del formulario
    }
});
```

procesar.php
```bush
<?php
if ($_SERVER['REQUEST_METHOD'] === 'POST') {
    // Validar entrada
    $nombre = trim($_POST['nombre']);
    $apellido = trim($_POST['apellido']);
    $sueldo = floatval($_POST['sueldo']);

    if (empty($nombre) || empty($apellido) || $sueldo <= 0) {
        die("Error: Por favor, completa todos los campos correctamente. <a href='index.html'>Volver</a>");
    }

    // Datos de conexión
    $host = 'localhost';
    $usuario = 'root';
    $contraseña = '';
    $baseDatos = 'demo';

    // Conectar a la base de datos
    $conn = new mysqli($host, $usuario, $contraseña, $baseDatos);

    if ($conn->connect_error) {
        die("Error de conexión: " . $conn->connect_error);
    }

    // Insertar datos de forma segura
    $sql = "INSERT INTO empleados (nombre, apellido, sueldo) VALUES (?, ?, ?)";
    $stmt = $conn->prepare($sql);
    $stmt->bind_param("ssd", $nombre, $apellido, $sueldo);

    if ($stmt->execute()) {
        echo "Datos guardados exitosamente. <a href='index.html'>Volver</a>";
    } else {
        echo "Error al guardar los datos: " . $stmt->error;
    }

    $stmt->close();
    $conn->close();
} else {
    echo "Acceso no permitido.";
}
?>
```


### Asegurese de realizarlo en localhost/nombre_carpeta/index.html
