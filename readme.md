#Preguntas práctica 1:

	-  ¿Qué comando utilizaste en el paso 11? ¿Por qué?  
	El git reset —hard HEAD~1, porque este comando me permite retroceder al commit padre del commit en el que estaba, además de restaurar el working copy a la versión en la que se encuentra el padre.
	-  ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?  
	Primero he ejecutado un git log para ver los commits disponibles en la rama styles y he visto que ya no tenía disponible la versión alternativa de git-nuestro.md. Para poder localizar el identificador del commit desde el cual he retrocedido he lanzado un git reflog y he copiado el identificador del commit desaparecido para seguido lanzar un git reset con el SHA y moverme de nuevo a él. 
	-  El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?  
	No ha dado ninguno. Ya que la rama style tiene dentro de sí misma el commit de la master, es decir, contiene la evolución de los commit de master y por lo tanto la modificación sobre el archivo git-nuestro.md en style es un cambio a posterior con respecto en el tiempo del commit que había en master.
	-  El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?  
	Sí. En este caso tanto la rama styled como la htmlify contenían el mismo commit del archivo git-nuestro.md en el mismo punto en el tiempo, por lo que al intentar que styled absorbiese a htmlify git no ha sabido cual de las dos versiones mantener. Lo he solucionado editando el archivo y borrando todo menos la parte de styled para después hacer un git add seguido de un git commit.
	-  El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?  
	En este merge vuelve a saltar un conflicto. La rama styled tiene más commits que la master, por lo que al intentar que master absorba a styled y no tener esta los commits de styled git se ha encontrado que al incorporar el archivo git-nuestro.md con cambios de styled no cuadraba con los que ya existían en la versión master. En este caso he vuelto a editar el archivo para mantener los cambios de master y hacer un git add seguido de un git commit.
	-  ¿Qué comando o comandos utilizaste en el paso 25?  
	He dibujado un diagrama con el comando git log --all --decorate --oneline --graph.
	-  El merge del paso 26, ¿Podría ser fast forward? ¿Por qué?  
	No, porque las ramas no forman una lista. En este caso, master no contiene  todos los commits de title, por lo que el merge debe ser no fast-forward para que se genere un nuevo commit que contenga los commits  tanto de master como de title.
	-  ¿Qué comando o comandos utilizaste en el paso 27?  
	He retrocedido al commit anterior al merge con un git reset 77fd997 para deshacer el merge pero manteniendo los cambios en el working copy.
	-  ¿Qué comando o comandos utilizaste en el paso 28?  
	Para descartar los cambios que tenía aun del merge he hecho un git restore git-nuestro.md
	-  ¿Qué comando o comandos utilizaste en el paso 29?  
	git branch -D title
	-  ¿Qué comando o comandos utilizaste en el paso 30? 
	Primero un git reflog para localizar el indicador del commit en el que estaba cuando se realizó el merge con title y luego un git reset 107be3e seguido de un git Restore git-nuestro.md para restaurar los datos del merge en el working copy.
	-  ¿Qué comando o comandos usaste en el paso 32?  
	Primero un git reflog para localizar el indicador del commit en el que estaba cuando se creó git-nuestro.md y seguido ejecutar un git reset —hard 44f5340 para quedarme igual que como empecé en el primer commit del ejercicio.
	-  ¿Qué comando o comandos usaste en el punto 33?  
	Primero un git reflog para localizar el indicador del commit en el que estaba cuando se realizó la subida del rezo con título y luego un git reset —hard 91c4faf para moverme a él y mantener el working copy con los datos del mismo.

