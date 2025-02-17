# Despliegue de Aplicaciones Web - Práctica entregable 2 - Roberto Rodríguez González

# 1. Trabajo en local (resolución mediante comandos)

Antes de comenzar el trabajo, escribimos el comando siguiente para que el historial de ramas se mantenga como un árbol:

```bash
git config --global merge.ff false
```

![101.png](101.png)

## 1.1. Inicializa un nuevo repositorio Git en una carpeta llamada `"labdist"` y agrega los archivos proporcionados en el aula virtual. Renombra la rama master a `main` , si es necesario. Realiza el primer commit. Muestra el log del repositorio.

```bash
git init
git branch -m master main
git status
git add .
git commit -m "Repositorio creado, archivos agregados"
git log --oneline
```

![102.png](102.png)

## 1.2. Incluye un fichero `.gitignore` para que los ficheros [`README.md`](http://readme.md/) , `LICENCE.txt` y `passwords.txt` sean ignorados por el control de versiones. Realiza el commit y muestra los logs del repositorio en una línea.

```bash
touch .gitignore
echo "README.md" >> .gitignore
echo "LICENCE.txt" >> .gitignore
echo "passwords.txt" >> .gitignore
git add .gitignore
```

![103.png](103.png)

![104.png](104.png)

![105.png](105.png)

## 1.3. En el repositorio, crea los archivos [`README.md`](http://readme.md/) , `LICENCE.txt` y `passwords.txt` con algún contenido. Muestra el estado del repositorio. Muestra el listado de archivos ignorados.

```bash
echo "Lorem ipsum README" >> README.md
echo "Lorem ipsum LICENCE" >> LICENCE.txt
echo "Lorem ipsum passwords" >> passwords.txt
git status
```

![106.png](106.png)

![108.png](108.png)

![109.png](109.png)

![110.png](110.png)

```bash
git status --ignored
```

![107.png](107.png)

## 1.4. Crea una rama `feature-estilos` . Cámbiate a ella.

- Modifica el archivo **`estilos.css`** :
    - propiedad `color` del `body` y de `h2` : `#2a2a2a`
    - propiedad `background-color` de `header` y `footer`: `#2a75ff`
- Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje "actualizados estilos a azules"

```bash
git checkout -b feature-estilos
git status
git add estilos.css
git add .
git commit -m "Actualizados estilos a azules"
```

![112.png](112.png)

El archivo **`estilos.css`** modificado desde Visual Studio Code:

![111.png](111.png)

## 1.5. Vuelve a  a la rama `main` . En el archivo `index.html` añade un comentario donde se indique tu nombre como autor de la página. Comprueba el estado del repositorio. Añade los cambios, realiza un commit con el mensaje ' añadido autor en index'. Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

```bash
git checkout main
git status
git add index.html
git commit -m "Añadido autor en index"
git log --oneline --graph --decorate
```

![114.png](114.png)

El archivo **`index.html`** modificado desde Visual Studio Code: 

![113.png](113.png)

![114.png](114%201.png)

## 1.6. Fusiona la rama `feature-estilos` en la rama `main` . Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

```bash
git merge feature-estilos
git log --oneline --graph --decorate
```

![115.png](115.png)

# 2. Trabajo en remoto (resolución mediante Sourcetree y GitHub)

## 2.1. Continúa con el repositorio `labdist` . Añade el repositorio a Sourcetree

## 2.2 En tu cuenta de GitHub, crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir todas las ramas. Muestra, además, la captura de pantalla donde se vean en GitHub, algo similar a lo mostrado

![201.png](201.png)

![202.png](202.png)

![203.png](203.png)

![204.png](204.png)

![205.png](205.png)

![206.png](206.png)

## 2.3. En el repositorio local, crea una rama `feature-index` . Añade el siguiente código dentro de la `<section class="about">` . Añade los cambios y crea un commit con el mensaje "Añadido párrafo equipo en index.html". Sube los cambios al remoto. (Recuerda que debes usar SourceTree en todo este apartado )

![207.png](207.png)

```html
<h2>Conoce a Nuestro Equipo</h2>
<p>labdist está formado por un equipo de diseñadores y
desarrolladores apasionados que trabajan juntos para ofrecer soluciones
tecnológicas de alta calidad. Cada miembro de nuestro equipo aporta
experiencia en diseño, programación, y soporte técnico, asegurando que
nuestros clientes reciban un servicio completo y personalizado.</p>
<p>Nuestro objetivo es que cada cliente se sienta acompañado en su
aventura digital, con un equipo profesional que entiende sus necesidades y
trabaja para hacer crecer su presencia en línea.</p>
```

![208.png](208.png)

SourceTree nos marca que tenemos cambios pendientes de añadir en index.html:

![209.png](209.png)

![210.png](210.png)

![211.png](211.png)

Lo subimos al remoto:

![212.png](212.png)

![213.png](213.png)

## 2.4. En el repositorio local, fusiona la rama `feature-index` en la rama `main` .

![214.png](214.png)

![215.png](215.png)

## 2.5. Edita el fichero `contacto.html` . Borra unas líneas. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit

![216.png](216.png)

![217.png](217.png)

![218.png](218.png)

## 2.6. Te das das cuenta del error. Deshaz TOTALMENTE el commit anterior. Captura el estado actual del repositorio. (Asegúrate de que el fichero `contacto.html` ha recuperado todas las líneas borradas y no hay cambios pendientes en el repositorio.)

Clic derecho en la rama main y seleccionamos `reset current branch to this commit`:

![219.png](219.png)

Y dejamos `contacto.html` tal y como estaba:

![220.png](220.png)

![221.png](221.png)

## 2.7. Crea una una rama `feature-mapa` y cámbiate a ella. Incluye este código en el archivo `contacto.html` . Añade los cambios. Realiza un commit

![222.png](222.png)

```html
<section class="map">
<h2>Nuestra Ubicación</h2>
<p>C/Luis Moya 335, Gijón, Asturias</p>
<iframe src="[https://www.google.com/maps](https://www.google.com/maps)?
q=C%2FLuis%20Moya%20335%2C%20Gij%C3%B3n%2C%20Asturias&output=embed"
width="600" height="450" style="border:0;" allowfullscreen=""
loading="lazy"></iframe>
</section>
```

![223.png](223.png)

![224.png](224.png)

Añadimos los cambios y hacemos commit:

![225.png](225.png)

![226.png](226.png)

## 2.8. Sube los cambios al remoto - los de todas las ramas. Muestra en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa`.

![227.png](227.png)

![228.png](228.png)

Los cambios:

![229.png](229.png)

## 2.9. En GitHub, en la rama `main` , fusiona la rama `feature-mapa` . Baja los cambios del remoto a local. Deja los dos repositorios sincronizados. Muestra una captura de pantalla donde se vea la página principal de tu repositorio remoto

![230.png](230.png)

![232.png](232.png)

Hacemos pull para tenerlo en local:

![233.png](233.png)

![234.png](234.png)

# 3. Conflictos

## 3.1. Crea una rama  `hotfix-js`. Cámbiate a ella. Añade este código en el fichero `script.js` . Confirma el cambio y haz un commit con el mensaje "corregido problema en `script.js`". (Fíjate en los números de línea de tu editor ...)

![301.png](301.png)

![302.png](302.png)

![303.png](303.png)

![304.png](304.png)

## 3.2. Vuelve a la rama rama `main` . En el fichero `script.js` en las mismas líneas que en la cuestión anterior, añade el código siguiente. Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js rama main".

Nos vamos de nuevo a la línea 26 y editamos el archivo:

![306.png](306.png)

![307.png](307.png)

![305.png](305.png)

## 3.3. Fusiona la rama `hotfix-js` en `main` . Debe producirse un conflicto. Resuélvelo como consideres oportuno. Cuando termines la resolución del conflicto sube los cambios al remoto.

![309.png](309.png)

Nos da el anticipado error:

![310.png](310.png)

![311.png](311.png)

![312.png](312.png)

Aquí, Visual Studio Code deja incluso más claras las diferencias que se dan en el conflicto.

![313.png](313.png)

![314.png](314.png)

Una vez resuelto el conflicto, lo marcamos como tal, hacemos commit y lo subimos todo al remoto.

![315.png](315.png)

![316.png](316.png)

![317.png](317.png)

![318.png](318.png)

![319.png](319.png)

# 4. Enlace a videoclip

# 5. Enlace a repositorio en GitHub

https://github.com/roberrod0/labdist