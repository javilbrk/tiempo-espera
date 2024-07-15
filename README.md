
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tiempo de Espera en Urgencias Hospital Dr. Gustavo Fricke</title>
    <style>
        body {
            font-family: Calibri, Arial, sans-serif; /* Tipografía Calibri como primera opción */
            text-align: center;
            margin: 0; /* Ajustar el margen a 0 para ocupar todo el espacio */
            background: linear-gradient(to bottom right, #4e8cff, #4e4cff); /* Fondo azul en degradé */
            color: #fff; /* Color de texto blanco para contraste */
        }
        h1 {
            color: #fff; /* Color de título blanco */
            padding-top: 50px; /* Espacio adicional arriba del título */
        }
        .formulario {
            margin-top: 20px; /* Espacio adicional arriba del formulario */
        }
        form {
            background: rgba(255, 255, 255, 0.7); /* Fondo semi-transparente para el formulario */
            padding: 20px; /* Espacio interno dentro del formulario */
            border-radius: 10px; /* Bordes redondeados */
            display: inline-block; /* Alinear el formulario en línea con el texto */
        }
        label {
            display: block; /* Mostrar etiquetas en bloques separados */
            margin-bottom: 5px; /* Espacio entre etiquetas y campos de entrada */
        }
        input[type="text"] {
            width: 200px; /* Ancho del campo de entrada de texto */
            padding: 5px; /* Espaciado interno */
            margin-bottom: 10px; /* Espacio abajo del campo de entrada */
            border-radius: 5px; /* Bordes redondeados */
            border: 1px solid #ccc; /* Borde del campo de entrada */
        }
        button[type="submit"] {
            background-color: #4caf50; /* Color de fondo verde para el botón */
            color: white; /* Color de texto blanco */
            padding: 10px 20px; /* Espacio interno del botón */
            border: none; /* Quitar borde del botón */
            cursor: pointer; /* Cambiar cursor al pasar por encima */
            border-radius: 5px; /* Bordes redondeados */
        }
        .tiempo-espera {
            display: none; /* Ocultar el elemento por defecto */
            font-size: 1.5rem; /* Tamaño de fuente para el tiempo de espera */
            margin-top: 20px; /* Espacio adicional arriba del tiempo de espera */
        }
    </style>
</head>
<body>
    <header>
        <h1>Tiempo de Espera en Urgencias Hospital Dr. Gustavo Fricke</h1>
    </header>
    <section>
        <div class="formulario">
            <form id="formulario-paciente">
                <label for="rut">RUT del paciente:</label>
                <input type="text" id="rut" name="rut" required>
                <br><br>
                <button type="submit">Enviar</button>
            </form>
        </div>
        <div class="tiempo-espera" id="tiempo-espera">Esperando datos...</div>
    </section>
    <script>
        // Función para procesar el formulario y mostrar el tiempo de espera con categorización ESI
        document.getElementById('formulario-paciente').addEventListener('submit', function(event) {
            event.preventDefault();
            let rut = document.getElementById('rut').value;

            // Simulación de tiempo de espera aleatorio entre 5 y 60 minutos
            let tiempoEspera = Math.floor(Math.random() * (60 - 5 + 1)) + 5;

            // Determinar categorización ESI según el tiempo de espera
            let categoria = '';
            if (tiempoEspera <= 5) {
                categoria = 'ESI 1 (Grave)';
            } else if (tiempoEspera <= 15) {
                categoria = 'ESI 2 (Mediana gravedad)';
            } else if (tiempoEspera <= 30) {
                categoria = 'ESI 3 (Menos grave)';
            } else if (tiempoEspera <= 45) {
                categoria = 'ESI 4 (Leve)';
            } else {
                categoria = 'ESI 5 (Atención general)';
            }

            // Mostrar el tiempo de espera y categorización ESI
            document.getElementById('tiempo-espera').style.display = 'block'; // Mostrar el elemento
            document.getElementById('tiempo-espera').textContent = `RUT ${rut}, su tiempo de espera estimado es de ${tiempoEspera} minutos. Categorización: ${categoria}.`;
        });
    </script>
</body>
</html>
