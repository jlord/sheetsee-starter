# Snippets

Here you'll find code snippets to get you going on some basic Sheetsee elements. The sections correspond to the section comments in `index.html`: HTML, Template, JavaScript.

In the JavaScript portion of the `index.hmtl` you have two `<script>` tags which contain a call to Tabletop.js to fetch your spreadsheet data and then a send that data too function when it's done, this is called the _callback_. It is inside of this callback function, named `myData`, that you'll add the bits of JavaScript in the snippets. For example, if the snippet says `console.log("Hello Y'all!")` then your `index.html`'s section should become this:

```JavaScript
document.addEventListener('DOMContentLoaded', function() {
  var URL = "YOURSPREADSHEETSKEYHERE"
  Tabletop.init( { key: URL, callback: myData, simpleSheet: true } )
})

function myData(data) {
  console.log("Hello Y'all!")
} 
```

## Add a Table

_HTML_

```HTML
<div id="table"></div>
<input id="table-filter" type="text"></input>
```

_Template_

_A template for a simple table with column headers that are sortable and a search box. Replace the content in {{}} with a column header from your spreadsheet._

```HTML
<script text="text/javascript" id="table-templ">
  <table>
    <th><tr>
      <td class="tHeader">COLUMN HEADER</td><td class="tHeader">COLUMN HEADER</td><td class="tHeader">COLUMN HEADER</td>
    </tr></th>
    <tbody><tr>
      <td>{{REPLACE}}</td><td>{{REPLACE}}</td><td>{{REPLACE}}</td>
    </tr></tbody>
  </table>
</script>
```

_JavaScript_

Add this inside of the call back function two `<script>` tags that contain your tabletop

```JavaScript
var tableOpts = {
                  "data": data,
                  "pagination": 10,
                  "tableDiv": "#table",
                  "filterDiv": "#table-filter",
                  "templateID": "table-templ"
                  }
Sheetsee.makeTable(tableOpts)
Sheetsee.initiateFilter(tableOpts)
```

_CSS_

_Add these styles to your `css/style.css` file to style the sortable table headers and pagination elements._

```CSS
#Pagination {background: #eee;}
.pagination-next, .pagination-pre {cursor: pointer;}
.no-pag {color: #acacac;}

.tHeader {
  cursor: pointer;
}

.tHeader::after {
  content: " \25BC";
  font-size: 10px;
  padding-left: 3px;
}
```

