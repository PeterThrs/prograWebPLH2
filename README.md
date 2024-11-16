# Consumo de APIs en Angular

Se utiliza la API pública: https://api.escuelajs.co/api/v1/users


## Servicio para consumir el API
<div align='center'>
    <img  src="src/assets/img-reporte/img1.png" width="50%">
    <p>Codigo para conosumir el api</p>
</div>

- HttpClient: Es un servicio que permite realizar solicitudes HTTP (GET, POST, PUT, DELETE, etc.) desde tu aplicación Angular.

- Injectable: Marca esta clase como un servicio que puede ser inyectado en otros componentes o servicios de Angular mediante el sistema de Inyección de Dependencias. Al declararlo con providedIn: 'root', Angular se encarga de instanciar este servicio como un singleton (única instancia para toda la app).

- Observable: Forma parte de rxjs (Reactive Extensions for JavaScript) y es el patrón que Angular usa para manejar flujos de datos asincrónicos, como las respuestas HTTP.

- urlBase: Define la URL base de la API que se consumirá. Es una buena práctica usar variables para las URLs en lugar de hardcodearlas en cada método.

1. Firma del método:
    - Devuelve un Observable<Usuario[]>, lo que significa que este método no retorna los datos inmediatamente, sino que proporciona un stream que emite los datos cuando están disponibles.
    - El tipo Usuario[] indica que se espera una respuesta en forma de un array de objetos del tipo Usuario.

2. Llamada HTTP:
    - this.clienteHttp.get<Usuario[]>(this.urlBase):
    Usa el método get del servicio HttpClient para realizar una solicitud HTTP GET a la API.
    - El tipo genérico <Usuario[]> le indica a TypeScript qué tipo de datos espera de la respuesta (un array de usuarios).
    - this.urlBase: La URL a la que se envía la solicitud.

3. Retorno:
    - return: Devuelve el observable generado por HttpClient. Este observable puede ser suscrito por cualquier componente o servicio que necesite usar los datos.


## Agregar HttpClientModule
<div align='center'>
    <img  src="src/assets/img-reporte/img2.png" width="50%">
    <p>Agregacion de HttpClientModule para realizar peticiones HTTP</p>
</div>

1. Explicación del provideHttpClient
    - provideHttpClient(withFetch()): Configura HttpClient para usar la API Fetch. Esto puede ser útil para aprovechar las capacidades modernas de Fetch API, como mejores promesas y soporte para streams.
    - provideHttpClient(): Simplemente proporciona HttpClient sin ninguna configuración adicional.
    - Ambos se aseguran de que HttpClient esté disponible en toda tu aplicación, permitiéndote hacer solicitudes HTTP desde tus servicios.

## Consumir el servicio en un Componente
<div align='center'>
    <img  src="src/assets/img-reporte/img3.png" width="50%">
    <p>Metodo para consumir el servicio</p>
</div>

- En el código se muestra cómo un componente en Angular utiliza el servicio para consumir una API y manejar los datos obtenidos.

1. ngOnInit
    - ngOnInit(): Método del ciclo de vida del componente que se ejecuta automáticamente después de que Angular ha inicializado el componente.
    - Dentro de ngOnInit, se llama al método obtenerUsuarios para cargar los datos cuando el componente se inicializa.

2. subscribe
    - subscribe: Escucha las respuestas del observable.
        - next: Se ejecuta si la solicitud es exitosa.
            - Asigna los datos obtenidos (datos) a las propiedades:
                - this.usuarios: Almacena los usuarios obtenidos.
                - this.dataSource.data: Si se está utilizando una tabla (como Angular Material), actualiza los datos para mostrar en el frontend.
        - error: Maneja errores si la solicitud falla.



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
