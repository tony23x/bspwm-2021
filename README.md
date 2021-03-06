![screen](https://user-images.githubusercontent.com/55555800/147170398-cb82dd1e-1650-4db6-85d4-e13c838a3ddb.png)
<h5 align="center"> Configuración de: https://github.com/darch7 y notas del tito s4vitar ~> https://pastebin.com/EEX1Dsuq </h5>
<hr>
  
### Setup
 
Bspwm:

```sh
 sudo apt install build-essential git vim xcb libxcb-util0-dev libxcb-ewmh-dev libxcb-randr0-dev libxcb-icccm4-dev libxcb-keysyms1-dev libxcb-xinerama0-dev libasound2-dev libxcb-xtest0-dev libxcb-shape0-dev -y
 
 git clone https://github.com/baskerville/bspwm.git ~/Descargas/bspwm
 
 cd ~/Descargas/bspwm
 
 make
 
 sudo make install
 
 mkdir -p ~/.config/{bspwm,sxhkd}
```
 
Sxhkd:
 
```sh
 git clone https://github.com/baskerville/sxhkd.git ~/Descargas/sxhkd
 
 cd ~/Descargas/sxhkd/
 
 make
 
 sudo make install
```
 
Polybar:
 
```sh
 sudo apt install build-essential git cmake cmake-data pkg-config python3-sphinx python3-packaging libuv1-dev libcairo2-dev libxcb1-dev libxcb-util0-dev libxcb-randr0-dev libxcb-composite0-dev python3-xcbgen xcb-proto libxcb-image0-dev libxcb-ewmh-dev libxcb-icccm4-dev
 
 sudo apt install libxcb-xkb-dev libxcb-xrm-dev libxcb-cursor-dev libasound2-dev libpulse-dev i3-wm libjsoncpp-dev libmpdclient-dev libcurl4-openssl-dev libnl-genl-3-dev
 
 git clone https://github.com/VaughnValle/blue-sky.git ~/Descargas/blue-sky

 git clone --recursive https://github.com/polybar/polybar ~/Descargas/polybar
 
 mkdir ~/Descargas/polybar/build
 
 cd ~/Descargas/polybar/build
 
 cmake ..
 
 make -j$(nproc)
 
 sudo make install
```
 
Picom:
 
```sh
 git clone https://github.com/ibhagwan/picom.git ~/Descargas/picom

 cd ~/Descargas/picom/
 
 git submodule update --init --recursive
 
 sudo apt install libev-dev libx11-xcb-dev libxcb-damage0 libxcb-damage0-dev libxcb-sync-dev libxcb-present-dev libxcb-glx0-dev uthash-dev libconfig-dev libgl-dev libdbus-1-dev -y

 meson --buildtype=release . build

 ninja -C build

 sudo ninja -C build install
 ```
 
Slimlock:

```sh
 sudo apt install slim libpam0g-dev libxrandr-dev libfreetype6-dev libimlib2-dev libxft-dev -y
 
 git clone https://github.com/joelburget/slimlock.git ~/Descargas/slimlock
 
 cd ~/Descargas/slimlock/
 
 sudo make
 
 sudo make install
 
 sudo cp ~/Descargas/blue-sky/slim/slim.conf /etc/

 sudo cp -r ~/Descargas/blue-sky/slim/default /usr/share/slim/themes
```

Fuentes de agua:
 
```sh
 sudo cp ~/Descargas/blue-sky/polybar/fonts/* /usr/share/fonts/truetype/
 
 fc-cache -v
```
 
ZSH:
 
```sh
 user=$(whoami)
 
 sudo usermod --shell /usr/bin/zsh $user
 
 sudo usermod --shell /usr/bin/zsh root
```

Firefox:
 
 ```sh
 sudo apt install firejail
 ```

 Lanzar firefox bajo este contexto enjaulado con sxhkd e instalamos el addon 'FoxyProxy' para Firefox y le configuras para usar Burpsuite en 127.0.0.1:8080 (Default)

Spotify:

```sh
 sudo apt install git make rustc -y
 
 git clone https://github.com/abba23/spotify-adblock.git ~/Descargas/spotify-adblock 

 cd ~/Descargas/spotify-adblock/

 make

 sudo make install
 ```
 Usa Windows + k para lanzar Spotify sin anuncios.

Now: 

```sh
 git clone https://github.com/tony23x/bspwm-2021.git ~/Descargas/bspwm-2021
  
 mv ~/Descargas/bspwm-2021/local/* ~/.local
 
 mv ~/Descargas/bspwm-2021/config/* ~/.config
 
 cp -rf ~/Descargas/bspwm-2021/.Xresources ~
 
 chmod -R u+x ~/.config ~/.local ~/.Xresources
```

Finally:
 
* Sal de la session y da click en la parte superior derecha en el circulo, luego click en bspwm e ingresa tus credenciales
 
* Wallpaper:
 
Instalamos 'feh' con:
 
```sh
 sudo apt install feh
 ``` 
 ...para poder cargar fondos de pantalla y cargamos en el archivo bspwmrc justo al final la siguiente línea:
 
```sh
feh --bg-fill /home/s4vitar/Desktop/S4vitar/Images/fondo.jpg
```

O instalamos 'nitrogen' con:

```sh
 sudo apt install nitrogen 
 ``` 
 ... y para poder cargar fondos de pantalla, usa Windows + n
 
* Instalamos bat, lsd, fzf y ranger e instalamoos el plugin sudo para la ZSH 
 
* Seleccionamos el tema Nord para Rofi con:
 
 ```sh
 rofi-theme-selector
 ```
 
* Para slimlock si queremos cambiar la imagen del panel, nos vamos a la ruta '/usr/share/slim/themes/default' y retocamos el archivo 'panel.png'.

Si no aparece en el login'bspwm' instala con:
 
```sh
 sudo apt install bspwm sxhkd -y
 ``` 
