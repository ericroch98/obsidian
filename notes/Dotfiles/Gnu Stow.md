## Naming Convention
Es gibt zwei Möglichkeiten Stow einzurichten. Hier wird davon ausgegangen, dass sich das Verzeichnis mit den zu linkenden Dateien im HOME-Verzeichnis befindet. Mit dem Befehl `stow .` nimmt stow die aktuellen Dateien und linkt sie in das übergeordnete Verzeichnis.
### 1. direkte Abbildung der Home-Verzeichnisses
Beispiel:

```
~ (hier werden die Dateien gelinked)
|
|--	dotfiles (in diesem Ordner stow . ausführen)
	|
	|-- .bashrc
	|-- .config
	    |-- kitty
	    |   |-- kitty.conf
	    |-- starship.toml
	    |-- tmux
	        |-- plugins
	        |-- .tmux.conf
```
**Vorteil:** alles kann mit `stow .`, wenn man sich im **dotfiles-Verzeichnis** befindet direkt gelinked werden.
**Nachteil:** man kann nur umständlich über die -d und -t flag einzelne Konfugurationen verlinken. [Quelle](https://www.gnu.org/software/stow/manual/stow.html#Invoking-Stow)


### 2. Erstellen von Packages
Beispiel:
```
~
|
|-- dotfiles
    |
    |-- bash (package-name)
    |   |-- .bashrc
    |-- kitty (package-name)
    |   |-- .config
    |       |-- kitty
    |           |-- kitty.conf
    |-- starship (package-name)
    |   |-- .config
    |        |-- starship.toml
    |-- tmux (package-name)
        |-- .config
            |-- tmux
                |-- plugins
                |-- tmux.conf     
```
**Vorteil:** Konfigurationen für einzelne Software kann mit `stow package-name` für die gewünschte Software geladen werden. Konfigurationen für neue Software ist in einem eigenen Package und verringert das Risiko bestehende Dateien ausversehen zu verändern.
**Nachteil**: Zu Beginn etwas unintuitiv und viel Redundanz.