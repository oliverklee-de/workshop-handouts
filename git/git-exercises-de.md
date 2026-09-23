# Übungen zu Git

Die nötigen Befehle findet ihr im
[Git-Cheatsheet](../cheatsheets/git-cheatsheet-de.md).

## Git-Installation

1. Installiert euch Git (siehe die [README](README.md)).

## Bash/Linux-Kommandozeile

1. Lasst euch anzeigen, in welchem Verzeichnis ihr gerade seid.
2. Lasst euch anzeigen, welche Verzeichnisse und Dateien es im aktuellen
   Verzeichnis gibt.
3. Wechselt in ein Unterverzeichnis.
4. Lasst euch wieder anzeigen, in welchem Verzeichnis ihr gerade seid.
5. Wechselt wieder ein Verzeichnis nach oben.
6. Wechselt mit `cd -` wieder in das Unterverzeichnis und wieder zurück.
7. Wechselt in das Verzeichnis, in dem ihr die Übungen für heute machen
   möchtet, und in dem ihr Dateien anlegen möchtet.
8. Legt eine leere Datei an (`touch`).
9. Schaut, dass die Datei jetzt tatsächlich existiert.
10. Schaut noch einmal - aber benutzt diesmal den Befehl in der History über die
    Cursortasten.
11. Benennt die Datei um.
12. Schaut, dass die Datei jetzt anders heißt (indem ihr mit CTRL + R in der
    History sucht).
13. Löscht die Datei.
14. Schaut, dass die Datei jetzt tatsächlich nicht mehr existiert.

## Git-Konfiguration

1. Richtet euch Tab-Autovervollständigung für Git ein. Ihr könnt es testen,
   indem ihr `git check` tippt und dann Tab drückt. Wenn aus `check` ein
   `checkout` wird, tut's die Autovervollständigung.
2. Konfiguriert Git anhand der Anleitung im [README](README.md). Prüft die
   Einstellungen danach mit `git config --list`. Ersetzt dabei in den ersten
   beiden Zeilen die Platzhalter mit eurem echten vollen Namen und eurer
   Mailadresse.

## Lokales Arbeiten

1. Lasst euch anzeigen, welche Git-Version ihr benutzt.
2. Lasst euch die Git-Hilfe anzeigen.
3. Lasst euch die Git-Hilfe für `git init` anzeigen. Falls die Hilfe auf der
   Kommandozeile angezeigt wird, kommt ihr mit der `q`-Taste wieder raus.
4. Legt das Verzeichnis an, mit dem ihr lokal üben möchtet, und wechselt in das
   Verzeichnis.
5. Legt ein leeres Git-Repository an.
6. Lasst euch den Status des Repositories anzeigen.
7. Legt eine kleine Textdatei `hans.txt` an.
8. Lasst euch den Status anzeigen.
9. Fügt die Datei zur Staging-Area hinzu.
10. Lasst euch den Status anzeigen.
11. Lasst euch die Unterschiede zum letzten Commit anzeigen.
12. Lasst euch die Unterschiede der Staging-Area zum letzten Commit anzeigen.
13. Committet die Änderungen. Gebt dabei die Commit-Message direkt mit an.
14. Lasst euch den Status anzeigen.
15. Lasst euch das Log anzeigen.
16. Schaut euch mit `gitk` die History grafisch an.
17. Lasst euch den letzten Commit anzeigen.
18. Lasst euch die Liste der im letzten Commit geänderten Dateien anzeigen.
19. Und jetzt noch einmal dasselbe mit der Commit-ID.
20. Bearbeitet die existierende Datei `hans.txt` und legt außerdem eine zweite
    Datei `wurst.txt` neu an.
21. Lasst euch die Unterschiede zum letzten Commit anzeigen. (Mit `q` kommt ihr
    da wieder raus.)
22. Fügt die Datei zur Staging-Area hinzu.
23. Lasst euch den Status anzeigen.
24. Lasst euch die Unterschiede zum letzten Commit anzeigen.
25. Lasst euch die Unterschiede der Staging-Area zum letzten Commit anzeigen.
26. Commited die Änderungen, benutzt aber diesmal für die Commit-Message einen
    separaten Editor, indem ihr sie nicht direkt schon auf der Kommandozeile
    angebt.
27. Lasst euch Status und Log anzeigen.
28. Bearbeitet `hans.txt`. Commit die Datei, ohne vorher ein explizites `add`
    zu machen.
29. Lasst euch das Log einzeilig anzeigen.

## Schadensbegrenzung

1. Bearbeitet die `hans.txt` und fügt diese zum letzten Commit hinzu.
2. Lasst euch das Log anzeigen.
3. Bearbeitet `hans.txt` und setzt die Datei dann wieder die Version aus dem
   letzten Commit zurück.
4. Setzt `hans.txt` auf die Version auf dem vorletzten Commit zurück (ohne zu
   committen).
5. Macht den kompletten letzten Commit rückgängig.
6. Ändert eine Datei. Bringt die Änderungen mit dem Stash in Sicherheit.
7. Holt die Änderungen wieder aus dem Stash.
8. Setzt die Datei wieder auf den Ursprungszustand zurück.

## Branches

1. Lasst euch anzeigen, welche Branches es gibt und auf welchem Branch ihr
   gerade seid.
2. Legt einen Branch `pinguin` an.
3. Wechselt auf den Branch.
4. Legt in dem Branch eine Datei `watscheln.txt` an und committet sie.
5. Schaut euch das Log an.
6. Wechselt wieder auf den `master`-Branch und schaut euch wieder das Log an.
7. Lasst euch den Unterschied zum `pinguin`-Branch anzeigen.
8. Wechselt mit `git checkout -` zum `pinguin` und wieder zurück zum `master`.
9. Merget den `pinguin`-Branch (per Fast-Forward, ohne Merge-Commit)
   in den `master` und schaut euch das Log an.
10. Entfernt den letzten Commit vom `master` wieder, sodass der `master` wieder
    den Zustand von vor dem Merge hat.
11. Merget den `pinguin`-Branch (ohne Fast-Forward, mit Merge-Commit)
    in den `master` und schaut euch das Log an.
12. Findet die Commit-IDs der beiden Eltern-Commits des Merge-Commits
    und vollzieht die Commit-IDs und die Struktur per `gitk` nach.
13. Löscht den `pinguin`-Branch.
14. Legt mit einem Kommando einen Branch `nacktmull` an und wechselt direkt in
    den Branch.
15. Legt eine Datei `frittiertes-mars.txt` an und committet sie.
16. Wechselt wieder in den `master`.
17. Löscht den `nacktmull`-Branch, ohne ihn zu mergen.

## Rebase und Konflikte

1. Legt einen Branch `tee` an, wechselt in den Branch, legt dort eine Datei
   `earl grey.txt` (mit Leerzeichen!) mit ein paar Zeilen Text an und committet
   sie.
2. Wechselt in den `master`, legt dort eine Datei `brot.txt` an und committet
   sie.
3. Wechselt auf den `tee`-Branch und rebased von `master`.
4. Wechselt in den `master`, bearbeitet `brot.txt` und committet die
   Änderungen.
5. Wechselt nach `tee`, bearbeitet in `brot.txt` dieselben Zeilen und committet
   die Änderungen.
6. Rebased von `master` und lasst euch den Status der Konflikte anzeigen.
7. Brecht das Rebase ab.
8. Rebased noch einmal. Löst diesmal die Konflikte im Editor, added die Datei
   und führt den Rebase dann zu Ende.
9. Legt einen Branch an, legt dort einen Commmit an und cherry-pickt diesen auf
   einen anderen Branch.

## RSA-Keys und Accounts

1. Erzeugt euch ein RSA-Schlüsselpaar **ohne Passphrase** (falls noch nicht
   geschehen). Hier die Anleitungen, wie man das unter Windows macht:
    - https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
    - https://dhue.de/git-fur-windows-installieren-und-ssh-keys-nutzen/
    - https://jdblischak.github.io/2014-09-18-chicago/novice/git/05-sshkeys.html
2. Loggt euch bei GitHub ein und ladet euren öffentlichen RSA-Schlüssel hoch.
    - https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/
3. Teilt Oliver euren GitHub-Usernamen mit und bittet ihn, euch zum
   Übungs-Repository hinzuzufügen.
4. Klont euch per SSH das Repository unter `https://github.com/symfony/demo`.
   Werft es nicht weg - ihr braucht es später noch.

## Verteiltes Arbeiten

1. Klont euch das Übungsrepository von GitHub/GitLab. Achtet dabei darauf,
   dass ihr es per SSH klont und nicht per HTTPS.
2. Wechselt in das Verzeichnis des geklonten Repositories.
3. Lasst euch die Remotes anzeigen.
4. Und jetzt mit den URLs.
5. Lasst euch die lokalen Branches anzeigen.
6. Lasst euch die Remote-Branches anzeigen.
7. Check den `gurkensalat`-Remote-Branch aus und wechselt direkt auf den Branch.
8. Wartet, bis Oliver etwas geändert und gepusht hat. Pullt euch die Änderungen.
9. Wechselt wieder auf den `main` und löscht den lokalen `gurkensalat`-Branch
   wieder.
10. Pullt euch die Änderungen.
11. Legt einen Branch an, legt dort einen Datei an und committet sie.
12. Wartet, bis Oliver etwas geändert und gepusht hat.
13. Wechselt zum `main`, pullt, wechselt zu eurem Branch, rebased, wechselt
    wieder zu `main`, merget euren Branch, pusht, und löscht euren Branch.
14. Erzeugt lokal einen Branch `development` sowie einen Branch `release`.
15. Legt in beiden Branches je zwei unterschiedliche Commits an.
16. Mergt `release` in `development`, sodass dabei ein Merge-Commit entsteht.
17. Fügt in beiden Branches je einen Commit hinzu, der dieselbe Stelle derselben
    Datei verändert, und mergt wieder `release` in `development`.
18. Erzeugt einen Branch `bugfix` von `release` und fügt dort einen Commit
    hinzu.
19. Fügt in `release` auch einen Commit hinzu.
20. Rebased den Branch `bugfix` auf `release`.

## Noch mehr Schadensbegrenzung

1. Erzeugt einen Branch nicht von `master`, sondern vom vorletzten Commit von
   `master`.
   Löscht den Branch dann wieder.
2. Schaut euch das Reflog an.
3. Stellt den gelöschten Branch `nacktmull` wieder her.
4. Wechselt auf den Branch.
5. Bearbeitet den obersten Commit per `amend`.
6. Vertauscht die letzten beiden Commits per interaktivem Rebase.
7. Löscht den vorletzten Commit aus dem Branch (per interaktivem Rebase).
8. Wechselt wieder auf den `master` und löscht den `nacktmull`-Branch.
9. Erzeugt einen Commit auf `master`. Findet zwei unterschiedliche Wege,
   diesen Commit auf einen neuen Branch zu retten, bevor ihr den `master`
   wieder auf den Stand ohne diesen Commit zurücksetzt.
10. Findet im Symfony-Demo-Repository per `git bisect` heraus, welcher Commit
    die Datei `app.json` gelöscht hat. (Spickt dafür bitte _nicht_ in der
    History
    dieser Datei - das wäre im Sinne dieser Übung.) Setzt danach das Repository
    wieder in einen jungfräulichen Zustand zurück.
11. Rebased den Branch `bugfix` auf `development`.
12. Findet 3 unterschiedliche Wege, wieder einen Branch `bugfix` zu haben, der
    wieder
    `release` plus die Inhalte der Commits aus `bugfix` enthält.
13. Legt zwei Dateien um Hauptverzeichnis eures Projektes an. Räumt diese mit
    Git-Bordmitteln wieder weg.
14. Legt eine Datei im Hauptverzeichnis an und eine im Unterverzeichnis.
    Räume beide mit Git-Bordmitteln wieder weg.
15. Legt einen neuen Branch an und macht dort den letzten Commit wieder
    rückgängig, sodass es dafür auch einen Commit gibt.
16. Räumt eure lokalen Kopien von Remote-Branches des Übungsprojektes wieder
    weg.
17. Führt die Garbage-Collection aus. Und jetzt noch einmal aggressiv.

## .gitignore und .gitattributes

1. Bearbeitet die `.gitignore so`, dass Dateien in allen Verzeichnissen
   ignoriert werden, die Endung `.bak` haben. Testet dies.
2. Sorgt dafür, dass das Verzeichnis `.idea/` nur im Projekt-Wurzelverzeichnis
   ignoriert wird. Testet beides.
3. Legt ein Verzeichnis `logs/` an. Sorgt dann dafür, dass dieses Verzeichnis
   im Git auftaucht, aber alle Dateien darin nicht.
4. Legt ein Verzeichnis `public/` an, darin `index.html`, sowie ein Verzeichnis
   `public/generated/`. Sorgt dafür, dass `public/generated/` und
   `public/index.html` im Git sind, alle anderen Dateien in `public/` sowie
   alle Dateien in `public/generated/` aber ignoriert werden.
5. Stellt ein, dass für minifiziertes JavaScript und minifiziertes CSS kein
   Git-Diff angezeigt wird. Testet dies mit dem minifizierten jQuery und dem
   minifizierten Bootstrap-CSS.

## Tags und Releases

1. Lasst euch im Spielwiesen-Projekt lokal alle Tags anzeigen.
2. Erzeugt im Spielwiesen-Projekt ein annotiertes Tag für euren Geburtstag,
   z.B. `v2.4.75` für den 2.4.1975.
3. Pusht alle Tags auf remote.
4. Überprüft auf GitHub/GitLab, dass euer Tag angekommen ist.
5. Nur GitLab: Erzeugt aus dem Tag ein Release.
6. Legt noch ein zweites Tag an, das wie euer erstes Tag heißt, aber mit "x",
   also zum Beispiel: `x2.4.75`
7. Pusht das Tag nach origin.
8. Löscht das Tag wieder lokal.
9. Löscht das Tag wieder von origin.
10. Legt von eurem Projekt ein ZIP-Archiv an. Schaut in das ZIP hinein.
11. Stellt ein, dass eine Datei eurer Wahl nicht im Archiv erscheint.
    Testet dies.

## Arbeiten mit Merge-Requests/Pull-Requests

Rollen:

- **A:** Autor:in
- **R:** Reviewer:in

1. Teilt euch in Zweiergruppen auf (und in einer Dreiergruppe, falls wir eine
   ungerade Anzahl Leute sind).
2. Sprecht ab, wer zuerst Autor:in ist und wer Reviewer:in. Spielt damit
   die Übungen durch und wechselt danach die Rollen.
3. **A:** Erzeugt im Übungsprojekt einen lokalen Branch mit eurem eigenen
   Namen. Legt dort eine Datei an, die auch euren eigenen Namen trägt, und
   committet sie.
4. **A:** Pusht den Branch auf das Remote-Repository.

### Ab hier: GitHub-Version

1. **A:** Erstellt einen Draft-Pull-Request und weist ihn euch selbst als
   Assignee zu.
2. **A:** Amended lokal den Commit auf diesem Branch und force-pusht.
3. **A:** Markiert den Pull-Request als nicht mehr "Draft" und setzt euren
   Buddy als Reviewer (GitHub).
4. **R:** Reviewt den Pull-Request eures Buddys, lobt per Kommentar eine Zeile,
   bittet per Kommentar an einer Zeile um eine Änderung
   und markiert den Review als "Änderungen benötigt".
5. **A:** Macht auf eurem eigenen Branch die gewünschten Änderungen, legt diese
   in
   einem neuen Commit ab und pusht euren Branch.
   Kommentiert den Kommentar außerdem mit "Done.".
6. **R:** Schaut euch den aktualisierten PR an.
   Markiert die Diskussion als gelöst.
   Schlagt diesmal eine einzeilige Änderung vor.
7. **A:** Übernehmt in eurem eigene PR die Änderung, holt euch den Commit auf
   lokal, squasht, und force-pusht.
8. **R:** Schlagt diesmal weitere Änderungen vor:
    * eine, die zwei Zeilen ändert
    * eine, die aus einer Zeile zwei macht
    * eine, die eine existierende Zeile löscht
9. **A:** Übernehmt die von eurem Buddy vorgeschlagene Änderungen.
   Squasht diesmal nicht.
10. **R:** Reviewt das Endergebnis, genehmigt den PR mit ein paar lobenden
    Worten (z.B. "LGTM"), und mergt ihn. Löscht den Branch.

### Ab hier: GitLab-Version

1. **A:** Erstellt einen WIP-Merge-Request und weist ihn euch selbst zu.
   Stellt ein, dass beim Mergen gesquasht werden soll und der Branch gelöscht
   werden soll.
2. **A:** Amended lokal den Commit auf diesem Branch und force-pusht.
3. **A:** Markiert den Merge-Request als nicht mehr "work in progress" und
   weist den Merge-Request eurem Buddy zu.
4. **R:** Reviewt den Merge-Request eures Buddys, lobt per Kommentar eine Zeile,
   bittet per Kommentar an einer Zeile um eine Änderung,
   markiert den Merge-Request als "Daumen runter" und weist
   den MR wieder zurück zu.
5. **A:** Macht auf eurem eigenen Branch die gewünschten Änderungen, legt diese
   in einem neuen Commit ab und pusht euren Branch. Weist den MR wieder eurem
   Review-Buddy zu.
   Kommentiert den Kommentar außerdem mit "Done.".
6. **R:** Schaut euch den aktualisierten MR an.
   Markiert die Diskussion als gelöst.
   Schlagt diesmal eine einzeilige Änderung vor.
   Denkt dabei ans Hin- und Her-Zuweisen.
7. **A:** Übernehmt in eurem eigene MR die Änderung, holt euch den Commit auf
   lokal, squasht, und force-pusht.
8. **R:** Schlagt diesmal weitere Änderungen vor:
    * eine, die zwei Zeilen ändert
    * eine, die aus einer Zeile zwei macht
    * eine, die eine existierende Zeile löscht
9. **A:** Übernehmt die von eurem Buddy vorgeschlagene Änderungen.
   Squasht diesmal nicht.
10. **R:** Reviewt das Endergebnis, genehmigt den MR mit ein paar lobenden
    Worten (z.B. "LGTM"), und mergt ihn. Squasht dabei die Commits und
    bearbeitet
    die Commit-Message.

## Commit-Messages

1. Lest euch den
   [Artikel über gute Commit-Message](https://chris.beams.io/posts/git-commit/)
   durch.
2. Schaut euch die
   [Commit-History des TYPO3-Core](https://github.com/TYPO3/TYPO3.CMS/commits/master)
   an. Nehmt euch zwei Commit-Messages vor, bei denen die Subjekt-Zeile nicht
   den Empfehlungen aus dem Artikel entspricht, und verbessert sie.
   Präsentiert dann die Vorher- und Nachher-Version beider Commit-Messages der
   Gruppe.
3. Sucht euch eine Commit-Message von euch selbst in eurem echten Projekt
   heraus,
   verbessert die komplette Message (mit Beschreibung), und präsentiert sie der
   Gruppe.

## Open-Source-Arbeit mit Forks

**Wichtig in diesem Abschnitt: Bitte erstellt hier nur sinnvolle Änderungen, die
das Git-Cheatsheet oder die Aufgaben verbessern, und keine unsinnigen
Test-Änderungen.**

1. Forkt das
   [Workshop-Handouts-Repository](https://github.com/oliverklee-de/workshop-handouts/).
2. Klont euch euren Fork auf lokal.
3. Legt euch lokal ein `upstream`-Remote an.
4. Sucht euch einen Abschnitt im
   [Git-Cheatsheet](../cheatsheets/git-cheatsheet-de.md) heraus,
   den ihr verbessern möchtet, erstellt dafür ein Ticket und weist es euch zu.
   **Bitte nur echte Tickets, keine Dummy-Tickets!**
   Alternativ könnt ihr auch gerne Fehler in den Aufgaben (also diesem
   Dokument) beheben. Eventuell stehen dafür in den
   [Issues](https://github.com/oliverklee-de/workshop-handouts/issues)
   auch schon offene Punkte, die ihr übernehmen könnt.
5. Legt dafür einen sinnvoll benannten Branch an und fügt dort eure Änderungen
   ein.
   Hier ist ein
   [Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
6. Erstellt daraus einen Pull-Request. Schreibt in die Beschreibung (nicht das
   Subject) der Commit-Message den Text `Fixes #<Ticketnummer>`, damit das
   Ticket beim Mergen des Pull-Requests automatisch geschlossen wird. **Bitte
   nur echte Pull-Requests, keine Dummy-PRs!**
7. Wartet auf Review-Feedback. Überarbeitet und rebaset euren PR nach Bedarf.
8. Wartet, bis Oliver euren PR gemergt hat.
9. Geht auf GitHub auf den geschlossenen PR und löscht darüber den
   Remote-Branch.
10. Bringt dann euren Fork auf den aktuellen Stand und löscht lokal den
    gemergten
    Branch (nachdem ihr `git remote prune origin` gemacht habt).

## Bonusaufgaben

Falls ihr Lust auf Knobelaufgaben habt:

1. Spielt [The Git Game](https://github.com/git-game/git-game).
2. Spielt [The Git Game 2](https://github.com/git-game/git-game-v2).
