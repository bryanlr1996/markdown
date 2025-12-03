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
<img width="886" height="258" alt="image" src="https://github.com/user-attachments/assets/e03f502f-c972-430a-b589-cd52fca1225c" />

Una vez se ejecuta Streamlit, se abre el navegador que tengamos por defecto y veremos un formulario con dos campos:

- **Ruta del parquet**: debemos introducir la ruta donde se encuentra el archivo dentro de Azure DataLake Storage. Tiene que tener el siguiente formato:
`abfss://<contenedor>@<storage>.dfs.core.windows.net/<ruta hasta el parquet>`

<img width="886" height="43" alt="image" src="https://github.com/user-attachments/assets/557c6371-cc5a-4da6-8cab-6da5becf0054" />
<br/><br/>

- **Clave de acceso**: debemos introducir la clave de acceso del storage para poder acceder al parquet. Esta clave la podemos encontrar en Azure, buscando el recurso y accediendo a la sección de Claves de acceso. Debemos hacer clic en **Mostrar**.
<img width="780" height="417" alt="image" src="https://github.com/user-attachments/assets/c1e6a012-1931-497a-9f68-fc52579f77b4" />

> ❌ **Alerta:**  
> No tocar en ningún caso la opción "Girar clave".  
> Esto reinicia la clave y puede dañar el resto de proyectos que la utilicen.
<br/><br/>

Una vez hemos rellenado los dos campos, le podemos dar a **Buscar Parquet**. Esta acción puede requerir cierto tiempo en función del tamaño del parquet y de si el clúster estaba activo.<br/>
Si se ha podido cargar el parquet, nos mostrará una tabla editable con los registros. En caso de no poder leer el parquet, nos mostrará un error durante 5 segundos y nos devolverá a la pantalla inicial.


**3. Modificar Parquet**
<img width="1035" height="310" alt="image" src="https://github.com/user-attachments/assets/f3ba8027-f665-4d21-903b-14c78421f43d" />

Una vez tengamos el parquet cargado, veremos una **tabla con los registros**. Para editar un campo de un registro, hacemos **doble clic** en la celda correspondiente. 

Para **eliminar registros**, podemos hacer clic en la **primera columna** del registro para seleccionarlo, lo que habilita la opción de eliminar (icono de **papelera** sobre la tabla en el lado derecho). 

Si queremos **seleccionar todos los registros**, podemos hacerlo haciendo clic en la **celda superior izquierda**.

Para **añadir un nuevo registro**, debemos ir a la parte inferior de la tabla (último registro) y añadir una nueva fila.


**4. Cerrar parquet**

Al hacer clic en **Cerrar parquet**, volveremos a la **pantalla inicial** sin guardar los cambios.

**5. Registros duplicados**

Al hacer clic en este botón podemos ver **cuántos registros están duplicados**. 

- Si **no hay duplicados**, se mostrará el mensaje: *"No hay registros duplicados"*.
- Si **hay duplicados**, se mostrará una **tabla** con dichos registros.


**6. Guardar cambios**

Al hacer clic en este botón, se nos pedirá **introducir el nombre** con el que queremos guardar el parquet. Una vez confirmado, se mostrará el mensaje: *"Archivo preparado para guardar"* y un botón que permite **descargarlo en local**.
<img width="449" height="359" alt="image" src="https://github.com/user-attachments/assets/b9e0c273-ea91-4798-b0dc-04bc874f7336" />

> 💡 **Nota:** Por ahora, la descarga es **local** y **no modifica el archivo original**.
