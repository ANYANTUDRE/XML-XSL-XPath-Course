# Introduction

## What is XML?
- XML stands for **eXtensible Markup Language** and is much like HTML.
- XML is a software- and hardware-independent tool for **storing and transporting data.**
- XML was designed to be **self-descriptive** and is a **W3C Recommendation**.

### XML does NOT DO anything
Indeed, XML is just information wrapped in tags.
This note is a note to Tove from Jani, stored as XML:
```xml
<note>
  <to>Tove</to>
  <from>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
</note>
```
The XML above has a sender information, a receiver information, a heading and a message body.

### The difference between XML and HTML
XML and HTML were designed with different goals:
- XML was designed to **carry data** - with focus on **what data is**.
- HTML was designed to **display data** - with focus on **how data looks**.


### XML does not use predefined tags
XML tags are **not predefined like HTML tags** are ( e.g., `<p>`, `<h1>`, `<table>` ).
The tags are "invented" by the author of the XML document.

### XML is extensible
Most XML applications will work as expected even if new data is added (or removed).

### XML simplifies things
XML simplifies **data sharing, data transport, platform changes, data availability.**

### XML is a W3C Recommendation


# How Can XML be Used?

- XML **separates data from presentation**: it does not carry any information about how to be displayed.
- XML is often a **complement to HTML**: used to store or transport data, while HTML is used to format and display the same data.
- XML **separates data from HTML**.

## Transaction Data
Thousands of XML formats exist, in many different industries, to describe day-to-day data transactions from financial transactions to medical data and scientific measurements.

#### Example: XML News
XMLNews is a specification for exchanging news and other information.
```xml
<?xml version="1.0" encoding="UTF-8"?>
<nitf>
  <head>
    <title>Colombia Earthquake</title>
  </head>
  <body>
    <headline>
      <hl1>143 Dead in Colombia Earthquake</hl1>
    </headline>
    <byline>
      <bytag>By Jared Kotler, Associated Press Writer</bytag>
    </byline>
    <dateline>
      <location>Bogota, Colombia</location>
      <date>Monday January 25 1999 7:28 ET</date>
    </dateline>
  </body>
</nitf>
```

# XML Tree

## XML Tree Structure
XML documents are formed as **element trees**. 
An XML tree starts at a **root element and branches from the root to child elements.**
All elements can have **sub elements** (child elements):
```xml
<root>
  <child>
    <subchild>.....</subchild>
  </child>
</root>
```
The terms **parent, child, and sibling** are used to describe the relationships between elements.
Parents have children. Children have parents. Siblings are children on the same level (brothers and sisters).
All elements can have **text content and attributes**.

## Example
![](https://www.w3schools.com/xml/nodetree.gif)
The image above represents books in this XML:

```xml
<?xml version="1.0" encoding="UTF-8"
<bookstore>
  <book category="cooking">
    <title lang="en">Everyday Italian</title>
    <author>Giada De Laurentiis</author>
    <year>2005</year>
    <price>30.00</price>
  </book>
  <book category="children">
    <title lang="en">Harry Potter</title>
    <author>J K. Rowling</author>
    <year>2005</year>
    <price>29.99</price>
  </book>
  <book category="web">
    <title lang="en">Learning XML</title>
    <author>Erik T. Ray</author>
    <year>2003</year>
    <price>39.95</price>
  </book>
</bookstore>
```

XML uses a much self-describing syntax.
- A prolog defines the **XML version** and the **character encoding**:
```xml
<?xml version="1.0" encoding="UTF-8"?>
```
- The next line is the **root element** of the document:
```xml
<bookstore>
...
</bookstore>
```
- The `<book>` elements have 4 child elements: `<title>`, `<author>`, `<year>`, `<price>`.


# XML syntax rules
The syntax rules of XML are very simple, logical and easy to learn and use.
- XML Documents must have a **root element** (the parent of all other elements).
- The XML **prolog is optional** but if it exists, it must come first in the document.
- All XML elements must have a **closing tag**.
- XML tags are **case sensitive**.
- XML elements must be **properly nested**
- XML **attribute values must always be quoted.**
- **Entity references:**
    - &lt;	 --> less than
    - &gt;	 --> greater than
    - &amp;	 --> ampersand
    - &apos; --> apostrophe
    - &quot; --> quotation mark
    - 
- **Comments in XML:**
```xml
<!-- This is a comment -->
```
- **White-space is preserved in XML.**
- **XML stores new line as LF (line feed).**

### Well Formed XML
XML documents that conform to the syntax rules above are said to be **"Well Formed" XML documents.**


# XML Elements

## What is an XML Element?
An XML element is everything from (including) the element's start tag to (including) the element's end tag.

```xml
<price>29.99</price>
```
An element can contain:
- text
- attributes
- other elements
- or a mix of the above

## Empty XML Elements
An element with no content is said to be empty.
In XML, you can indicate an empty element like this:
```xml
<element></element>
```
Or use a so called self-closing tag:
```xml
<element />
```

## XML Naming Rules
XML elements must follow these naming rules: Element names 
- are case-sensitive
- must start with a letter or underscore
- cannot start with the letters xml (or XML, or Xml, etc)
- can contain letters, digits, hyphens, underscores, and periods
- cannot contain spaces

**Tip!** Choose your **naming style** (Lower case, Upper case, Snake case, Pascal case or Camel case) and **be consistent about it**!


# XML Attributes
Attributes are designed to contain data related to a specific element.

## XML Attributes Must be Quoted
Attribute values must always be quoted. Either single or double quotes can be used.
For a person's gender, the `<person>` element can be written like this:

```xml
<person gender="female">
```
or like this:
```xml
<person gender='female'>
```
## XML Elements vs. Attributes
Take a look at these two examples:
```xml
<person gender="female">
  <firstname>Anna</firstname>
  <lastname>Smith</lastname>
</person>
```

```xml
<person>
  <gender>female</gender>
  <firstname>Anna</firstname>
  <lastname>Smith</lastname>
</person>
```
In the first example, gender is an attribute. In the last example, gender is an element. Both examples provide the **same information.**

**There are no rules about when to use attributes or when to use elements in XML!**

Some things to consider when using attributes are:
- attributes **cannot contain multiple values** (elements can)
- attributes **cannot contain tree structures** (elements can)
- attributes **are not easily expandable** (for future changes)

## XML Attributes for Metadata
Sometimes ID references are assigned to elements to identify them in much the same way as the id attribute in HTML.  
**Example:**
```xml
<messages>
  <note id="501">
    <to>Tove</to>
    <from>Jani</from>
    <heading>Reminder</heading>
    <body>Don't forget me this weekend!</body>
  </note>
  <note id="502">
    <to>Jani</to>
    <from>Tove</from>
    <heading>Re: Reminder</heading>
    <body>I will not</body>
  </note>
</messages>
```
The id attributes above are for identifying the different notes. It is not a part of the note itself.

**Metadata (data about data) should be stored as attributes, and the data itself should be stored as elements.**

# XML namespaces

## Name conflicts
In XML, element names are defined by the developer. This often results in a conflict when trying to mix XML documents from different XML applications.
For example a `<table>` element may carry HTML table information or a table (a piece of furniture).
If these XML fragments were added together, there would be a name conflict. Both contain a <table> element, but the elements have different content and meaning.

## XML Namespaces - The xmlns Attribute
Name conflicts in XML can easily be avoided using a **name prefix**. When using prefixes in XML, a **namespace** for the prefix must be defined.
The namespace can be defined by an `xmlns` attribute in the start tag of an element.

The namespace declaration has the following syntax. `xmlns:prefix="URI"`.

```xml
<root>

<h:table xmlns:h="http://www.w3.org/TR/html4/">
  <h:tr>
    <h:td>Apples</h:td>
    <h:td>Bananas</h:td>
  </h:tr>
</h:table>

<f:table xmlns:f="https://www.w3schools.com/furniture">
  <f:name>African Coffee Table</f:name>
  <f:width>80</f:width>
  <f:length>120</f:length>
</f:table>

</root>
```
In the example above:
- The xmlns attribute in the first <table> element gives the h: prefix a qualified namespace.
- The xmlns attribute in the second <table> element gives the f: prefix a qualified namespace.
When a namespace is defined for an element, all child elements with the same prefix are associated with the same namespace.

Namespaces can also be declared in the XML root element:
```xml
<root xmlns:h="http://www.w3.org/TR/html4/"
xmlns:f="https://www.w3schools.com/furniture">
```

## Default Namespaces
Defining a default namespace for an element saves us from using prefixes in all the child elements. It has the following syntax:
```xml
xmlns="namespaceURI"
```

## Namespaces in real use
XSLT is a language that can be used to transform XML documents into other formats.
The XML document below, is a document used to transform XML into HTML.

The namespace "http://www.w3.org/1999/XSL/Transform" identifies XSLT elements inside an HTML document:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">

<xsl:template match="/">
<html>
<body>
  <h2>My CD Collection</h2>
  <table border="1">
    <tr>
      <th style="text-align:left">Title</th>
      <th style="text-align:left">Artist</th>
    </tr>
    <xsl:for-each select="catalog/cd">
    <tr>
      <td><xsl:value-of select="title"/></td>
      <td><xsl:value-of select="artist"/></td>
    </tr>
    </xsl:for-each>
  </table>
</body>
</html>
</xsl:template>

</xsl:stylesheet>
```


# Displaying XML
Raw XML files can be viewed in all major browsers but don't expect XML files to be displayed as HTML pages.
### Viewing XML Files
```
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Tove</to>
  <from>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
</note>
```
Look at the XML file above in your browser: [note.xml](Look at the XML file above in your browser: note.xml)

### Viewing an Invalid XML File
If an erroneous XML file is opened, some browsers will report the error, and some will display it, or display it incorrectly.
```
<?xml version="1.0" encoding="UTF-8"?>
<note>
  <to>Tove</to>
  <From>Jani</from>
  <heading>Reminder</heading>
  <body>Don't forget me this weekend!</body>
</note>
```
Try to open the following XML file: [note_error.xml](https://www.w3schools.com/xml/note_error.xml)

### Why Does XML Display Like This?
XML documents **do not carry information about how to display the data.**
Since XML tags are "invented" by the author of the XML document, browsers do not know if a tag like `<table>` describes an HTML table or a dining table.

Without any information about how to display the data, the browsers can just display the XML document as it is.
**Tip:** If you want to style an XML document, use [**XSLT**]().


# XML HttpRequest
All modern browsers have a built-in **XMLHttpRequest** object to request data from a server.

## The XMLHttpRequest object
The XMLHttpRequest object can be used to request data from a web server.
The XMLHttpRequest object is a developers dream, because you can:
- Update a web page without reloading the page
- Request data from a server  - after the page has loaded
- Receive data from a server  - after the page has loaded
- Send data to a server - in the background

## Sending an XMLHttpRequest
A common JavaScript syntax for using the XMLHttpRequest object looks much like this:
```js
var xhttp = new XMLHttpRequest();
xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
       // Typical action to be performed when the document is ready:
       document.getElementById("demo").innerHTML = xhttp.responseText;
    }
};
xhttp.open("GET", "filename", true);
xhttp.send();
```

## Example Explained

The first line in the example above creates an XMLHttpRequest object:
```js
var xhttp = new XMLHttpRequest();
```
The `onreadystatechange` property specifies a function to be executed every time the status of the XMLHttpRequest object changes:
```js
xhttp.onreadystatechange = function()
```
When **readyState** property is 4 and the status property is **200**, the response is ready:
```js
if (this.readyState == 4 && this.status == 200)
```
The **responseText** property returns the server response as a text string.
The text string can be used to update a web page:
```js
document.getElementById("demo").innerHTML = xhttp.responseText;
```


# XML Parser

# XML DOM

# XML and XPath

## What is XPath?
XPath is a major element in the XSLT standard.
XPath can be used to navigate through elements and attributes in an XML document.
- XPath is a syntax for defining parts of an XML document
- XPath uses path expressions to navigate in XML documents
- XPath contains a library of standard functions
- XPath is a major element in XSLT and in XQuery
- XPath is a W3C recommendation

## XPath Path Expressions
XPath uses path expressions to select nodes or node-sets in an XML document. These path expressions look very much like the expressions you see when you work with a traditional computer file system.

XPath expressions can be used in JavaScript, Java, XML Schema, PHP, Python, C and C++, and lots of other languages.

## XPath is Used in XSLT
XPath is a major element in the XSLT standard.

With XPath knowledge you will be able to take great advantage of XSL.

## XPath Example
Considering the following XML document:

```xml
<?xml version="1.0" encoding="UTF-8"?>

<bookstore>

<book category="cooking">
  <title lang="en">Everyday Italian</title>
  <author>Giada De Laurentiis</author>
  <year>2005</year>
  <price>30.00</price>
</book>

<book category="children">
  <title lang="en">Harry Potter</title>
  <author>J K. Rowling</author>
  <year>2005</year>
  <price>29.99</price>
</book>

<book category="web">
  <title lang="en">XQuery Kick Start</title>
  <author>James McGovern</author>
  <author>Per Bothner</author>
  <author>Kurt Cagle</author>
  <author>James Linn</author>
  <author>Vaidyanathan Nagarajan</author>
  <year>2003</year>
  <price>49.99</price>
</book>

<book category="web">
  <title lang="en">Learning XML</title>
  <author>Erik T. Ray</author>
  <year>2003</year>
  <price>39.95</price>
</book>

</bookstore>
```
In the table below we have listed some XPath expressions and the result of the expressions:

| XPath Expression | XPath Expression |
|---------------------------------------|-------------------------------------------------------------------------|
| /bookstore/book[1] | Selects the first book element that is the child of the bookstore element| 
| /bookstore/book[last()]| Selects the last book element that is the child of the bookstore element|
| /bookstore/book[last()-1]| Selects the last but one book element that is the child of the bookstore element|
| /bookstore/book[position()<3] | Selects the first two book elements that are children of the bookstore element | 
| //title[@lang]| Selects all the title elements that have an attribute named lang|
| //title[@lang='en']| Selects all the title elements that have a "lang" attribute with a value of "en"|
| /bookstore/book[price>35.00]| Selects all the book elements of the bookstore element that have a price element with a value greater than 35.00| 
| /bookstore/book[price>35.00]/title| Selects all the title elements of the book elements of the bookstore element that have a price element with a value greater than 35.00|


# XML and XSLT
With XSLT you can transform an XML document into HTML.

## Displaying XML with XSLT
XSLT (eXtensible Stylesheet Language Transformations) is the recommended style sheet language for XML.

XSLT is far more sophisticated than CSS. With XSLT you can add/remove elements and attributes to or from the output file. You can also rearrange and sort elements, perform tests and make decisions about which elements to hide and display, and a lot more.

XSLT uses XPath to find information in an XML document.

## XSLT Example
We will use the following XML document:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<breakfast_menu>

<food>
<name>Belgian Waffles</name>
<price>$5.95</price>
<description>Two of our famous Belgian Waffles with plenty of real maple syrup</description>
<calories>650</calories>
</food>

<food>
<name>Strawberry Belgian Waffles</name>
<price>$7.95</price>
<description>Light Belgian waffles covered with strawberries and whipped cream</description>
<calories>900</calories>
</food>

<food>
<name>Berry-Berry Belgian Waffles</name>
<price>$8.95</price>
<description>Light Belgian waffles covered with an assortment of fresh berries and whipped cream</description>
<calories>900</calories>
</food>

<food>
<name>French Toast</name>
<price>$4.50</price>
<description>Thick slices made from our homemade sourdough bread</description>
<calories>600</calories>
</food>

<food>
<name>Homestyle Breakfast</name>
<price>$6.95</price>
<description>Two eggs, bacon or sausage, toast, and our ever-popular hash browns</description>
<calories>950</calories>
</food>

</breakfast_menu>
```


Use XSLT to transform XML into HTML, before it is displayed in a browser:
```xml
<?xml version="1.0" encoding="UTF-8" ?>
<xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform">
<xsl:template match="/"

<html>
<body style="font-family:Arial;font-size:12pt;background-color:#EEEEEE">
<xsl:for-each select="breakfast_menu/food">
  <div style="background-color:teal;color:white;padding:4px">
    <span style="font-weight:bold"><xsl:value-of select="name"/> - </span>
    <xsl:value-of select="price"/>
    </div>
  <div style="margin-left:20px;margin-bottom:1em;font-size:10pt">
    <p>
    <xsl:value-of select="description"/>
    <span style="font-style:italic"> (<xsl:value-of select="calories"/> calories per serving)</span>
    </p>
  </div>
</xsl:for-each>
</body>
</html>


</xsl:template>
</xsl:stylesheet>
```

If you want to learn more about XSLT, go to our XSLT Tutorial.



