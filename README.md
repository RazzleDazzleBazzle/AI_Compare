# AI Compare — Privacy Policy & Features

## Privacy Policy

**Effective date:** June 2026  
**Developer:** Darren Wilson

### Summary
AI Compare does not collect, store, transmit, or share any personal data.  
All file processing happens entirely on your device.

### Data Collection
AI Compare collects **no data whatsoever**. Specifically:

- No analytics or telemetry
- No crash reporting sent to external servers
- No advertising identifiers
- No user accounts or registration
- No network requests of any kind

### File Access
The app requests access to files you explicitly select using the system file picker  
or drag-and-drop. Files are read locally for comparison purposes only and are never  
copied, cached beyond the active session, or transmitted anywhere.

### Third-Party SDKs
None. AI Compare has no third-party dependencies.

### Contact
For privacy questions or concerns, open an issue at:  
https://github.com/YOUR_USERNAME/AI_Compare/issues

---

## Features

### Core Comparison
- Side-by-side file diff with line-level change detection
- Myers diff algorithm for small files; optimised linear diff for large files
- Character-level highlighting within changed lines
- Colour-coded changes: red (deleted), green (inserted), yellow (modified)
- Gutter bar indicators for instant visual scanning

### File Format Support
- **Plain text** — `.txt`, `.md`, `.csv`, and any UTF-8 encoded file
- **Source code** — Swift, Python, JavaScript, TypeScript, HTML, CSS, JSON, XML, YAML, Shell, C, C++
- **JSON** — automatically pretty-printed and key-sorted before diffing, making minified JSON fully comparable
- **PDF** — text extraction via PDFKit; falls back to image render for scanned/image-only PDFs
- **Word documents** — `.docx` text extraction without requiring Microsoft Word
- **Images** — side-by-side visual comparison with pixel-level difference overlay

### Large File Handling
- Long lines (minified files, base64 blobs) are soft-wrapped at 200 characters for readability
- Files over 3,000 combined lines use an O(N) hash-based diff to stay responsive
- Character-level diff is skipped for lines over 500 characters to maintain performance

### Navigation
- Previous / Next difference buttons with position counter (e.g. "3 / 12")
- Scroll jumps directly to the selected difference in both panes simultaneously

### Display
- Synchronized scrolling — both panes scroll together vertically
- Independent horizontal scrolling per pane to inspect long lines
- Line number toggle
- Adjustable font size (9pt – 24pt monospaced)
- Customisable highlight colour via colour picker
- Full dark mode support
- No scroll bounce — horizontal scroll stops cleanly at content edges

### Platform Support
- **iPad** — side-by-side layout, optimised for large screen
- **iPhone** — tabbed layout switching between File A and File B
- **Mac (Designed for iPad / Native)** — side-by-side layout with AppKit scroll views

### Performance
- Diff computed on a background thread — UI stays responsive during calculation
- UITableView / NSTableView row virtualisation — thousands of lines scroll smoothly
- Lazy attributed string rendering — no upfront allocation cost for large files
