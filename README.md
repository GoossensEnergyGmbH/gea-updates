# GEA Updates

Dieses Repository ist der offizielle öffentliche Updatekanal für **GEA – Goossens Energy Analyse** der Goossens Energy GmbH.

Es enthält ausschließlich:

- freigegebene Windows-Installations- und Updatepakete,
- die zugehörigen Tauri-Updater-Signaturen,
- die maschinenlesbare Updateinformation `latest.json`,
- kurze Versionshinweise.

Der Quellcode der Anwendung, private Signaturschlüssel, Passwörter, Projektdateien und Kundendaten werden hier nicht veröffentlicht.

GEA prüft beim Programmstart, ob eine neuere Version vorhanden ist. Vor der Installation wird jedes Paket kryptografisch gegen den in der Anwendung hinterlegten öffentlichen Updater-Schlüssel geprüft. Nicht von Goossens Energy freigegebene Pakete werden abgelehnt.

Die verbindliche Struktur eines Releases ist in [`RELEASE_CONTRACT.md`](RELEASE_CONTRACT.md) beschrieben. `latest.example.json` dient ausschließlich als Schema- und Integrationsbeispiel und darf nicht als produktive Updateinformation verwendet werden.

Copyright © 2026 Goossens Energy GmbH. Alle Rechte vorbehalten.
