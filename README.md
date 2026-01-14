# Menrva Group Website - Netlify Deployment

## 🚀 Stap-voor-stap: Website online zetten via Netlify

### Methode 1: Direct uploaden (Makkelijkst)

1. **Ga naar** https://app.netlify.com
2. **Registreer** of log in (kan met Google/GitHub/email)
3. **Sleep de uitgepakte `menrva-netlify` map** naar het "Drag and drop" gebied
4. **Wacht** tot de build klaar is (duurt ~1-2 minuten)
5. **Klaar!** Je krijgt een URL zoals `random-name-123.netlify.app`

### Methode 2: Via GitHub (Aanbevolen voor updates)

1. **Maak een GitHub account** op https://github.com
2. **Maak een nieuwe repository** genaamd `menrva-website`
3. **Upload alle bestanden** uit de `menrva-netlify` map
4. **Ga naar Netlify** → "Add new site" → "Import an existing project"
5. **Kies GitHub** en selecteer je repository
6. **Deploy** → Build settings worden automatisch herkend via `netlify.toml`

---

## 🔗 Eigen domeinnaam koppelen

1. **In Netlify:** Ga naar je site → "Domain settings"
2. **Klik** "Add custom domain"
3. **Voer je domein in** (bijv. `menrvagroup.be`)
4. **Voeg DNS records toe** bij je domeinregistrar:
   - Type: `CNAME`
   - Name: `www`
   - Value: `jouw-site.netlify.app`
   
   OF voor root domein:
   - Type: `A`
   - Name: `@`
   - Value: `75.2.60.5` (Netlify IP)

---

## 📁 Projectstructuur

```
menrva-netlify/
├── index.html          # Hoofdpagina
├── package.json        # Dependencies
├── vite.config.js      # Build configuratie
├── netlify.toml        # Netlify instellingen
├── public/
│   └── favicon.svg     # Browser icoon
└── src/
    ├── main.jsx        # React entry point
    └── App.jsx         # De website code
```

---

## ✏️ Website aanpassen

Om teksten/prijzen aan te passen, open `src/App.jsx` en zoek naar de relevante sectie. Na aanpassingen:

**Als je direct hebt geüpload:**
- Upload de hele map opnieuw naar Netlify

**Als je GitHub gebruikt:**
- Push je wijzigingen → Netlify bouwt automatisch opnieuw

---

## 🔐 Admin wachtwoord

Het admin wachtwoord voor de agenda is: `menrva2025`

Om dit te wijzigen, zoek in `App.jsx` naar:
```javascript
if (adminPassword === 'menrva2025') {
```

---

## ❓ Problemen?

- **Build failed?** Check of alle bestanden correct zijn geüpload
- **Formulieren werken niet?** Controleer de Formspree ID's in App.jsx
- **Styling ziet er raar uit?** Probeer cache te legen (Ctrl+Shift+R)

Netlify support: https://docs.netlify.com
