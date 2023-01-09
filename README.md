# Description

Mr. Data Converter takes CSV or tab-delimited data from a spreadsheet such as Excel and converts it into several web-friendly formats, including JSON and XML.
Use it online here: http://thdoan.github.com/mr-data-converter/

### Modifications to Shan Carter's version

- [Enhancement] added safe header names option
- [Enhancement] added Trac output type (thanks Rednox)
- [Enhancement] added C# output type (DataTable)
- [Enhancement] added ColdFusion output type
- [Enhancement] added Go output type
- [Enhancement] added Lua output types (Dictionary Table, Array Table)
- [Enhancement] added Markdown output type
- [Enhancement] added Perl output type
- [Enhancement] added Rich Text Format (RTF) output type
- [Enhancement] added Wiki output type
- [Enhancement] added XML - Smart output type
- [Enhancement] added YAML output type
- [Enhancement] added auto-select on input focus
- [Enhancement] added input auto-focus on page load
- [Enhancement] added output auto-select on menu selection (conversion)
- [Enhancement] added "Loading..." status for right panel
- [Enhancement] added `CSVParser.escapeText()` to convert common punctuation marks, symbols, and diacritics into HTML entities for HTML and XML outputs
- [Enhancement] added favicons (mobile and desktop)
- [Enhancement] added HTML class name format option
- [Enhancement] overhauled CSS to make layout fluid (no need for 'resize' event handler)
- [Enhancement] improved formatting for HTML class names
- [Enhancement] improved indentation for various output types when whitespace is enabled
- [Enhancement] replaced 'Null' with 'Empty' in ASP / VBScript
- [Enhancement] removed 'useUnderscores' option (unused)
- [Enhancement] removed ActionScript output type as it was redundant with JSON Properties
- [Enhancement] compressed images and optimized code
- [Enhancement] JS files now combined and minified
- [Enhancement] Settings are now saved to local storage
- [Fix] unchecking "Include whitespace" option resulted in invalid ASP/VBScript output
- [Fix] invalid column headers for some output types
- [Fix] column headers containing spaces resulted in invalid key name for ActionScript, incorrect class name for HTML, invalid MySQL definition, invalid attribute name for XML Properties, and invalid tag names for XML Nodes and XML Illustrator
- [Fix] floats without a leading zero were flagged as 'int'
- [Fix] some numbers with a leading zero (e.g., Australia postal code 0800) were not quoted, which resulted in invalid JSON
- [Fix] empty fields were outputted as `null` instead of `""`
- [Fix] JSON Array of Columns, JSON Array of Rows, and JSON Dictionary not outputting null values
- [Fix] tool breaking on non-quoted fields containing double quotes when pasting directly from Excel
- [Fix] text containing double quotes were not escaped in ActionScript, ASP/VBScript, JSON (all types), PHP, Python, Ruby, and XML Properties output
- [Fix] text containing single quotes (apostrophes) were not escaped in MySQL output
- [Fix] data comprising one empty column with header outputs nothing
- [Fix] wrong output when arriving after hitting Back button
- [Fix] incorrect delimiter detection when set to Auto in some cases
- [Fix] incorrect HTML output when first row is not the header
- [Enhancement] new formatting options for XML - Smart output type

### XML - Smart

This output type gives you additional flexibility on how to structure the XML by modifying the column headers.

#### Custom row nodes - node[attribute]

Input:
```
product[product-id]	ean	upc
P6907603	1200102146463	192371146460
P6907903	1200102146470	192371146477
```

Output:
```
<?xml version="1.0" encoding="UTF-8"?>
<products>
  <product product-id="P6907603">
    <ean>1200102146463</ean>
    <upc>192371146460</upc>
  </product>
  <product product-id="P6907903">
    <ean>1200102146470</ean>
    <upc>192371146477</upc>
  </product>
</products>
```

**NOTE:** The modification above only works in the first column.

#### Custom row item container nodes - node[attribute="value"]

Input:
```
product[product-id]	custom-attribute[attribute-id="color"]	custom-attribute[attribute-id="size"]
P6907603	Black	XS
```

Output:
```
<?xml version="1.0" encoding="UTF-8"?>
<products>
  <product product-id="P6907603">
    <custom-attributes>
      <custom-attribute attribute-id="color">Black</custom-attribute>
      <custom-attribute attribute-id="size">XS</custom-attribute>
    </custom-attributes>
  </product>
</products>
```

**NOTE:** The modification above only works in the second and subsequent columns.

### Future plans

- Add more output types
- Add more formatting options for output
