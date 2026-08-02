## Git

### Comandos basicos

1. Crear una carpeta con el mismo nombre del repositorio
```mkdir dev-handbook```
2. Ingresas a la carpeta creada 
```cd dev-handbook```
3. Inicializas Git
```git init``` (Este comando crea una carpeta oculta , que convierte la carpeta en un repositorio Git)
4. Una vez ya creado el repositorio en GitHub , se debe de vincular al repositorio local
```git remote add origin https://github.com/axlgutierrezl26/dev-handbook.git```
5. Se puede realizar una verificacion
```git remote -v```
Se debe de visualizar algo asi:<br>
Ejemplo:<br>
origin  https://github.com/usuario/ordercraft-docs.git (fetch)<br>
origin  https://github.com/usuario/ordercraft-docs.git (push)<br>
6. Subir el proyecto
```git add .``` (Se encarga de avisar que se agrega un nuevo cambio)
```git commit -m 'init project'``` (Se encarga de agregar un mensaje al cambio)
```git branch -M main``` (Si el repositorio esta limpio es necesario generar una rama principal llamada main)
```git push -u origin main``` (La primera vez se debe de utilizar -u es importante porque configura el upstream)<br>
Posterior del anterior comando, solo sera necesario ejecutar
```git push```








