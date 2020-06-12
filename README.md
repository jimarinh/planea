# PLANEA: Collaborative tool for curriculum management
by Jorge Iván Marín <jorgemarin@uniquindio.edu.co>, Universidad del Quindío, Colombia
v1.0, 2020-06-12

## What is PLANEA?

**PLANEA** is a web-based tool to manage the curricular planning of an academic program, 
providing collaborative work and analytical tools for its supervision and control.

**The current release version is in Spanish. A future release will be on English.**

**PLANEA** has been conceived as a tool that involves all the stages of curricular planning, 
starting from the configuration of the study plan, collaborative construction
of the curricular contents or *syllabus*, review of the coherence and consistency of the curricular structure, 
approval of syllabus, public access to the information, semester's evaluation, and the version control of 
the *syllabus*.

**PLANEA**, instead of using documents elaborated in *office tools*, as in the traditional approach,
uses modules to capture information that may be used to analyze the consistency about the study plan,
and to automatically generate documents and reports.

Although the initial design of **PLANEA** was conceived to support the structure of a curriculum under 
the *CDIO* approach (*C*onceive-*D*esign-*I*mplement-*O*perate), it can be adapted to
any institutional norm or curricular approach. 

**PLANEA** not only stores the *syllabus* of all the academic spaces in a program but also: 

- automatically generates reports, tables, figures and statistics that support the curriculum design process under the
perspective of *integrated curriculum* supported on the *CDIO Syllabus*; 

- supports the teacher planning for a specific course under the *constructive alignment* approach; 

- manages the traceability of the different modifications at curriculum level; 

- stores evidences about the learning assessment under CDIO Standard 11 (Learning Assessment); 

- and supports self-assessment at the curriculum level of the study plan, in order to aid 
  the CDIO 12 Standard (Self-evaluation) and all self-evaluation processes.


## General features

**PLANEA** have been designed to support different processes under hierarchical roles in the platform. 
Here is a brief list of the functions for each role: 


**Administrator**

- User Management
- Parameterization according to institutional regulations (templates, ILO categories)
- Creation of study plans


**Coordinator**

- Configuration of the curricular structure
- ILOs and general rubrics for each study plan
- Assignment of collaborators
- Review of the curricular structure
- Management of syllabus versions 
- Management of the curricular evaluation


**Teacher**-Collaborator

- Modification of syllabus authorized by the coordinator


**Teacher**-Lecturer

- Course planning
- Course Evaluation
- Area evaluation

**Public user**
- Access to the latest version of the syllabus


## Technical requirements

On a technical level, **PLANEA** can be installed on any web server that supports
*_PHP version 5.5_* and *_MySQL_*, since its source code has been written mostly in
PHP and JavaScript.

**PLANEA** uses some third party OpenSource components, some of these are included
within the source code of **PLANEA** to facilitate its installation; others are accessed online,
so that additional installation of these components is not necessary.

## Installation

- Download **PLANEA** from the GitHUB repository and unzip the files. This generates the following
file structure: 
  > / doc
  
  > / web-server
  
  > / sql-server

- Copy all the files from the `/web-server` folder, the source code of **PLANEA**, to your
  Web server.
  For example, suppose that the copied files are accessed through the URL `myserver.org/planes`.

- On the MySQL server create the database that will be used by **PLANEA**, for example, `planea-db`.

- Before importing the SQL tables into the database, it is recommended that you modify the file
  `/sql-server/template.sql` in order to customize the admin user in the table
  `users` and make adjustments to the pre-initialized `cdiosyllabus_xxx_skills` tables and
  `verb_list`. If these tables are not modified, the default values ​​will be used.
  
- Import the `/sql-server/template.sql` file into your MySQL server, to create all the
  table structure required by **PLANEA**.
  
- From the file management panel of your web server, modify the file `planea_connection.php`.
  The values ​​of the variables `$username`,`$password`, `$dbname` and `$servername` must
  match the values ​​configured when creating the database in step 3. In many
  Web servers, the `$servername` field can be left with the `localhost` value.
  
- Optionally you can modify the `planea_logosbar` and `planea.css` files to customize 
  the logos' bar and color theme.
  
 
**PLANEA** is ready to be used and it can be accessed through the `myserver.org/planea` in your
Web browser. Use the username `root@planea` and password `0`.
