# interdesk – Projektstruktur

## Überblick
Statische Website mit mehreren HTML-Unterseiten, gemeinsamer Navigation, Footer und zentralem Styling.

## Struktur
- Startseite: index.html
- Datenschutz: datenschutz.html
- Nutzungsbedingungen: terms.html
- Projekte: projects.html
- Zusatzseiten: construction1.html, hero-proposals.html
- Stylesheets: newstyle.css (primär), styles.css (legacy/zusätzlich)
- Assets: img/

## Architekturprinzipien
- Gemeinsames Layout pro Seite: Navigation → Main-Content → Footer.
- Zentrales Styling über newstyle.css.
- Wiederverwendete UI-Patterns: .navigation, .main-content, .content, .footer.

## Navigation
- Hauptnavigation (Desktop + Mobile) verlinkt auf Startseite und Unterseiten.
- Footer enthält Datenschutz, Nutzungsbedingungen und Projekte.

## Pflegehinweise
- Neue Seiten sollen das bestehende Layout und die CSS-Klassen verwenden.
- Änderungen an Navigation/Footern konsistent über alle Seiten ausrollen.