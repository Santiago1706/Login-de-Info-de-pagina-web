# Login-de-Info-de-pagina-web

<!DOCTYPE html>
<html lang="es">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Página de Inicio de Sesión</title>
    <style>
        /* Estilos de la página */
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
        }
        .main-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            background-color: #c9d5ff;
            border-radius: 30px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.35);
            overflow: hidden;
            width: 768px;
            max-width: 100%;
        }
        .image-container {
            flex: 1;
            background-image: url('https://ideogram.ai/assets/image/lossless/response/6Ml6oamMQxOmD6cODLJgLg');
            background-size: cover;
            background-position: center;
            height: 200px;
        }
        .form-container {
            flex: 1;
            padding: 40px;
            background-color: #fff;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }
        .form-container h1 {
            font-size: 1.5rem;
            color: #512da8;
            margin-bottom: 20px;
        }
        .form-container input {
            background-color: #eee;
            border: none;
            margin: 8px 0;
            padding: 10px 15px;
            font-size: 13px;
            border-radius: 8px;
            width: 100%;
            outline: none;
        }
        .form-container button {
            background-color: #512da8;
            color: #fff;
            font-size: 12px;
            padding: 10px 45px;
            border: 1px solid transparent;
            border-radius: 8px;
            font-weight: 600;
            text-transform: uppercase;
            margin-top: 10px;
            cursor: pointer;
        }
        .form-container #error-message {
            display: none;
            color: red;
            margin-top: 10px;
        }
        .form-container #loading-spinner {
            display: none;
            margin-top: 10px;
            color: #512da8;
        }
        #main-content {
            display: none;
            text-align: center;
            padding: 40px;
            background-color: #fff;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
            border-radius: 30px;
        }
        nav ul {
            list-style: none;
            padding: 0;
        }
        nav ul li {
            display: inline-block;
            margin: 0 10px;
        }
        nav ul li a {
            text-decoration: none;
            color: #512da8;
            font-weight: 500;
        }
        #logoutBtn {
            margin-top: 20px;
            padding: 10px 20px;
            background-color: #512da8;
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
        }
    </style>
</head>

<body>
    <div class="main-container">
        <!-- Encabezado con logo -->
        <div class="header">
            <img src="https://i.pinimg.com/originals/99/47/ef/9947ef6c76e8a40da1ef4d7a5d281809.png" alt="Logo" style="width: 50px; height: 50px;">
            <h1>Alfabetización en el Reciclaje de Artefactos Tecnológicos en el C.D.S</h1>
        </div>

        <!-- Contenedor principal -->
        <div class="container" id="login-container">
            <!-- Imagen a la izquierda -->
            <div class="image-container"></div>

            <!-- Formulario a la derecha -->
            <div class="form-container">
                <form id="loginForm" onsubmit="return false;">
                    <h1>Iniciar Sesión</h1>
                    <input type="text" id="username" placeholder="Usuario" required>
                    <input type="password" id="password" placeholder="Contraseña" required>
                    <button type="submit">Iniciar Sesión</button>
                    <p id="error-message"></p>
                    <div id="loading-spinner">Verificando información...</div>
                </form>
            </div>
        </div>

        <!-- Contenido principal que se muestra tras el login -->
        <div id="main-content">
            <h1>Bienvenido a la Página Principal</h1>
            <nav>
                <ul>
                    <li><a href="file:///C:/Users/esteban%20laiseca%20hoyo/OneDrive/Escritorio/ARTICULO%20INVESTIGATIVO/CODIGO%20HTML/P%C3%A1gina%20Web.html#inicio">Pagina Web (Sublime)</a></li>
                    <li><a href="https://santiago1706.github.io/Alfabetizaci-n-en-el-Reciclaje-de-Artefactos-Tecnol-gico-en-el-C.D.S/">Pagina web (Github)</a></li>
                    <li><a href="file:///C:/Users/esteban%20laiseca%20hoyo/OneDrive/Escritorio/ARTICULO%20INVESTIGATIVO/CODIGO%20HTML/TEXT%20HTML">Codigo HTML</a></li>
                </ul>
            </nav>
            <button id="logoutBtn">Cerrar Sesión</button>
        </div>
    </div>

    <script>
        const validUsername = "Santiago";
        const validPassword = "1087812026";

        document.getElementById("loginForm").addEventListener("submit", function(event) {
            event.preventDefault(); // Evita que el formulario recargue la página.

            const username = document.getElementById("username").value;
            const password = document.getElementById("password").value;
            const errorMessage = document.getElementById("error-message");
            const loadingSpinner = document.getElementById("loading-spinner");

            // Ocultar mensaje de error, mostrar spinner
            errorMessage.style.display = "none";
            loadingSpinner.style.display = "block";

            // Simular un tiempo de espera para verificar las credenciales
            setTimeout(() => {
                if (username === validUsername && password === validPassword) {
                    // Ocultar el contenedor de login y mostrar el contenido principal
                    document.getElementById("login-container").style.display = "none";
                    document.getElementById("main-content").style.display = "block";
                } else {
                    // Si las credenciales son incorrectas, muestra el mensaje de error
                    errorMessage.textContent = "Usuario o contraseña incorrecta. Verifícalo e inténtalo de nuevo.";
                    errorMessage.style.display = "block";
                    loadingSpinner.style.display = "none";
                }
            }, 2000); // Simula 2 segundos de carga
        });

        // Cerrar sesión
        document.getElementById("logoutBtn").addEventListener("click", function() {
            // Ocultar el contenido principal y mostrar el formulario de login
            document.getElementById("main-content").style.display = "none";
            document.getElementById("login-container").style.display = "flex";
        });
    </script>
</body>

</html>
