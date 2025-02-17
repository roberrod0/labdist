# Despliegue de Aplicaciones Web - Práctica entregable 2 - Roberto Rodríguez González

# 1. Trabajo en local (resolución mediante comandos)

Antes de comenzar el trabajo, escribimos el comando siguiente para que el historial de ramas se mantenga como un árbol:

```bash
git config --global merge.ff false
```

![01.png](01.png)

## 1.1. Inicializa un nuevo repositorio Git en una carpeta llamada `"labdist"` y agrega los archivos proporcionados en el aula virtual. Renombra la rama master a `main` , si es necesario. Realiza el primer commit. Muestra el log del repositorio.

```bash
git init
git branch -m master main
git status
git add .
git commit -m "Repositorio creado, archivos agregados"
git log --oneline
```

![02.png](02.png)

## 1.2. Incluye un fichero `.gitignore` para que los ficheros [`README.md`](http://readme.md/) , `LICENCE.txt` y `passwords.txt` sean ignorados por el control de versiones. Realiza el commit y muestra los logs del repositorio en una línea.

```bash
touch .gitignore
echo "README.md" >> .gitignore
echo "LICENCE.txt" >> .gitignore
echo "passwords.txt" >> .gitignore
git add .gitignore
```

![03.png](03.png)

![04.png](04.png)

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

## 1.6. Fusiona la rama `feature-estilos` en la rama `main` . Muestra los logs del repositorio en una línea, gráficamente y con 'decoración'

```bash
git merge feature-estilos
git log --oneline --graph --decorate
```

![115.png](115.png)

# 2. Trabajo en remoto (resolución mediante Sourcetree y GitHub)

## 2.1. Continúa con el repositorio `labdist` . Añade el repositorio a Sourcetree

![Sourcetree 2025-02-14 16.47.55.png](Sourcetree_2025-02-14_16.47.55.png)

![Sourcetree 2025-02-14 16.49.03.png](Sourcetree_2025-02-14_16.49.03.png)

## 2.2 En tu cuenta de GitHub, crea un repositorio remoto y sube al remoto los ficheros de tu repositorio local. Debes subir todas las ramas. Muestra, además, la captura de pantalla donde se vean en GitHub, algo similar a lo mostrado

![New repository - Google Chrome 2025-02-14 16.51.23.png](New_repository_-_Google_Chrome_2025-02-14_16.51.23.png)

![Sourcetree 2025-02-14 17.09.10.png](Sourcetree_2025-02-14_17.09.10.png)

![push todas las ramas.png](push_todas_las_ramas.png)

![subido todo correctamente.png](subido_todo_correctamente.png)

## 2.3. En el repositorio local, crea una rama `feature-index` . Añade el siguiente código dentro de la `<section class="about">` . Añade los cambios y crea un commit con el mensaje "Añadido párrafo equipo en index.html". Sube los cambios al remoto. (Recuerda que debes usar SourceTree en todo este apartado )

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

![crear rama.png](crear_rama.png)

![añade codigo feature index.png](aade_codigo_feature_index.png)

SourceTree nos marca que tenemos cambios pendientes de añadir en index.html:

![voy a añadir los cambios.png](voy_a_aadir_los_cambios.png)

![commit.png](commit.png)

![confirmado commit.png](confirmado_commit.png)

Lo subimos al remoto:

![subida al remoto.png](subida_al_remoto.png)

![ya esta en github.png](ya_esta_en_github.png)

## 2.4. En el repositorio local, fusiona la rama `feature-index` en la rama `main` .

![que si quiero merge.png](que_si_quiero_merge.png)

![está.png](est.png)

## 2.5. Edita el fichero `contacto.html` . Borra unas líneas. Muestra los ficheros con cambios pendientes y las diferencias. Añade los cambios y haz un commit

![lineas borradas.png](lineas_borradas.png)

![los cambios hechos.png](los_cambios_hechos.png)

![commit de fusion y eliminado.png](commit_de_fusion_y_eliminado.png)

## 2.6. Te das das cuenta del error. Deshaz TOTALMENTE el commit anterior. Captura el estado actual del repositorio. (Asegúrate de que el fichero `contacto.html` ha recuperado todas las líneas borradas y no hay cambios pendientes en el repositorio.)

Clic derecho en la rama main y seleccionamos `reset current branch to this commit`:

![reset to commit.png](reset_to_commit.png)

Y dejamos `contacto.html` tal y como estaba:

![contacto recupera las lineas.png](contacto_recupera_las_lineas.png)

![sin cambios pendientes.png](sin_cambios_pendientes.png)

## 2.7. Crea una una rama `feature-mapa` y cámbiate a ella. Incluye este código en el archivo `contacto.html` . Añade los cambios. Realiza un commit

![crea rama feature-mapa.png](crea_rama_feature-mapa.png)

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

![añadir mapa a contacto.png](aadir_mapa_a_contacto.png)

![pendiente de stage.png](pendiente_de_stage.png)

Añadimos los cambios y hacemos commit:

![commit de mapa.png](commit_de_mapa.png)

![listo en sourcetree.png](listo_en_sourcetree.png)

## 2.8. Sube los cambios al remoto - los de todas las ramas. Muestra en el remoto los cambios del archivo `contacto.html` en la rama `feature-mapa`.

![subir cambios.png](subir_cambios.png)

![cambios en contacto en feature mapa.png](cambios_en_contacto_en_feature_mapa.png)

Los cambios:

![los cambios en el remoto.png](los_cambios_en_el_remoto.png)

## 2.9. En GitHub, en la rama `main` , fusiona la rama `feature-mapa` . Baja los cambios del remoto a local. Deja los dos repositorios sincronizados. Muestra una captura de pantalla donde se vea la página principal de tu repositorio remoto

![merge.png](merge.png)

![merge pull request.png](merge_pull_request.png)

![fusionada check.png](fusionada_check.png)

Hacemos pull para tenerlo en local:

![pull desde sourcetree.png](pull_desde_sourcetree.png)

![faltaba el push.png](faltaba_el_push.png)

# 3. Conflictos

## 3.1. Crea una rama  `hotfix-js`. Cámbiate a ella. Añade este código en el fichero `script.js` . Confirma el cambio y haz un commit con el mensaje "corregido problema en `script.js`". (Fíjate en los números de línea de tu editor ...)

![crea rama hotfix.png](crea_rama_hotfix.png)

![cambia script.png](cambia_script.png)

![pendiente añadir cambios.png](pendiente_aadir_cambios.png)

![commit script.png](commit_script.png)

## 3.2. Vuelve a la rama rama `main` . En el fichero `script.js` en las mismas líneas que en la cuestión anterior, añade el código siguiente. Confirma el cambio y haz un commit con el mensaje "corregido problema en script.js rama main".

Nos vamos de nuevo a la línea 26 y editamos el archivo:

![cambia script desde main.png](cambia_script_desde_main.png)

![pendiente cambios.png](pendiente_cambios.png)

![save commit main.png](save_commit_main.png)

## 3.3. Fusiona la rama `hotfix-js` en `main` . Debe producirse un conflicto. Resuélvelo como consideres oportuno. Cuando termines la resolución del conflicto sube los cambios al remoto.

![que si quiero merge.png](que_si_quiero_merge%201.png)

Nos da el anticipado error:

![merge conflict.png](merge_conflict.png)

![situacion actual.png](situacion_actual.png)

![ahi esta el problema.png](ahi_esta_el_problema.png)

Aquí, Visual Studio Code deja incluso más claras las diferencias que se dan en el conflicto.

![pendiente de arreglar.png](pendiente_de_arreglar.png)

![codigo modificado.png](codigo_modificado.png)

Una vez resuelto el conflicto, lo marcamos como tal, hacemos commit y lo subimos todo al remoto.

![marcar como resuelto.png](marcar_como_resuelto.png)

![commit final.png](commit_final.png)

![push final.png](push_final.png)

![listo.png](listo.png)

![final github.png](final_github.png)

# 4. Enlace a videoclip

# 5. Enlace a repositorio en GitHub

https://github.com/roberrod0/labdist