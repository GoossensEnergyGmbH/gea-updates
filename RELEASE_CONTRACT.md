# GEA – Vertrag für den öffentlichen Updatekanal

Dieses Repository verteilt ausschließlich freigegebene Windows-Versionen von **GEA – Goossens Energy Analyse**. Der vollständige Quellcode wird in einem getrennten privaten Repository verwaltet.

## 1. Releasekennzeichnung

Jede produktive Version verwendet einen semantischen Git-Tag im Format:

```text
vMAJOR.MINOR.PATCH
```

Beispiel: `v0.2.0`.

## 2. Erforderliche Release-Dateien

Ein produktiver Windows-x64-Release enthält mindestens:

- einen Authenticode-signierten NSIS-Installer `*-setup.exe`,
- die zu diesem Installer gehörende Tauri-Updater-Signatur `*.exe.sig`,
- die maschinenlesbare Updateinformation `latest.json`,
- Versionshinweise.

Eine zusätzliche MSI-Datei ist zulässig, aber für den automatischen Updatekanal nicht erforderlich.

## 3. Struktur von `latest.json`

```json
{
  "version": "0.2.0",
  "notes": "Versionshinweise",
  "pub_date": "2026-08-27T00:00:00.000Z",
  "platforms": {
    "windows-x86_64": {
      "signature": "INHALT_DER_GENERIERTEN_SIG_DATEI",
      "url": "https://github.com/GoossensEnergyGmbH/gea-updates/releases/download/v0.2.0/Goossens%20Energy%20Analyse_0.2.0_x64-setup.exe"
    }
  }
}
```

Die `signature` enthält den vollständigen Text der von Tauri erzeugten Signaturdatei, nicht deren Dateipfad.

## 4. Stabiler Abrufpunkt

GEA ruft die jeweils aktuelle Updateinformation ausschließlich über folgenden stabilen Endpunkt ab:

```text
https://github.com/GoossensEnergyGmbH/gea-updates/releases/latest/download/latest.json
```

## 5. Freigabekriterien

Ein Release darf nur veröffentlicht werden, wenn:

- alle Fach-, Persistenz-, Struktur- und Sicherheitstests bestanden sind,
- der Windows-Installer erfolgreich erzeugt wurde,
- die Windows-Authenticode-Signatur den Status `Valid` besitzt,
- die separate Tauri-Updater-Signatur vorhanden ist,
- Version, Git-Tag, Installername und `latest.json` übereinstimmen,
- die Freigabe aus der geschützten Releasepipeline des privaten GEA-Quellrepositories erfolgt.

## 6. Nicht zulässige Inhalte

In diesem öffentlichen Repository dürfen nicht gespeichert werden:

- Anwendungsquellcode,
- private Signatur- oder Zertifikatsschlüssel,
- Passwörter, Tokens oder API-Zugangsdaten,
- lokale Datenbanken,
- Projekt- oder Kundendaten,
- nicht freigegebene Teststände.

## 7. Signaturtrennung

Die Windows-Authenticode-Signatur bestätigt den Herausgeber des Installers. Die Tauri-Updater-Signatur schützt den automatischen Updateprozess. Beide Prüfungen sind voneinander unabhängig und für produktive Releases erforderlich.
