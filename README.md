# PHP CodeSniffer - Custom standard ruleset

[![PHP from Packagist](https://img.shields.io/packagist/php-v/arxeiss/coding-standards)](https://packagist.org/packages/arxeiss/coding-standards)
[![Packagist Version](https://img.shields.io/packagist/v/arxeiss/coding-standards)](https://packagist.org/packages/arxeiss/coding-standards)

Custom ruleset for [PHP CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) with [Slevomat sniffs](https://github.com/slevomat/coding-standard). Ruleset is based on **PSR2 + PSR12** with additional rules, more detailed list is below. Ruleset is possible to use with **space indentation** and also **tabs indentation**.

## Installation and running

Install with composer:
```bash
composer require --dev arxeiss/coding-standards
```

and run CodeSniffer
```bash
./vendor/bin/phpcs --standard=./vendor/arxeiss/coding-standards/Rules/phpcs-spaces.xml .
```

### Custom ruleset file

Better way is to create custom file `phpcs.xml`, with content like *phpcs.example.xml*. After that it is possible to run
```bash
./vendor/bin/phpcs --standard=./phpcs.xml
```

> More info about PHP CodeSniffer can be found in the [PHP CS wiki](https://github.com/squizlabs/PHP_CodeSniffer/wiki)

### Groups of sniffs

Package consist of multiple files based on the used sniffs.<br>
There are 3 files basic files including all selected sniffs. Use *phpcs-spaces.xml* or *phpcs-tabs.xml*, not both. Optionally it is possible to add also *phpcs-strict.xml*.

- **phpcs-spaces.xml** - Contains all sniffs with space indentation
- **phpcs-tabs.xml** - Contains all sniffs with tabs indentation
- **phpcs-strict.xml** - Contains extra, more strict rules based on Slevomat rules

It can be handy to not include all sniffs at once, specially when migrating big project. Files above just including these partial files:
- **Parts/phpcs-psr.xml** - PSR2 + PSR12 standards
- **Parts/phpcs-use-spaces.xml** or **Parts/phpcs-use-tabs.xml** - Include only one file on the indentation preferences
- **Parts/phpcs-generic.xml** - Additional Generic rules
- **Parts/phpcs-pear.xml** - Additional PEAR rules
- **Parts/phpcs-squiz.xml** - Additional Squiz rules
- **Parts/phpcs-slevomat.xml** - Selected Slevomat rules

If building own ruleset based on partial files, always use *Parts/phpcs-psr.xml*, then *Parts/phpcs-use-spaces.xml* or *Parts/phpcs-use-tabs.xml*.<br>
Later more additional rules can be added. See *phpcs.example.xml*.

## Included sniffs

See [SniffList](SniffsList.md), I wrote one sentence explanation for each used sniff into XML files.

Also Slevomat rules have some comments about in their repository Readme https://github.com/slevomat/coding-standard

## More suggested

## Check that Namespace matches file structure
This is used from my own blog in Laravel, where main folder `app` is `BlogApp` namespace.

```xml
<rule ref="SlevomatCodingStandard.Files.TypeNameMatchesFileName">
    <properties>
        <property name="rootNamespaces" type="array">
            <element key="app" value="BlogApp"/>
        </property>
    </properties>
</rule>
```

## Since v0.11.0 `mixed` typehint is not required

Explanation can be found here https://github.com/arxeiss/php-coding-standards/pull/6

If you want to force linter to use `mixed` typehint, you can enable by adding this into phpcs.xml file.

```xml
<rule ref="SlevomatCodingStandard.TypeHints.ParameterTypeHint"> <!-- Check correct type hints -->
    <properties>
        <property name="enableMixedTypeHint" value="true"/>
    </properties>
</rule>
<rule ref="SlevomatCodingStandard.TypeHints.PropertyTypeHint"> <!-- Check type hint for class property -->
    <properties>
        <property name="enableMixedTypeHint" value="true"/>
    </properties>
</rule>
<rule ref="SlevomatCodingStandard.TypeHints.ReturnTypeHint"> <!-- Correct return type hint -->
    <properties>
        <property name="enableMixedTypeHint" value="true"/>
    </properties>
</rule>
```
