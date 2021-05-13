# Changelog

## v0.8.x

### v0.8.0

> Requires Slevomat coding standards 7.0 or higher

**Added rules:**
 - SlevomatCodingStandard.ControlStructures.RequireNullSafeObjectOperator
 - SlevomatCodingStandard.Exceptions.RequireNonCapturingCatch
 - SlevomatCodingStandard.Functions.RequireTrailingCommaInDeclaration

**Added strict rules:**
 - SlevomatCodingStandard.TypeHints.UnionTypeHintFormat

**Renamed rules:**
 - SlevomatCodingStandard.Functions.TrailingCommaInCall into SlevomatCodingStandard.Functions.**Require**TrailingCommaInCall

## v0.7.x

### v0.7.1

Added support for PHP 8

### v0.7.0

> Requires Slevomat coding standards 6.4 or higher

**Added rules:**
 - SlevomatCodingStandard.Commenting.DeprecatedAnnotationDeclaration
 - SlevomatCodingStandard.ControlStructures.RequireMultiLineCondition
 - SlevomatCodingStandard.Functions.RequireMultiLineCall

**Added strict rules:**
 - SlevomatCodingStandard.ControlStructures.RequireSingleLineCondition
 - SlevomatCodingStandard.Functions.RequireSingleLineCall

 **Removed rule:**
 - SlevomatCodingStandard.Classes.UnusedPrivateElements - Is *deprecated*

## v0.6.x

### v0.6.1

 - Fix typo in `phpcs-slevomat.xml` file
 - Requires higher Slevomat coding standards with fixed bugs

### v0.6.0

> Requires Slevomat coding standards 6.3 or higher

**Added rules:**
 - Generic.Files.InlineHTML
 - Generic.NamingConventions.ConstructorName
 - PEAR.Formatting.MultiLineAssignment
 - SlevomatCodingStandard.Classes.UnusedPrivateElements
 - SlevomatCodingStandard.ControlStructures.DisallowContinueWithoutIntegerOperandInSwitch
 - SlevomatCodingStandard.ControlStructures.NewWithParentheses
 - SlevomatCodingStandard.ControlStructures.RequireMultiLineTernaryOperator
 - SlevomatCodingStandard.Operators.RequireCombinedAssignmentOperator
 - SlevomatCodingStandard.Operators.SpreadOperatorSpacing
 - SlevomatCodingStandard.PHP.ReferenceSpacing
 - SlevomatCodingStandard.PHP.UselessSemicolon
 - SlevomatCodingStandard.PHP.UselessParentheses
 - SlevomatCodingStandard.Variables.DuplicateAssignmentToVariable

**Added strict rules:**
 - Generic.Formatting.SpaceAfterNot
 - SlevomatCodingStandard.Arrays.DisallowImplicitArrayCreation
 - SlevomatCodingStandard.Arrays.SingleLineArrayWhitespace
 - SlevomatCodingStandard.Commenting.ForbiddenAnnotations
 - SlevomatCodingStandard.ControlStructures.AssignmentInCondition
 - SlevomatCodingStandard.ControlStructures.RequireShortTernaryOperator
 - SlevomatCodingStandard.ControlStructures.UselessIfConditionWithReturn
 - SlevomatCodingStandard.ControlStructures.UselessTernaryOperator
 - SlevomatCodingStandard.TypeHints.NullTypeHintOnLastPosition
 - Squiz.PHP.CommentedOutCode

## v0.5.0

> Requires Slevomat coding standards 6.2 or higher

**Added rules:**
- SlevomatCodingStandard.Classes.DisallowMultiConstantDefinition
- SlevomatCodingStandard.Classes.DisallowMultiPropertyDefinition
- SlevomatCodingStandard.Functions.ArrowFunctionDeclaration
- SlevomatCodingStandard.PHP.DisallowDirectMagicInvokeCall
- SlevomatCodingStandard.Variables.DisallowSuperGlobalVariable
- SlevomatCodingStandard.Whitespaces.DuplicateSpaces

---

## v0.4.0 - v0.4.1

**Added rules:**

- SlevomatCodingStandard.Arrays.MultiLineArrayEndBracketPlacement
- SlevomatCodingStandard.Classes.ConstantSpacing
- SlevomatCodingStandard.Classes.ParentCallSpacing
- SlevomatCodingStandard.Classes.PropertySpacing
- SlevomatCodingStandard.Classes.RequireMultiLineMethodSignature
- SlevomatCodingStandard.Classes.RequireSingleLineMethodSignature
- SlevomatCodingStandard.Functions.DisallowEmptyFunction
- SlevomatCodingStandard.Operators.NegationOperatorSpacing

**Removed rule:**
- Squiz.WhiteSpace.MemberVarSpacing

---

## v0.3.x

### v0.3.0

- Added Squiz ArrayDeclaration sniff to check spacing in the array declaration

---

## v0.2.x

### v0.2.1

- Fixed bug - PHP CS Strict disable checking double quotes (#1)
- Fixed bug - Strict Rules conflict (#2)

### v0.2

- Add ruleset for space indentation and tabs indentation

---

## v0.1.x

### v0.1.0

- Initial release of custom ruleset
