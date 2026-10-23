# pycharm
Py files for learning pycharm
Learning Git Again

1. Crear una carpeta para tu proyecto
mkdir MiProyecto
cd MiProyecto

2. Inicializar Git en el proyecto
git init

Esto crea el repositorio local.

3. Verificar el estado
git status

Muestra qué archivos están siendo rastreados y cuáles no.

4. Configurar usuario (solo la primera vez)
git config --global user.name "Roberto Herrera"
git config --global user.email "correo@promerica.com"


Verificar configuración:

git config --list

5. Crear archivos

Ejemplo:

echo "# Mi Proyecto" > README.md

o simplemente crea archivos desde Visual Studio, VS Code, etc.

6. Agregar archivos al repositorio local

Agregar un archivo específico:
git add README.md

Agregar todos los archivos:
git add .

7. Crear el primer commit
git commit -m "Primer commit"

8. Crear un repositorio en GitHub

En GitHub:
- Clic en New Repository
- Asigna un nombre
- Crear repositorio
- Copia la URL

Ejemplo:
https://github.com/usuario/MiProyecto.git

9. Vincular el repositorio local con GitHub
git remote add origin https://github.com/usuario/MiProyecto.git


Verificar:

git remote -v

10. Subir el proyecto a GitHub

Primera vez:

git branch -M main
git push -u origin main

1. Flujo diario de trabajo
- Ver cambios
git status

- Agregar cambios
git add .

- Crear commit
git commit -m "Descripción del cambio"

- Subir cambios a GitHub
git push

- Descargar un repositorio existente
git clone https://github.com/usuario/MiProyecto.git


2. Entrar al proyecto:

- cd MiProyecto

- Obtener cambios del repositorio remoto
git pull

- Ver historial
git log

3. Versión resumida:

git log --oneline

4. Flujo completo resumido
- mkdir MiProyecto
- cd MiProyecto

- git init

- git add .
- git commit -m "Primer commit"

- git remote add origin https://github.com/usuario/MiProyecto.git

- git branch -M main
- git push -u origin main


Después de cada cambio:

- git add .
- git commit -m "Descripción del cambio"
- git push


5. Como desarrollador .NET, si trabajas con Visual Studio también te recomiendo crear un archivo .gitignore para excluir carpetas como:

bin/
obj/
.vs/

Así evitarás subir archivos compilados innecesarios al repositorio.


6. Con el error:
git push -u origin main To https://github.com/robertocarloshg/pycharm.git ! [rejected] main -> main (non-fast-forward) error: failed to push some refs to...

Ese error significa que el repositorio de GitHub ya tiene contenido (normalmente un README.md, .gitignore o licencia) y tu repositorio local no tiene esos cambios. Git evita sobrescribir el historial remoto.

Opción recomendada: Traer primero los cambios de GitHub

- Ejecuta:
git pull origin main --allow-unrelated-histories

Si aparecen conflictos, resuélvelos y luego:

git add .
git commit -m "Resolver conflictos"

Después vuelve a subir:

git push -u origin main

- Verifica qué tiene el repositorio remoto
- Puedes revisar:
git remote -v

- Y ver el historial local:

git log --oneline

Si el repositorio de GitHub está vacío o no te importa perder lo que tiene Puedes forzar la subida:

git push -u origin main --force


⚠️ Esto sobrescribirá el contenido actual de GitHub con el contenido de tu máquina local.

Lo más probable en tu caso

Si al crear el repositorio en GitHub marca:
✅ Add a README file
Entonces GitHub creó un primer commit y por eso aparece el error.

En ese caso usa:
git pull origin main --allow-unrelated-histories
git push -u origin main
