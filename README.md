# XML-Parser

1. Parse an XML document. Name of the file to parse should be given as the program argument. Here is an example file:

```xml
  <bookstore>
     <book id="bk111" test="1">
        <author>O'Brien, Tim</author>
        <title>MSXML3: A Comprehensive Guide</title>
        <genre>Computer</genre>
        <price>36.95</price>
        <publish_date>2000-12-01</publish_date>
        <description>The Microsoft MSXML3 parser is covered in
        detail, with attention to XML DOM interfaces, XSLT processing,
        SAX and more.</description>
     </book>
     <book id="bk112">
        <author>Galos, Mike</author>
        <title>Visual Studio 7: A Comprehensive Guide</title>
        <genre>Computer</genre>
        <price>49.95</price>
        <size> 22 </size>
        <publish_date>2001-04-16</publish_date>
        <last_description test="1">Microsoft Visual Studio 7 is explored in depth,
        looking at how Visual Basic, Visual C++, C#, and ASP+ are
        integrated into a comprehensive development
        environment.</last_description>
     </book>
  </bookstore>
```
 
2.  Find all elements with the attribute: test=”1”

```xml
  <bookstore>
     <book id="bk111" test="1">
        <author>O'Brien, Tim</author>
        <title>MSXML3: A Comprehensive Guide</title>
        <genre>Computer</genre>
        <price>36.95</price>
        <publish_date>2000-12-01</publish_date>
        <description>The Microsoft MSXML3 parser is covered in
        detail, with attention to XML DOM interfaces, XSLT processing,
        SAX and more.</description>
     </book>
     <book id="bk112">
        <author>Galos, Mike</author>
        <title>Visual Studio 7: A Comprehensive Guide</title>
        <genre>Computer</genre>
        <price>49.95</price>
        <size> 22 </size>
        <publish_date>2001-04-16</publish_date>
        <last_description test="1">Microsoft Visual Studio 7 is explored in depth,
        looking at how Visual Basic, Visual C++, C#, and ASP+ are
        integrated into a comprehensive development
        environment.
        </last_description>
     </book>
  </bookstore>
```
 
3.  Compress/Decompress the contents of those elements using ‘gzip’, based on the command line options ‘--gzip’ and ‘--gunzip’ respectively. Compression should apply only to those elements – marked with the “test” attribute. The rest of the XML file should remain the same as the original. And the generated file should be still valid XML. Name of the generated file could be hardcoded in the program. For example, the above input could produce:

```xml
  <bookstore>
     <book id="bk111" test="1">
        [[gziped content of the element text. Maybe base64 encoded?]]
     </book>
     <book id="bk112">
        <author>Galos, Mike</author>
        <title>Visual Studio 7: A Comprehensive Guide</title>
        <genre>Computer</genre>
        <price>49.95</price>
        <size> 22 </size>
        <publish_date>2001-04-16</publish_date>
        <last_description test="1">
           [[gziped content of the elment text.  Maybe base64 encoded?]]
        </last_description>
     </book>
  </bookstore>
```

4. It should be possible to get the original document after passing it thought the application twice, first with ‘--gzip’ and then with ‘--gunzip’ arguments.

5. No extra files should be generated by the program. You may use temporary files if you need to, but make sure they are gone by the time the program exits.

6. You may use any extra package and libraries you find useful.

7. It is important that your solution work correctly and adhere to all the requirement.
