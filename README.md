# Web-Projekte — Fallstudien

Websites, die ich gebaut, live geschaltet und übergeben habe.
Gebaut wird mit **Claude Code im Terminal**, nicht mit Website-Baukästen.

Hier stehen Vorgehen, Messwerte und was schiefging.
**Kein Kundencode in diesem Repo** — die Projekte liegen privat, weil sie
Kundeneigentum sind.

---

## Projekt 1 — Komfortzone Hannover

**Live:** https://www.komfortzonehannover.de
**Auftraggeber:** Trageladen in Hannover-Nordstadt
**Zeitraum:** Mai bis September 2026
**Rolle:** Alleinige Umsetzung — Konzept, Bau, Domain-Umzug, Rechtstexte, Übergabe

### Ausgangslage

Squarespace-Seite mit laufendem Abo. Sie funktionierte, war aber langsam, hatte
kein strukturiertes Markup für die lokale Suche, und die Rechtstexte beschrieben
teilweise Dinge, die es auf der Seite gar nicht gab.

Erschwerend: Der Laden wurde von einem Vorgängerbetrieb übernommen. Die
Sichtbarkeit bei Google hing noch an dessen Domain.

### Umsetzung

- Website neu gebaut: Startseite mit Story-Aufbau, Shop-Seite, Fehlerseite,
  Impressum, Datenschutzerklärung
- **Reines HTML und CSS** — kein Baukasten, kein Framework, keine Abhängigkeiten
- Schriften lokal eingebunden statt von Google geladen
  (LG München I, 20.01.2022, Az. 3 O 17493/20)
- Deployment über GitHub, automatisch bei jedem Push
- Domain von Squarespace-DNS zu Cloudflare umgezogen, ohne Ausfallzeit
- `LocalBusiness`-Markup mit Adresse, Koordinaten, Öffnungszeiten, Bewertungen,
  Leistungen und Buchungs-Aktion
- Weiterleitungen für alle alten Adressen, die noch im Google-Index standen

### Ergebnis, gemessen

| | Vorher (Squarespace) | Nachher |
|---|---|---|
| Ladezeit | nicht gemessen | **0,20 s** |
| Übertragene Datenmenge | — | 15,8 KB (von 61,5 KB, komprimiert) |
| Laufende Kosten | 16–25 € / Monat Abo | **0 € / Monat Hosting**, nur Domain (~15 €/Jahr) |
| Strukturierte Daten | keine | `LocalBusiness` vollständig |
| Ausfallzeit beim Umzug | — | **keine** |
| Tote Links aus dem Google-Index | mehrere | **0**, alle weitergeleitet |

Zur Einordnung: Google stuft alles unter 0,8 s als gut ein.

### Was schiefging — und wie ich es gefunden habe

**Der Fehler:** Nach dem ersten Deployment lagen **2.239 Dateien** öffentlich auf
dem Server, darunter der komplette `node_modules`-Ordner.

**Die Ursache:** Sobald eine `package.json` im Repository liegt, behandelt der
Build-Server das Projekt als Node-Anwendung und lädt den gesamten Baum mit hoch.
Das passiert still — die Seite funktioniert, nichts schlägt fehl.

**Die Behebung:** `.assetsignore` anlegen und ausschließen, was nicht ausgeliefert
werden soll. Danach: 4 Dateien statt 2.239.

**Warum das hier steht:** Weil generierter Code solche Fehler nicht meldet. Wer
nur das Ergebnis im Browser prüft, sieht eine funktionierende Website. Gefunden
habe ich es beim Durchsehen der Deployment-Ausgabe.

### Drei weitere Punkte aus dem Projekt

- **Cloudflare Pages statt Workers.** Die aktuelle Oberfläche führt Projekte
  standardmäßig über Workers, das braucht eine eigene Zone. Pages kommt mit zwei
  DNS-Einträgen aus und war hier der richtige Weg.
- **Rechtstexte einer alten Seite nie ungeprüft übernehmen.** Hosting-Anbieter,
  Schriftarten und eingebundene Dienste ändern sich beim Umzug fast immer. Im
  alten Impressum stand zusätzlich eine falsche Postleitzahl.
- **Bei der Wettbewerbsanalyse prüfen, welche URL genau rankt.** Hier war es nicht
  die Hauptdomain des Wettbewerbers, sondern eine Subdomain — die bereits den
  Laden des Auftraggebers beschrieb. Ohne diese Prüfung wäre die ganze Analyse
  falsch gewesen.

### Wie ich mit KI arbeite

Gebaut mit **Claude Code im Terminal** — nicht mit Prompt-zu-Website-Diensten und
nicht mit Baukästen.

Der Ablauf: Ich lege Struktur, Inhalte und technische Entscheidungen fest, lasse
die Umsetzung schreiben, prüfe und korrigiere. Bei Rechtstexten und Markup habe
ich jede Angabe gegen die tatsächliche Seite geprüft, weil generierte Texte dort
regelmäßig Dinge behaupten, die nicht zutreffen.

Nicht delegierbar waren: der Domain-Umzug ohne Ausfallzeit, die Entscheidung für
Pages statt Workers, und das Finden des `node_modules`-Fehlers.

---

## Womit ich arbeite

| Bereich | Werkzeuge |
|---|---|
| KI-gestützte Entwicklung | Claude Code (Terminal), Claude, ChatGPT |
| Website | HTML, CSS, Git, GitHub |
| Hosting und Domains | Cloudflare Pages, DNS, Weiterleitungen |
| Auffindbarkeit | `LocalBusiness`-Markup, Seitenstruktur, Canonical |
| Server | Linux, Incus-Container, Nextcloud, WordPress-Migration |

## Was ich gemacht habe

- Website von Grund auf gebaut und live geschaltet, mit automatischem Deployment
- Domain umgezogen, ohne dass die Seite offline ging
- `LocalBusiness`-Markup und Weiterleitungen für Adressen aus dem Suchindex gesetzt
- Rechtstexte geprüft und angepasst, Schriften lokal eingebunden
- Ladezeit und Übertragungsmenge gemessen und gesenkt
- Dokumentation und Anleitung übergeben, sodass die Auftraggeberinnen selbst
  weiterarbeiten können
- Containerbasierte Serverumgebungen aufgesetzt und WordPress-Seiten migriert

## Was ich noch nicht gemacht habe

- Ad Creatives für Google und Meta
- Tracking-Pixel und Kampagnen-Auswertung
- Mehrere Kundenprojekte parallel

---

## Zum Hintergrund

Staatlich geprüfter Fahrzeugtechniker, davor Kfz-Meister. Zwei Jahre
Bordnetzentwicklung bei BMW und VW, danach Konstruktion mit CATIA V5. Heute im
E-Commerce tätig.

Den Umgang mit KI-gestützter Entwicklung habe ich mir selbst angeeignet — über
Fachvideos, Dokumentation und gebaute Projekte, die ich mitschreibe.

---

## Weitere Repos

| Repo | Inhalt |
|---|---|
| [`lms-to-wordpress-migration`](https://github.com/mazelwinkler-oss/lms-to-wordpress-migration) | Browser-Tool zur Migration von LMS-Kursen nach WordPress, erzeugt valides WXR-XML |
| [`wg-migration-tool`](https://github.com/mazelwinkler-oss/wg-migration-tool) | Migrations-Tool MemberPress zu WordPress Custom Platform |
