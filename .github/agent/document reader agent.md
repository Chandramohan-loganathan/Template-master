## UNIVERSAL DOCUMENT LAYOUT RECONSTRUCTION (MANDATORY)

The source document may be a:

* Banking Form
* Legal Agreement
* Letter
* Application Form
* Undertaking
* Declaration
* Sanction Letter
* Proprietorship Letter
* Promissory Note
* Any other structured document

Do not assume a fixed layout.

Instead, detect and reconstruct the visual layout of the source document.

### VISUAL-FIRST RECONSTRUCTION RULE

Treat every document as a visual page.

Do NOT treat the document as plain text.

Do NOT generate HTML directly from extracted text.

Before generating HTML:

1. Analyze the visual layout.
2. Identify all page regions.
3. Identify side-by-side sections.
4. Identify headers, footers, tables and signature blocks.
5. Reconstruct the layout using CKEditor-safe HTML.

Visual appearance takes precedence over text extraction order.

---

### PAGE REGION DETECTION

Identify the following regions whenever present:

* Top Left

* Top Center

* Top Right

* Middle Left

* Middle Center

* Middle Right

* Bottom Left

* Bottom Center

* Bottom Right

Examples:

Top Right:

* Form Number
* Document Code
* Reference Number

Top Center:

* Document Title
* Agreement Name
* Letter Heading

Middle Left:

* Customer Information
* Borrower Information
* Address Information

Middle Right:

* Date
* Place
* Branch Information
* Photo Box
* Signature Box

Bottom Right:

* Yours Faithfully
* Authorized Signatory
* Borrower Signature
* Proprietor Signature

Preserve the original visual location.

---

### COLUMN DETECTION RULE

If the source document visually contains multiple columns:

Example:

From:                       Residential Address

Customer Name               Customer Address

Date                        Place

Do NOT convert into:

From:
Residential Address

Customer Name
Customer Address

Date
Place

Instead preserve the columns using tables.

Example structure:

<table style="width:100%; border-collapse:collapse;">
<tr>
<td style="width:50%; vertical-align:top;">
Left Content
</td>
<td style="width:50%; vertical-align:top;">
Right Content
</td>
</tr>
</table>

This rule is mandatory.

---

### WORD DOCUMENT RECONSTRUCTION RULE

Many Word documents use:

* Tab Stops
* Right Tabs
* Left Tabs
* Center Tabs
* Invisible Tables
* Indentation
* Section Formatting

These elements are often lost during text extraction.

The converter must reconstruct these layouts using HTML tables and CSS alignment.

If content appears aligned in separate visual columns, recreate those columns using tables.

Never flatten structured content into paragraphs.

---

### VISUAL POSITION PRESERVATION RULE

For every visible element determine:

* Horizontal Position
* Vertical Position
* Alignment
* Relative Position

Preserve:

* Left aligned content
* Right aligned content
* Center aligned content
* Side-by-side sections
* Date and Place positioning
* Signature positioning
* Witness positioning
* Photo boxes
* Seal boxes
* Border boxes
* Form fields

Never rely on:

* Multiple spaces
* Tabs
*  
* Text extraction order

Always use structural HTML.

---

### FORM FIELD RECONSTRUCTION RULE

For dotted lines, blank fields and placeholders:

Preserve them exactly as shown.

Examples:

Name ....................................

Address ....................................

Date ....................................

Do not shorten them.

Do not replace them.

Do not convert them into variables.

Do not convert them into form inputs unless the source document contains actual form controls.

---

### DOCUMENT COMPARISON VALIDATION

Before returning HTML compare the generated layout against the source document.

Verify:

✓ Header position matches source

✓ Title position matches source

✓ Left column position matches source

✓ Right column position matches source

✓ Date position matches source

✓ Place position matches source

✓ Signature position matches source

✓ Witness position matches source

✓ Tables preserved

✓ Side-by-side sections preserved

✓ Paragraph spacing preserved

✓ Visual hierarchy preserved

✓ Closing block remains aligned correctly

If any of the above fails, rebuild the layout before generating final HTML.

---

### FINAL VISUAL REQUIREMENT

The generated HTML must look like the original document when viewed in:

* CKEditor
* Browser Preview
* Print Preview

The document should resemble the original page layout, not a sequence of paragraphs.

When there is a conflict between:

1. Extracted Text Order
2. Visual Layout

Always follow the Visual Layout.
