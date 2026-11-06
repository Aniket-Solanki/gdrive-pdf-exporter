# Google Drive PDF Exporter

> **Note**: This is a fork of [GerardCB/gdrive-pdf-exporter](https://github.com/GerardCB/gdrive-pdf-exporter) with local modifications. Original license: MIT.

A browser (JavaScript) console script to export Google Drive documents when the download option is disabled. The resulting documents are optimized, high-quality PDFs with working hyperlinks.

## Disclaimer

**This script is intended for personal use only.** Only use it on documents you own or have explicit permission to download.

## What It Does

When you open a Google Drive document (PDF, presentation, etc.) that has downloads disabled, this script:

1. Captures all visible page images at high resolution
2. Extracts clickable hyperlinks from the document
3. Generates an optimized PDF with custom page sizes (no white margins)
4. Adds working hyperlinks to the PDF
5. Compresses the output for reasonable file sizes
6. Downloads the resulting PDF

## Prerequisites

- Google Chrome browser (recommended) or any Chromium-based browser
- The document must be viewable in Google Drive (you need viewing permissions)

## How to Use

### Step 1: Open the Document

Navigate to the Google Drive document you want to export and ensure it's fully loaded in the preview. **Scroll through the entire document** to ensure all pages are loaded.

### Step 2: Open Developer Console

- **Windows/Linux**: Press `F12` or `Ctrl + Shift + J`
- **Mac**: Press `Cmd + Option + J`

### Step 3: Paste and Run the Script

Copy the entire script below, paste it into the console, and press `Enter`.

The full script is available in the repository. See `script.js` for the complete extractor.

### Step 4: Download

The PDF will automatically download using the original document name from Google Drive (or `document.pdf` if the name cannot be extracted).

## Tips for Better Quality

1. **Scroll through the entire document first** to ensure all pages are loaded
2. **Zoom in** before running the script - Drive loads higher resolution images at higher zoom levels (try 150% or 200%)
3. **Wait for loading** - Make sure all page thumbnails have finished loading
4. **Check console logs** - The script outputs resolution info for each page

## Troubleshooting

### Script doesn't run
- Check for any console messages asking to type a specific command to allow pasting code into the console
- Make sure you copied the entire script
- Check if the browser console shows any error messages
- Try refreshing the page and running again

### Output only contains the first few pages of the original document
- Scroll through all pages first to load the images. Ensure they are fully loaded and visible before running the script
- Try refreshing the page and waiting for it to fully load

### "No images found!" alert
- Make sure you're on a Google Drive document preview page (not the file list)
- Scroll through all pages first to load the images. Ensure they are fully loaded and visible before running the script
- Try refreshing the page and waiting for it to fully load

### Low quality output
- Zoom in to 150-200% before running the script
- Scroll through all pages to force Drive to load higher resolution images
- The quality is limited by what Google Drive serves in the browser

## Technical Details

- Uses jsPDF 2.5.1 for PDF generation with compression
- Captures images at native resolution (naturalWidth/Height)
- JPEG quality set to 0.92 (optimized for quality vs file size)
- Extracts and preserves clickable hyperlinks
- Custom page sizing prevents white margins
- 72 DPI conversion for optimal print quality

## Limitations

- Only captures what's visible in the browser (limited by Drive's image serving)
- Text is rasterized (not selectable in the PDF)
- Quality depends on Google Drive's image resolution

## License

MIT License - Use at your own risk and responsibility.
