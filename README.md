# wirtschaftsstandort
Wirtschaftsstandort auf einen Blick
Mehrsprachiges Modul (Deutsch, Englisch, Französisch, Italienisch) für graubuenden.ch: sechs Kennzahlen zum Wirtschaftsstandort Graubünden mit Eröffnungsanimation.
Eingebunden auf: (Seiten in Drupal eintragen, je Sprache)
Verantwortlich: (Name eintragen)
Design: GRF Evolution Styleguide (Granit-Familie), Schriften aus dem Repository `grf-fonts`
Einbindung: iFrame in Drupal, Höhenanpassung über den Auto-Height-Block in `index.html`
Sprache
Das Modul läuft im iFrame und kann die Sprache der Seite nicht direkt lesen. Die Sprache wird deshalb so bestimmt:
URL-Parameter `lang` (zuverlässig): `lang=de`, `lang=en`, `lang=fr` oder `lang=it`. In Drupal trägt jede Sprachversion der Seite ihre eigene iFrame-URL mit dem passenden `lang`.
Pfad der einbettenden Seite (Zusatz, nicht garantiert): enthält `document.referrer` einen Pfad wie `/fr/…`, wird diese Sprache übernommen. Viele Browser geben bei fremden Domains nur die Domain weiter, dann greift dieser Schritt nicht.
Standard: Deutsch.
Pro Sprache gelten eigene Zahlenformate (Deutsch 110’000 / 1.4, Englisch 110,000 / 1.4, Französisch 110 000 / 1,4, Italienisch 110’000 / 1,4). Die Übersetzungen stehen im Skript unter `var T`.
Zahlen über die URL steuern
Alle Parameter sind optional. Fehlende oder ungültige Werte bleiben beim Standardwert.
Parameter	Bedeutung	Standard
`lang`	Sprache (`de`, `en`, `fr`, `it`)	`de`
`einzugsgebiet`	Menschen im Einzugsgebiet, in Mio.	1.4
`erwerbstaetige`	Erwerbstätige im Kanton	110000
`jahr`	Stichjahr der Erwerbstätigen (4 Ziffern)	2024
`steuersatz_max`	Gewinnsteuersatz, oberer Wert in %	14.77
`steuersatz_min`	Gewinnsteuersatz, unterer Wert in %	7.83
`studierende`	Studierende an Bündner Hochschulen	2500
`industrieflaeche`	Verfügbare Industriefläche in m²	300000
`steuererleichterung`	Steuererleichterung bis zu, in % (0–100), auch in der Fussnote	100
Eingaben dürfen Dezimalkomma (`1,45`) und Tausendertrennzeichen (`110’000` oder `110'000`) enthalten.
Beispiel Deutsch mit allen Standardwerten:
```
https://graubuendenferien-sudo.github.io/REPO-NAME/?lang=de&einzugsgebiet=1.4&erwerbstaetige=110000&jahr=2024&steuersatz_max=14.77&steuersatz_min=7.83&studierende=2500&industrieflaeche=300000&steuererleichterung=100
```
Für die anderen Sprachen nur `lang=de` durch `lang=en`, `lang=fr` oder `lang=it` ersetzen.
Zahlen und Texte aktualisieren
Zahlen: im CMS (Drupal) die URL der iFrame-Komponente anpassen, in allen vier Sprachversionen. Im Code ist nichts zu ändern.
Texte: Die Übersetzungen stehen im Skript unter `var T`. Quellenangaben und Stichjahre sowie die Übersetzungen vor der Veröffentlichung von der fachlich verantwortlichen Person bzw. Muttersprachlern prüfen lassen.
