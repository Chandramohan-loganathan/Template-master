# OUTPUT FILES

After generating the HTML source code, automatically create an output file inside:

output/

Output filename:

GENERATED_HTML.txt

Rules:

1. The generated HTML source code must be written entirely into:

   output/GENERATED_HTML.txt

2. The file must contain only the final CKEditor-compatible HTML.

3. Do NOT include:

   * Markdown
   * Explanations
   * Notes
   * Comments
   * JSON
   * Code fences
   * Analysis text

4. The content of GENERATED_HTML.txt must be immediately usable by:

   * CKEditor Source Mode
   * Browser Preview
   * HTML Renderer

5. Whenever a new document is requested:

   * Read the requested file from Documents/
   * Generate the HTML
   * Replace the contents of output/GENERATED_HTML.txt with the latest generated HTML

6. Do not create multiple output files unless explicitly requested.

7. The output folder structure must remain:

   Documents/
   output/
   GENERATED_HTML.txt

8. The final response should return the generated HTML and ensure the same HTML is written into:

   output/GENERATED_HTML.txt

9. If HTML generation fails, do not create a partial file. Regenerate until all validation checks pass.

10. Before saving the file, verify:

✓ HTML is CKEditor compatible

✓ Visual layout matches source document

✓ Tables are preserved

✓ Alignment is preserved

✓ Signature blocks are preserved

✓ Place/Date positioning is preserved

✓ No text added

✓ No text removed

✓ No formatting instructions included

Only after successful validation should the content be written to:

output/GENERATED_HTML.txt
