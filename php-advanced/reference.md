# Reference and examples for advanced PHP

## Project structure

### Directory structure

- [example](https://github.com/phpList/core)
- [reference](https://github.com/php-pds/skeleton)

### Composer

- [Packagist](https://packagist.org/)
- [example](https://github.com/phpList/base-distribution/blob/master/composer.json)
- [reference](https://getcomposer.org/doc/04-schema.md)

### PHP namespaces

- [example](https://github.com/phpList/core/blob/master/src/Domain/Model/Messaging/SubscriberList.php)
- [reference](https://secure.php.net/manual/language.namespaces.php)

### PSR-4 autoloading

- [example](https://github.com/phpList/core/blob/master/composer.json)
- [reference](https://www.php-fig.org/psr/psr-4/)

## Symfony console

- [reference and example for the console component](https://symfony.com/doc/current/components/console.html)
- [reference and example for building a console command](https://symfony.com/doc/current/components/console/single_command_tool.html)

## Strict typing

- [example for type declarations](https://github.com/phpList/core/blob/master/src/Domain/Repository/Identity/AdministratorTokenRepository.php)
- [example for nullable types and void functions](https://git.typo3.org/Packages/TYPO3.CMS.git/blob/HEAD:/typo3/sysext/core/Tests/Unit/TypoScript/Parser/TypoScriptParserTest.php)
- [example for strict mode](https://github.com/phpList/core/blob/master/src/Domain/Model/Messaging/SubscriberList.php)
- [reference for type declarations](https://secure.php.net/manual/functions.arguments.php#functions.arguments.type-declaration)
- [reference for return type declarations](https://secure.php.net/manual/functions.returning-values.php#functions.returning-values.type-declaration)
- [reference for nullable types and void functions](https://secure.php.net/manual/migration71.new-features.php)
- [reference for strict mode](https://secure.php.net/manual/de/migration70.new-features.php)
- [reference for comparison operators](https://secure.php.net/manual/language.operators.comparison.php)
- [reference for var_export](https://secure.php.net/manual/function.var-export.php)

### More Symfony console

- [Blog post 1 about Symfony 4.1 console improvements](https://symfony.com/blog/new-in-symfony-4-1-console-improvements)
- [Blog post 2 about Symfony 4.1 console improvements](https://symfony.com/blog/new-in-symfony-4-1-advanced-console-output)
- [Links to additional console resources](https://symfony.com/doc/current/components/console.html#learn-more)
- [reference for symfony consoles helpers](https://symfony.com/doc/current/components/console/helpers/index.html)
- [reference for tables in the Symfony console](https://symfony.com/doc/current/components/console/helpers/table.html)
- [reference for the progress bar symfony view helper](https://symfony.com/doc/current/components/console/helpers/progressbar.html)
- [Slides for refactoring console applications](https://speakerdeck.com/el_stoffel/better-console-applications?slide=52)

## OOP

- [example for method visibility](https://github.com/phpList/core/blob/master/src/Core/Bootstrap.php)
- [example for abstract classes](https://github.com/phpList/core/blob/master/src/Domain/Repository/AbstractRepository.php)
- [example for interfaces](https://github.com/phpList/core/blob/master/src/Domain/Model/Interfaces/CreationDate.php)
- [example for traits](https://github.com/phpList/core/blob/master/src/Domain/Model/Traits/CreationDateTrait.php)
- [reference for method visibility](https://secure.php.net/manual/language.oop5.visibility.php)
- [reference for abstract classes](https://secure.php.net/manual/language.oop5.abstract.php)
- [reference for interfaces](https://secure.php.net/manual/language.oop5.interfaces.php)
- [reference for traits](https://secure.php.net/manual/language.oop5.traits.php)
- [reference for the Iterator interface](https://secure.php.net/manual/class.iterator.php)
- [post explaining why there should be no "Interface" suffix](https://www.alainschlesser.com/interface-naming-conventions/)
- [another post explaining why there should be no "Interface" suffix](http://verraes.net/2013/09/sensible-interfaces/)

## Build-in classes

### ZipArchive

- [example for reading and writing](https://github.com/oliverklee-de/csv_to_openimmo/blob/master/Classes/Service/Zipper.php)
- [reference](https://secure.php.net/ziparchive)

### DOMDocument

- [example for writing, part 1](https://github.com/oliverklee-de/csv_to_openimmo/blob/master/Classes/Service/OpenImmoBuilder.php)
- [example for writing, part 2](https://github.com/oliverklee-de/csv_to_openimmo/blob/master/Classes/Service/RealtyObjectBuilder.php)
- [reference](https://secure.php.net/DOMDocument)

### DateTime

- [example](https://github.com/phpList/core/blob/master/src/Domain/Model/Identity/AdministratorToken.php)
- [reference](https://secure.php.net/datetime)

## Clean code

- [reference for the PHP command line (including the linter)](https://secure.php.net/manual/features.commandline.options.php)
- [example for PHPDoc](https://github.com/phpList/rest-api/blob/master/src/Controller/SubscriberController.php)
- [reference for PHPDoc](https://manual.phpdoc.org/HTMLSmartyConverter/HandS/phpDocumentor/tutorial_phpDocumentor.howto.pkg.html)
- [PSR-1 reference](https://www.php-fig.org/psr/psr-1/)
- [PSR-2 reference](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md)
- [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)
- [reference for Composer scripts](https://getcomposer.org/doc/articles/scripts.md)
- [example for Composer scripts](https://github.com/MyIntervals/emogrifier/blob/master/composer.json)
- [example (phpList) for a PHP_CodeSniffer configuration](https://github.com/phpList/core/tree/master/config/PhpCodeSniffer)
- [PHP-CS-Fixer](https://github.com/FriendsOfPHP/PHP-CS-Fixer)
- [example (oelib) for a PHP-CS-Fixer configuration](https://github.com/oliverklee-de/oelib/blob/master/Configuration/php-cs-fixer.php)
- [PHPStan](https://github.com/phpstan/phpstan)
- [Psalm](https://github.com/vimeo/psalm)
- [PHPMD](https://github.com/phpmd/phpmd)
- [example (phpList) for a PHPMD configuration](https://github.com/phpList/core/tree/master/config/PHPMD)

## Error handling and logging

- [example for throwing exceptions](https://github.com/phpList/core/blob/master/src/Core/ApplicationKernel.php#L167)
- [example for catching exceptions](https://github.com/phpList/core/blob/master/src/Security/Authentication.php#L67)
- [example for custom exceptions](https://git.typo3.org/Packages/TYPO3.CMS.git/blob/HEAD:/typo3/sysext/core/Classes/Database/Schema/Exception/StatementException.php)
- [reference for exceptions](https://secure.php.net/manual/language.exceptions.php)
- [PhpStorm live template for the current UNIX timestamp](https://twitter.com/oliklee/status/955024213965930497)
- [PSR-3 logging interface standard](https://www.php-fig.org/psr/psr-3/)
- [reference for the Symfony console logger](https://symfony.com/doc/current/components/console/logger.html)
- [Monolog](https://github.com/Seldaek/monolog)
- [Monolog tutorial](https://stackify.com/php-monolog-tutorial/)

## Anonymous functions

- [example for anonymous functions (lamdas)](https://github.com/oliverklee-de/anagram-finder/blob/master/Classes/AnagramFinder.php)
- [example for assigning anonymous functions to variables and immediately executing them](https://github.com/georgringer/news/blob/master/ext_localconf.php)
- [example for immediately executing anonymous functions](https://github.com/helhum/typoscript_rendering/blob/master/ext_localconf.php)
- [example for closures](https://git.typo3.org/Packages/TYPO3.CMS.git/blob/HEAD:/typo3/sysext/frontend/Classes/Resource/FileCollector.php#l214)
- [reference for anonymous functions](https://secure.php.net/manual/functions.anonymous.php)
- [tutorial for anonymous functions](https://www.culttt.com/2013/03/25/what-are-php-lambdas-and-closures/)
- [reference for array_walk](https://secure.php.net/manual/function.array-walk.php)
- [reference for array_filter](https://secure.php.net/manual/function.array-filter.php)
- [tutorial for immediately-invoked function expressions (IIFE) in JavaScript](https://medium.com/@vvkchandra/essential-javascript-mastering-immediately-invoked-function-expressions-67791338ddc6)

## Low-level PHP

- [example for variable class names](https://github.com/phpList/core/blob/master/src/Core/ApplicationKernel.php#L142)
- [reference for variable variables](https://secure.php.net/manual/language.variables.variable.php)
- [example for the
  `__call` magic method](https://git.typo3.org/Packages/TYPO3.CMS.git/blob/HEAD:/typo3/sysext/filelist/Classes/FileFacade.php#l298)
- [reference for magic methods](https://secure.php.net/manual/language.oop5.magic.php)

## Built-in functions

- [example for regular expression matching](https://github.com/oliverklee-de/oelib/blob/master/Classes/AbstractMailer.php#L132)
- [example for regular expression replacing](https://github.com/oliverklee-de/oelib/blob/master/Classes/DataMapper.php#L1010)
- [reference for regular expression functions](https://secure.php.net/manual/ref.pcre.php)
- [example for using a stream handler](https://github.com/Nimut/testing-framework#database-fixtures)
- [example for defining a stream handler](https://github.com/Nimut/testing-framework/blob/master/src/TestingFramework/File/NtfStreamWrapper.php)
- [reference for streams](https://secure.php.net/manual/book.stream.php)
- [example for reading CSV files](https://github.com/oliverklee-de/csv_to_openimmo/blob/master/Classes/Service/CsvReader.php#L139)
- [reference for reading CSV files](https://secure.php.net/manual/function.fgetcsv.php)
