# PLANEA: Herramienta colaborativa para la gestión curricular
by Jorge Iván Marín <jorgemarin@uniquindio.edu.co>, Universidad del Quindío, Colombia
v1.0, 2020-06-12

## ¿Qué es PLANEA?

**PLANEA** es una herramienta web que sirve para administrar la planificación curricular de un programa 
académico, permitiendo el trabajo colaborativo, y brindando herramientas analíticas para su 
supervisión y control. 

**PLANEA** ha sido concebido como una herramienta que involucra todas las etapas de una planificación 
curricular, iniciando desde la configuración del plan de estudios, la construcción colaborativa
de contenidos curriculares o *sílabos*, la revisión de coherencia y consistencia de la estructura 
curricular, la aprobación de los contenidos curriculares, el acceso público de la información, 
la evaluación semestral de dichos contenidos, y el control de versiones de los *sílabos*.  

En **PLANEA**, en lugar de usar documentos elaborados en *herramientas ofimáticas*, como en el enfoque tradicional, 
se emplean módulos de captura de información que permiten analizar la consistencia de la información 
y generar automáticamente documentos y reportes. 

Aunque el diseño inicial de **PLANEA** se elaboró con base en la estructura de un plan de estudios bajo el enfoque 
curricular _CDIO_ (*C*oncebir-*D*iseñar-*I*mplementar-*O*perar), se puede adaptar a 
cualquier norma institucional o enfoque curricular. **PLANEA** no solo almacena los _sílabos_ de
todos los espacios académicos de un programa sino también: genera automáticamente los sílabos, 
tablas, figuras y estadísticas que sirven de apoyo al proceso de diseño curricular bajo la 
perspectiva de *currículo integrado* soportado en el *Syllabus CDIO*; apoya al docente para la
planificación semestral; gestiona la trazabilidad de las diferentes modificaciones de carácter 
micro-curricular; documenta la evaluación del aprendizaje bajo el Estándar CDIO 11 
(Evaluación del Aprendizaje); y apoya la auto-evaluación a nivel curricular del plan de 
estudios, con el fin de sistematizar el Estándar CDIO 12 (Auto-evaluación) y todos aquellos 
procesos de auto-evaluación. 


## Características generales

**PLANEA** se han estructurado para contar con los siguientes roles jerárquicos y sus funciones dentro de la plataforma:

**Administrador**

- Gestión de usuarios
- Parametrización según normativa institucional (plantillas, categorías de RAPs)
- Creación de plan de estudios


**Coordinador**

- Configuración de la estructura curricular
- RAPs y rúbricas generales para plan de estudios
- Asignación de colaboradores
- Revisión de la estructura curricular
- Gestión de versiones de los sílabos
- Gestión de la evaluación curricular


**Docente** colaborador

- Modificación de sílabos autorizados por el coordinador 

**Docente** titular

- Planeación del curso
- Evaluación del curso
- Evaluación de área

**Usuario público**
- Acceso a última versión vigente de los sílabos

## Requerimientos técnicos 

A nivel técnico, **PLANEA** puede ser instalado en cualquier servidor web que soporte 
*_PHP versión 5.5_* y *_MySQL_*, pues su código fuente ha sido escrito en su gran mayoría en 
PHP y JavaScript. 

**PLANEA** emplea algunos componentes OpenSource de terceros, algunos de estos están incluidos 
con el código fuente de **PLANEA** para facilitar su instalación, otros se acceden en línea, 
no siendo necesaria la instalación adicional de estos componentes.

## Instalación

Para la instalación de **PLANEA** debe contar con un servidor web que soporte PHP 5.5 o superior 
y MySQL.

- Descargue **PLANEA** del repositorio GitHUB y descomprima los archivos. Esto genera la siguiente
estructura de archivos: '
  >	/doc
  
  >	/web-server
  
  >	/sql-server

- Copie todos los archivos de la carpeta `/web-server`, con el código fuente de **PLANEA**, en su
  servidor Web. 
  Por ejemplo, supongamos que los archivos copiados se acceden a través de la URL `myserver.org/planea`.

- En el servidor MySQL cree la base de datos que empleará **PLANEA**, por ejemplo, `planea-db`.

- Antes de importar las tablas SQL a la base de datos, se recomienda que modifique el archivo 
  `/sql-server/template.sql` con el fin de personalizar el usuario administrador en la tabla 
  `users` y hacer ajustes a las tablas pre-inicializadas `cdiosyllabus_xxx_skills` y 
  `verb_list`. Si estas tablas no se modifican, se emplearán los valores por defecto.
  
- Importe el archivo `/sql-server/template.sql` en su servidor MySQL, para crear toda la 
  estructura de tablas requeridas por **PLANEA**.
  
- Desde el panel de administración de archivos de su servidos Web, modifique el archivo `planea_connection.php`.
  Los valores de las variables `$username`, `$password`, `$dbname` y `$servername` deben 
  coincidir con los valores configurados al crear la base de datos en el paso 3. En muchos
  servidores Web, el campo `$servername` se puede dejar con el valor `localhost`.
  
- Opcionalmente puede modificar los archivos `planea_logosbar` y `planea.css` para modificar 
  la barra de logos y colores de la plataforma.


**PLANEA** ya ha quedado instalado en su servidor y puede ser accedido a través del enlace
`myserver.org/planea` en su navegador Web.  Use como nombre de usuario `root@planea` y contraseña `0`.

