# RisenPC-Fluxbox-ES

MX Linux 23 tiene una versión Fluxbox pero no me gusta como queda, entonces esta es mi versión en español para Ordenadores con pocos recursos

# Requerimientos
Se requiere lo sigiente:

- MX Linux 23 (XFCE) [https://sourceforge.net/projects/mx-linux/files/Old/](https://sourceforge.net/projects/mx-linux/files/Old/)

# Instalación de Fluxbox y dependencias
Con lo siguiente instalaremos las dependencias necesarias:

**Dependencias**

```bash
sudo apt-get install fluxbox lxappearance lxrandr pnmixer numlockx qt5ct \
nitrogen gnome-icon-theme gxkb xfce4-appfinder network-manager-gnome \
pavucontrol
```


# Borre los estilos del paquete de Fluxbox  (Opcional)

El comando anterior instalará fluxbox pero ese trae unos temas muy feos, yo nunca los uso, yo los borro, le recomiendo hacer lo mismo, ponga en la terminal:

```bash
sudo rm -fr /usr/share/fluxbox/styles/
```

No se preocupe aquí usaremos unos

# Borrar los archivos originales de Fluxbox si Ud los usaba

Si usted estaba usando Fluxbox debe haber una carpeta escondida (Si no es este su caso omita este paso) , veala con Ctrl + H

.fluxbox

si esta carpeta usted ya la tenía creada hay que borrarla, puede hacerlo manualmente, o así:

```
sudo rm -fr ~/.fluxbox
```

# Instalar RisenPC Fluxbox Español

Estando en su HOME, kcopie todo de una sola vez  (también si no le funciona en su terminal copie uno por uno):

```bash
    git clone https://github.com/wachin/Risen-PC_Fluxbox_MX_Linux-23-XFCE
    mv Risen-PC_Fluxbox_MX_Linux-23-XFCE ~/.fluxbox
    cd .fluxbox
    mkdir -p ~/.config/pnmixer/
    cp config ~/.config/pnmixer/ && cd && echo "Dios les bendiga"
```
    
**Explicación**  
1er línea.- Clona el repositorio  
2da línea.- Mueve el repositorio entero allí mismo en su HOME cambiandole el nombre a .fluxbox  
3ra línea.- Entra en la carpeta oculta .fluxbox  
4ra línea.-  Crea la carpeta pnmixer (si ya estuviera no)  
5ta línea.- Copia y pega el archivo config de pnmixer que puse dentro de la carpeta .fluxbox que contiene la instrucción "pavucontrol" para que al darle clic y dar clic en elbotón "Mixer" aparezca el control de volumen. **Nota:** También se lo podría Ud poner manualmente así: Clic derecho al icono --> Preferences --> Behavior --> Volume Control Command y allí añadir: "pavucontrol"  

Por cierto, en la terminal quedarán ubicados en .fluxbox pero pueden salir de allí con cd.

# Instalar Menú de aplicaciones con iconos, con xdgmenumaker
El siguiente programa necesario se llama xdgmenumaker, que me gustaría que lo pongan dentro de alguna carpeta aparte, yo estoy usando:

🗀AppsLinux

usted puede crearla manualmente:

![](vx_images/300784791826807.png)

o también lo podría hacerlo desde una terminal con los siguientes comandos:

```
mkdir -p ~/AppsLinux
cd ~/AppsLinux
```

de cualquier manera si lo haga manual o desde la terminal, luego instale los paquetes:

```
sudo apt-get install txt2tags python3-xdg gobject-introspection
```
y luego clone el programa xdgmenumaker y entre en su directorio:

```
git clone https://github.com/gapan/xdgmenumaker && cd xdgmenumaker
```
después haga make:

```
make
```

y hagase super usuario (ponga su contraseña):

```
sudo su 
```
en la siguiente imagen verá usted hasta donde debe usted estar ubicado:

![](vx_images/547226287889771.png)

y luego poner lo siguiente:

```
make install && cd .. && exit
```

aquí un captura:

![](vx_images/547226287889772.png)

Con esto tendrá iconos de la mayoría de las aplicaciones en el menú de fluxbox

**Nota**: Si lo sedea puede borrar la carpeta xdgmenumaker con:

```bash
sudo rm -fr xdgmenumaker
```

## Creando el Menu de fluxbox, con xdgmenumaker

Ponga en una terminal:

```bash
xdgmenumaker -i -s16 -f fluxbox > ~/.fluxbox/xdg_menu
```

esto es necesario hacerlo sólo una vez

En ese archivo xdg_menu se escribirán todas las aplicaciones que están instaladas en su sistema para que estén disponibles para el menú de Fluxbox 

Para ver el menú de clic derecho en el escritorio o clic derecho en una de las dos esquinas o Super + M quedará así:

![](https://raw.githubusercontent.com/wachin/RisenPC-Fluxbox-ES/main/RisenPC-Fluxbox.png)


## Cierre sesión y vuelva a entrar

Cierre sesión y vuelva a entrar y verá disponible a fluxbox

![](vx_images/547226287889799.png)

la anterior y la siguiente imagen son de MX Linux 19:

![](vx_images/547226287889800.png)


## Actualizar el menú de Fluxbox cada vez que instale alguna aplicación

Esto debe saberlo pues en esta instalación se utiliza a xdgmenumaker pero hay que actualizar el menu después que uno instala alguna aplicación, para hacerlo clic en:

**Actualizar menu de Apps**  

![](vx_images/474065919268985.png)

Pero si no desea utilizar este menú sólo use el XFCE4-AppFinder


# Control de volumen
Clic en el control de volumen:  

![](vx_images/408873991826523.png)

y clic en "Mixer"  

![](vx_images/444275200615615.png)

y se abrirá el control de volumen:  

![](vx_images/156116023941366.png)



# Temas de iconos para aplicaciones KDE (Qt)

Se configura en:

**Menú --> Herramientas del Sistema --> Ajustes QT5 "Aplicaciones KDE"**

![](vx_images/478325900615604.png)

Esto si por un caso desee hacerlo, aunque no lo veo necesario

Si desea cambiar el color de alguna carpeta de dolpin lea:

**Cambiar colores en carpetas de Dolphin (Administrador de archivos) en MX Linux 21, antiX 21 basados en Debian 11 Bullseye, y Ubuntu 22.04 y otros con "Dolphin Folder Color"**  
[https://facilitarelsoftwarelibre.blogspot.com/2022/05/cambiar-colores-en-carpetas-de-dolphin-con-dolphin-folder-color-en-debian-11-ubuntu-22.04.html](https://facilitarelsoftwarelibre.blogspot.com/2022/05/cambiar-colores-en-carpetas-de-dolphin-con-dolphin-folder-color-en-debian-11-ubuntu-22.04.html)  

## El tamaño de las fuentes de las aplicaciones QT

Allí mismo en el configurador QT de clic en la pestaña:

**Tipos de letra**  

![](vx_images/547226287889779.png)

allí arriba como se ve en la imagen cambiar el tamaño de las fuentes:  

![](vx_images/547226287889780.png)

después dar clic en Aplicar luego en Aceptar y cerrar la aplicación escrita en QT ejemplo Kate, Dolphin u otra y vuelvala a abrir y ya tendrán las fuentes otro tamaño, o si cambió la fuente estará usando otra, allí como ve yo le he puesto:

**DejaVu Sans** - **Book** - **11**

pero usted puede elegir otro tipo, estilo, tamaño

como puede ser:  

![](vx_images/547226287889781.png)

y lo dejo así:  

![](vx_images/547226287889782.png)

y allí le di clic en Aceptar y Aplicar y reinicié la aplicación Qt que necesitaba.

# Corrección de foco para diálogos Qt/KDE

Fecha: 2026-07-14

En el archivo `~/.fluxbox/apps` añadí una regla `[transient]` para que algunos diálogos de aplicaciones Qt/KDE puedan tomar el foco correctamente:

```text
[transient] (Class=^(kate|kdenlive|dolphin|dmidiplayer|ksnip)$)
  [FocusProtection] {Gain,Lock}
[end]
```

Explicación:

- `[transient]` se aplica a ventanas de diálogo o ventanas modales que usan `WM_TRANSIENT_FOR`.
- `Gain` permite que el nuevo diálogo tome el foco cuando se abre.
- `Lock` evita que otra ventana robe el foco inmediatamente mientras el diálogo modal está activo.

Esta solución es más específica y menos invasiva que cambiar el modelo global de foco para todas las ventanas.

# Atajos de teclado, manual para crear atajos de teclado en Fluxbox

Para crear atajos de teclado personalizados en Fluxbox en Linux, debes modificar el archivo `~/.fluxbox/keys`, que es el archivo de configuración de los atajos de teclado en Fluxbox

## 1. **Ubicación del archivo de configuración de atajos de teclado**
   El archivo de configuración para los atajos de teclado en Fluxbox se encuentra en `~/.fluxbox/keys`. Este archivo se edita con cualquier editor de texto de tu preferencia (por ejemplo, `nano`, `vim`, `gedit`, etc.).

   Para editar el archivo, abre una terminal y ejecuta el siguiente comando:

```bash
nano ~/.fluxbox/keys
```

## 2. **Estructura de los atajos de teclado**
   En el archivo `keys`, cada línea se refiere a un atajo de teclado. Un atajo de teclado tiene tres componentes principales:

   - **Teclas modificadoras**: Las teclas que se usan junto con la tecla de acción, por ejemplo:
  
Ctrl = `Control`
Alt = `Mod1`
Tecla Windows (Super) = `Mod4`

   - **Tecla de acción**: La tecla que se presiona junto con las teclas modificadoras,, son letras como `a`, `k`, `m`, etc.
   - **Comando a ejecutar**: El comando que se ejecutará cuando el atajo de teclado se active. Esto puede ser abrir una aplicación, ejecutar un script, mostrar un menú, etc.

## 3. **Sintaxis para crear un atajo**

La sintaxis básica para un atajo de teclado es:

```
<modificadores> <tecla> :Exec <comando>
```

- `<modificadores>` puede ser una combinación de teclas como `Control`, `Mod1`, `Mod4`, etc.
- `<tecla>` es la tecla que se presiona junto con los modificadores.
- `<comando>` es el comando que deseas ejecutar cuando el atajo sea activado.

   A continuación, algunos ejemplos de atajos de teclado comunes:

   - **Abrir el navegador web**: Para abrir Firefox, el atajo sería:

```
Control Mod1 f :Exec firefox
```

   - **Abrir una terminal**: Para abrir la terminal con el atajo `Ctrl + Alt + T`:

```
Control Mod1 t :Exec xterm
```

   - **Cerrar una ventana**: Para cerrar la ventana activa con el atajo `Ctrl + Alt + C`:

```
Control Mod1 c :Close
```

   - **Alternar entre ventanas**: Para alternar entre las ventanas abiertas, el atajo sería:

     ```
     Mod1 Tab :NextWindow
     ```

   - **Abrir el administrador de archivos**: Para abrir Nautilus (el explorador de archivos) con el atajo `Ctrl + Alt + E`:

```
Control Mod1 e :Exec nautilus
```
** Nota:** Se puede cambiar por: dolphin, nemo, thunar, etc

#### 4. **Reiniciar Fluxbox**
   Después de agregar o modificar los atajos de teclado, es necesario recargar la configuración de Fluxbox para que los cambios surtan efecto. Para hacerlo, puedes ejecutar el siguiente comando:

```bash
fluxbox-remote restart
```

#### 5. **Ejemplo de un archivo de atajos de teclado completo**

Los siguientes atajos en `~/.fluxbox/keys` son unos atajos que estoy utilizando::

```
# Abrir AppFinder con atajo de teclado
# Esto significa que la Tecla Ctrl (Control) y Alt (Mod1) y la tecla A activarán a xfce4-appfinder
# Ctrl + Alt + A lanza xfce4-appfinder
Control Mod1 a :Exec xfce4-appfinder

# Abrir ksnip para capturar un rectángulo con el cursor
# Esto significa que la Tecla Ctrl (Control) y Alt (Mod1) y la tecla K ejecutarán a Ksnip
# Ctrol + Alt + K lanza Ksnip para capturar un rectángulo
Control Mod1 k :Exec ksnip --rectarea

# Abrir el menu de aplicaciones con atajo de teclado (en el lugar donde esté el cursor)
# Esto significa que la tecla de Windows (Mod4) y la tecla M abrirán el menú de las aplicaciones
# Super + M
Mod4 m :RootMenu

# Cómo poner una ventana siempre encima en Fluxbox
# Esto significa que la tecla Alt (Mod1) y la tecla V harán que la ventana que esté primero abiera se quedará allí
# https://linux.byexamples.com/archives/306/makes-your-windows-stay-on-top-toggle-it/
# Alt + V
Mod1 v :ToggleCmd {MacroCmd {RaiseLayer} {RaiseLayer}} {MacroCmd {LowerLayer} {LowerLayer}}

# Minimizar ventana activa
Mod4 n :Minimize

# Mostrar/ocultar escritorio (minimizar todas)
Mod4 d :ShowDesktop
```

### Tabla con mis atajos de teclado

Resumen de mis atajos de teclado:

|  Combinación de teclas  |                  Acción                  |                                   Comando ejecutado                                    |
| ----------------------- | ---------------------------------------- | -------------------------------------------------------------------------------------- |
| **Ctrl + Alt + A**      | Abrir AppFinder                          | `xfce4-appfinder`                                                                      |
| **Ctrl + Alt + K**      | Abrir Ksnip para capturar un rectángulo  | `ksnip --rectarea`                                                                     |
| **Super (Windows) + M** | Abrir el menú de aplicaciones de Fluxbox | `:RootMenu`                                                                            |
| **Alt + V**             | Poner una ventana siempre encima         | `:ToggleCmd {MacroCmd {RaiseLayer} {RaiseLayer}} {MacroCmd {LowerLayer} {LowerLayer}}` |
| **Super (Windows) + N** | Minimizar la ventana activa              | `:Minimize`                                                                            |
| **Super (Windows) + D** | Mostrar/ocultar escritorio               | `:ShowDesktop`                                                                         |

Con estos pasos y ejemplos, puedes agregar más atajos personalizados para cualquier aplicación o acción que desees realizar en Fluxbox.

Antes de que vea la configuración de los atajos de teclado, si usted es curioso y luego quisiera editar los atajos para añadir uno (para usuarios avanzados) puede dar clic derecho en algún lugar del escritorio si estuviera sin ninguna aplicación encima o sino de clic derecho a la izquierda abajo del escritorio:  

![](vx_images/547226287889775.png)

luego clic en:  

![](vx_images/547226287889776.png)

allí yo puse mis configuraciones al archivo .fluxbox/keys  

y a continuación mis atajos con imagenes, y un atajo que ya estaba:

## AppFinder
Para abrir el buscador de aplicaciones AppFinder (xfce4-appfinder)

Tecla Ctrl + Alt + A  

![](vx_images/547226287889770.png)


## Abrir menu de aplicaciones
EL siguiente atajo de teclado es para abrir el menu de aplicaciones en cualquier lugar donde esté el cursor, con el atajo de teclado:

Tecla Windows + M

o lo que es lo mismo:

Super + M  

![](vx_images/528004816576412.png)

**Nota:** Si no elige ninguna aplicación aplaste ESC para escapar

## Poner una ventana siempre encima
Si usted por ejemplo tiene abierta la terminal y quisiera que ella esté siempre enfrente de las demás ventanas aplaste:

Alt + V

para devolver esa ventana a su estado normal, estando enfrente de la ventana de esa aplicación otra vez dar:

Alt + V

**Nota:** La Tecla Alt se llama Mod1 en las configuraciones de los atajos de teclado de Fluxbox


## Minimizar ventana activa
Con las teclas:

Super + N

se minimiza la ventana activa.

**Nota**: Este atajo está configurado en el archivo `.fluxbox/keys` con:

```
Mod4 n :Minimize
```

## Mostrar/ocultar escritorio
Con las teclas:

Super + D

se muestra u oculta el escritorio con la acción `ShowDesktop` de Fluxbox.

**Nota**: Este atajo está configurado en el archivo `.fluxbox/keys` con:

```
Mod4 d :ShowDesktop
```


# Control de brillo para evitar cansancio ocular

En versiones anteriores usaba Gammy para el control de brillo, pero en el archivo actual `.fluxbox/startup` de este repositorio ya no está añadido al autoinicio. Actualmente allí está añadida esta línea para iniciar `xsct_gui.py`:

```bash
python3 /home/wachin/Dev/xsct_gui-dev/xsct_gui/xsct_gui.py &
```

Si usted no tiene ese programa en esa ruta, puede comentar o borrar esa línea del archivo `.fluxbox/startup`, o cambiarla por la herramienta de brillo que use en su sistema.

Ese archivo lo puede abrir desde el menú:  

![](vx_images/547226287889784.png)

allí lo puse:  

![](vx_images/547226287889785.png)

también lo puede buscar manualmente con el administrador de archivos  usando Ctrl + H para ver los archivos ocultos y buscar la ruta:

.fluxbox/startup

lo puede abrir a ese archivo con algún editor de texto, ejemplo en la siguiente imagen con Geany:  

![](vx_images/547226287889786.png)

Si decide usar Gammy, puede añadirlo manualmente al archivo `.fluxbox/startup` con una línea como esta:

```bash
gammy &
```

La siguiente imagen es de Gammy en MX Linux 21:

![](vx_images/547226287889778.png)



**Para Instalarlo en MX Linux 19.-** hay que compilarlo desde el código fuente, ver:

**Compilando gammy 0.9.51 (herramienta para ajustar el brillo / temperatura del monitor) en MX Linux 19**
<https://facilitarelsoftwarelibre.blogspot.com/2022/02/compilando-gammy-en-mx-linux-19.html>

Por cierto para minimizar gammy en MX Linux 19 es así como muestro en la siguiente imagen:  

![](vx_images/547226287889798.png)


# Cómo cambiar de Estilo de Fluxbox
Cuando usted cambie de estilo:

En es escritorio clic derecho en el menú, o en las esquinas o Super + M y clic en **Estilos**  

![](vx_images/67240114268985.png)

en esta imagen ustedes ven que se ven bien los nombres de los estilos disponibles, sin embargo cuando elijan otro estilo muy posiblemente no se verán bien, para que se vean bien si lo desean pueden cerrar sesión y cuando entren otra vez ya se verán bien las letras, pero esto de cerrar sesión no es necesario de hacerlo del todo, pueden seguir usando Fluxbox y ya en el siguiente ingreso se verá bien.

Por cierto hay algunos de estos temas en lo que al cambiar de tema no se ven todos los estilos disponibles, para arreglar eso de clic:

En es escritorio clic derecho en el menú, o en las esquinas o Super + M y clic en **Reajustar Fluxbox ** 

![](vx_images/353071596826508.png)

al hacer eso ya se verán bien todos los estilos disponibles


## Sombras en las ventanas con Picom (opcional)

Para que los temas se vean mejor y sea más fácil diferenciar dónde termina cada ventana, se puede usar `picom` para añadir una sombra suave alrededor de las ventanas.

Primero instale `picom`:

```bash
sudo apt install picom
```

Para dejarlo fijo, abra el archivo `~/.fluxbox/startup` y añada esta línea antes de `exec fluxbox`:

```bash
picom --backend xrender --shadow --shadow-radius 17 --shadow-offset-x -17 --shadow-offset-y -17 --shadow-opacity 0.30 --inactive-opacity 1 --active-opacity 1 --frame-opacity 1 --no-fading-openclose &
```

Este comando deja las ventanas con sombras en las cuatro esquinas, sin hacer transparentes las ventanas activas ni inactivas.


# Cambiar el idioma del teclado
Yo vivo en el Ecuador en Latinoamérica y uso la Distribución para Español Latino y por eso lo he dejado configurado para usarlo, cic en:

**Menú --> Preferencias de Fluxbox --> Startup "Aplicaciones que se cargarán al Inicio"**

![](vx_images/143144309268994.png)

allí en:  

![](vx_images/424300892826517.png)

como ve en esa imagen lo puede cambiar por Español España siguiendo esos pasos, así cada vez que usted inicie su ordenador se cargará ese teclado


## Cambiando el idioma del teclado al vuelo (cambio rápido)
Les he dejado un menú para cambiar rápidamente de teclado

En es escritorio clic derecho en el menú, o en las esquinas o Super + M y clic en **Idioma del teclado ** 

![](vx_images/463993105615600.png)

No hay muchos idiomas, pero si ustedes necesiten algún otro me avisan

Esto es util pues imaginese que usted está traduciendo algún documento y quiera cambiar rapido a otro idoma


# Cambiar el wallpaper (Fondo de pantalla)
La primera vez que lo vamos a usar es necesario reiniciar nitrogen, de clic en:

**Menú --> Herramientas del Sistema --> Resetear Nitrogen en 1er uso, y resetear para usar Dos Monitores**

![](vx_images/378662901615609.png)

esa opción sirve para dos cosas, lo estamos usando para la primera

después de esto si ya pueden dar clic en:

**Menú --> Herramientas del Sistema --> Cambair el fondo del escritorio con Nitrogen - imagenes del sistema-**

![](vx_images/547226287889787.png)

allí se abrirá nitrogen y podrán cambiar de wallpaper, por defecto abrirá los que están instalados en el sistema. En la siguiente imagen le pongo los pasos para elegir otro:  

![](vx_images/547226287889788.png)

solo que en el punto 2 donde dice **Automatic** cambiele a **Scaled**



# Para añadir un fondo de escritorio (Wallpaper) personalizado

Para usar una imagen como Wallpaper, debe crear una capeta en algún lugar, puede ser dentro de la carpeta Imágenes:  

![](vx_images/547226287889789.png)

ejemplo:  

![](vx_images/547226287889790.png)

le he puesto como nombre Wallpapers y dentro he puesto varios:  

![](vx_images/547226287889791.png)

para poder seleccionarlos desde Nitrogen, clic en:

**Menú --> Herramientas del Sistema --> Cambiar sus fondos de escritorio con Nitrogen - sus imagenes-**

![](vx_images/547226287889818.png)

luego debo dar clic en Nitrogen en:

**Preferencias ** 

![](vx_images/547226287889792.png)

allí añadir la ruta donde están sus Wallpapers:  

![](vx_images/547226287889793.png)

así:  

![](vx_images/547226287889794.png)

así me queda y doy clic en OK:  

![](vx_images/547226287889795.png)

y les pongo la siguiente imagen para que puedan ver Nitrogen ha cargado las imagenes de la carpeta que creé en Imágenes:  

![](vx_images/547226287889796.png)

**Nota:** Scaled es para que la imagen ocupe todo el fondo del escritorio si es que no fuera del mismo tamaño y Wallpaper cambiado:  

![](vx_images/547226287889797.png)



# Para añadir fondos de escritorio (Wallpaper) de los repositorios (de diferentes distribuciones)

En los repositorios hay varios paquetes de fondos de escritorio de diferentes distribuciones, si uno en Synaptic busca la palabra:

**backgrounds**

encontrará varios paquetes que tienen fondos de escritorio  

![](vx_images/547226287889801.png)

allí como ejemplo instalé:

mate-backgrounds

y si busco en los **Archivos instalados**  

![](vx_images/547226287889802.png)

quedan instalados en la siguiente ruta:

/usr/share/backgrounds/mate  

![](vx_images/547226287889803.png)

pero Nitrogen no los carga

La solución más fácil para mi es marcarlos para instalar:  

![](vx_images/547226287889804.png)

y generar un script de descarga:  

![](vx_images/547226287889805.png)

el script de descarga por defecto aparecerá para guardarlo dentro de la ubicación:

root

![](vx_images/547226287889806.png)

pero yo nunca lo guardo allí (porque después adquieren permisos de super usuario y solo se pueden borrar abriendo un administrador de archivos como root, ejemplo: sudo pcmanfm -pero hay que tener instalado en este ejemplo pcmanfm, u otro administrador de archivos, no recomiendo usar el mismo Thunar por algunas razones-), siempre lo guardo en alguna partición de Windows: NTFS o exFAT, y si usted no tienen ninguna puede poner un Pendrive y guardarlo allí pues generalmente están en formato fat32 o exFAT:

![](vx_images/547226287889807.png)

y una vez en el lugar guardado abrir el archivo:

![](vx_images/547226287889808.png)

cada una de las lineas generadas en el script:

![](vx_images/547226287889809.png)

se pueden descargar desde una terminal una por una, o todas al mismo tiempo:

![](vx_images/547226287889810.png)

**Nota:** Hay que esperar hasta que el porcentaje esté al 100% de descarga. En la imagen de arriba el **deb** se descargarán en **HOME**

luego a cada paquete lo puede descomprimir con clic derecho extraer aquí:

![](vx_images/547226287889811.png)

y dentro buscar las imágenes y moverlas a la carpeta donde usted tiene sus imagenes:

![](vx_images/547226287889812.png)

en la siguiente imagen ya he entrado en el lugar donde están todas las imágenes:

![](vx_images/547226287889813.png)

todas esas imagenes usted las puede mover al lugar donde tiene sus imagenes para fondos de escritorio

Otros paquete con imagenes para fondo de pantalla:

plasma-wallpapers-addons

**Nota:** Estas imagenes de los paquetes en synaptic buscando las palabras: backgrounds y wallpaper son de MX Linux 19, en MX Linux 21 puede que hayan más paquetes

# Dónde puedo descargar más wallpapers del mundo Linux?

Puede buscar en Google

**Los Wallpapers de Ubuntu:**

Ponga en Google lo siguiente:

backgrounds packages.ubuntu.com/

![](vx_images/547226287889814.png)

también con la palabra wallpaper:

wallpaper archive.ubuntu.com

![](vx_images/547226287889815.png)

de allí obtuve dos enlaces importantes:

http://archive.ubuntu.com/ubuntu/pool/universe/u/ubuntu-gnome-wallpapers/

http://archive.ubuntu.com/ubuntu/pool/main/u/ubuntu-wallpapers/

también

**Los Wallpapers de Deepin Linux**

wallpapers community-packages.deepin.com/

![](vx_images/547226287889816.png)

a la fecha que hago este tutorial encontré este enlace allí:

https://community-packages.deepin.com/deepin/pool/main/d/deepin-wallpapers/

también 

**Los Wallpapers de Linux Mint:**

wallpapers packages.linuxmint.com

![](vx_images/547226287889817.png)




# Problemas con abrir terminal en Thunar, solución añadir otra terminal
Si usted usa la opción de abrir la terminal aquí de Thunar pues no lo haga pues la terminal de XFCE (xfce4-terminal) no funciona bien en Fluxbox no se porqué (esto en MX Linux 19 o 21), mejor use Konsole, o gnome-terminal u otra

para hacerlo en el siguiente ejemplo con Konsole (debe ternerla instalada) añada otra terminal así, clic en:

**Editar --> Configurar Acciones personalizadas**

![](vx_images/227491714268986.png)

allí clic en el + y llene las siguientes acciones:

![](vx_images/224692296826509.png)

con los siguientes datos:

**Nombre:** Abrir Gnome Terminal aquí  
**Descripción:** Iniciar emulador de consola aquí  
**Orden:** gnome-terminal %f  

En icono pongale un icono de terminal, de clic en el botón

**Icono:**

luego clic en y ponga:

**Seleccionar icono de:** Todos los iconos  
**Buscar un icono:** utilities-terminal  

y **aceptar**

y en la pestaña "**Condiciones de aparición**", marcar **Carpetas**:

y **Aceptar**

Ahora si desea puede ubicar más arriba a gnome-terminal, haga así búsque abajo a:

"**Abrir Gnome Terminal aquí**"

![](vx_images/547226287889773.png)

y me queda así:

![](vx_images/547226287889774.png)

Cuando quiera abrir terminal le aparecerá disponible Gnome Terminal.



## Para añadir la terminal **Konsole**

Debe ternerla instalada:

`sudo apt install konsole`

los datos son así:

**Nombre**: Abrir Konsole aquí  
**Descripción**: Iniciar emulador de consola aquí  
**Orden**: konsole --workdir %f  

y en la pestaña "**Condiciones de aparición**", marcar **Carpetas**

y en **icono** lo mismo de arriba

cuando quiera abrir terminal aquí le aparecerá disponible Konsole

![](vx_images/300524728941352.png)

También si desea la puede mover más arriba

**Nota:** Se debería poder añadir otras terminales algo así mismo.

# Temas de iconos recomendados para usar Thunar 
Por defecto será usado el tema de iconos de Gnome que instalamos arriba y se verá el icono en la barra de herramientas, pero si usted desea usar otro como lo es Breeze, ya no se verá el icono de Thunar en la barra de herramientas

Si usted quiere usar otro tema de iconos uno de los que recomiendo es:

Papirus  

para usarlo 

**Menú --> Herramientas del Sistema --> Personalizar apariencia y comportamiento**

**Nota:** El menú principal de Fluxbox se lo puede abrir desde escritorio con clic derecho, o en las esquinas abajo izquierda o derecha abajo, o con el atajo de teclado Super + M

![](vx_images/506513509268989.png)

allí en la pestaña:

Tema de iconos

![](vx_images/511683991826512.png)

También pueden usar las variantes:

Papirus-Dark  
Papirus-Light  

además el tema:

Numix también debería de funcionar bien. Pueden probar otros si desean

este tema de iconos es además compatible con las aplicaciones KDE si lo usaran también al ponerlo en "Qt5Ct"




# Editar las opciones de Fluxbox (opcional)
Para facil acceso les he dejado 

En es escritorio clic derecho en el menú, o en las esquinas o Super + M y clic en **Preferencias de Fluxbox**

![](vx_images/455513928941351.png)

se abrirá el editor de texto que ustedes usen

# Gracias a Note
Este tutorial ha sido hecho gracias al editor de Markdown Multiplataforma VNote:

**Vnote for MX Linux 21 (y Linux basados en Debian 11 Bullseye) ~ Proyecto Facilitar el Software Libre en el Ecuador**
[https://facilitarelsoftwarelibre.blogspot.com/2022/07/vnote-for-mx-linux-deb-package.html](https://facilitarelsoftwarelibre.blogspot.com/2022/07/vnote-for-mx-linux-deb-package.html)

# Configurar la velocidad del cursor en dispositivos 
xinput-gui es una interfaz grafica para xinput que le permitirá editar propiedades de dispositivos como:

- Teclados
- Ratones
- Paneles táctiles
- Touchpad

Así será más rápido y fácil de usar, vea la siguiente entrada para ello:

**No funciona la velocidad del cursor al cambiar o poner un Mouse(o Touchpad) externo en Ubuntu 16.04, 18.04, OpenSUSE, Linux Mint, Debian, antiX, MX Linux, etc - SOLUCIÓN xinput-gui **  
[https://facilitarelsoftwarelibre.blogspot.com/2020/07/no-funciona-la-velocidad-del-cursor-al.html](https://facilitarelsoftwarelibre.blogspot.com/2020/07/no-funciona-la-velocidad-del-cursor-al.html)


Dios les bendiga  


# CONSULTAS: 

Editing_the_init_file  
http://fluxbox-wiki.org/category/howtos/en/Editing_the_init_file.html  

How to place the toolbar to the top in fluxbox? - Unix & Linux Stack Exchange   
https://unix.stackexchange.com/questions/146277/how-to-place-the-toolbar-to-the-top-in-fluxbox  

Fluxbox Documentation  
http://fluxbox.sourceforge.net/docbook/en/html/  

DSL Tips and Tricks :: Changing Fluxbox time display to 24 hour format  
http://www.damnsmalllinux.org/f/topic-3-26-12332-0.html  

IceWM install and setup guide  
http://forums.fedoraforum.org/showthread.php?t=282433  

xdgmenumaker  
https://github.com/gapan/xdgmenumaker  

Nitrogen - ArchWiki  
https://wiki.archlinux.org/title/nitrogen  

Xubuntu Thunar "Open Terminal Here" opens konsole in homefolder  
https://askubuntu.com/questions/891680/xubuntu-thunar-open-terminal-here-opens-konsole-in-homefolder  
https://askubuntu.com/a/892502  https://github.com/mifi/lossless-cut
