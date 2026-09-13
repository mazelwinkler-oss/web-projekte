# Web-Projekte

Websites, die ich gebaut, live geschaltet und übergeben habe — mit Claude Code im
Terminal, nicht mit Baukästen.

Hier stehen Vorgehen, gemessene Ergebnisse und was schiefgegangen ist.
**Kein Kundencode in diesem Repo**, die Projekte liegen privat.

**[Live-Projekt ansehen → komfortzonehannover.de](https://www.komfortzonehannover.de)**

---

## Inhalt

| | |
|---|---|
| [Auf einen Blick](#auf-einen-blick) | die Kennzahlen in einer Tabelle |
| [Projekt: Komfortzone Hannover](#projekt-komfortzone-hannover) | Ausgangslage, Entscheidung, Umsetzung |
| [Der Fehler, den ich gefunden habe](#der-fehler-den-ich-gefunden-habe) | 2.239 Dateien, die niemand sehen sollte |
| [Projekt: Arbeitgeber](#projekt-landingpage-und-exposés-für-meinen-arbeitgeber) | wie ich dazu gekommen bin |
| [Wie ich arbeite](#wie-ich-arbeite) | Wissensablage, Skills, Nachfragen |
| [Werkzeuge und Können](#werkzeuge-und-können) | womit, und was ich gemacht habe |
| [Was ich noch nicht gemacht habe](#was-ich-noch-nicht-gemacht-habe) | die offenen Lücken |
| [Selbstgebaute Werkzeuge](#selbstgebaute-werkzeuge) | DiktierMaus und andere |
| [Hintergrund](#hintergrund) | Werdegang in drei Sätzen |

---

## Auf einen Blick

| | Vorher | Nachher |
|---|---|---|
| Website | Notlösung ohne Gestaltung | gestaltete Seite mit Story-Aufbau |
| Ladezeit | nicht gemessen | **0,20 s** (Google wertet unter 0,8 s als gut) |
| Übertragene Daten | — | 15,8 KB von 61,5 KB, komprimiert |
| Laufende Kosten | 16–25 € / Monat Abo | **0 € Hosting**, nur Domain (~15 €/Jahr) |
| Strukturierte Daten | keine | `LocalBusiness` vollständig (maschinenlesbarer Steckbrief des Ladens) |
| Eindeutige Adresse für Google | nicht gesetzt | Canonical-Tag gesetzt (sagt Google, welche Adresse zählt) |
| Fehlerseite | graue Standardmeldung | eigene, im Design des Ladens |
| Ausfallzeit beim Domain-Umzug | — | **keine** |

---

## Projekt: Komfortzone Hannover

| | |
|---|---|
| **Live** | https://www.komfortzonehannover.de |
| **Auftraggeber** | Trageladen in Hannover-Nordstadt |
| **Zeitraum** | Mai bis September 2026 |
| **Rolle** | Alleinige Umsetzung: Konzept, Texte, Bau, Domain-Umzug, Übergabe |

### Ausgangslage

Es gab noch keine gestaltete Website. Auf Squarespace lag eine Notlösung: die
nötigsten Informationen, damit Kunden überhaupt Termine buchen konnten. Kein
Aufbau, kein Konzept, keine strukturierten Daten für die lokale Suche.

Erschwerend: Der Laden wurde von einem Vorgängerbetrieb übernommen. Die
Sichtbarkeit bei Google hing noch an dessen Domain.

**Meine Aufgabe:** eine richtige Website gestalten und live bringen.

### Die Entscheidung, die das Projekt geprägt hat

Nachdem der Entwurf stand, kam die eigentliche Frage: Wie kommt dieses Design auf
Squarespace?

Antwort: gar nicht direkt. Squarespace nimmt kein fertiges HTML und CSS entgegen.
Ich hätte das Layout im Baukasten nachbauen müssen — mit dem Ergebnis, dass es
nicht so aussieht wie entworfen, und mit dem Abo als laufendem Kostenposten.

Ich habe die Alternativen recherchiert und mit den Inhaberinnen durchgesprochen.
Ausschlaggebend waren drei Punkte:

1. Das Design sollte genau so umgesetzt werden, wie es entworfen wurde
2. Ein Online-Shop soll später dazukommen — die Lösung musste dafür offen sein
3. Die laufenden Kosten sollten runter

**Ergebnis:** statische Seite auf Cloudflare Pages statt Baukasten. Keine
technische Vorliebe, sondern das Resultat dieser Abwägung.

### Aufbau der Seite: eine Seite, die einer Erzählung folgt

Die Startseite ist bewusst als durchgehende Seite gebaut, nicht als Menü mit
Unterseiten. Der Aufbau folgt dem Muster der Heldenreise, wie es Alexander
Christiani in „Webseiten StoryMagic" für Websites beschreibt — mit Donald Millers
StoryBrand als Grundlage.

Die Reihenfolge der Abschnitte ist deshalb keine Geschmacksfrage:

| Element der Methode | Umsetzung auf der Seite |
|---|---|
| **Einstieg** — in zehn Sekunden klarmachen, worum es geht | „Eine Babytrage kauft man nicht. Man passt sie an." |
| **Problem** — die Lage beschreiben, bis der Besucher sich wiedererkennt | Erst das Äußere (Baby quengelt, Rücken zwickt), dann das Innere (das Gefühl, etwas falsch zu machen) |
| **Mentor** — wer hilft und warum man ihm vertrauen kann | Überschrift „Wer dich begleitet", nicht „Über uns". Der Kunde bleibt im Mittelpunkt |
| **Plan** — Komplexität in drei Schritte auflösen | „In drei Schritten zur richtigen Trage": Termin buchen, Beratung vor Ort, passende Trage |
| **Was sich ändert** — Gewinn und Verlust zeigen | „Eine Stunde Beratung. Oder Monate Unsicherheit." Beide Seiten, nicht nur die schöne |
| **Vertrauen und Einwände** | Echte Kundenstimmen und Bewertung, danach die häufigen Fragen vor der Buchung |
| **Abschluss** | Greift den Einstiegssatz wieder auf und führt zum nächsten Schritt |

Der Leitsatz dieser Methode: **Design verkauft nicht, Klarheit verkauft.** Wer
erst scrollen und suchen muss, springt ab — deshalb keine Bildergalerien im
Kopfbereich und keine Unterseiten für Inhalte, die zusammengehören.

Eigenständige Seiten gibt es nur dort, wo sie hingehören: Shop, Impressum,
Datenschutz.

### Wie die Texte entstanden sind

Die Texte stammen nicht von den Inhaberinnen und auch nicht aus einem
Textgenerator. Sie sind in vier Schritten entstanden:

1. **Gespräche.** Was macht den Laden aus, was sollen Besucher verstehen, was
   wird im Beratungsalltag immer wieder gefragt. Das war die Rohmasse.
2. **Recherche.** Wie beschreiben andere Anbieter ihre Beratung, welche Fragen
   tauchen in Bewertungen und Foren auf, was sagen Fachquellen zum Thema Tragen.
3. **Struktur nach der Methode.** Jeder Abschnitt bekam die Aufgabe, die ihm im
   Aufbau oben zugewiesen ist — der Problem-Abschnitt beschreibt, der
   Plan-Abschnitt ordnet, der Abschluss führt zur Buchung.
4. **Schreiben mit KI, dann abstimmen.** Die Entwürfe entstanden mit Claude auf
   Basis von Schritt 1 bis 3. Danach ging jeder Abschnitt zurück an die
   Inhaberinnen, wurde korrigiert und angepasst, bis die Formulierungen zum Laden
   passten.

Der Satz auf der Startseite — „Eine Babytrage kauft man nicht. Man passt sie an."
— stammt aus Schritt 1. Er fiel im Gespräch, nicht im Entwurf.

**Warum das so lief:** Eine KI kann formulieren, aber sie weiß nicht, was in
einem Beratungsgespräch tatsächlich gefragt wird. Dieses Wissen musste erst
eingesammelt werden. Der Schreibschritt war der kürzeste von den vieren.

### Umsetzung

- **Reines HTML und CSS** — kein Baukasten, kein Framework, keine Abhängigkeiten
- Schriften lokal eingebunden statt von Google geladen
  (LG München I, 20.01.2022, Az. 3 O 17493/20)
- Deployment über GitHub, automatisch bei jedem Push
- Domain von Squarespace-DNS zu Cloudflare umgezogen, ohne Ausfallzeit
- `LocalBusiness`-Markup: ein für Besucher unsichtbarer Steckbrief im Quelltext,
  den Google maschinell ausliest — Adresse, Koordinaten, Öffnungszeiten,
  Bewertungen, Leistungen und Terminbuchung. Dadurch kann Google Öffnungszeiten
  und Sterne direkt im Suchergebnis anzeigen statt nur einen Link.
- Canonical-Tag gesetzt: Die Seite ist mit und ohne „www“ erreichbar. Das Tag
  sagt Google, welche der beiden Adressen die richtige ist — sonst bewertet die
  Suchmaschine zweimal denselben Inhalt und teilt die Punkte auf.
- Eigene Fehlerseite: Wer eine Adresse falsch eintippt, landet auf einer Seite im
  Design des Ladens mit Weg zurück — nicht auf der grauen Standardmeldung des
  Hosting-Anbieters.
- Seiten für Impressum und Datenschutz eingebunden. Die Texte dafür wurden vom
  Auftraggeber über einen Rechtstext-Generator gestellt.

**Aktueller Stand:** Die Seite ist live und in Benutzung. Drei Bildplätze warten
noch auf Fotos, die erst gemacht werden müssen. Der Online-Shop ist in
Vorbereitung.

---

## Der Fehler, den ich gefunden habe

**Was los war:** Nach dem ersten Deployment lagen **2.239 Dateien** öffentlich auf
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

### Zwei weitere Punkte aus dem Projekt

- **Cloudflare Pages statt Workers.** Die aktuelle Oberfläche führt Projekte
  standardmäßig über Workers, das braucht eine eigene Zone. Pages kommt mit zwei
  DNS-Einträgen aus und war hier der richtige Weg.
- **Bei der Wettbewerbsanalyse prüfen, welche Adresse genau in der Suche steht.**
  Hier war es nicht die Hauptdomain des Wettbewerbers, sondern eine Subdomain —
  die bereits den Laden des Auftraggebers beschrieb. Ohne diese Prüfung wäre die
  ganze Analyse falsch gewesen.

---

## Projekt: Landingpage und Exposés für meinen Arbeitgeber

Eingestellt bin ich im technischen Kundensupport eines E-Commerce-Unternehmens.
Als dort ankam, dass ich mich intensiv mit KI-gestützter Entwicklung beschäftige,
kam die Anfrage, ob ich Produkt-Exposés und eine Landingpage übernehmen kann.

Beides habe ich gebaut — neben der eigentlichen Stelle, nicht als Teil davon.

Das ist der Grund, warum ich mich auf diese Anzeige bewerbe: Die Arbeit, die dort
nebenbei entstanden ist, ist die, die ich hauptberuflich machen möchte.

---

## Wie ich arbeite

Beide Projekte sind nicht dadurch entstanden, dass ich einer KI gesagt habe, was
ich will, und das Ergebnis übernommen habe. Dahinter steht ein Ablauf, den ich
mir über zwei Jahre aufgebaut habe.

### 1. Wissen sammeln, bevor gebaut wird

Bei jedem neuen Thema recherchiere ich zuerst — Fachvideos, Dokumentation,
Praxisberichte. Was brauchbar ist, landet nicht in einem Lesezeichen, sondern in
einer eigenen Wissensablage: rund 20 Themenbereiche als durchsuchbare
Textdateien, aufgebaut mit Obsidian.

Der entscheidende Teil: **Claude Code hat direkten Zugriff auf diese Ablage.**
Damit arbeite ich nicht mit einer KI, die bei null anfängt, sondern mit einer,
die meine Notizen, Projektstände und festgelegten Regeln kennt.

### 2. Bauen und dabei hinterfragen

Während der Umsetzung frage ich gezielt nach: Ist das so gelöst, wie es üblich
ist? Was passiert hier technisch? Was liegt danach tatsächlich auf dem Server?

Diese Fragen kosten Zeit und finden Fehler, die im fertigen Ergebnis nicht zu
sehen sind — siehe oben.

### 3. Aus dem Ergebnis eine wiederverwendbare Anleitung machen

Wenn etwas funktioniert, schreibe ich den Weg als **Skill** fest: eine
strukturierte Anleitung, die Claude Code beim nächsten Mal selbst befolgt. Aus
dem Komfortzone-Projekt ist so ein Ablaufplan für statische Websites entstanden —
Aufbau, Deployment, Domain-Umzug, strukturierte Daten, Prüfschritte.

Der Effekt: Das zweite Projekt dieser Art beginnt nicht wieder bei null. Ändert
sich etwas, wird der Skill überarbeitet statt die Arbeit wiederholt.

### 4. Werkzeuge bauen, wo Handarbeit anfällt

Was sich nicht als Anleitung lösen lässt, wird ein kleines Programm — siehe
[Selbstgebaute Werkzeuge](#selbstgebaute-werkzeuge).

> **Warum das hier steht:** Die Frage bei KI-gestützter Arbeit ist nicht, ob
> jemand ein bestimmtes Werkzeug schon kennt. Sie ist, wie schnell und wie
> gründlich sich jemand ein neues erschließt. Dieser Ablauf ist meine Antwort
> darauf, und er funktioniert unabhängig vom Thema.

---

## Werkzeuge und Können

| Bereich | Womit |
|---|---|
| KI-gestützte Entwicklung | Claude Code (Terminal), eigene Skills, Claude, ChatGPT |
| Website | HTML, CSS, Git, GitHub |
| Hosting und Domains | Cloudflare Pages, DNS |
| Auffindbarkeit | `LocalBusiness`-Markup, Seitenstruktur, Canonical |
| Server | Linux, Incus-Container, Nextcloud, WordPress-Migration |
| Wissensablage | Obsidian, mit direktem Zugriff durch Claude Code |

**Was ich damit gemacht habe:**

- Website von Grund auf gebaut und live geschaltet, mit automatischem Deployment
- Domain umgezogen, ohne dass die Seite offline ging
- `LocalBusiness`-Markup gesetzt: Adresse, Koordinaten, Öffnungszeiten,
  Bewertungen, Leistungen und Buchungsaktion maschinenlesbar hinterlegt
- Schriften lokal eingebunden, sodass beim Seitenaufruf keine externen Server
  kontaktiert werden
- Ladezeit und Übertragungsmenge gemessen und gesenkt
- Dokumentation und Anleitung übergeben, sodass die Auftraggeberinnen selbst
  weiterarbeiten können
- Containerbasierte Serverumgebungen aufgesetzt und WordPress-Seiten migriert

---

## Was ich noch nicht gemacht habe

- Ad Creatives für Google und Meta
- Tracking-Pixel und Kampagnen-Auswertung
- Mehrere Kundenprojekte parallel

---

## Selbstgebaute Werkzeuge

Wenn mich in der täglichen Arbeit etwas ausbremst, baue ich mir ein Werkzeug
dafür.

**DiktierMaus** — ein Diktierprogramm für den eigenen Rechner. Ich arbeite viel
im Terminal und wollte Anweisungen nicht mehr tippen. Taste gedrückt halten,
sprechen, loslassen — der Text steht im Eingabefeld. Die Spracherkennung läuft
lokal, es geht nichts an einen fremden Dienst. Zusätzlich legt das Programm die
letzten Texte ab, sodass nichts verloren geht, wenn ein Fenster abstürzt.

**Umbenennen von Rechnungen** — liest eingehende Rechnungen und benennt sie nach
ihrem Inhalt, statt dass ich jede einzeln öffne.

Beide sind aus einem eigenen Ärgernis entstanden, nicht aus einer Übung.

---

## Hintergrund

Staatlich geprüfter Fahrzeugtechniker, davor Kfz-Meister. Zwei Jahre
Bordnetzentwicklung bei BMW und VW, danach Konstruktion mit CATIA V5. Heute im
E-Commerce tätig.

Den Umgang mit KI-gestützter Entwicklung habe ich mir selbst angeeignet — über
Fachvideos, Dokumentation und gebaute Projekte, die ich mitschreibe.

**Weitere Repos:**
[`lms-to-wordpress-migration`](https://github.com/mazelwinkler-oss/lms-to-wordpress-migration) ·
[`wg-migration-tool`](https://github.com/mazelwinkler-oss/wg-migration-tool)
