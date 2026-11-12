A scanner front-end to efficiently scan several multi-page documents.

For each document, enter a name, then feed pages to the scanner one at a time.
scanloop keeps scanning a page whenever the scanner is ready; press Ctrl+C when
the document is done. The pages are merged into `NAME/NAME.pdf`, which opens
in a PDF viewer, and scanloop asks for the next document's name (`q` to quit).

Requirements:

- A scan command that writes one page to stdout: `scanimage` (from SANE,
  `$ sudo apt install sane-utils`) or Epson's `imagescan` are detected
  automatically. scanimage is run with sudo. To use another, pass `--scan-cmd`
  or set `SCAN_CMD`.
- ImageMagick's `convert` (`$ sudo apt install imagemagick`). On Debian and
  Ubuntu, ImageMagick's default security policy blocks writing PDFs; to allow
  it, remove or comment out the `pattern="PDF"` line in
  `/etc/ImageMagick-6/policy.xml`.

To install:

`$ pip install scanloop`

To run:

`$ scanloop`

See `scanloop --help` for options, such as the output quality and format.
