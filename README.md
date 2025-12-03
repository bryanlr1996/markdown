<h1 align="center">Parquet Editor</h1>

<p><strong>Versión:</strong> 1.0</p>
<p><strong>Descripción:</strong> App con Streamlit que permite leer archivos .parquet de un Azure DataLake Storage. Se pueden editar registros, eliminar registros y añadir registros. También permite buscar registros duplicados y finalmente descargar el parquet una vez hemos terminado de modificarlo.</p>
<p><strong>Consideraciones:</strong> Esta primera versión no permite leer parquets encriptados. La primera vez que se ejecuta Parquet Editor puede tardar unos minutos en arrancar ya que tiene que preparar un entorno virtual en el cual instala las dependencias necesarias. La carga del parquet puede tardar unos minutos si el cluster estaba apagado.</p>
