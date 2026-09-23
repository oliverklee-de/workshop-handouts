[![oliverklee.de](/images/Logo.svg)](https://www.oliverklee.de/)

# Git-Cheatsheet

## 💻 Git-Installation

### Mac git-Installation

Wer homebrew benutzt:

```bash
brew install git
```

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
git config --global branch.autosetupmerge always
git config --global branch.autosetuprebase always
git config --global color.ui auto
git config --global core.autocrlf false
git config --global core.eol lf
git config --global core.precomposeunicode true
git config --global core.quotepath false
git config --global init.defaultbranch main
git config --global pull.rebase true
git config --global push.default simple
git config --global rebase.autostash true
git config --global rerere.enabled true
```

`core.eol=lf` sorgt dafür, dass GIT den Unix-Linefeed als Default-Zeilenumbruch
kennt und verwendet, sofern keine `.gitattributes`-Regel etwas anderes festlegt.

Wichtig: Solltet Ihr nachträglich Einstellungen für `autocrlf` oder `core.eol`
ändern, muss das lokale repository neu ausgecheckt werden.

## 📝 Lokales Arbeiten

Den Zustand des lokalen Repositories anzeigen: `git status`

## 🌿 Branches

| Aktion                                                             | Git-Befehl                       |
|--------------------------------------------------------------------|----------------------------------|
| Alle lokalen Branches anzeigen                                     | `git branch`                     |
| Einen lokalen Branch löschen, der keine ungemergten Änderungen hat | `git branch -d <branchname>`     |
| Einen Branch lokalen löschen (auch mit ungemergten Änderungen)     | `git branch -D <branchname>`     |
| Remote-Branch löschen                                              | `git push origin :<branchname> ` |
| Verwaiste Remote-Referenzen aufräumen                              | `git remote prune origin`        |

## 🔀 Rebase und Konflikte

Einen Branch mit einem anderen rebasen:

1. einen Branch A auschecken: `git switch <branchnameA>`
2. den ausgecheckten Branch A mit einem anderen Branch B rebasen:
   `git rebase <branchnameB>`

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

## 📬 Workflow für PR

| Aktion                                                                                 | Kommando                           |
|----------------------------------------------------------------------------------------|------------------------------------|
| Neuen Branch von `main` erstellen und wechseln                                         | `git switch -c <neuerbranch> main` |
| Alle Änderungen committen *(`-a` fügt geänderte Dateien hinzu, **aber keine Neuen!**)* | `git commit -a`                    |
| Den neuen Branch auf Remote pushen und als Tracking-Branch setzen                      | `git push -u origin <neuerbranch>` |

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

in Github auf das Original-Repository wechseln und über den Button **Fork**
einen eigenen Fork anlegen.

den Fork lokal clonen: `git clone <fork-repository> (<zielverzeichnis>)`

in das Zielverzeichnis wechseln: `cd <zielverzeichnis>`

mit dem Original-Repository verknüpfen:
`git remote add upstream <Repository-URL>`

### Den lokalen Main mit Upstream synchronisieren und auf euren Fork pushen

zum Main wechseln: `git switch main`

den Fork mit dem Original abgleichen: `git fetch upstream`

den lokalen Main abgleichen: `git rebase upstream/main`

### Einen Pull-Request bearbeiten

die Änderungen im bestehenden Commit veröffentlichen: `git commit --amend`

### Nach dem geschlossenen Pull-Request das eigene Fork wieder updaten

online in der Maske den Remote-Branch löschen

1. zum geschlossenen Pull-Request wechseln
2. den Branch löschen

zum Main wechseln: `git switch main`

prüfen, ob der Remote-Branch noch existiert: `git remote prune origin`

den lokalen Branch löschen `git branch -D <branchName>`

den lokalen Main mit Upstream synchronisieren und auf euren Fork pushen

## ✉️ Commit-Message

### Subject

Das Subject einer Commit-Message sollten im Englischen den Imperativ benutzen
(`Use a chronological sorting`) und im Deutschen den Infinitiv
(`Auf chronologische Sortierung umstellen`).

### Body

Der Body einer Commit-Message sollte das Warum eines Commits beschreiben (fall
nötig).

Wenn ein Pull-Request ein Ticket schließt, sollte im Body
`Fixes #<Ticketnummer>` stehen. Das sorgt dafür, dass beim Mergen des PRs das
Ticket automatisch geschlossen wird. Üblicherweise steht diese Zeile am Ende des
Bodys.

### Projektspezifische Commit-Message-Konventionen

Je nach Projekt oder Organisation können im Subject Codes für die Art der
Änderung stehen.

Bei Projekten von [oliverklee.de](https://www.oliverklee.de/) verwenden wir
beispielsweise die folgenden Codes (angelehnt an die Konventionen des
TYPO3-Core):

- `[FEATURE]` (plus GitHub-Label **enhancement**): wenn neue Funktionalität
  hinzugefügt wird
- `[BUGFIX]` (plus GitHub-Label **bug**): wenn etwas repariert wird, das vorher
  kaputt war
- `[CLEANUP]`: wenn nur Code aufgeräumt wird (z. B. Auto-Formatierung)
- `[DOCS]`: für Änderungen an der Dokumentation
- `[TASK]`: alles andere

### Weiterführende Links zu Best-Practices für Commit-Messages

- https://cbea.ms/git-commit/
- https://www.freecodecamp.org/news/how-to-write-better-git-commit-messages/
- https://www.gitkraken.com/learn/git/best-practices/git-commit-message
- https://docs.typo3.org/m/typo3/guide-contributionworkflow/main/en-us/Appendix/CommitMessage.html
- https://github.com/oliverklee-de/seminars/commit/1df376e2f57b680383e886cfa3201e4de2fc5479

## 🐧 Weiterführende Informationen zu Kommandozeile/ Linux

* siehe [Linux Cheatsheet](linux-cheatsheet-de.md)
