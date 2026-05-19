# ⚡ Tezz - Privacy-First Document & Image Suite

![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E)
![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)
![No Server](https://img.shields.io/badge/Architecture-Serverless-7C3AED?style=for-the-badge)

**Tezz** is a lightning-fast, 100% client-side document and image processing web application. Designed to eliminate the latency and security risks of traditional cloud-based editors, Tezz processes heavy binary files directly in the browser's local RAM. 

**Your data never leaves your screen.**

---

## 🛑 The Problem
Traditional PDF and image editors force users to upload sensitive documents (bank statements, legal contracts, IDs) to remote cloud servers. This introduces three major UX failures:
1. **Privacy Risks:** Users surrender their data to third-party servers.
2. **Upload Latency:** Waiting for 50MB files to upload on slow networks breaks the workflow.
3. **Paywalls:** Essential tools are often locked behind subscriptions after a few uses.

## 💡 The Solution
Tezz leverages **WebAssembly (WASM)** and **Browser-Native Canvas APIs** to shift all computational load to the edge (the user's device). By executing C++ level mathematical models directly in the browser, Tezz offers infinite, instant processing with absolute zero data harvesting.

---

## 🛠️ The 10-Tool Arsenal

### Document Processing
* **Merge PDFs:** Drag-and-drop multiple documents to compile a single, ordered PDF.
* **Compress PDF:** High, Medium, and Low compression tiers using dynamic canvas scaling to preserve vector text legibility while crushing file size.
* **Split PDF:** Extract specific page ranges instantly.
* **Text to PDF:** Generate brand-new documents with automated word-wrapping and mathematical center-alignment.

### AI & Data Extraction
* **✨ AI OCR Scanner:** Uses a localized WebAssembly port of the Tesseract AI engine to extract raw text from flattened images and scanned PDFs. 
* **PDF to Image:** Renders individual PDF pages as high-resolution PNGs (auto-generates ZIP archives for multi-page documents).
* **PDF to Text:** Extracts digital text layers into clean `.TXT` or `.DOC` files.

### Image Utilities
* **Images to PDF:** Batch convert JPG/PNG/WEBP files into a compiled presentation.
* **Image Converter:** Cross-convert between formats with auto-zipping for bulk processing and automatic transparency-flattening for JPGs.
* **Image Compressor:** Smart resolution-scaling to bypass browser limitations on PNG compression.

---

## 🧠 Under the Hood (Technical Architecture)

Tezz is built to survive real-world browser constraints:
* **Memory Management:** Mobile browsers aggressively crash tabs that overload the Canvas API. Tezz features a dynamic scaling clamp (`maxDim = 3500px`) that actively throttles memory usage for massive documents, preventing silent crashes on iOS and Android.
* **Fractional Pixel Rendering:** Integrated `Math.ceil()` logic into the canvas context to eliminate sub-pixel rendering bugs that cause white borders on compressed PDF exports.
* **Asynchronous Blob Streaming:** Replaced legacy `toDataURL` methods with asynchronous `toBlob` data streams to handle ultra-heavy files without freezing the main UI thread.

---

## 🎨 UI / UX Design

Designed with a focus on premium, immersive aesthetics:
* **Dynamic Environmental Theming:** A CSS-variable driven engine that switches between *Midnight Sky* (Deep indigo/space blacks) and *Early Morning Sun* (Dawn whites/sunrise gradients) based on user preference, saved via `localStorage`.
* **Glassmorphism System:** Deep backdrop blurs, subtle border highlights, and floating UI panels.
* **Adaptive Mobile Layout:** Replaces traditional stacked menus with a swipeable, native-app-style horizontal tab bar to maximize touch-targets and screen real estate on phones.

---

## 🚀 How to Run Locally

Tezz requires absolutely zero build steps, node modules, or servers.

1. Clone or download this repository.
2. Double click `index.html` to open it in any modern web browser.
3. Done.

---

## 📚 Core Libraries
Tezz relies on these incredible open-source projects:
* [pdf-lib](https://pdf-lib.js.org/) (Document manipulation)
* [pdf.js](https://mozilla.github.io/pdf.js/) (Mozilla's rendering engine)
* [Tesseract.js](https://tesseract.projectnaptha.com/) (AI OCR Vision)
* [JSZip](https://stuk.github.io/jszip/) (Client-side archiving)
* [SortableJS](https://sortablejs.github.io/Sortable/) (Drag-and-drop physics)

---

**Designed & Engineered by Tejash Raj** *MDes, Indian Institute of Technology (IIT) Guwahati* [View Design Portfolio on Behance](https://www.behance.net/tejashraj)
