me muevo con **cd nombreDeFile** que quiero || cd (ppal)  || cd..  (arriba)

**pwd**v   :    donde estoy

crear **mkdir** ....

eliminar **rmdir** ...

**ls** me muestro los archivos en ese file --  **git ls-tree**

para inicializar el file  **git init**  (me crea archivos ocultos para el git) (master)

...............>>> **add**             ........................>>> **commit** (-m "mens" -a)

dir trabajo                                   staging area                                       repositorio

........ <<<   **git rm --cached (file)**     (0 commit)
unstaged:<<<   **restore --staged (file)**  (hay commit)   **(1)** 

contrasenas:  **git rm --cached (file)**      (no hice push)   **git commit --amend --no-edit** 
                                              (ya hice push)   **git commit -m "..."** (pero quedan los rastros del desastre)

.                     **git rm (file) + git commit** (borra el archivo de todos lados, hace otro, no borra el error)

    
     
Va al anterior commit:      **restore  (file)**                      
        (si es nuevo vuelve)                                son lo mismo
        (si ya estaba en repo, saca las modif)              (con todo esto lo elimina del rep)



si borro algo de working,                      si quiero traer a staging

lo quiero recuperar y                          **git reset --hard  (NOOO)**

que estaba en el commit:                      (**cuando** esta modif en verde)

**git restore <file>**            **(2)**       mejor (1-unstage)>(2-version anteior)
**git checkout <file> (viejo!)**

(cuando esta modif en rojo)



**status** para ver que hay en area 1(rojo) y 2(verde) en staged


para comparar:  **git diff <cod commit> <cod commit>** (lines de cambio)  ||  **git diff --name-only <> <>** (archiv name)  || **git diff --word-dif <> <>** (palabras)


modificar commit:    **git commit --amend** (corrijo commit y mensaje)     **--no-edit**   (corrijo commit)

si quiero cambiar nombre de un archivo recién comiteado: **git mv <mal> <bien>** + **git commit --amend**


ir hacia atrás (sin borrar commits):  **git reset --soft <>||head\~<#>**   mueve todo a staging si luego **commmit** desaparecen los commits intermedios

&#x20;                                 **git reset --mixed <>**            mueve al working

borra todo:                              **git reset --hard <>  (OJO!!!!)**



ver los commits **git log --oneline (--all)<-** con all me muestra otras ramas antes haya desfasaje



ramas: **git branch <>**  (Crear)  ||   **git switch <> (checkout <>** viejo\*\*)\*\*  (ir a la lrama)

para crear y mover todo de una: **git switch -c <name>**

borrar rama: **git branch -d <>**  (NO estar en ka rama!)

cambio nombre: **git branch -m <> <>** (si estoy en otra) ||  **git branch -m <>** (en la misma)



para unir las ramas me pongo en la que quiero dejar y traigo la otra : **git merge <>**

si me confunfi vuelvo atras con :  **git reset --hard ORIG_HEAD** (si no hice el push)



para ignorar en un commit agrego:  **.ignore**  en la carpeta con los nombres a ignorar:

#vamos a ignorar .....
*.txt                   (ignoro todos txt)
!readme.txt             (menos este)
<nombre carpeta>/       (toda la carpeta chau)
#Copy.txt**             (todo lo que termine en copia)

Lo puedo poner global en otra carpeta y hacer un:    **git config --global core.excludesfile <direccion>**

.                                                    **"C:\\Users\\josue\\OneDrive\\Desktop\\.gitignore"**


**ALIAS:   git config --global alias.<name Alias> "(sin git)......":**

**log1 -> log --oneline**

**lst <> -> ls-tree -r --name-only <>**



si hice un **reset --hard (HEAD\~n)**   puedo volver con **reset --hard <commit>**

para poder ver los commits uso **: reflog,**  de ahi saco la referencia



también puedo hacer **--checkout <n>**   queda detached Head (rama sin nombre) +  **--switch -c <nombre>**       y ahora tengo las 2 ramas solo creadas     
puedo hacer todo junto: **git  --switch <nuevo nimbre rama>  <commit>        

tengo que clonar el repo en mi compu: git clone http:....... (sacada de la pag de GitHub)

hago cambio en la compu  --> git push -u  <servidor remoto>  <rama en mi compu>   sube toda la rama
traigo los cambios del remoto con  -->  git pull  = fetch + merge (mas control con esto)
touch  crea archivos    code .  abre archivos