# Amaravati — Telugu & English Bilingual Web Page

A lightweight, single-page bilingual website template with **Google Translate** integration for English ↔ Telugu translation and a **custom Telugu font selector**. Built for Andhra Pradesh government web projects.

## Live Demo

Open `index.html` in any browser or deploy to GitHub Pages.
https://moinuxdesigner.github.io/telugu-translate

## Features

- **Language Switching** — Dropdown to switch between English and Telugu using Google Translate
- **Telugu Font Selector** — Choose from 6 popular Telugu Google Fonts:
  - Mandali
  - Noto Sans Telugu
  - Baloo Tammudu 2
  - Suranna
  - Gidugu
  - Anek Telugu
- **Google Translate Bar Hidden** — The default Google Translate toolbar is hidden for a clean UI
- **Always Starts in English** — Clears Google Translate cookie on load to prevent stale Telugu sessions
- **Responsive Design** — Built with Tailwind CSS, works on mobile, tablet, and desktop
- **Zero Build Step** — Single HTML file, no npm/node required

## How to Use

### Quick Start

1. Clone or download this repo:
   ```bash
   git clone https://github.com/moinUXDesigner/amaravati.git
   ```
2. Open `index.html` in a browser
3. Select **తెలుగు** from the language dropdown to translate
4. Pick a Telugu font from the font dropdown that appears

### For Developers — Integrating into Your Project

#### 1. Add Google Fonts to `<head>`
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Mandali&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Telugu:wght@400;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Baloo+Tammudu+2:wght@400;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Suranna&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Gidugu&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Anek+Telugu:wght@100..800&display=swap" rel="stylesheet">
```

#### 2. Add CSS for hiding the translate bar & Telugu font classes
```css
/* Hide Google Translate bar */
.goog-te-banner-frame, body > .skiptranslate {
  display: none !important;
  height: 0 !important;
  visibility: hidden !important;
}
html, body {
  margin-top: 0 !important;
  top: 0 !important;
}

/* Telugu fonts — use !important to override Google Translate inline styles */
body.mandali-regular, body.mandali-regular * {
  font-family: "Mandali", sans-serif !important;
}
/* ... add more font classes as needed */
```

#### 3. Add Language & Font Dropdowns
```html
<select id="lang-select" onchange="onLangChange(this.value)">
  <option value="en">English</option>
  <option value="te">తెలుగు</option>
</select>
<select id="font-select" onchange="setTeluguFont(this.value)" class="hidden">
  <option value="mandali-regular">Mandali</option>
  <!-- add more fonts -->
</select>
```

#### 4. Add the Script
Copy the `<script>` block from `index.html` — it handles:
- Loading Google Translate dynamically
- Clearing the `googtrans` cookie so page defaults to English
- Showing/hiding the font dropdown based on language
- Applying the selected Telugu font with `!important` override

## Tech Stack

- HTML5
- Tailwind CSS (CDN)
- Google Translate Widget
- Google Fonts (Telugu)

## Adding More Telugu Fonts

1. Find a Telugu font on [Google Fonts](https://fonts.google.com/?subset=telugu)
2. Add the `<link>` tag in `<head>`
3. Add a CSS class with `!important`:
   ```css
   body.my-font, body.my-font * {
     font-family: "My Font", sans-serif !important;
   }
   ```
4. Add an `<option>` in the font dropdown
5. Add the class name to the `fontClasses` array in the script

## License

Open source — free to use, modify, and distribute.

## Author

Built by [moinUXDesigner](https://github.com/moinUXDesigner)
