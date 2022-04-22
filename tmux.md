### Panes

Crear nuevo pane vertical
* ctrl+b y luego %

Crear nuevo pane horizontal
* ctrl+b y luego "

Cambiar de pane
* ctrl+v arrow

### Windows

Crear nueva ventana
* ctrl+b y luego c

Mover a ventana
* crtl+b y luego número de ventana

Renombrar ventana
* ctrl+b luego , y poner el nombre

### Sessions

Detach de sessión
* ctrl+b d

Ver sesiones abiertas de tmux
* tmux ls

Attach a sesión
* tmux attach -t <session number>

Renombrar sesión
* tmux rename-session -t 0 <nombre deseado>

Iniciar sesión nombrada
* tmux new -s docker

Matar sesión
* tmux kill-session -t docker