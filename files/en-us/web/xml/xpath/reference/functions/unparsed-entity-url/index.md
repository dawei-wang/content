---
title: unparsed-entity-url
slug: Web/XML/XPath/Reference/Functions/unparsed-entity-url
page-type: xpath-function
sidebar: xmlsidebar
---

The `unparsed-entity-url()` function returns the URI of the unparsed entity with the given name. This is non-XML data referenced in the DTD of the source document.

## Syntax

```plain
string unparsed-entity-url(string)
```

### Parameters

The name of the unparsed entity. If the argument is not a string, it is converted using the rules of the string() function. The name should be an XML Name.

### Return value

The URI of the unparsed entity retrieved from the DTD, if it exists. Otherwise an empty string.

## Specifications

[XSLT 1.0 12.4](https://www.w3.org/TR/xslt-10/#function-unparsed-entity-uri)

## Gecko support

Not supported.
