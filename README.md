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
**Rolle:** Alleinige Umsetzung — Konzept, Bau, Domain-Umzug, Übergabe

### Ausgangslage

Es gab noch keine gestaltete Website. Auf Squarespace lag eine Notlösung: die
nötigsten Informationen, damit Kundinnen überhaupt Termine buchen konnten. Kein
Aufbau, kein Konzept, keine strukturierten Daten für die lokale Suche.

Erschwerend: Der Laden wurde von einem Vorgängerbetrieb übernommen. Die
Sichtbarkeit bei Google hing noch an dessen Domain.

**Meine Aufgabe:** eine richtige Website gestalten und live bringen.

### Die Entscheidung, die das Projekt geprägt hat

Nachdem der Entwurf stand, kam die eigentliche Frage: Wie kommt dieses Design auf
Squarespace?

Antwort: gar nicht direkt. Squarespace nimmt kein fertiges HTML und CSS entgegen.
Ich hätte das Layout im Baukasten nachbauen müssen — mit dem Ergebnis, dass es
nicht so aussieht wie entworfen, und mit dem Abo als laufender Kostenposten.

Ich habe die Alternativen recherchiert und intern mit den Inhaberinnen
durchgesprochen. Ausschlaggebend waren drei Punkte:

1. Das Design sollte genau so umgesetzt werden, wie es entworfen wurde
2. Ein Online-Shop soll später dazukommen — die Lösung musste dafür offen sein
3. Die laufenden Kosten sollten runter

Ergebnis: statische Seite auf Cloudflare Pages statt Baukasten. Das war keine
technische Vorliebe, sondern das Resultat dieser Abwägung.

### Umsetzung

- Website neu gebaut: Startseite mit Story-Aufbau, Shop-Seite, Fehlerseite,
  sowie die Seiten für Impressum und Datenschutz. Die Texte dafür wurden vom
  Auftraggeber über einen Rechtstext-Generator gestellt, ich habe sie eingebunden.
- **Reines HTML und CSS** — kein Baukasten, kein Framework, keine Abhängigkeiten
- Schriften lokal eingebunden statt von Google geladen
  (LG München I, 20.01.2022, Az. 3 O 17493/20)
- Deployment über GitHub, automatisch bei jedem Push
- Domain von Squarespace-DNS zu Cloudflare umgezogen, ohne Ausfallzeit
- `LocalBusiness`-Markup mit Adresse, Koordinaten, Öffnungszeiten, Bewertungen,
  Leistungen und Buchungs-Aktion
- Weiterleitungen für alle alten Adressen, die noch im Google-Index standen

### Ergebnis, gemessen

| | Vorher (Squarespace-Notlösung) | Nachher |
|---|---|---|
| Website | Informationsseite ohne Gestaltung | gestaltete Seite mit Story-Aufbau |
| Ladezeit | nicht gemessen | **0,20 s** |
| Übertragene Datenmenge | — | 15,8 KB (von 61,5 KB, komprimiert) |
| Laufende Kosten | 16–25 € / Monat Abo | **0 € / Monat Hosting**, nur Domain (~15 €/Jahr) |
| Strukturierte Daten | keine | `LocalBusiness` vollständig |
| Ausfallzeit beim Umzug | — | **keine** |
| Tote Links aus dem Google-Index | mehrere | **0**, alle weitergeleitet |

Zur Einordnung: Google stuft alles unter 0,8 s als gut ein.

**Aktueller Stand:** Die Seite ist live und in Benutzung. Drei Bildplätze warten
noch auf Fotos, die erst gemacht werden müssen. Der Online-Shop ist in
Vorbereitung.

### Was schiefging — und wie ich es gefunden habe

**Der Fehler:** Nach dem ersten Deployment lagen **2.239 Dateien** öffentlich auf
dem Server, darunter der komplette `node_modules`-Ordner.

**Die Ursache:** Sobald eine `package.json` im Repository liegt, behandelt der
Build-Server das Projekt als Node-Anwendung und lädt den gesamten Baum mit hoch.
Das passiert still — die Seite funktioniert, nichts schlägt fehl.

**Die Behebung:** `.assetsignore` anlegen und ausschließen, was nicht ausgeliefert
werden soll. Danach: 4 Dateien statt 2.239.

**Wie es aufgefallen ist:** Nicht im Browser — dort sah alles richtig aus. Ich
hatte nach dem Deployment nachgefragt, was tatsächlich auf dem Server gelandet
ist. Die Antwort war eine Zahl, die nicht zu einer Seite aus vier Dateien passte.

**Warum das hier steht:** Genau das ist für mich der Kern der Arbeit mit KI. Das
Ergebnis sah fertig aus, die Seite lief, nichts schlug fehl. Wer an dieser Stelle
nicht nachfragt, liefert einen Server aus, auf dem 2.239 fremde Dateien liegen.
Ich übernehme Ergebnisse nicht, ich frage nach, was passiert ist.

### Drei weitere Punkte aus dem Projekt

- **Cloudflare Pages statt Workers.** Die aktuelle Oberfläche führt Projekte
  standardmäßig über Workers, das braucht eine eigene Zone. Pages kommt mit zwei
  DNS-Einträgen aus und war hier der richtige Weg.
- **Beim Umzug ändern sich die technischen Rahmenbedingungen.** Hosting-Anbieter,
  Schriftarten und eingebundene Dienste sind nach einem Plattformwechsel andere
  als vorher. Wo die alten Angaben auf der Seite nicht mehr zum neuen Aufbau
  passten, habe ich das an die Auftraggeberinnen gemeldet, damit sie die Texte
  aktualisieren lassen konnten.
- **Bei der Wettbewerbsanalyse prüfen, welche URL genau rankt.** Hier war es nicht
  die Hauptdomain des Wettbewerbers, sondern eine Subdomain — die bereits den
  Laden des Auftraggebers beschrieb. Ohne diese Prüfung wäre die ganze Analyse
  falsch gewesen.

### Wie ich mit KI arbeite

Gebaut mit **Claude Code im Terminal** — nicht mit Prompt-zu-Website-Diensten und
nicht mit Baukästen.

Der Ablauf: Ich lege Struktur, Inhalte und technische Entscheidungen fest und
lasse die Umsetzung schreiben. Danach frage ich nach, was tatsächlich passiert
ist — nicht nur, ob das Ergebnis im Browser stimmt.

Das ist die Stelle, an der Projekte auseinandergehen. Ein generiertes Ergebnis
sieht meistens fertig aus. Ob es das ist, zeigt sich erst, wenn man nachhakt:
Was liegt auf dem Server? Welche Werte stehen im Markup? Wird von außen etwas
nachgeladen? Die drei Punkte oben — die 2.239 Dateien, die Markup-Angaben und
die falsch identifizierte Wettbewerber-URL — sind alle so aufgefallen.

Nicht delegierbar waren: der Domain-Umzug ohne Ausfallzeit, die Entscheidung für
Pages statt Workers, und das Finden des `node_modules`-Fehlers.

---

## Projekt 2 — Landingpage und Exposés für meinen Arbeitgeber

Eingestellt bin ich im technischen Kundensupport eines E-Commerce-Unternehmens.
Als dort ankam, dass ich mich intensiv mit KI-gestützter Entwicklung beschäftige,
kam die Anfrage, ob ich Produkt-Exposés und eine Landingpage übernehmen kann.

Beides habe ich gebaut — neben der eigentlichen Stelle, nicht als Teil davon.

Das ist der Grund, warum ich mich auf diese Anzeige bewerbe: Die Arbeit, die dort
nebenbei entstanden ist, ist die, die ich hauptberuflich machen möchte.

---

## Mitgewirkt

**alissa-stein.com** — Website einer Moderatorin, live.
Kein alleiniges Projekt von mir. Ich habe an der Umsetzung mitgewirkt, den
Hauptteil haben andere gemacht.

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
- Schriften lokal eingebunden, sodass beim Seitenaufruf keine externen Server
  kontaktiert werden
- Ladezeit und Übertragungsmenge gemessen und gesenkt
- Dokumentation und Anleitung übergeben, sodass die Auftraggeberinnen selbst
  weiterarbeiten können
- Containerbasierte Serverumgebungen aufgesetzt und WordPress-Seiten migriert

## Was ich noch nicht gemacht habe

- Ad Creatives für Google und Meta
- Tracking-Pixel und Kampagnen-Auswertung
- Mehrere Kundenprojekte parallel

---

## Werkzeuge, die ich mir selbst gebaut habe

Wenn mich in der täglichen Arbeit etwas ausbremst, baue ich mir ein Werkzeug
dafür. Zwei Beispiele:

**DiktierMaus** — ein Diktierprogramm für den eigenen Rechner. Ich arbeite viel
im Terminal und wollte Anweisungen nicht mehr tippen. Taste gedrückt halten,
sprechen, loslassen — der Text steht im Eingabefeld. Die Spracherkennung läuft
lokal, es geht nichts an einen fremden Dienst. Zusätzlich legt das Programm die
letzten Texte ab, sodass nichts verloren geht, wenn ein Fenster abstürzt.

**Umbenennen von Rechnungen** — ein Werkzeug, das eingehende Rechnungen liest und
nach ihrem Inhalt benennt, statt dass ich jede einzeln öffne und umbenenne.

Beide sind aus einem eigenen Ärgernis entstanden, nicht aus einer Übung.

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
