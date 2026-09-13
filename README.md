# Web-Projekte — Fallstudien

Websites, die ich mit KI-Unterstützung gebaut, live geschaltet und übergeben habe.
Hier steht, wie sie entstanden sind, was gemessen wurde und was schiefging.

**Kein Kundencode in diesem Repo.** Die Projekte liegen in privaten Repos,
weil sie Kundeneigentum sind. Hier stehen Vorgehen, Messwerte und Live-Links.

---

## Projekt 1 — Komfortzone Hannover

**Live:** https://www.komfortzonehannover.de
**Auftraggeber:** Trageladen in Hannover-Nordstadt
**Zeitraum:** Mai bis September 2026
**Rolle:** Alleinige Umsetzung — Konzept, Bau, Domain-Umzug, Rechtstexte, Übergabe

### Ausgangslage

Bestehende Squarespace-Website mit laufendem Abo. Die Seite funktionierte, war
aber langsam, hatte kein strukturiertes Markup für die lokale Suche, und die
Rechtstexte beschrieben teilweise Dinge, die es auf der Seite gar nicht gab.

Erschwerend: Der Laden wurde von einem Vorgängerbetrieb übernommen. Die
Sichtbarkeit bei Google hing noch an dessen Domain.

### Aufgabe

Neue Website bauen, Domain umziehen ohne Ausfallzeit, Rechtstexte in Ordnung
bringen, Auffindbarkeit in der lokalen Suche verbessern, laufende Kosten senken.

### Umsetzung

- Komplette Website neu gebaut: Startseite mit Story-Aufbau, Shop-Seite,
  Fehlerseite, Impressum, Datenschutzerklärung
- **Reines HTML und CSS** — kein Baukasten, kein Framework, keine Abhängigkeiten
- Schriften lokal eingebunden statt von Google geladen
  (LG München I, 20.01.2022, Az. 3 O 17493/20)
- Deployment über GitHub, automatisch bei jedem Push
- Domain von Squarespace-DNS zu Cloudflare umgezogen, ohne Ausfallzeit
- `LocalBusiness`-Markup mit Adresse, Koordinaten, Öffnungszeiten, Bewertungen,
  Leistungen und Buchungs-Aktion
- Weiterleitungen für alle alten Adressen, die noch in Googles Index standen

### Ergebnis, gemessen

| | Vorher | Nachher |
|---|---|---|
| Ladezeit | nicht gemessen | **0,20 Sekunden** |
| Übertragene Datenmenge | — | 15,8 KB (von 61,5 KB, komprimiert) |
| Hosting-Kosten | 16–25 € / Monat | **0 € / Monat** |
| Strukturierte Daten | keine | `LocalBusiness` vollständig |
| Ausfallzeit beim Umzug | — | **keine** |
| Tote Links aus dem Google-Index | mehrere | **0**, alle weitergeleitet |

Zur Einordnung: Google stuft alles unter 0,8 Sekunden als gut ein.

### Was schiefging — und was ich daraus gelernt habe

**Der Fehler:** Beim ersten Deployment lagen **2.239 Dateien** öffentlich auf dem
Server, darunter der komplette `node_modules`-Ordner. Ursache: Sobald eine
`package.json` im Repository liegt, behandelt der Build-Server das Projekt als
Node-Anwendung und lädt alles mit hoch.

**Die Behebung:** `.assetsignore` anlegen und dort ausschließen, was nicht
ausgeliefert werden soll. Danach: 4 Dateien statt 2.239.

**Weitere Punkte aus dem Projekt:**

- **Cloudflare Pages statt Workers.** Die neue Oberfläche führt Projekte
  standardmäßig über Workers, das braucht aber eine eigene Zone. Pages kommt mit
  zwei DNS-Einträgen aus und war für dieses Projekt der richtige Weg.
- **Rechtstexte einer alten Seite nie ungeprüft übernehmen.** Hosting-Anbieter,
  Schriftarten und eingebundene Dienste ändern sich beim Umzug fast immer. Im
  alten Impressum stand zusätzlich eine falsche Postleitzahl.
- **Bei der Wettbewerbsanalyse prüfen, welche URL genau rankt.** Hier war es nicht
  die Hauptdomain des Wettbewerbers, sondern eine Subdomain — die bereits den
  Laden des Auftraggebers beschrieb. Ohne diese Prüfung wäre die Analyse falsch
  gewesen.

### Wie ich mit KI gearbeitet habe

Gebaut mit **Claude Code** im Terminal, nicht mit einem Website-Baukasten und
nicht mit Prompt-zu-Website-Diensten.

Der Unterschied in der Praxis: Ich gebe Struktur, Inhalte und Entscheidungen vor
und lasse die Umsetzung schreiben, dann prüfe und korrigiere ich. Bei den
Rechtstexten und beim Markup habe ich jede Angabe gegen die tatsächliche Seite
geprüft, weil generierte Texte dort regelmäßig Dinge behaupten, die nicht
zutreffen.

Was dabei nicht delegierbar war: der Domain-Umzug ohne Ausfallzeit, die
Entscheidung für Pages statt Workers, und das Finden des `node_modules`-Fehlers.

---

## Was ich kann

Nach Tätigkeit sortiert, nicht nach Werkzeug:

- **Website von Grund auf bauen und live schalten** — HTML, CSS, statisches
  Hosting, automatisches Deployment bei jedem Push
- **Domain umziehen, ohne dass die Seite offline geht** — DNS, Nameserver,
  Weiterleitungen für alte Adressen aus dem Suchindex
- **Auffindbarkeit technisch vorbereiten** — Seitenstruktur, Titel, Canonical,
  `LocalBusiness`-Markup mit Adresse, Zeiten, Bewertungen
- **Rechtstexte prüfen und anpassen** — Impressum, Datenschutz, lokal
  eingebundene Schriften statt externer Ladevorgänge
- **Ladezeit und Übertragungsmenge messen und senken**
- **Sauber übergeben** — Dokumentation und Anleitung, sodass die Auftraggeber
  selbst damit weiterarbeiten können
- **Mit KI im Terminal arbeiten** — Claude Code, Git, Deployment-Pipelines

## Was ich noch nicht gemacht habe

- Ad Creatives für Google und Meta
- Tracking-Pixel und Kampagnen-Auswertung
- Mehrere Kundenprojekte parallel

---

## Hintergrund

Staatlich geprüfter Fahrzeugtechniker, davor Kfz-Meister, Stationen bei BMW und
VW in der Bordnetzentwicklung, danach CATIA-V5-Konstrukteur. Heute im
E-Commerce tätig und parallel mit KI-gestützter Entwicklung beschäftigt:
Websites, Automatisierungen und der Aufbau containerbasierter Serverumgebungen.

Kein klassischer Programmierer. Meine Arbeitsweise ist, mit KI echte Lösungen zu
bauen, zu prüfen und zu verantworten.

---

## Weitere Repos

| Repo | Inhalt |
|---|---|
| [`lms-to-wordpress-migration`](https://github.com/mazelwinkler-oss/lms-to-wordpress-migration) | Browser-Tool zur Migration von LMS-Kursen nach WordPress, erzeugt valides WXR-XML |
| [`wg-migration-tool`](https://github.com/mazelwinkler-oss/wg-migration-tool) | Migrations-Tool MemberPress zu WordPress Custom Platform |
| [`smart-invoice-rename`](https://github.com/mazelwinkler-oss/smart-invoice-rename) | Rechnungen automatisch umbenennen nach Inhalt |

---

**Kontakt:** über GitHub oder die im Lebenslauf angegebene Adresse.
