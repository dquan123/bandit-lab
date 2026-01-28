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
