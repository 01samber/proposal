# Company Proposal Form

A professional, self-contained proposal and estimate form for creating job quotes. Built with HTML, CSS, and JavaScript, it runs in any browser or as a portable Windows desktop app. Export proposals as PDF (via print), PNG image, or plain text—with full narrative support and no backend required.

---

## Features

### Cost & Target Calculation
- **Full Cost (x)** and **Profit % (y)** inputs
- **Target Grand Total** = x × (1 + y/100), displayed in real time
- Validation ensures the proposal grand total matches the target before export

### Work Order & Narrative
- **WO#** field for work order or job ID
- **Narrative** textarea that expands automatically for print/image export—no content is cut off
- Long narratives flow across multiple pages in PDF and display fully in image export

### Incurred Costs
- **Trip** and **Assessment** amounts
- Automatic total calculation

### Labor
- Configurable **Tech $/hr** and **Helper $/hr** (defaults: $75 and $45)
- Add multiple labor days with **+ Add Day**
- Per day: Technicians, Tech Hours, Helpers, Helper Hours
- Remove days as needed
- Tech and helper rates shown in print/export

### Parts & Materials
- Description, quantity, unit price per line
- **+** button to increment quantity
- Add/remove line items dynamically
- Line totals and subtotal calculated automatically

### Tax
- Configurable **Tax Rate** (%)
- Subtotal + Tax = Grand Total
- Required subtotal for markup (hidden in print/export)

### Export Options
| Option | Output | Use Case |
|--------|--------|----------|
| **Print** | PDF (via browser print → Save as PDF) | Formal proposals, email |
| **Image** | PNG file | Quick sharing, screenshots |
| **Text** | `.txt` file | Plain-text backup, notes |

### Print & Export Behavior
- Logo embedded (base64) for reliable display in all exports
- Narrative fully visible—no clipping in PDF or image
- Cost & Target, validation message, and action buttons hidden when printing
- Browser headers/footers (URL, page numbers) removed for clean PDF output

---

## Tech Stack

- **HTML5** – Semantic structure
- **CSS3** – Custom properties, gradients, print media queries
- **JavaScript** – Vanilla JS, no frameworks
- **Bootstrap 5.3** – Layout and components (CDN)
- **html2canvas** – Image export (CDN)
- **Plus Jakarta Sans** – Typography (Google Fonts)
- **Electron** – Desktop app packaging (optional)

---

## Quick Start

### Option 1: Run in Browser
1. Open `index.html` in any modern browser (Chrome, Edge, Firefox)
2. Fill out the form and export as needed

### Option 2: Run as Desktop App
```bash
npm install
npm start
```

### Option 3: Build Portable .exe for USB
```bash
npm install
npm run build
```
The executable is in `dist/Proposal Form 1.0.0.exe`. Copy it to a USB drive—it runs on any Windows PC without installation or Node.js.

---

## Project Structure

```
proposal/
├── index.html          # Main form (HTML, CSS, JS)
├── main.js             # Electron main process
├── package.json        # Dependencies & build config
├── proposal-icon.png   # App icon for desktop build
├── USB-SETUP-GUIDE.txt # Step-by-step USB deployment
├── README.md           # This file
└── .gitignore
```

---

## Build Commands

| Command | Description |
|---------|-------------|
| `npm start` | Run the app in Electron (development) |
| `npm run build` | Build portable Windows .exe |
| `npm run build:installer` | Build Windows installer (.msi) |

---

## USB Deployment

1. **Build** (on a machine with Node.js):
   ```bash
   cd proposal
   npm install
   npm run build
   ```

2. **Copy** `dist/Proposal Form 1.0.0.exe` to your USB drive.

3. **Run** on any Windows laptop: double-click the .exe. No Node.js or other tools required.

See `USB-SETUP-GUIDE.txt` for detailed steps.

---

## Customization

- **Logo**: Replace the base64 image in `index.html` or use `gsapgroup_logo.jpg` in the same folder.
- **Labor rates**: Default Tech $75/hr, Helper $45/hr—edit in the form or in the `getTechRate`/`getHelperRate` functions.
- **Company name**: Edit the `<h1>` in `index.html`.
- **Colors**: CSS custom properties in `:root` (e.g. `--accent`, `--text-primary`).

---

## Browser Support

- Chrome, Edge, Firefox, Safari (modern versions)
- Requires JavaScript enabled
- CDN resources (Bootstrap, fonts, html2canvas) need internet on first load; desktop app can run offline after first run

---

## License

MIT
