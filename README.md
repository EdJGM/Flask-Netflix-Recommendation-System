# Netflix Recommendation System

Este proyecto es un sistema de recomendación de películas basado en contenido, desarrollado con Flask y utilizando datos de Netflix.

## Descripción

La aplicación permite a los usuarios ingresar el nombre de una película y obtener recomendaciones de películas similares basadas en varias características textuales (título, director, elenco, géneros y descripción).

## Estructura del Proyecto

- `app.py`: Archivo principal de la aplicación Flask que contiene la lógica de recomendación y las rutas.
- `templates/`: Carpeta que contiene las plantillas HTML (`index.html` y `result.html`).
- `static/stylesheets/`: Carpeta que contiene los archivos CSS (`style.css` y `result.css`).
- `netflix_titles.csv`: Archivo CSV que contiene los datos de las películas y programas de TV de Netflix.

## Instalación

1. Clona el repositorio:

   ```sh
   git clone https://github.com/tu_usuario/tu_repositorio.git
   cd tu_repositorio
   ```
2. Crea un entorno virtual e instala las dependencias:

    ```sh
    python -m venv venv
    venv\Scripts\activate  # En Windows
    # source venv/bin/activate  # En macOS/Linux
    pip install -r requirements.txt
    ```

3. Asegúrate de tener el archivo netflix_titles.csv en el directorio raíz del proyecto.

## Ejecución

Para ejecutar la aplicación localmente, usa el siguiente comando:

    ```sh
    python app.py
    ```

Luego, abre tu navegador y ve a http://localhost:8000.

## Uso

1. Abre la aplicación en tu navegador.
2. Ingresa el nombre de una película en el campo de texto.
3. Haz clic en "submit" para obtener las recomendaciones.

## Archivos CSS
- style.css
    Este archivo contiene los estilos para la página principal (index.html).

- result.css
    Este archivo contiene los estilos para la página de resultados (result.html).

## Archivos HTML
- index.html
    Página principal donde los usuarios pueden ingresar el nombre de una película.

- result.html
    Página de resultados que muestra las recomendaciones de películas.

## Código Principal (app.py)
- **Limpieza de Datos:** Se limpian los datos eliminando espacios y convirtiendo todo a minúsculas.

- **Creación de la "Sopa" de Palabras:** Se combinan varias características textuales de cada película.

- **Vectorización de Texto:** Se utiliza CountVectorizer para convertir la "sopa" de palabras en una matriz de conteo de palabras.

- **Cálculo de Similitud:** Se calcula la similitud del coseno entre las películas.

- **Generación de Recomendaciones:** Se obtienen las películas más similares basadas en la similitud del coseno.