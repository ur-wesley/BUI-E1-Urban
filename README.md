# Buildtools und CI/CD

## Idee

Meine Idee ist die Generierung eines "Buches" als Ordnerstruktur aus einer Markdown Datei. Dabei lade ich das Markdown und splitte die Datei auf um Kapitel und Seiten zu erstellen. Ich habe mich dabei nur auf das erstellen der Dateien konzentriert und nicht auf die korrekte Darstellung des Markdowns.

Umgesetzt habe ich das mit Gradle. Hauptsächlich führe ich `gradle all` aus, um die Dateien zu generieren. Um den Output zu löschen wird `gradle clean` verwendet.

## Erweiterung

Ich habe die Ausgabe um folgende Punkte erweitert:

- Metadaten wie Seitenanzahl im JSON Format
- Inhaltsverzeichnis im Markdown Format
- GitHub Actions für CI/CD -> die "Bücher" werden automatisch generiert wenn `build.gradle` geändert wird oder eine Änderung im `src` Verzeichnis vorgenommen wird. Die generierten Dateien werden zum Download bereitgestellt.
- Release-Automatisierung -> bei Git-Tags (z.B. `v1.0.0`) wird automatisch ein GitHub Release mit den generierten Dateien erstellt.
