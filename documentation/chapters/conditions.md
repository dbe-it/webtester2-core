[Home](../README.md)

# The Conditions Utility Class
The utility class `Conditions` provides several factory methods for creating `Condition` instances.
These are specialized subclasses of Java 8's `Predicate` interface and can be used in the following sub-systems:

- Waiting: `@Wait` and `Wait.until(..)`
- Post Construct Assertions: `@PostConstructMustBe(...)`
- Filtering of `PageFragement` Streams

```java
// ad-hoc finding of page fragments with filter
browser.findMany(".textfield").filter(Conditions.is(Conditions.visible()));
// waiting until a certain condition is met
Wait.until(textField).has(Conditions.text("foo"));
```

## Syntax

Conditions are designed to be readable. They take a lot of inspiration from Hamecrest's `Matcher` and AssertJ's fluent API.
It is generally recommended to use static imports when working with the `Conditions` class.

We provide two kinds of out of the box conditions in the `info.novatec.testit.webtester.conditions` package:

- Syntax operations like `Has`, `Is`, `Not` and `Either` in order to make conditions more readable
- Page fragment conditions like `Attribute`, `Visible`, `Selected` etc.

## List of current Conditions

**Syntax:**

- `Either`
- `Has`
- `Is`
- `Not`

**Page Fragment:**

- `Attribute`
- `AttributeWithValue`
- `Disabled`
- `Editable`
- `Enabled`
- `Interactable`
- `Invisible`
- `Present`
- `PresentAndVisible`
- `ReadOnly`
- `Selected`
- `SelectedIndex`
- `SelectedIndices`
- `SelectedText`
- `SelectedTexts`
- `SelectedValue`
- `SelectedValues`
- `Visible`
- `VisibleTextContains`
- `VisibleTextEquals`

## Examples
```java
// ## Wait API ##
Wait.until(checkbox).is(selected());
 
// ## Ad-Hoc PageObject creation API
browser.findMany(".textfield").filter(is(visible));
```

# Linked Documentation

- [Ad-Hoc Finding of Page Objects](ad-hoc-find.md)
- [Waiting](waiting.md)
