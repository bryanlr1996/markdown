<h1 align="center">Parquet Editor</h1>

<p><strong>Versión:</strong> 1.0</p>
<p><strong>Descripción:</strong> App con Streamlit que permite leer archivos .parquet de un Azure DataLake Storage. Se pueden editar registros, eliminar registros y añadir registros. También permite buscar registros duplicados y finalmente descargar el parquet una vez hemos terminado de modificarlo.</p>
<p><strong>Consideraciones:</strong> Esta primera versión no permite leer parquets encriptados. La primera vez que se ejecuta Parquet Editor puede tardar unos minutos en arrancar ya que tiene que preparar un entorno virtual en el cual instala las dependencias necesarias. La carga del parquet puede tardar unos minutos si el cluster estaba apagado.</p>

## Guía de uso

**1. Ejecutar el launcher**  
   Al hacer clic sobre `launcher.exe`, se abrirá un terminal que comprobará si tenemos un entorno virtual creado. En caso de existir, ejecuta Streamlit. Si no hay un entorno virtual con las dependencias requeridas, crea el entorno e inicia la instalación.

<img width="348" height="175" alt="image" src="https://github.com/user-attachments/assets/68b7793f-5249-43f4-b116-6667fab6fb8a" />

<img width="573" height="135" alt="image" src="https://github.com/user-attachments/assets/07c61fe1-0334-45d5-99af-72d96c143b22" />
<br/><br/>
**2. Cargar archivo parquet**  

Una vez se ejecuta Streamlit, se abre el navegador que tengamos por defecto y veremos un formulario con dos campos:

- **Ruta del parquet**: debemos introducir la ruta donde se encuentra el archivo dentro de Azure DataLake Storage. Tiene que tener el siguiente formato:
`abfss://<contenedor>@<storage>.dfs.core.windows.net/<ruta hasta el parquet>`

<img width="886" height="43" alt="image" src="https://github.com/user-attachments/assets/557c6371-cc5a-4da6-8cab-6da5becf0054" />
