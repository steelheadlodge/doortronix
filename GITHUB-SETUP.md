# Doortronix.com — GitHub Pages Setup

## Overview
Static site hosted on GitHub Pages, served at `doortronix.com`.
NY tri-state area sales & service company.  
Sister site: **doortronixusa.com** (manufacturing / factory-direct).

---

## Repo structure
```
doortronix/
├── index.html              ← Home
├── services.html           ← Services (installation, PM, emergency, inspections)
├── service-area.html       ← NY / NJ / CT coverage map
├── products.html           ← Products sold & installed
├── about.html              ← About the company
├── contact.html            ← Service request / quote form (Formspree)
├── CNAME                   ← doortronix.com
├── css/style.css
├── js/main.js
└── images/
    └── revolution.jpg      ← Copied from doortronixusa.com images/
```

---

## GitHub Pages setup
1. Push this folder to a new GitHub repo (e.g. `steelheadlodge/doortronix`)
2. In repo **Settings → Pages**: set source to **main branch / root**
3. GitHub will detect the `CNAME` file and set the custom domain automatically

---

## DNS — Network Solutions
Log into Network Solutions and update DNS for `doortronix.com`:

### A Records (delete old ones, add these four)
| Host | Points To       |
|------|-----------------|
| @    | 185.199.108.153 |
| @    | 185.199.109.153 |
| @    | 185.199.110.153 |
| @    | 185.199.111.153 |

### CNAME Record
| Host | Points To                   |
|------|-----------------------------|
| www  | steelheadlodge.github.io    |

> After DNS propagates (up to 24h), GitHub will issue a free HTTPS certificate automatically.
> Enable "Enforce HTTPS" in repo Settings → Pages once the cert is issued.

---

## Formspree (contact form)
1. Go to https://formspree.io and create an account / new form
2. Copy the form endpoint URL (e.g. `https://formspree.io/f/xabcdefg`)
3. Replace `https://formspree.io/f/XXXXXXXX` in `contact.html` with your real endpoint

---

## Things to update before launch
- [ ] Replace `(212) 555-1234` with real phone number throughout all pages
- [ ] Replace `service@doortronix.com` with real email address
- [ ] Update Formspree endpoint in `contact.html`
- [ ] Copy `images/revolution.jpg` from the doortronixusa.com repo into `images/`
- [ ] Add any real photos (facility, installs, team) to `images/` and wire into pages
- [ ] Review/update address and location details in `about.html`
- [ ] Update year founded / stats in `about.html` and `index.html` if needed
- [ ] Review service area list in `service-area.html` for accuracy
