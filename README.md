# Consumo de APIs en Angular

Se utiliza la API pública: https://api.escuelajs.co/api/v1/users

<div align='center'>
    <img  src="src/assets/img-reporte/img1.png" width="300">
    <p>Servicio usuario para consumir el api</p>
</div>

<div align='center'>
    <img  src="src/assets/img-reporte/img2.png" width="300">
    <p>Agregacion de HttpClientModule para realizar peticiones HTTP</p>
</div>

<div align='center'>
    <img  src="src/assets/img-reporte/img3.png" width="300">
    <p>Metodo para consumir el servicio</p>
</div>

## Preguntas

¿Qué hace el método getUsers en este servicio?
Consume el api y regresa una Observable que contiene un arreglo de datos

¿Por qué es necesario importar HttpClientModule?
HttpClientModule es necesario en Angular para habilitar el uso de HttpClient, que permite realizar peticiones HTTP a APIs y servidores externos en la aplicación.

¿Qué función cumple el método ngOnInit en el componente UserListComponent?
El método ngOnInit se utiliza para inicializar el componente y es el lugar ideal para cargar datos o llamar servicios cuando el componente se muestra por primera vez en la vista.

¿Para qué sirve el bucle *ngFor en Angular?
El bucle *ngFor en Angular permite iterar sobre una lista de elementos y renderizarlos en la plantilla del componente, mostrando cada elemento de forma dinámica en la vista.

¿Qué ventajas tiene el uso de servicios en Angular para el consumo de APIs?
Los servicios centralizan la lógica de consumo de datos, permitiendo que los componentes se enfoquen en la presentación. Facilitan la reutilización del código, la inyección de dependencias y las pruebas, mejorando la estructura y mantenimiento de la aplicación.

¿Por qué es importante separar la lógica de negocio de la lógica de presentación?
Separar estas lógicas permite que los componentes sean más manejables y modulares, facilitando cambios en la interfaz sin afectar la lógica de negocio y manteniendo el código más claro y escalable.

¿Qué otros tipos de datos o APIs podrías integrar en un proyecto como este?
Podrías añadir APIs de autenticación, geolocalización, pagos, redes sociales o análisis. Estas integraciones aportan funciones adicionales que enriquecen la experiencia del usuario y amplían las capacidades del proyecto.
