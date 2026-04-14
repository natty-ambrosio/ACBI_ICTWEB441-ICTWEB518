 multi-page static website for **Bryan's Café**, a fictional Sydney café chain. Built as an academic project for units **ICTWEB441** (Produce basic client-side script) and **ICTWEB518** (Build a document using extensible markup language).

---

## Pages

| Page | File | Description |
|---|---|---|
| About | `index.html` | Landing page with café story and history |
| Menu | `menu.html` | Menu loaded dynamically from XML |
| Contact | `contact.html` | Enquiry form + branch locations loaded from XML |
| Privacy Policy | `privacy.html` | Privacy policy page |

---

## Project Structure

```
bryanCafe/
├── index.html          # About page (home)
├── menu.html           # Menu page
├── contact.html        # Contact page
├── privacy.html        # Privacy policy
├── style.css           # Shared stylesheet
├── menu.xml            # Menu data (meals, beverages)
├── menu.dtd            # DTD schema for menu.xml
├── branches.xml        # Branch location data
├── branches.dtd        # DTD schema for branches.xml
└── images/
    ├── logo.svg
    ├── banner.svg
    ├── about.svg
    ├── history.svg
    ├── salad.svg
    ├── sandwich.svg
    ├── pie.svg
    ├── toast.svg
    ├── coffee.svg
    └── beverage.svg
```

---

## Technologies

- **HTML5** — semantic page structure
- **CSS3** — custom stylesheet (`style.css`)
- **Bootstrap 5.3** — responsive layout, navbar, cards, form components (loaded via CDN)
- **XML + DTD** — structured data for menu items and branch locations, validated against DTD schemas
- **JavaScript (vanilla, ES5)** — client-side scripting:
  - Dynamic year in footer (`new Date().getFullYear()`)
  - `fetch()` + `DOMParser` to load and render `menu.xml` and `branches.xml` at runtime
  - Form validation using the HTML5 Constraint Validation API

---

## XML Data

### `menu.xml` / `menu.dtd`
Stores the café menu organised into sections (`meals`, `beverages`). Each `<item>` holds a name, price, description, and image path. Validated against `menu.dtd`.

### `branches.xml` / `branches.dtd`
Stores location data for the three café branches (Surry Hills, Haymarket, Circular Quay). Each `<branch>` holds address, phone, opening hours, and a Google Maps link. Validated against `branches.dtd`.

---

## Running Locally

Because `menu.html` and `contact.html` use `fetch()` to load XML files, the site must be served from a local web server (browsers block `fetch()` on `file://` URLs).

**Option 1 — VS Code Live Server extension**
Right-click `index.html` → *Open with Live Server*

**Option 2 — Python**
```bash
cd bryanCafe
python -m http.server 8080
```
Then open `http://localhost:8080` in a browser.

**Option 3 — Node.js (`npx serve`)**
```bash
npx serve bryanCafe
```

---

## Academic Context

| Detail | Value |
|---|---|
| Units | ICTWEB441, ICTWEB518 |
| Institution | ACBI — Australian College of Business Intelligence |
| Year | 2026 |

---

## Branches

| Location | Address | Phone |
|---|---|---|
| Surry Hills | 76 Devonshire St, Surry Hills NSW | 02 9211 1234 |
| Haymarket | 451 Pitt St, Haymarket Sydney NSW | 02 9262 5678 |
| Circular Quay | 31 Alfred Street, Circular Quay NSW | 02 8971 9101 |
