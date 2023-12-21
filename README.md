# TaskForce - Gestión de Tareas
TaskForce es una aplicación web desarrollada en Django que permite a los usuarios administrar tareas, dividirlas en completadas y pendientes, marcar tareas importantes y registrar la fecha de finalización.

## Instrucciones para configurar y ejecutar el proyecto
* Requisitos previos
* Python 3.x
* Django 3.x
* SQLite3
## Pasos de configuración
- Clonar el repositorio: git clone https://github.com/santi-developer/aplicaci-n-TaskForge.git
- Instalar las dependencias: pip install -r requirements.txt
- Realizar migraciones de la base de datos: python manage.py migrate
- Crear un superusuario: python manage.py createsuperuser
- Iniciar el servidor local: python manage.py runserver
## Estructura del proyecto y decisiones de diseño
## Estructura de directorios
- /crud
  - crud
    - __init__.py
    - asgi.py
    - settings.py
    - urls.py
    - wsgi.py
  - /task
    - /templates
       - base.html
       - create-task.html
       - home.html
       - signin.html
       - signup.html
       - task_detail.html
       - task.html
    - /static
       - style.CSS
    - _init_.py
    - admin.py
    - apps.py
    - forms.py
    - models.py
    - tests.py
    - views.py
  - sqlite3
  - manage.py
        
            
# Decisiones de diseño
Se implementó una estructura MVC de Django para separar las vistas, modelos y plantillas.
Utilización de SQLite3 como base de datos por defecto de Django debido a su simplicidad y portabilidad.
## Cómo usar el proyecto
- Uso básico
   * Iniciar sesión con las credenciales del superusuario para administrar los modelos de la aplicacion.
   * Registrarse en la aplicacion como usuario normal.
   * despues de tener la cuenta valida se podra iniciar sesion.
   * Crear nuevas tareas.
   * Marcar tareas como completadas o pendientes.
   * Marcar las tareas como importantes o no si no tienen tanta importancia.
   * Actualizar detalles de las tareas.
   * Eliminar tareas.
     
Configuración adicional
Para personalizar el estilo de las tareas importantes, modificar los estilos CSS en /task/static/estilos.css.

## Información adicional sobre la aplicación TaskForge

### Vistas y modelos

#### Organización de las Vistas:
En nuestra aplicación Task, las vistas están organizadas siguiendo el patrón de diseño MVC (Modelo-Vista-Controlador). Las rutas y controladores se definen en el archivo `urls.py` y se dividen en aplicaciones específicas. Por ejemplo:
- `tasks/urls.py`: Contiene las URL y vistas relacionadas con las tareas.

#### Interacción entre las Vistas y los Modelos:
Las vistas interactúan con los modelos a través de consultas a la base de datos utilizando el ORM de Django. Por ejemplo, en la vista de detalle de una tarea (`task_detail`), se accede a los datos del modelo `Task` para mostrar la información detallada de una tarea específica.

### Estructura de la Base de Datos

#### Modelos y Relaciones:
Nuestra base de datos utiliza el ORM de Django y tiene la siguiente estructura para las tareas:
- Modelo `Task`: Contiene campos como `title`, `description`, `date_created`, `date_completed`, y `user` (relacionado con el modelo `User`).

#### Relaciones entre Modelos:
- La relación entre `Task` y `User`: Cada tarea está asociada a un usuario específico a través de la relación ForeignKey con el modelo `User`.



