VISUAL POSITIONING EXAMPLE (MANDATORY REFERENCE MODEL)

The following example demonstrates how visual positioning must be interpreted.

This example is a reference model for banking and legal forms.

Do not treat the document as flowing text.

Treat the document as a visual page.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

REFERENCE PAGE LAYOUT

Top Right:

KGB-F-7/480P/SPB

Top Center:

PRONOTE

Upper Left:

Rs. ....................................

Upper Right:

Place: ....................................

Directly Below Place:

Date: ....................................

Middle Section:

On Demand I / We _______________________________________

---

---

Witness Section (Left Side):

WITNESS:

1. ---

2. ---

Photo Box (Right Side):

┌─────────┐
│         │
│ PHOTO   │
│  BOX    │
│         │
└─────────┘

Separator Line:

---

Lower Section:

TAKE DELIVERY LETTER TO DPN

Left Side:

From:

Right Side:

Place: ....................................

Date: ....................................

Bottom Right:

To,

The Manager,

Karnataka Grameena Bank

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

VISUAL POSITIONING RULES

Rule 1

Document reference numbers must remain in the top-right area.

Example:

KGB-F-7/480P/SPB

Alignment:

Right

Position:

Top Right

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 2

Document titles must remain centered.

Example:

PRONOTE

Alignment:

Center

Position:

Top Center

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 3

Amount fields must remain on the left side.

Example:

Rs. ....................................

Position:

Left

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 4

Place fields must remain on the right side.

Example:

Place: ....................................

Position:

Right

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 5

Date fields must appear directly below Place when shown in the source document.

Example:

Place: ....................................

Date: ....................................

Position:

Right Side

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 6

Witness sections must remain on the left side.

Example:

WITNESS:

1. ---

2. ---

Position:

Left Side

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 7

Photo boxes, seal boxes and signature boxes must remain on the right side if they appear on the right side in the source document.

Preserve their relative location.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 8

"From" sections must remain on the left side when displayed on the left side in the source document.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 9

"Place" and "Date" sections within delivery letters must remain on the right side when displayed on the right side in the source document.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Rule 10

"To, The Manager..." blocks must remain positioned in the lower-right area when displayed in the lower-right area in the source document.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

TABLE-BASED POSITIONING RULE

Whenever content appears side-by-side visually:

USE HTML TABLES.

Never use:

display:flex

float

position:absolute

position:relative

position:fixed

CSS Grid

Multiple spaces

Tab characters

Browser-dependent spacing

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

MANDATORY EXAMPLE

If the document visually appears as:

Rs. ....................................

Place: ....................................

Date: ....................................

Generate:

<table style="width:100%;border-collapse:collapse;">
<tr>
<td style="width:50%;vertical-align:top;">
Rs. ....................................
</td>

<td style="width:50%;text-align:right;vertical-align:top;">
Place: ....................................
</td>
</tr>

<tr>
<td></td>

<td style="text-align:right;">
Date: ....................................
</td>
</tr>
</table>

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

VISUAL PRIORITY RULE

The generated HTML must match the visual page layout.

Visual position always overrides:

* OCR order
* Text extraction order
* Paragraph order
* Reading order

If the visual document and extracted text conflict:

Follow the visual document.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

FINAL VISUAL REQUIREMENT

The generated HTML must visually resemble the source document page when rendered in:

* CKEditor
* Browser Preview
* Print Preview

The document should look like the original form, not a collection of paragraphs.

Visual reconstruction is mandatory.
