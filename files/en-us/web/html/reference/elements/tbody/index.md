---
title: "<tbody>: The Table Body element"
slug: Web/HTML/Reference/Elements/tbody
page-type: html-element
browser-compat: html.elements.tbody
---

{{HTMLSidebar}}

The **`<tbody>`** [HTML](/en-US/docs/Web/HTML) element encapsulates a set of table rows ({{HTMLElement("tr")}} elements), indicating that they comprise the body of a table's (main) data.

{{InteractiveExample("HTML Demo: &lt;tbody&gt;", "tabbed-taller")}}

```html interactive-example
<table>
  <caption>
    Council budget (in £) 2018
  </caption>
  <thead>
    <tr>
      <th scope="col">Items</th>
      <th scope="col">Expenditure</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row">Donuts</th>
      <td>3,000</td>
    </tr>
    <tr>
      <th scope="row">Stationery</th>
      <td>18,000</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <th scope="row">Totals</th>
      <td>21,000</td>
    </tr>
  </tfoot>
</table>
```

```css interactive-example
thead,
tfoot {
  background-color: #2c5e77;
  color: #fff;
}

tbody {
  background-color: #e4f0f5;
}

table {
  border-collapse: collapse;
  border: 2px solid rgb(140 140 140);
  font-family: sans-serif;
  font-size: 0.8rem;
  letter-spacing: 1px;
}

caption {
  caption-side: bottom;
  padding: 10px;
}

th,
td {
  border: 1px solid rgb(160 160 160);
  padding: 8px 10px;
}

td {
  text-align: center;
}
```

## Attributes

This element includes the [global attributes](/en-US/docs/Web/HTML/Reference/Global_attributes).

### Deprecated attributes

The following attributes are deprecated and should not be used. They are documented below for reference when updating existing code and for historical interest only.

- `align` {{deprecated_inline}}

  - : Specifies the horizontal alignment of each body cell. The possible {{Glossary("enumerated")}} values are `left`, `center`, `right`, `justify`, and `char`. When supported, the `char` value aligns the textual content on the character defined in the [`char`](#char) attribute and on offset defined by the [`charoff`](#charoff) attribute. Use the {{cssxref("text-align")}} CSS property instead, as this attribute is deprecated.

- `bgcolor` {{deprecated_inline}}

  - : Defines the background color of each body cell. The value is an HTML color; either a [6-digit hexadecimal RGB code](/en-US/docs/Web/CSS/hex-color), prefixed by a `#`, or a [color keyword](/en-US/docs/Web/CSS/named-color). Other CSS {{cssxref("color_value", "&lt;color&gt;")}} values are not supported. Use the {{cssxref("background-color")}} CSS property instead, as this attribute is deprecated.

- `char` {{deprecated_inline}}

  - : Specifies the alignment of the content to a character of each body cell. Typical values for this include a period (`.`) when attempting to align numbers or monetary values. If [`align`](#align) is not set to `char`, this attribute is ignored.

- `charoff` {{deprecated_inline}}

  - : Specifies the number of characters to offset the body cell content from the alignment character specified by the [`char`](#char) attribute.

- `valign` {{deprecated_inline}}

  - : Specifies the vertical alignment of each body cell. The possible {{Glossary("enumerated")}} values are `baseline`, `bottom`, `middle`, and `top`. Use the {{cssxref("vertical-align")}} CSS property instead, as this attribute is deprecated.

## Usage notes

- The `<tbody>` is placed after any {{HTMLElement("caption")}}, {{HTMLElement("colgroup")}}, and {{HTMLElement("thead")}} elements.
- If {{HTMLElement("tr")}} elements are specified as direct children of the {{HTMLElement("table")}} (see "tag omission" in the [technical summary](#technical_summary) for a description of when this is valid), then the markup generated by the browser will include a `<tbody>` element that encapsulates them. As a result, CSS selectors such as `table > tr` will not select these elements. See also the [Not specifying a body](#not_specifying_a_body) example.
- It's permitted to use more than one `<tbody>` per table as long as they are all consecutive. This allows to divide the rows ({{HTMLElement("tr")}} elements) in large tables into sections, each of which may be separately formatted if so desired. If not marked up to be consecutive elements, browsers will correct this author error, ensuring any {{HTMLElement("thead")}} and {{HTMLElement("tfoot")}} elements are rendered as the first and last elements of the table, respectively.
- Along with its related {{HTMLElement("thead")}} and {{HTMLElement("tfoot")}} elements, the `<tbody>` element provides useful {{Glossary("semantics", "semantic")}} information and can be used when rendering for either screen or print. Specifying such table content groups also provides valuable contextual information for assistive technologies, including screen readers and search engines.
- When printing a document, in the case of a multipage table, the {{HTMLElement("thead")}} and {{htmlelement("tfoot")}} elements usually specify information that remains the same—or at least very similar—on each page, while the `<tbody>` element's contents generally will differ from page to page.
- When a table is presented in a screen context (such as a window) that is not large enough to display the entire table, the {{Glossary("user agent")}} may let the user scroll the contents of the {{HTMLElement("thead")}}, `<tbody>`, {{htmlelement("tfoot")}}, and {{HTMLElement("caption")}} blocks separately from one another for the same parent {{htmlelement("table")}}.

## Examples

See {{HTMLElement("table")}} for a complete table example introducing common standards and best practices.

### Not specifying a body

This example demonstrates that the browser automatically encapsulates {{HTMLElement("tr")}} elements within a `<tbody>` element if the rows are not nested within a table grouping element (`<tbody>`, `<tfoot>`, or `<thead>`) and are, as in this example, the direct children of the {{HTMLElement("table")}} element.

#### HTML

Here, a very basic table with some table rows ({{HTMLElement("tr")}} elements) containing data ({{HTMLElement("td")}} elements) about students is created.

```html
<table>
  <tr>
    <td>3741255</td>
    <td>Jones, Martha</td>
    <td>Computer Science</td>
    <td>240</td>
  </tr>
  <tr>
    <td>3971244</td>
    <td>Nim, Victor</td>
    <td>Russian Literature</td>
    <td>220</td>
  </tr>
  <tr>
    <td>4100332</td>
    <td>Petrov, Alexandra</td>
    <td>Astrophysics</td>
    <td>260</td>
  </tr>
</table>
```

#### CSS

Note the CSS in the example, where a {{cssxref("background-color")}} is specified for the `<tbody>` element and the `tbody` is used as a part of an additional {{Glossary("css_selector", "CSS selector")}}. Alternatively, {{Glossary("developer_tools", "browser developer tools")}} can be used to check the presence of the `<tbody>` element in the {{Glossary("dom", "DOM")}}.

```css
tbody {
  background-color: #e4f0f5;
}

tbody > tr > td:last-of-type {
  width: 60px;
  text-align: center;
}
```

```css hidden
table {
  border-collapse: collapse;
  border: 2px solid rgb(140 140 140);
  font-family: sans-serif;
  font-size: 0.8rem;
  letter-spacing: 1px;
}

td {
  border: 1px solid rgb(160 160 160);
  padding: 8px 10px;
}
```

#### Result

{{EmbedLiveSample("Not_specifying_a_body", 650, 100)}}

### Basic body structure

This example extends and enhances the basic table from the [previous example](#not_specifying_a_body).

#### HTML

We introduce a table head ({{HTMLElement("thead")}} element) and explicitly use a `<tbody>` element to structure the table into {{Glossary("semantics", "semantic")}} sections. The table head contains the column headers ({{HTMLElement("th")}} elements). The `<tbody>` element represents the body section of the table, which contains a number of rows ({{HTMLElement("tr")}} elements) with the table's main data, which is the data of each student.

The use of such table content groups and {{Glossary("semantics", "semantic")}} markup is not only useful for visual presentation (via CSS styling) and contextual information for assistive technologies; moreover, the explicit use of the `<tbody>` element helps the browser to create the intended table structure, avoiding unwanted results.

```html
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
      <th>Major</th>
      <th>Credits</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
      <td>Computer Science</td>
      <td>240</td>
    </tr>
    <tr>
      <td>3971244</td>
      <td>Nim, Victor</td>
      <td>Russian Literature</td>
      <td>220</td>
    </tr>
    <tr>
      <td>4100332</td>
      <td>Petrov, Alexandra</td>
      <td>Astrophysics</td>
      <td>260</td>
    </tr>
  </tbody>
</table>
```

#### CSS

The CSS is nearly unchanged from the [previous example](#not_specifying_a_body), except for some basic styling to highlight the table head so that the headers of the columns stand out from the data in the table body. As in the [example above](#not_specifying_a_body), the `tbody` [type selector](/en-US/docs/Web/CSS/Type_selectors) is used to style the body cells.

```css
tbody {
  background-color: #e4f0f5;
}

tbody > tr > td:last-of-type {
  text-align: center;
}

thead {
  border-bottom: 2px solid rgb(160 160 160);
  background-color: #2c5e77;
  color: #fff;
}
```

```css hidden
table {
  border-collapse: collapse;
  border: 2px solid rgb(140 140 140);
  font-family: sans-serif;
  font-size: 0.8rem;
  letter-spacing: 1px;
}

th,
td {
  border: 1px solid rgb(160 160 160);
  padding: 8px 10px;
}
```

#### Result

{{EmbedLiveSample("Basic_body_structure", 650, 140)}}

### Multiple bodies

This example extends and enhances the table from the [example above](#basic_body_structure) even more by introducing multiple body sections.

Using multiple `<tbody>` elements allows creating row groupings within a table. Each table body can potentially have its own head row or rows; however, _there may only be one {{HTMLElement("thead")}} element per table_! Because of that, {{HTMLElement("tr")}} with {{HTMLElement("th")}} elements can be used to create headers within each `<tbody>`.

#### HTML

Building on the table in the [previous basic example](#basic_body_structure), more students are added and, instead of listing each student's major on each row, the students are grouped by major. Note that each major is enclosed within its own `<tbody>` block, with the first row ({{HTMLElement("tr")}} element) serving as the head of the block, displaying the major title within a {{HTMLElement("th")}} element that uses the [`colspan`](/en-US/docs/Web/HTML/Reference/Elements/th#colspan) attribute to span the header across all three columns of the table. Each remaining row within each major's `<tbody>` represents one student.

```html
<table>
  <thead>
    <tr>
      <th>Student ID</th>
      <th>Name</th>
      <th>Credits</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th colspan="3">Computer Science</th>
    </tr>
    <tr>
      <td>3741255</td>
      <td>Jones, Martha</td>
      <td>240</td>
    </tr>
    <tr>
      <td>4077830</td>
      <td>Pierce, Benjamin</td>
      <td>200</td>
    </tr>
    <tr>
      <td>5151701</td>
      <td>Kirk, James</td>
      <td>230</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th colspan="3">Russian Literature</th>
    </tr>
    <tr>
      <td>3971244</td>
      <td>Nim, Victor</td>
      <td>220</td>
    </tr>
  </tbody>
  <tbody>
    <tr>
      <th colspan="3">Astrophysics</th>
    </tr>
    <tr>
      <td>4100332</td>
      <td>Petrov, Alexandra</td>
      <td>260</td>
    </tr>
    <tr>
      <td>8892377</td>
      <td>Toyota, Hiroko</td>
      <td>240</td>
    </tr>
  </tbody>
</table>
```

#### CSS

Most of the CSS is unchanged. However, a slightly more subtle style is added for header cells contained directly within a `<tbody>` (as opposed to those that reside in the {{HTMLElement("thead")}}). This is used for the headers indicating each table section's corresponding major.

```css
tbody > tr > th {
  border-top: 2px solid rgb(160 160 160);
  border-bottom: 1px solid rgb(140 140 140);
  background-color: #e4f0f5;
  font-weight: normal;
}

tbody {
  background-color: whitesmoke;
}

thead {
  background-color: #2c5e77;
  color: #fff;
}
```

```css hidden
table {
  border-collapse: collapse;
  border: 2px solid rgb(140 140 140);
  font-family: sans-serif;
  font-size: 0.8rem;
  letter-spacing: 1px;
}

th,
td {
  border: 1px solid rgb(160 160 160);
  padding: 6px 8px;
  text-align: left;
}

tbody > tr > td:last-of-type {
  text-align: center;
}
```

#### Result

{{EmbedLiveSample("Multiple_bodies", 650, 300)}}

## Technical summary

<table class="properties">
  <tbody>
    <tr>
      <th scope="row">
        <a href="/en-US/docs/Web/HTML/Guides/Content_categories"
          >Content categories</a
        >
      </th>
      <td>None.</td>
    </tr>
    <tr>
      <th scope="row">Permitted content</th>
      <td>Zero or more {{ HTMLElement("tr") }} elements.</td>
    </tr>
    <tr>
      <th scope="row">Tag omission</th>
      <td>
        A <code>&lt;tbody&gt;</code> element's start tag can be omitted if the first thing inside the <code>&lt;tbody&gt;</code> element is a {{HTMLElement("tr")}} element, and if the element is not immediately preceded by a <code>&lt;tbody&gt;</code>, {{HTMLElement("thead")}}, or {{HTMLElement("tfoot")}} element whose end tag has been omitted. (It can't be omitted if the element is empty.)
        A <code>&lt;tbody&gt;</code> element's end tag can be omitted if the <code>&lt;tbody&gt;</code> element is immediately followed by a <code>&lt;tbody&gt;</code> or {{HTMLElement("tfoot")}} element, or if there is no more content in the parent element.
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted parents</th>
      <td>
        Within the required parent {{ HTMLElement("table") }} element,
        the <code>&lt;tbody&gt;</code> element can be added after any
        {{ HTMLElement("caption") }}, {{HTMLElement("colgroup") }},
        and {{ HTMLElement("thead") }} elements.
      </td>
    </tr>
    <tr>
      <th scope="row">Implicit ARIA role</th>
      <td>
        <code
          ><a href="/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/rowgroup_role"
            >rowgroup</a
          ></code
        >
      </td>
    </tr>
    <tr>
      <th scope="row">Permitted ARIA roles</th>
      <td>Any</td>
    </tr>
    <tr>
      <th scope="row">DOM interface</th>
      <td>{{domxref("HTMLTableSectionElement")}}</td>
    </tr>
  </tbody>
</table>

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Learn: HTML table basics](/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_table_basics)
- {{HTMLElement("caption")}}, {{HTMLElement("col")}}, {{HTMLElement("colgroup")}}, {{HTMLElement("table")}}, {{HTMLElement("td")}}, {{HTMLElement("tfoot")}}, {{HTMLElement("th")}}, {{HTMLElement("thead")}}, {{HTMLElement("tr")}}: Other table-related elements
- {{cssxref("background-color")}}: CSS property to set the background color of each body cell
- {{cssxref("border")}}: CSS property to control borders of body cells
- {{cssxref("text-align")}}: CSS property to horizontally align each body cell content
- {{cssxref("vertical-align")}}: CSS property to vertically align each body cell content
