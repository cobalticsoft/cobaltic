# Cobaltic – Store Web Assets

Static HTML pages for the Google Play Store listing.
These files are **completely separate** from the Android source code.

## Structure

```
store-web/
├── index.html              # Multilingual landing page (auto language detection)
├── README.md
├── privacy/
│   ├── hu.html             # Adatvédelmi Nyilatkozat (Hungarian)
│   ├── en.html             # Privacy Policy (English)
│   ├── de.html             # Datenschutzerklärung (German)
│   ├── es.html             # Política de Privacidad (Spanish)
│   ├── fr.html             # Politique de Confidentialité (French)
│   └── nl.html             # Privacybeleid (Dutch)
└── terms/
    ├── hu.html             # Felhasználási Feltételek (Hungarian)
    ├── en.html             # Terms of Service (English)
    ├── de.html             # Nutzungsbedingungen (German)
    ├── es.html             # Términos de Servicio (Spanish)
    ├── fr.html             # Conditions d'Utilisation (French)
    └── nl.html             # Gebruiksvoorwaarden (Dutch)
```

## Language detection (index.html)

The landing page auto-detects the visitor's language via `navigator.languages`
(works in browsers and Play Store WebView alike). Fallback order:

1. URL hash: `index.html#hu` — allows direct linking to a specific language
2. `navigator.languages` — device/browser language preference list
3. Default: English

Direct language links: `#hu` `#en` `#de` `#es` `#fr` `#nl`

## Hosting

Host these files on any static hosting service (GitHub Pages, Netlify, etc.).
The Play Store requires a **publicly accessible URL** for the Privacy Policy.

### Suggested URLs after hosting

| Page | URL |
|------|-----|
| Landing page | `https://yourdomain.com/` or `https://yourdomain.com/index.html` |
| Privacy Policy (EN) | `https://yourdomain.com/privacy/en.html` |
| Privacy Policy (HU) | `https://yourdomain.com/privacy/hu.html` |
| Terms of Service (EN) | `https://yourdomain.com/terms/en.html` |

### Quick GitHub Pages setup

1. Push the `store-web/` directory contents to a public GitHub repository (as root)
2. Settings → Pages → Deploy from branch → `main` / `/(root)`
3. Use the generated `https://<user>.github.io/<repo>/privacy/en.html` URL in Play Console

## TODO — KFT company information

The following company details need to be added to all privacy and terms files
once confirmed:

- [ ] Company name (cégnév)
- [ ] Registered address (székhely)
- [ ] Company registration number (cégjegyzékszám)
- [ ] Tax number (adószám)
- [ ] Contact email address

## Updating

When app features or permissions change, update all 6 language files.
Always update the "Last updated" date at the top of each page.
