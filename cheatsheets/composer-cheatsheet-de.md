# Composer-Cheatsheet

## Installation
Aktuelle PHP-Version: `php --version`

Composer-Download: https://getcomposer.org/

Composer-Version: `composer --version`

Composer-Hilfe: `composer helper (<command>)`

Liste der Composer-Befehle: `composer list`

Composer-Update: `composer selfupdate`

## Grundlagen
Neues Projekt anlegen: `composer init`

Abhängigkeiten installieren: `composer install`

List der installierten Pakete und Versionen: `composer show`

Standard-Ort der installierten Abhängigkeiten: `vendor/`

Standard-Ort des Composer-Autoloaders: `vendor/autoload.php`

## Abhängigkeiten
[Dokumentation von Requirement-Constraints](https://getcomposer.org/doc/articles/versions.md)

Abhängigkeit hinzufügen: `composer require <Paketname>`

Dev-Abhängigkeit hinzufügen: `composer require --dev <Paketname>`

Abhängigkeiten aktualisieren: `composer update`

## Globale Installation
Paket global installieren: `composer global install <Paketname>`

## Weitere Befehle
Neues Projekt aus Paket erstellen: `composer create-project <Paketname>`

Warum ist ein Paket installiert? `composer why <Paketname>`

`composer.json` überprüfen: `composer validate`

Autoloader neu erzeugen: `composer dumpautoload` oder `composer dump-autoload`
