# Introduction

## What is XML?
- XML stands for **eXtensible Markup Language** much like HTML.
- XML is a software- and hardware-independent tool for **storing and transporting data.**
- XML was designed to be **self-descriptive** and is a **W3C Recommendation**.

## XML Does Not DO Anything
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
The XML above is quite self-descriptive. It has a sender information, a receiver information, a heading and a message body.

## The difference between XML and HTML

XML and HTML were designed with different goals:
- XML was designed to **carry data** - with focus on what data is.
- HTML was designed to **display data** - with focus on how data looks.


## XML does not use predefined tags
XML tags are **not predefined like HTML tags** are.
The tags in the example above (like <to> and <from>) are not defined in any XML standard. These tags are "invented" by the author of the XML document.

HTML works with predefined tags like <p>, <h1>, <table>, etc.

## XML is Extensible
Most XML applications will work as expected even if new data is added (or removed).

## XML simplifies things
XML simplifies **data sharing, data transport, platform changes, data availability.**

## XML is a W3C Recommendation

# How Can XML be Used?

- XML **separates data from presentation**: it does not carry any information about how to be displayed
- XML is often a **complement to HTML**: store or transport data, while HTML is used to format and display the same data.
- XML **separates data from HTML**.

## Transaction Data
Thousands of XML formats exist, in many different industries, to describe day-to-day data transactions from financial transactions to medical data and scientific measurements.

### Example: XML News
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
```
- The <book> elements have 4 child elements: <title>, <author>, <year>, <price>.


# XML Syntax Rules
The syntax rules of XML are very simple and logical. The rules are easy to learn, and easy to use.
- XML Documents Must Have a Root Element (the parent of all other elements)
- The XML Prolog is optional but If it exists, it must come first in the document.
- All XML Elements Must Have a Closing Tag
- XML Tags are **Case Sensitive**
- XML Elements Must be **Properly Nested**
- XML Attribute Values Must Always be Quoted
- Entity References:
    - &lt;		less than
    - &gt;	  greater than
    - &amp;	 	ampersand
    - &apos;	apostrophe
    - &quot;	quotation mark
- Comments in XML
```xml
<!-- This is a comment -->
```
- White-space is Preserved in XML
- XML Stores New Line as LF(line feed)

### Well Formed XML
XML documents that conform to the syntax rules above are said to be "Well Formed" XML documents.
