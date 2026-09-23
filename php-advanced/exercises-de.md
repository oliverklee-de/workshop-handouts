# Übungsaufgaben zu fortgeschrittenem PHP

## Über das Übungsprojekt

Das Übungsprojekt `words` wird ein Kommandozeilen-basierter Werkzeugkasten
sein, mit dem ihr verschiedene Dinge mit Buchstaben, Wörtern und Wörterbüchern
tun könnt. Außerdem wird das Projekt ein paar Testfunktionen haben, mit denen
ihr einige PHP-Funktionalitäten ausprobieren könnt.

Das Projekt wird keine webbasierte Oberfläche haben, damit wir uns bei dem
Workshop nicht mit Web-Frameworks oder CMSen zu beschäftigen brauchen.

## Infrastruktur-Checks

1. Loggt euch per SSH auf euren Container ein.
2. Prüft, welche PHP-Version installiert ist: `php --version`
3. Prüft, welche Composer-Version installiert ist: `composer --version`
4. Prüft, dass ihr mit eurer IDE Dateien im Container anlegen und bearbeiten
   könnt.

## Projektstruktur

1. Legt euch ein Verzeichnis `words` für das Übungsprojekt an.
2. Falls ihr das Projekt mit Git versionieren möchtet (was ich sehr empfehle),
   initialisiert das lokale Git-Repository.
3. Legt die empfohlene Verzeichnisstruktur an. Falls ihr mit Git arbeitet, legt
   auch die `.gitkeep`-Dateien in den leeren Verzeichnissen an.
4. Stellt bei euch in der IDE ein, dass ihr Unix-Zeilenenden benutzt und keine
   BOM einfügt.
5. Schaut auf Packagist nach, welche Pakete der User `oliverklee`
   veröffentlicht hat.
6. Sucht euch einen aussagekräftigen Packagist-Usernamen aus und prüft, dass
   dieser Username noch nicht vergeben ist.
7. Falls ihr erwägt, irgendwann mal ein Projekt auf Packagist zu
   veröffentlichen, registriert euch auf Packagist, damit euer Username
   dauerhaft euch gehört.
8. Lest euch die Doku zur `composer.json` durch.
9. Legt eine `composer.json` für euer Projekt mit dem Typ `project` an.
   Schaut euch die Dokumentation für die `composer.json` an und füllt alle
   Eigenschaften, für die ihr sinnvolle Daten angeben könnt. Tragt auch die
   erforderlichen PHP-Versionen ein.
   Haltet bei den Eigenschaften die Reihenfolge in der Doku ein.
10. Autoformatiert die `composer.json`.
11. Lest euch die Doku zum PSR-4-Autoloading durch.
12. Überlegt euch einen Composer-Vendor-Namespace für euch. Dieser muss nicht
    identisch mit eurem Packagist-Usernamen sein, auch wenn diese sich
    üblicherweise entsprechen.
13. Tragt für euren Composer-Vendor-Namespace und den Produktnamen `Words`
    PSR-4-Autoloading in eure `composer.json` ein.

## Symfony-Konsole

Die Symfony-Konsole wird unser Einstiegspunkt für die Funktionalität sein,
die unser Projekt bekommt.

1. Lest euch die Doku zur Symfony-Konsole durch.
2. Legt eine Datei `bin/console` an und macht sie ausführbar.
3. Legt eine Klasse `Greet` im Unter-Namespace `Command` an.
4. Baut das `console`-Skript und ein Konsolen-Kommando, das mit `hello:greet`
   den Text "Hello world!" ausgibt. Sorgt für gute Doku zu dem Kommando.
5. Erweitert das Kommando um einen optionalen zweiten Parameter `name`. Falls
   dieser gesetzt ist, sieht die Ausgabe stattdessen so aus:

```bash
bin/console hello:greet Oliver
Hello, Oliver!
```

## Strikte Typisierung

1. Lest euch die Doku zu strikter Typisierung durch.
2. Lagert die beiden Begrüßungen (mit und ohne Namen) in separate Methoden aus.
3. Versorgt die neuen Methoden mit korrekten Typ-Deklarationen (und die alten
   auch, falls da noch etwas fehlen sollte). Falls ihr PHP >= 7.1 einsetzt,
   benutzt Nullable-Type-Declarations und Void-Funktionen, wo es passt.
4. Lest euch die Doku zum Strict-Mode durch und stellt alle PHP-Dateien auf
   Strict-Mode um. Testet, dass alles noch funktioniert.
5. Schreibt ein neues Konsolen-Kommando `php:comparisons`, das die folgenden
   Werte mit dem nicht-strikten Vergleichsoperator `==` vergleicht und in einer
   Tabelle die Ergebnisse "yes" bzw. "no" ausgibt. Benutzt `var_export`, um
   die Werte mit erkennbaren Typen zu erhalten.
    - 0
    - 0.0
    - "0.0"
    - 1
    - 1.0
    - "0"
    - "1"
    - "true"
    - false
    - true
    - null
    - 42
    - "42"
    - "42 cups"

## OOP

### Dinge bauen

Ihr könnt die Aufgaben in diesem Abschnitt entweder so bauen, dass sie nur mit
ASCII-Zeichen umgehen können, oder auch so, dass sie auch UTF-8 können.
Mit UTF-8 ist deutlich kniffliger, aber dafür könnt ihr auch mit Wörterbüchern
arbeiten, die beispielsweise deutsch oder französisch sind, und ihr werdet
einiges über die Arbeit mit UTF-8 in PHP lernen.

1. Schreibt ein Kommando `word:reverse`, das ein Argument erwartet und den
   übergebenen String umdreht.
   Falls das übergebene Wort mit einem Großbuchstaben anfängt, soll das
   erzeugte Wort auch mit einem Großbuchstaben anfangen. (Mehrere Wörter sowie
   Binnenmajuskel braucht das Kommando nicht zu berücksichtigen.)
2. Sorgt dafür, dass die Funktion auch bei Umlauten am Wortanfang die Groß- und
   Kleinschreibung richtig umsetzt.
3. Schreibt ein Kommando `word:sort`, das das übergebene Wort alphabetisch
   sortiert. Aus "hello" wird dann beispielsweise "ehllo". Groß- und
   Kleinschreibung sollen wir bei `word:reverse` funktionieren.
4. Schreibt ein Kommando `anagram:check`, das zwei Wörter erwartet und prüft,
   ob die beiden Wörter Anagramme voneinander sind (unabhängig von der Groß-
   und Kleinschreibung). "Leo" ist beispielsweise ein Anagramm von "Ole".
5. Findet eine Liste aller Wörter einer Sprache als Textdatei im Netz (de_DE,
   en_GB oder en_US oder auch eine andere Sprache) und legt sie im
   Projekt ab.
6. Schreibt ein Kommando `resources:read-words`, das alle Wörter aus der
   Datei ausliest und auf der Konsole ausgibt.
7. Schreibt ein Kommando `palindrome:find-all`, das alle Palindrome in der
   Wortliste findet und auf der Konsole ausgibt.
8. Schreibt ein Kommando `anagram:find-all`, das alle Anagramme in der
   Wortliste findet und ausgibt.

### Die Dinge strukturieren

1. Schaut euch die Doku zu den verschiedenen OOP-Themen an.
2. Überlegt euch auf Papier ein Konzept, wie ihr euren Code mit diesen
   Konzepten überarbeiten könnt, damit ihr weniger Dopplung habt und der Code
   mehr der Absicht hinter dem Code entspricht. Unter anderem sollten die
   Kommando-Klassen auf `Command` enden und die Struktur der Kommandos
   widerspiegeln, also beispielsweise `Command\Hello\GreetCommand` für
   `hello:greet`.
3. Besprecht dieses Konzept mit mir.
4. Setzt dieses Konzept um. Geht dabei kleine Schritte, sodass ihr schnell immer
   wieder korrekt funktionierenden Code habt.

Unter anderen solltet ihr dabei diese Klasse bzw. Methoden haben (alle innerhalb
eures Project-Namespaces):

- `Domain\Model\Word`
- `Word::isPalindrome(): bool`
- `Word::isAnagramOf(Word $word): bool`
- `Domain\Model\WordSet implements \Iterator`
- `File\WordListReader`
- `WordProcessing\AnagramFinder::findAnagrams(Word[] $words): WordSet[]`
- `WordProcessing\PalindromeFinder::findPalindromes(Word[] $words): Word[]`

Hinweis: Die Notation `KlassenName::methodenName()` hier im Pseudo-Code
bedeutet, dass die Klasse `KlassenName` eine Method `methodenName` haben soll.

Hinweis: Die Notation `Word[]` hier im Pseudo-Code funktioniert nicht als
Typ-Deklaration in PHP, sondern nur als PHPDoc-Annotation. Die entsprechende
Typ-Deklaration in PHP wäre `array`.

## Eingebaute Klassen

1. Lest euch die Doku zum `ZipArchive` durch.
2. Packt das Wörterbuch (per Hand) in eine ZIP-Datei.
3. Stellt die Funktionen, die das Wörterbuch lesen, auf das ZIP um.
   Arbeitet zuerst mit einer Variante, die das ZIP in ein Verzeichnis entpackt,
   und stellt dann darauf um, dass die Datei mit den Wörtern direkt aus dem
   ZIP gelesen wird.
4. Überlegt euch eine XML-Struktur, in der man Anagramme aus einer Wortliste
   gut darstellen kann. Besprecht diese Struktur mit mir.
5. Fügt dem Kommando `anagram:find-all` ein optionales Argument hinzu, mit dem
   man angeben kann, in welche Datei das Ergebnis der Suche nach Anagrammen
   geschrieben werden soll. Dies soll dann eine XML-Datei mit der Struktur
   sein, die ihr vorher definiert habt.
6. Fügt zur XML-Struktur den aktuellen Zeitstempel als ISO 8601 hinzu.
   Arbeitet dabei mit der `DateTime`-Klasse.
7. Schaut, ob ihr wieder etwas refactoren solltet. Falls ja, besprecht die
   Änderungen mit mir und setzt sie um.

## Sauber programmieren

1. Lintet den PHP-Code in `src/` und `bin`.
2. Schreibt euch ein Composer-Script `ci:php:lint`, das in diesen beiden
   Ordnern den PHP-Code lintet.
3. Baut einen PHP-Syntaxfehler ein und testet, dass der Linter diesen findet.
4. Überfliegt die Doku zu PHPDoc.
5. Fügt PHPDoc zu eurem Code hinzu, wo die Typ-Deklarationen und die
   Methodennamen nicht schon aussagekräftig genug sind.
6. Lest euch PSR-1 und PSR-2 durch.
7. Installiert in eurem Projekt per Composer (als Development-Abhängigkeit)
   PHP_CodeSniffer.
8. Lasst den Sniffer mit dem PSR-2-Standard auf den Ordnern `src/` und `bin`
   laufen.
9. Schreibt euch ein Composer-Script `ci:php:sniff`, das die beiden Ordner
   mit PHP_CodeSniffer snifft.
10. Behebt alle Warnungen und Fehler, die PHP_CodeSniffer gefunden hat.
11. Kopiert euch die PHP_CodeSniffer-Konfiguration von phpList, ergänzt das
    Composer-Skript entsprechend und schaut, was es jetzt an neuen Warnungen
    gibt.
12. Installiert euch PHP-CS-Fixer (wieder als Development-Abhängigkeit) und
    kopiert euch die PHP-CS-Fixer-Konfiguration von oelib. Schreibt euch ein
    Composer-Skript `php:cs:fix`, das die beiden Ordner fixt.
13. Fixt mit PHP-CS-Fixer möglichst viele Warnungen. Behebt die anderen
    Warnungen manuell.
14. Installiert euch PHPStan, schreibt dafür ein Composer-Skript `ci:php:stan`,
    und arbeitet euch nach und nach durch die Levels, bis ihr alle Warnungen
    behoben habt.
15. Installiert euch Psalm, schreibt dafür ein Composer-Skript `ci:php:psalm`,
    und arbeitet euch nach und nach durch die Levels, bis ihr alle Warnungen
    behoben habt.
16. Installiert euch PHPMD, kopiert euch die Konfiguration von phpList,
    schreibt dafür ein Composer-Skript `ci:php:md`, und behebt alle Warnungen.
17. Schreibt ein Composer-Skript `ci:static`, das alle statischen Analysen
    aufruft.

Ab dieser Stelle gehört es zu allen folgenden Aufgaben, dass ihr euren Code
regelmäßig mit der statischen Analyse prüft und etwaige Warnungen und Fehler
behebt.

## Fehlerbehandlung

1. Geht euren Code durch und ergänzt Fehlerprüfungen an den Stellen, an denen
   Fehler auftreten können. Werft in diesem Fall eine aussagekräftige Exception
   mit einer Nachricht und einem Fehlercode (dem aktuellen
   UNIX-Timestamp in Sekunden).
   Legt für die geworfenen Exceptions auch die nötigen `@throws`-Annotationen
   an.
2. Testet, dass die Exceptions tatsächlich geworfen werden.
3. Wrappt den Code in `console` in ein catch und gebt eine etwaige Exception
   schön auf der Konsole aus.
4. Schreibt eine eigene Exception-Klasse
   `ZipReaderException extends RuntimeException`
   und benutzt diese beim Lesen der ZIP-Datei.
5. Lest euch den PSR-3-Standard durch.
6. Baut die Exceptions so um, dass ihr den Symfony-Console-Logger nutzt. Lasst
   alle Probleme loggen (kleine wie große), werft aber nur dort eine Exception,
   wo das Programm tatsächlich nicht mehr sinnvoll weitermachen kann.
7. Tragt Monolog als Abhängigkeit ein und loggt innerhalb des
   Projektverzeichnisses nach `var/log/error.log` und `var/log/debug.log`
   (mit den entsprechenden Log-Leveln). Loggt jetzt auch die normale Benutzung.
   Schaut euch an, was in beiden Fällen bei welchen Problemen geloggt wird.

## Anonyme Funktionen

1. Lest euch die Doku zu anonymen Funktionen durch.
2. Baut `console` in eine anonyme Funktion um, die ihr entweder direkt ausführt
   oder in einer lokalen Variablen speichert und diese dann ausführt.
3. Schaut die Stellen in eurem Code durch, wo ihr über ein Array iteriert, und
   baut diese auf `array_walk` oder `array_filter` mit Lambdas um, wo es
   inhaltlich sinnvoll ist.

## Low-level-PHP

1. Baut `console` so um, dass ihr ein Array von Klassennamen habt (mit
   `::class`), über die ihr iteriert, um die Kommandos zu instanziieren
   und der Applikation hinzuzufügen.
