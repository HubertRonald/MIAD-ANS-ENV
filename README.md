[![Docker](https://img.shields.io/badge/docker-%230db7ed.svg?style=flat-square&logo=docker&logoColor=white)](https://docs.docker.com/desktop/setup/install/windows-install/)
[![VS Code](https://img.shields.io/badge/Visual%20Studio%20Code-007ACC?logo=visualstudiocode&logoColor=fff&flat-square=plastic)](https://code.visualstudio.com/download)
[![Python](https://img.shields.io/badge/python-3670A0?style=flat-square&logo=python&logoColor=ffdd54)](https://peps.python.org/pep-0596/#schedule-first-bugfix-release)
![GitHub last commit](https://img.shields.io/github/last-commit/HubertRonald/MIAD-ANS-ENV?style=flat-square)
![GitHub commit activity](https://img.shields.io/github/commit-activity/t/HubertRonald/MIAD-ANS-ENV?style=flat-square&color=dodgerblue)

# MIAD-ANS-ENV
Ambiente para trabajar el Modulo 7 del curso: Datos Espaciales del curso Aprendizaje No Supervisado - Uniandes.

# Devcontainer
Para levantar el devontainer en local deberías tener ya instalado VS Code y Docker

1.- Clona el repositorio

```bash
git clone https://github.com/HubertRonald/MIAD-ANS-ENV.git
```

2.- Abre la carpeta MIAD-ANS-ENV en el IDE: VS Code

3.- Pulsa la esquina inferior izquierda del IDE: VS Code `Abrir una ventana remota`

4.- Seleccionar la opción: `Volver a abrir en el contenedor`

5.- Una vez levantada la instancia ejecuta el notebook `app.ipynb` para probar que carga las dependencias

# Kernel: Notebook

Este está en la siguiente ruta cuando lo selecciones en el notebook
```bash
$ which python
/usr/local/bin/python
```

La versionde python a escoger es:

```bash
$ python --version
Python 3.7.17
```

# .gitignore

Fue generado en [gitignore.io](https://www.toptal.com/developers/gitignore/) con los filtros `python`, `macos`, `windows` y consumido mediante su API como archivo crudo desde la terminal:

```bash
curl -L https://www.toptal.com/developers/gitignore/api/python,macos,windows > .gitignore
```

# Autores

* **Hubert Ronald** - *Trabajo Inicial* - [HubertRonald](https://github.com/HubertRonald)

* **site** - [hubertronald.github.io/](https://hubertronald.github.io/)

Ve también la lista de [contribuyentes](https://github.com/HubertRonald/MIAD-ANS-ENV/contributors) que participaron en este proyecto.



# Licencia

Este proyecto está bajo licencia MIT - ver la [LICENCIA](LICENSE) archivo (en inglés) para más detalle.