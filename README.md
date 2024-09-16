1. ¿Qué comando utilizaste en el paso 11? ¿Por qué?
Comando: git reset --hard HEAD^
Explicación: Este comando deshace el último commit moviendo el HEAD al commit anterior y elimina cualquier cambio que se haya realizado en el área de trabajo (working copy). El parámetro --hard asegura que los cambios en el área de trabajo también se pierdan, restaurando el estado del repositorio al commit anterior.
2. ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
Comando: git reset --hard ORIG_HEAD
Explicación: Después de deshacer el commit, Git guarda una referencia llamada ORIG_HEAD, que apunta al commit antes del último reset. Este comando permite "rehacer" el commit deshecho previamente, restaurando el estado del repositorio al commit original.
3. El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
Respuesta: No debería causar conflictos, ya que estás realizando un merge de la rama styled con main. En este punto, styled debería contener cambios en estilo que no entren en conflicto con el contenido de main, ya que el trabajo en styled fue aislado.
4. El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
Respuesta: Es posible que cause conflictos, porque en la rama htmlify se hicieron cambios al formato del archivo (como añadir etiquetas HTML), mientras que styled tenía modificaciones en estilo con Markdown. Si ambas ramas modificaron las mismas líneas del archivo git-nuestro.md, habrá conflictos.
5. El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
Respuesta: No debería causar conflictos, ya que después del merge de htmlify en styled, styled ya contiene todos los cambios y ahora se está fusionando con main. Si no se han hecho más cambios en main desde el paso 13, no habría conflictos.
6. ¿Qué comando o comandos utilizaste en el paso 25?
Comando: Para dibujar el diagrama de ramas y commits, podrías usar uno de estos comandos:
git log --graph --oneline --all
git log --graph --decorate --all
Explicación: Estos comandos muestran un diagrama gráfico de las ramas y los commits, lo que ayuda a visualizar el historial y cómo se han realizado los merges entre ramas.
7. El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?
Respuesta: No, no podría ser un merge fast forward, ya que en el paso 26 se solicita explícitamente hacer un merge "no fast-forward". Un merge fast forward ocurre cuando no hay commits divergentes entre la rama que estás fusionando y la rama principal, lo que permite avanzar directamente la referencia del HEAD. Sin embargo, en este caso se debe crear un nuevo commit de merge que combine los historiales de ambas ramas.
8. ¿Qué comando o comandos utilizaste en el paso 27?
Comando: git reset --hard HEAD^
Explicación: Este comando deshace el último commit de merge sin perder los cambios en el área de trabajo, moviendo el HEAD al commit anterior y eliminando el commit de merge, pero manteniendo los cambios aplicados.
9. ¿Qué comando o comandos utilizaste en el paso 28?
Comando: git checkout -- <file>
Explicación: Este comando descarta los cambios en el área de trabajo (working copy), restaurando el archivo al estado que tenía en el último commit.
10. ¿Qué comando o comandos utilizaste en el paso 29?
Comando: git branch -d title
Explicación: Este comando elimina la rama title. El parámetro -d asegura que la rama solo se elimine si sus cambios ya han sido fusionados con otra rama.
11. ¿Qué comando o comandos utilizaste en el paso 30?
Comando: git merge title
Explicación: Este comando rehace el merge que se había deshecho anteriormente. Ahora que el merge ha sido deshecho y los cambios en el área de trabajo han sido descartados, este merge integra nuevamente los cambios de title en main.
12. ¿Qué comando o comandos usaste en el paso 32?
Comando: git checkout <commit_hash>
Explicación: Este comando mueve el HEAD al commit inicial donde se creó el poema, utilizando el hash correspondiente al commit de creación del archivo git-nuestro.md.
13. ¿Qué comando o comandos usaste en el punto 33?
Comando: git checkout <commit_hash>
Explicación: Similar al paso anterior, este comando permite volver al commit donde se añadió el título al poema, utilizando el hash correspondiente a ese commit final.

