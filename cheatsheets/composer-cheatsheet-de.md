[![oliverklee.de](/images/Logo.svg)](https://www.oliverklee.de/)

# Composer-Cheatsheet

## Installation

|                            | Kommandos                                            |
|----------------------------|------------------------------------------------------|
| Aktuelle PHP-Version       | `php --version`                                      |
| Composer-Download          | [https://getcomposer.org/](https://getcomposer.org/) |
| Composer-Version           | `composer --version`                                 |
| Composer-Hilfe             | `composer help (<command>)`                          |
| Liste der Composer-Befehle | `composer list`                                      |
| Composer-Update            | `composer self-update`                               |

## Grundlagen

|                                                      | Kommandos             |
|------------------------------------------------------|-----------------------|
| Neues Projekt erstellen                              | `composer init`       |
| Abhängigkeiten installieren                          | `composer install`    |
| Installierte Pakete und Versionen anzeigen           | `composer show`       |
| Standardverzeichnis der installierten Abhängigkeiten | `vendor/`             |
| Standardverzeichnis des Composer-Autoloaders         | `vendor/autoload.php` |


## Abhängigkeiten

[Dokumentation von Requirement-Constraints](https://getcomposer.org/doc/articles/versions.md)

|                              | Kommandos                            |
|------------------------------|--------------------------------------|
| Abhängigkeit hinzufügen      | `composer require <Paketname>`       |
| Dev-Abhängigkeit hinzufügen  | `composer require --dev <Paketname>` |
| Abhängigkeiten aktualisieren | `composer update`                    |


## Globale Installation

|                            | Kommando                              |
|----------------------------|---------------------------------------|
| Paket global installieren: | `composer global require <Paketname>` |

## Weitere Befehle

|                                   | Kommandos                                             |
|-----------------------------------|-------------------------------------------------------|
| Neues Projekt aus Paket erstellen | `composer create-project <Paketname>`                 |
| Warum ist ein Paket installiert?  | `composer why <Paketname>`                            |
| `composer.json` überprüfen        | `composer validate`                                   |
| Autoloader neu erzeugen           | `composer dumpautoload` oder `composer dump-autoload` |

## Kleiner Composer-Merksatz

* **Wenn eine composer.lock vorhanden ist** ➡️ `composer install`
* **Wenn keine composer.lock vorhanden ist** ➡️ `composer update`
* **Wenn ein .ddev-Ordner vorhanden ist** ➡️ `ddev composer install` (oder update)
