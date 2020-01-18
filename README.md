# PHP CodeSniffer - Custom standard ruleset

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

There is no really good documentation for sniffs. I wrote one sentence explanation for each used sniff into XML files.

### Generic (34 sniffs)
 - Generic.Arrays.ArrayIndent
 - Generic.Arrays.DisallowLongArraySyntax
 - Generic.Classes.DuplicateClassName
 - Generic.CodeAnalysis.AssignmentInCondition
 - Generic.CodeAnalysis.EmptyStatement
 - Generic.CodeAnalysis.ForLoopShouldBeWhileLoop
 - Generic.CodeAnalysis.UnconditionalIfStatement
 - Generic.CodeAnalysis.UnnecessaryFinalModifier
 - Generic.CodeAnalysis.UselessOverridingMethod
 - Generic.Commenting.DocComment
 - Generic.ControlStructures.InlineControlStructure
 - Generic.Files.ByteOrderMark
 - Generic.Files.LineEndings
 - Generic.Files.LineLength
 - Generic.Formatting.DisallowMultipleStatements
 - Generic.Formatting.NoSpaceAfterCast
 - Generic.Functions.FunctionCallArgumentSpacing
 - Generic.NamingConventions.UpperCaseConstantName
 - Generic.PHP.CharacterBeforePHPOpeningTag
 - Generic.PHP.DeprecatedFunctions
 - Generic.PHP.DisallowAlternativePHPTags
 - Generic.PHP.DisallowShortOpenTag
 - Generic.PHP.ForbiddenFunctions
 - Generic.PHP.LowerCaseConstant
 - Generic.PHP.LowerCaseKeyword
 - Generic.PHP.LowerCaseType
 - Generic.PHP.NoSilencedErrors
 - Generic.Strings.UnnecessaryStringConcat
 - Generic.WhiteSpace.ArbitraryParenthesesSpacing
 - Generic.WhiteSpace.DisallowSpaceIndent - *Depends on selected indentation configuration*
 - Generic.WhiteSpace.DisallowTabIndent - *Depends on selected indentation configuration*
 - Generic.WhiteSpace.IncrementDecrementSpacing
 - Generic.WhiteSpace.LanguageConstructSpacing
 - Generic.WhiteSpace.ScopeIndent
 - Generic.WhiteSpace.SpreadOperatorSpacingAfter

### PEAR (4 sniffs)
 - PEAR.Commenting.FunctionComment
 - PEAR.Commenting.InlineComment
 - PEAR.Functions.ValidDefaultValue
 - PEAR.WhiteSpace.ObjectOperatorIndent

### PSR1 (3 sniffs)
 - PSR1.Classes.ClassDeclaration
 - PSR1.Files.SideEffects
 - PSR1.Methods.CamelCapsMethodName

### PSR12 (16 sniffs)
 - PSR12.Classes.AnonClassDeclaration
 - PSR12.Classes.ClassInstantiation
 - PSR12.Classes.ClosingBrace
 - PSR12.ControlStructures.BooleanOperatorPlacement
 - PSR12.ControlStructures.ControlStructureSpacing
 - PSR12.Files.DeclareStatement
 - PSR12.Files.FileHeader
 - PSR12.Files.ImportStatement
 - PSR12.Files.OpenTag
 - PSR12.Functions.NullableTypeDeclaration
 - PSR12.Functions.ReturnTypeDeclaration
 - PSR12.Keywords.ShortFormTypeKeywords
 - PSR12.Namespaces.CompoundNamespaceDepth
 - PSR12.Operators.OperatorSpacing
 - PSR12.Properties.ConstantVisibility
 - PSR12.Traits.UseDeclaration

### PSR2 (12 sniffs)
 - PSR2.Classes.ClassDeclaration
 - PSR2.Classes.PropertyDeclaration
 - PSR2.ControlStructures.ControlStructureSpacing
 - PSR2.ControlStructures.ElseIfDeclaration
 - PSR2.ControlStructures.SwitchDeclaration
 - PSR2.Files.ClosingTag
 - PSR2.Files.EndFileNewline
 - PSR2.Methods.FunctionCallSignature
 - PSR2.Methods.FunctionClosingBrace
 - PSR2.Methods.MethodDeclaration
 - PSR2.Namespaces.NamespaceDeclaration
 - PSR2.Namespaces.UseDeclaration

### SlevomatCodingStandard (36 sniffs)
 - SlevomatCodingStandard.Arrays.TrailingArrayComma
 - SlevomatCodingStandard.Classes.DisallowLateStaticBindingForConstants
 - SlevomatCodingStandard.Classes.EmptyLinesAroundClassBraces
 - SlevomatCodingStandard.Classes.ModernClassNameReference
 - SlevomatCodingStandard.Classes.TraitUseSpacing
 - SlevomatCodingStandard.Classes.UselessLateStaticBinding
 - SlevomatCodingStandard.Commenting.EmptyComment
 - SlevomatCodingStandard.Commenting.InlineDocCommentDeclaration
 - SlevomatCodingStandard.Commenting.RequireOneLinePropertyDocComment
 - SlevomatCodingStandard.ControlStructures.EarlyExit
 - SlevomatCodingStandard.ControlStructures.JumpStatementsSpacing
 - SlevomatCodingStandard.ControlStructures.LanguageConstructWithParentheses
 - SlevomatCodingStandard.ControlStructures.RequireNullCoalesceOperator
 - SlevomatCodingStandard.Exceptions.DeadCatch
 - SlevomatCodingStandard.Exceptions.ReferenceThrowableOnly
 - SlevomatCodingStandard.Functions.StaticClosure
 - SlevomatCodingStandard.Functions.TrailingCommaInCall
 - SlevomatCodingStandard.Functions.UnusedInheritedVariablePassedToClosure
 - SlevomatCodingStandard.Namespaces.AlphabeticallySortedUses
 - SlevomatCodingStandard.Namespaces.DisallowGroupUse
 - SlevomatCodingStandard.Namespaces.FullyQualifiedExceptions
 - SlevomatCodingStandard.Namespaces.FullyQualifiedGlobalConstants
 - SlevomatCodingStandard.Namespaces.FullyQualifiedGlobalFunctions
 - SlevomatCodingStandard.Namespaces.NamespaceDeclaration
 - SlevomatCodingStandard.Namespaces.NamespaceSpacing
 - SlevomatCodingStandard.Namespaces.ReferenceUsedNamesOnly
 - SlevomatCodingStandard.Namespaces.RequireOneNamespaceInFile
 - SlevomatCodingStandard.Namespaces.UnusedUses
 - SlevomatCodingStandard.Namespaces.UseDoesNotStartWithBackslash
 - SlevomatCodingStandard.Namespaces.UseSpacing
 - SlevomatCodingStandard.Namespaces.UselessAlias
 - SlevomatCodingStandard.Numbers.DisallowNumericLiteralSeparator
 - SlevomatCodingStandard.PHP.OptimizedFunctionsWithoutUnpacking
 - SlevomatCodingStandard.PHP.ShortList
 - SlevomatCodingStandard.PHP.TypeCast
 - SlevomatCodingStandard.Variables.UnusedVariable

### Squiz (34 sniffs)
 - Squiz.Arrays.ArrayBracketSpacing
 - Squiz.Arrays.ArrayDeclaration
 - Squiz.Classes.ClassFileName
 - Squiz.Classes.SelfMemberReference
 - Squiz.Classes.ValidClassName
 - Squiz.Commenting.DocCommentAlignment
 - Squiz.Commenting.EmptyCatchComment
 - Squiz.Commenting.FunctionComment
 - Squiz.ControlStructures.ControlSignature
 - Squiz.ControlStructures.ForEachLoopDeclaration
 - Squiz.ControlStructures.ForLoopDeclaration
 - Squiz.ControlStructures.LowercaseDeclaration
 - Squiz.Functions.FunctionDeclaration
 - Squiz.Functions.FunctionDeclarationArgumentSpacing
 - Squiz.Functions.LowercaseFunctionKeywords
 - Squiz.Functions.MultiLineFunctionDeclaration
 - Squiz.Operators.ValidLogicalOperators
 - Squiz.PHP.Eval
 - Squiz.PHP.GlobalKeyword
 - Squiz.PHP.Heredoc
 - Squiz.PHP.InnerFunctions
 - Squiz.PHP.LowercasePHPFunctions
 - Squiz.PHP.NonExecutableCode
 - Squiz.Scope.MethodScope
 - Squiz.Scope.StaticThisUsage
 - Squiz.Strings.DoubleQuoteUsage
 - Squiz.WhiteSpace.CastSpacing
 - Squiz.WhiteSpace.ControlStructureSpacing
 - Squiz.WhiteSpace.FunctionSpacing
 - Squiz.WhiteSpace.MemberVarSpacing
 - Squiz.WhiteSpace.ObjectOperatorSpacing
 - Squiz.WhiteSpace.ScopeClosingBrace
 - Squiz.WhiteSpace.ScopeKeywordSpacing
 - Squiz.WhiteSpace.SemicolonSpacing
 - Squiz.WhiteSpace.SuperfluousWhitespace
