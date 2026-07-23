# Nächste Schritte

Kurze Übergabe, damit du die Seite selbst fertigstellen kannst. Die Seite ist live unter
**https://pascal-kuptz.github.io/berkay-portfolio/** und läuft als statische Seite (nur HTML/CSS,
etwas JS, keine Datenbank, kein Build-Schritt).

## Lokal starten

Im Projektordner einen beliebigen Static-Server starten, zum Beispiel:

```bash
python -m http.server 8453
```

Dann http://localhost:8453 öffnen. Änderungen an den Dateien einfach speichern und neu laden.

## Was noch zu tun ist

### 1. Kontakt-E-Mail eintragen (überall dieselbe)
Aktuell steht überall die Platzhalter-Adresse `kontakt@berkay-sevgili.ch`. Bitte durch deine echte
Adresse ersetzen. Sie kommt an diesen Stellen vor:
- `index.html` – das Kontaktformular (mailto) und die Mail-Adresse in der Kontaktsektion
- `index.html` – im strukturierten Datenblock (JSON-LD, `"email"`)
- `impressum.html` und `datenschutz.html`

### 2. Impressum ausfüllen (`impressum.html`)
Die Seite ist ein Entwurf. Fülle die mit `[eckigen Klammern]` markierten Felder aus: Name, Adresse,
E-Mail, optional Telefon. In der Schweiz gibt es keine Impressumspflicht wie in Deutschland, klare
Kontaktangaben sind bei geschäftlicher Nutzung aber Pflicht (UWG) und generell sinnvoll. Das Stand-
Datum unten eintragen.

### 3. Datenschutzerklärung ausfüllen (`datenschutz.html`)
Ebenfalls ein Entwurf, ausgerichtet am revidierten Schweizer Datenschutzgesetz (revDSG). Verantwortliche
Stelle (Name/Adresse) ergänzen und das Stand-Datum setzen. Der Text beschreibt den aktuellen Stand:
Hosting über GitHub Pages, Schriften über Google Fonts, Kontaktformular per mailto. **Wenn du am
Formular oder an den Schriften etwas änderst (siehe unten), muss dieser Text angepasst werden.**

Beide Rechtsseiten teilen sich das Stylesheet `legal.css`. Es ist kein Ersatz für eine juristische
Prüfung – im Zweifel kurz rechtlich gegenlesen lassen.

### 4. Kontaktformular echt nutzbar machen
Momentan öffnet der Button „Nachricht senden" nur das E-Mail-Programm des Besuchers (mailto). Das
funktioniert, ist aber unelegant und scheitert, wenn kein Mail-Client eingerichtet ist. Da GitHub Pages
rein statisch ist (kein serverseitiger Code möglich), brauchst du einen Formular-Dienst. Einfachste
Optionen ohne eigenen Server:
- **Formspree** (formspree.io) – `form`-Tag bekommt eine `action`-URL, fertig. Gratis-Kontingent reicht meist.
- Alternativen: Web3Forms, Formcarry, Getform.
- Oder ein kleines Serverless-Backend (z. B. Cloudflare Worker), falls du mehr Kontrolle willst.

Die entsprechende Stelle steht in `index.html` im `<script>` am Seitenende (Kommentar `TODO`) sowie im
`<form id="contact-form">`. Nach der Umstellung die Datenschutzerklärung um den genutzten Dienst ergänzen.

### 5. Optional, aber empfehlenswert
- **Google Fonts selbst hosten:** Dann wird keine IP-Adresse mehr an Google übertragen (sauberer für
  den Datenschutz). Aktuell werden die Schriften Archivo, Instrument Serif und IBM Plex Mono per Link geladen.
- **Eigene Domain** statt der `github.io`-Adresse (die trägt aktuell Pascals Benutzernamen).
- **Vorschaubild fürs Teilen (Open Graph):** aktuell wird das Porträt genutzt; ideal wäre ein Bild im
  Format 1200×630 px. Meta-Tags stehen im `<head>` von `index.html`.
- **Favicon** ergänzen (aktuell keins gesetzt).
- **Englische Version**, falls gewünscht (die alte Seite hatte eine DE/EN-Umschaltung).

## Ein paar Hinweise zum Bestehenden

- **Texte:** durchgehend Du-Form, Schweizer Schreibweise (ss statt ß), bewusst ohne Gedankenstriche.
- **Kundenstimmen:** Pascals Zitat ist ein echtes Testimonial. Die beiden anderen sind wörtliche Auszüge
  aus deinen Arbeitszeugnissen (PostFinance, PwC), transparent als solche gekennzeichnet. Wenn du die
  unterzeichnenden Personen namentlich nennen möchtest (statt nur Firma/Rolle), lässt sich das ergänzen.
- **SEO/GEO:** Im `<head>` steckt strukturiertes schema.org-Markup (Person, Dienstleistung, Bewertungen).
  Die Bewertungen sind mit 5/5 kodiert – das ist eine Auslegung der durchweg positiven Referenzen. Wenn du
  das lieber ohne Sterne hättest, sag Bescheid bzw. entferne die `reviewRating`/`aggregateRating`-Blöcke.

## Deployment

Die Seite liegt im GitHub-Repo `pascal-kuptz/berkay-portfolio` (GitHub Pages, Branch `main`, Ordner `/`).
Jeder Push auf `main` löst automatisch einen neuen Build aus (dauert rund eine Minute). Für eine dauerhafte
eigene Lösung kannst du das Repo auf deinen eigenen GitHub-Account übernehmen.

## Dateien im Überblick

| Datei | Inhalt |
|---|---|
| `index.html` | komplette Startseite (HTML, CSS mit Design-Token-System, JS) |
| `impressum.html`, `datenschutz.html` | Rechtsseiten (Entwurf) |
| `legal.css` | Stylesheet der Rechtsseiten |
| `assets/` | Bilder (Porträt, Zürich, Pascal) als web-optimierte Dateien |
| Wurzelordner | Original-Fotos (PNG) und Logo-SVGs als Quellen |
