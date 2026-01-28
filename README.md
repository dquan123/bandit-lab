## Bandit Level 0
**Objetivo:**  
Encontrar la contraseña del siguiente nivel y hacer las conexiones para empezar a jugar
**Comandos utilizados:**

ls

cat readme
## Explicación:
Se listaron archivos y al encontrar el readme se leyo la contraseña del nivel 1

## Contraseña obtenida:
ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

## Bandit Level 1
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo con nombre poco comun

**Comandos utilizados:**

ls

cat ./-
## Explicación:
Se listaron archivos y al encontrar el archivo con nombre - se uso cat./ para poder leer su contenido

## Contraseña obtenida:
263JGJPfgU6LtdEvgfWU1XP5yac29mFx

## Bandit Level 2
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo con nombre con espacios

**Comandos utilizados:**

ls

cat -- 'Nombre del archivo'
## Explicación:
Se listaron archivos y al encontrar el archivo con nombre '--spaces in this filename--0 se uso cat -- 'Archivo' para poder leer su contenido, ya que las comillas sirven para leer nombres con espacios pero cat detecta - como una opción, así que al poner -- se indica que no viene una opcion en lo siguiente.

## Contraseña obtenida:
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

## Bandit Level 3
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un directorio con un archivo oculto

**Comandos utilizados:**

ls -a

cd 'Directorio'

cat 'Archivo'
## Explicación:
Se listaron archivos y al encontrar el directorio inhire me moví con cd, luego al listar vi que no se encontraba nada con ls, así que usé ls -a para listar los archivos y directorios, incluidos los ocultos, luego seguí el proceso del ejercicio anterior para leerlo con cat 'archivo'

## Contraseña obtenida:
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

## Bandit Level 4
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un directorio con archivos que no se pueden leer facilmente

**Comandos utilizados:**

ls

cd 'Directorio'

cat -- 'Archivo'
## Explicación:
Se listaron archivos y al encontrar el directorio inhire me moví con cd, luego al listar vi que habían varios archivos, usé cat -- 'Archivo' ya que los archivos iniciaban con - y necesitaba indicar que no venia una funcion luego de cat, leí uno por uno hasta encontrar el único con contenido leíble por el ojo humano y no con caracteres raros.

## Contraseña obtenida:
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

## Bandit Level 5
**Objetivo:**
Encontrar la contraseña del siguiente nivel dentro de un montón de archivos y directorios, el correcto cumple: human-readable, 1033 bytes in size, not executable

**Comandos utilizados:**

ls

ls -a

cd Directorio

cat Archivo

find

-type f

-size 1033c

! -executable
## Explicación:
Lo primero fue usar ls para listar el contenido, al ver que habían muchos directorios y archivos dentro, se utilizaron los siguientes comandos para encontrar el archivo que cumpliera con las condiciones establecidas: find . para buscar en el directorio actual, junto con los 3 comandos, -type f para filtrar solo por archivos, -size 1033c para filtrar solo los que tienen 1023 bytes de tamaño y ! -executable para filtrar también por los que no sos ejecutables, al ejecutar el comando me dio la ruta del archivo, así que me moví con cd al directorio correcto y al no encontrar el archivo con ls, usé ls -a para ver los ocultos y por último usé cat 'Archivo' para leer el contenido.

## Contraseña obtenida:
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

## Bandit Level 6
**Objetivo:**
Encontrar la contraseña del siguiente nivel dentro de todo el servidor, en un archivo que cumpla con lo siguiente: owned by user bandit7, owned by group bandit6, 33 bytes in size

**Comandos utilizados:**

ls

ls -a

cat 'ruta del archivo'

find /

-type f

-size 33c

-user bandit7

-group bandit6
## Explicación:
Lo primero fue ls -a para listar todo el contenido, incluidos los ocultos, al ver que no había nada me di cuenta que el archivo estaba en cualquier lugar de todo el servidor, luego usé el comando find / para buscar alrededor de todo el servidor, y le apliqué filtros con los siguientes 4 comandos: -type f para buscar solo archivos, -size nc para el tamaño del arhivo en bytes, -user 'Usuario' para el usuario al que pertenece el archivo y 'group 'Grupo' para el grupo al que pertenece el archivo. Al ejecutarlo me dio la ruta completa y ya que no está en el directorio actual usé cat 'Ruta completa en el servidor del archivo' para leer su contenido.

## Contraseña obtenida:
morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

## Bandit Level 7
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo con miles de datos, la cual se encuentra junto a la palabra milionth

**Comandos utilizados:**

ls

grep 'Palabra' 'Archivo'
## Explicación:
Lo primero fue ls para ver los archivos, en este caso solo era 1, con ls vi el nombre de este, luego usé el comando grep para imprimir la línea de un archivo en donde encuentre una palabra indicada, en este caso: grep 'millionth' 'data.txt' y esto imprimió la línea del archivo en donde encontró milionth, y ahí estaba la contraseña.

## Contraseña obtenida:
dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

## Bandit Level 8
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo con miles de datos con líneas que se repiten, la contraseña es la única que no se repite

**Comandos utilizados:**

ls

sort 'Archivo' 

| 

uniq -u
## Explicación:
Lo primero fue ls para ver los archivos, en este caso solo era 1, con ls vi el nombre de este, luego usé el comando sort data.txt porque me di cuenta que uniq solo funciona de manera correcta si el archivo se encuentra ordenado, en la misma línea puse el caracter | para indicar la salida y finalmente uniq -u para mostrar las líneas que aparecen una sola vez en el archivo.

## Contraseña obtenida:
4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

## Bandit Level 9
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo con varios datos que no son legibles, la contraseña es legible obviamente y está precedida por varios caracteres '='

**Comandos utilizados:**

ls

strings 'Archivo'

|

grep 'Cadena'
## Explicación:
Lo primero fue ls para ver los archivos, en este caso solo era 1, con ls vi el nombre de este, luego usé el comando strings 'data.txt' para extraer el texto legible del archivo, luego | para unir dos comandos, y luego grep '==' para filtrar por lo que precedía el patrón, que en este caso, eran al menos 2 signos de igual '=='. 


## Contraseña obtenida:
FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

## Bandit Level 10
**Objetivo:**
Encontrar la contraseña del siguiente nivel en un archivo que se encuentra codificado en base 64

**Comandos utilizados:**

ls

base64 -d 'Archivo'
## Explicación:
Lo primero fue ls para ver los archivos, en este caso solo era 1, con ls vi el nombre de este, después usé el comando base64 -d 'data.txt', ya que base64 trabaja con base 64 y -d decodifica un archivo, esto me arrojó el texto decodificado con la contraseña.


## Contraseña obtenida:
dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
