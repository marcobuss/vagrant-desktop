# Vagrant Box fürs Angular2 Training

## Voraussetzungen
Auf dem Rechner müssen [vagrant](https://www.vagrantup.com/) und [Virtualbox](https://www.virtualbox.org/) installiert sein.

## Clonen und Starten
Clone dieses Repository mittels `git clone https://github.com/rattermeyer/vagrant-desktop.git`.
Wechsle in das Verzeichnis vagrant-desktop.

Kopiere die Datei `customization.yml.sample` nach `customization.yml` und passe sie
für dich an.

Wenn du zufrieden bist, dann starte die Box mittels

`vagrant up`

Wenn das durch ist noch einmal

`vagrant reload`

## Ergebnis + Nacharbeiten

Du bekommst eine Xubuntu basierte Box mit deinem User (siehe `customization.yml`) eingerichtet.
Installiert sind

* IntelliJ Ultimate in der aktuellen Version 2016.3.3. Dieses befindet sich unter /opt/intellij. Aufruf über `idea`. Dann kann man alles weitere (Desktop Icons, Plugins, etc einrichten)
* Google Chrome
* [nvm](https://github.com/creationix/nvm)
* node 6.9.4
* angular-cli
* Kursunterlagen gecloned nach git/angular2kurs
* [meld](http://meldmerge.org/) als Mergetool
* Nützliche git aliases
* [tig](https://jonas.github.io/tig/) als ncurses basiertes git frontend, allerdings ist die git Integration in IntelliJ sehr gut. Für denjenigen, der trotzdem einen exteren grafischen git client hat, habe ich
* [giteye](http://www.collab.net/products/giteye) hinzugefügt. Welches über `/opt/giteyey/current/GitEye` gestartet wird

Das Keyboard ist auf deutsch, allerdings wurden keine weiteren Language Einstellungen vorgenommen.
Achtung: Es wurde nicht überprüft ob die Shortcuts vom Desktop Environment und IntelliJ sich nicht "beißen". Wenn ihr eine Einstellung habt, die ihr gut findet, dann könnt ihr sie mir gerne schicken. Für xfce findet ihr die unter `.config/xfce4/xfconf/xfce-perchannel-xml/xfce4-keyboard-shortcuts.xml`.

Bitte installiert ggf. die aktualisierte Version der VirtualBox Guest Extensions.

# Erweiterungen

* Es kann auch einfach weitere Editoren installiert werden:

* atom
* vim

Für vim müsst ihr dazu in die `customizatio.yml`

Folgende Zeile einfügen

    vim_install: True

Für atom ist ebenfalls nur `atom_install: True` notwendig.

Ihr könnt aber noch Packages direkt installieren lassen:

      atom_desktop_icon: True
      atom_packages:
      - ansible-snippets
      - ansible-vault
      - asciidoc-preview
      - language-ansible
      - language-asciidoc
      - markdown-writer
      - markdown-table-formatter
      - linter-ansible-linting
      - atom-typescript


## Known Issues

* Es wird nicht überprüft, ob eine globale Library schon installiert ist, sondern es wird nochmals versucht sie zu installieren (kostet Zeit)
