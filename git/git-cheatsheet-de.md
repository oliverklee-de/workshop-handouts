[![oliverklee.de](/images/Logo.svg)](https://www.oliverklee.de/)

# Git-Cheatsheet

## 💻 Git-Installation

### Mac git-Installation

Wer homebrew benutzt:

```bash
brew install git
```

Ansonsten kann ein inoffizeller Mac Installer benutzt werden:
http://sourceforge.net/projects/git-osx-installer/

## 🐧 Bash/Linux-Kommandozeile

| Aktion                                                | Kommando             |
|-------------------------------------------------------| -------------------- |
| Zeige Verzeichnisinhalt                               | `ls`                 |
| In Verzeichnis `<dir>` wechseln                       | `cd <dir>`           |
| Zum letzten Verzeichnis wechseln                      | `cd -`               |
| Pfad des aktuellen Verzeichnisses anzeigen            | `pwd`                |
| Verzeichnis erstellen                                 | `mkdir <dir>`        |
| Datei löschen                                         | `rm <file>`          |
| Datei verschieben oder umbenennen                     | `mv <file1> <file2>` |
| Datei anlegen oder Dateizeit auf aktuelle Zeit setzen | `touch <file>`       |

## ⚙️ Git-Konfiguration

Denkt daran, die Platzhalter durch euren echten vollen Namen und eure
Mailadresse zu ersetzen.

### Persönliche Daten

```bash
git config --global user.name "Jane Doe"
git config --global user.email "jane.doe@example.com"
```

### Sachen zum Copy'n'Pasten

```bash
git config --global core.autocrlf false
git config --global core.eol lf
git config --global branch.autosetupmerge always
git config --global branch.autosetuprebase always
git config --global color.ui auto
git config --global core.precomposeunicode true
git config --global core.quotepath false
git config --global pull.rebase true
git config --global push.default simple
git config --global rebase.autostash true
git config --global rerere.enabled true
```

`Core.eol=lf` sorgt dafür, dass GIT den Unix-Linefeed als Default-Zeilenumbruch
kennt und verwendet.

Wichtig: Solltet Ihr nachträglich Einstellungen für `autocrlf` oder `core.eol`
ändern, muss das lokale repository neu ausgecheckt werden.

## 📝 Lokales Arbeiten

Den Zustand des lokalen Repositories anzeigen: `git status`

## 🛠️ Schadensbegrenzung

### Teil 1

_to do_

### Teil 2

_to do_

## 🌿 Branches

alle lokalen Branches anzeigen: `git branch`

einen Branch löschen, der keine ungemergten Änderungen hat:
`git branch -d <branchname>`

einen Branch löschen (auch mit ungemergten Änderungen):
`git branch -D <branchname>`

## 🔀 Rebase und Konflikte

Einen Branch mit einem anderen rebasen:

1. einen Branch A auschecken: `git switch <branchnameA>`
1. den ausgecheckten Branch A mit einem anderen Branch B rebasen: `git rebase <branchnameB>`

### Konflikte

_to do_

### Interaktiver Rebase

Rebase ausführen: `git rebase -i HEAD~<Anzahl der Schritte>`

| Commands in File-Edit Mode | Beschreibung                                                 |
|----------------------------|--------------------------------------------------------------|
| `p`, pick                  | Commit verwenden                                             |
| `r`, reword                | Commit verwenden und Commit-Log ändern                       |
| `e`, edit                  | Commit verwenden und den Commit selbst ändern (Log & Inhalt) |
| `s`, squash                | Commit verwenden und mit vorhergehendem Commit verschmelzen  |
| `f`, fixup                 | wie squash, Commit-Log verwerfen                             |
| `x`, exec                  | Shell-Command ausführen – restliche Zeile nach `x, exec`     |
| `d`, drop                  | Commit löschen                                               |

Datei speichern und schließen

## 🚫 .gitignore

Verzeichnis `.idea/` im Hauptverzeichnis ignorieren: `/.idea/`

alle `*.backup`-Dateien in allen Verzeichnissen ignorieren: `*.backup`

Alle Dateien in `/var/log/` ignorieren bis auf die Datei `.gitkeep` dort (damit
das Verzeichnis trotzdem im Git-Repository vorhanden ist):

```
/var/log/*
!/var/log/.gitkeep
```

Alles in `/private/` und `/private/typo3conf/` ignorieren, aber das
Verzeichnis `/private/typo3conf/l10n` nicht ignorieren (das von TYPO3
automatisch erzeugt wird, sodass wir da keine `.gitignore` benötigen):

```
/private/*
!/private/typo3conf
/private/typo3conf/*
!/private/typo3conf/l10n
```

## 🌐 Verteiltes Arbeiten

_to do_

## 🐙 Arbeiten mit GitHub im selben Projekt

_to do_

## 🏷️ Tags

| Aktion                               | Kommando                                     |
|--------------------------------------|----------------------------------------------|
| Alle lokalen Tags anzeigen           | `git tag`                                    |
| Annotierten Tag erzeugen             | `git tag -a <tagname> -m "<Commit message>"` |
| GPG-signierten Tag erzeugen          | `git tag -s <tagname> -m "<Commit message>"` |
| Alle Tags auf remote pushen          | `git push --tags`                            |
| Commits und anschließend Tags pushen | `git push --follow-tags`                     |
| Tag lokal löschen                    | `git tag -d <tagname>`                       |
| Tag remote löschen                   | `git push origin :<tagname>`                 |

## 🌐 Open-Source-Arbeit mit Forks

### Mit dem Fork verbinden

in Github auf das Original-Repository wechseln und über den Button **Fork** einen eigenen Fork anlegen.

den Fork lokal clonen: `git clone <fork-repository> (<zielverzeichnis>)`

in das Zielverzeichnis wechseln: `cd <zielverzeichnis>`

mit dem Original-Repository verknüpfen: `git remote add upstream <Repository-URL>`

### Den lokalen Master mit Upstream synchronisieren und auf euren Fork pushen

zum Master wechseln: `git checkout master`

den Fork mit dem Original abgleichen: `git fetch upstream`

den lokalen Master abgleichen: `git rebase upstream/master`

### Einen Pull-Request bearbeiten

die Änderungen im bestehenden Commit veröffentlichen: `git commit --amend`

die Änderungen auf den Fork verschieben (force): `git push -f`

**Wichtig**
in der Beschreibung `Fixes #<Ticketnummer>` angeben, damit beim Merge das Ticket automatisch geschlossen werden kann.
Üblicherweise steht die Zeile am Ende der Beschreibung.

### Nach dem geschlossenen Pull-Request das eigene Fork wieder updaten

online in der Maske den Remote-Branch löschen

1. zum geschlossenen Pull-Request wechseln
1. den Branch löschen

zum Master wechseln: `git checkout master`

prüfen, ob der Remote-Branch noch existiert: `git remote prune origin`

den lokalen Branch löschen `git branch -D <Branch Name>`

den lokalen Master mit Upstream synchronisieren und auf euren Fork pushen
