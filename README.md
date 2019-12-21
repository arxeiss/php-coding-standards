# PHP CodeSniffer - Custom standard ruleset

Custom ruleset for [PHP CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) with [Slevomat sniffs](https://github.com/slevomat/coding-standard).

## Installation and running

Install with composer:
```bash
composer require --dev arxeiss/coding-standards
```

and run CodeSniffer
```bash
./vendor/bin/phpcs --standard=./vendor/arxeiss/coding-standards/Rules/phpcs.xml .
```

### Custom ruleset file

Better way is to create custom file `phpcs.xml`, with content like *phpcs.example.xml*. After that it is possible to run
```bash
./vendor/bin/phpcs --standard=./phpcs.xml
```

> More info about PHP CodeSniffer can be found in the [PHP CS wiki](https://github.com/squizlabs/PHP_CodeSniffer/wiki)

### Groups of sniffs

Package consist of multiple files based on the used sniffs. It can be handy to not include all sniffs at once. Here are possible files
- **Parts/phpcs-psr.xml** - PSR2 + PSR12 standards
- **Parts/phpcs-generic.xml** - Additional Generic rules
- **Parts/phpcs-pear.xml** - Additional PEAR rules
- **Parts/phpcs-squiz.xml** - Additional Squiz rules
- **Parts/phpcs-slevomat.xml** - Selected Slevomat rules
- **phpcs.xml** - Contains all parts listed above
- **phpcs-strict.xml** - Contains extra more strict rules based on Slevomat rules

Always use *Parts/phpcs-psr.xml* with additional rules. See *phpcs.example.xml*.
