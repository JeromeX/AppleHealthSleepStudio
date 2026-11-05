<div align="center">

# 🌙 Apple Health Sleep Studio 2.4.3

### Die lokale Analyseplattform für Schlaf-, Herz-Kreislauf- und Aktivitätsdaten der Apple Watch

**Windows · C# · .NET 10 · WPF · SQLite**

</div>

---

## 🧭 Produkt auf einen Blick

Apple Health Sleep Studio ist eine Windows-Desktopanwendung zur grafischen Auswertung von Gesundheits- und Schlafdaten, die von einer **Apple Watch** erfasst und über einen Apple-Health-Export bereitgestellt werden.

Die Anwendung bündelt Schlafverläufe, Vitalwerte, Aktivitätsdaten und Datenabdeckung in einer einheitlichen Arbeitsoberfläche. Messwerte können auf Tages- und Zeitraumebene betrachtet und – soweit Einzelmesspunkte vorhanden sind – bis auf Datum und Uhrzeit untersucht werden.

Der Schwerpunkt liegt auf einer nachvollziehbaren, datenschutzorientierten und visuell aufbereiteten Darstellung. Die Anwendung erstellt **keine medizinischen Diagnosen** und ersetzt keine ärztliche Beurteilung.

## 🧩 Funktionsbereiche

### 🏠 1. Dashboard und Arbeitsbereiche

- Zentrale Übersicht der verfügbaren Schlaf-, Vital- und Aktivitätsdaten.
- Grafische Kacheln und Diagramme statt einer rein tabellarischen Darstellung.
- Orientierung am aktuell ausgewählten Zeitraum.
- Sichtbare Unterscheidung zwischen vorhandenen Messwerten und fehlender Datenabdeckung.
- Einheitliche Navigation zwischen den Analysebereichen.

### 🗓️ 2. Vollseiten-Kalender

- Großflächiger Kalender direkt innerhalb der Anwendung.
- Navigation durch Monate und Tage.
- Direkte Auswahl eines Datums zur Betrachtung der zugehörigen Daten.
- Tagesabdeckung als Hinweis darauf, für welche Tage Messdaten vorliegen.
- Zusätzliche Tagesdetails und Zusammenfassungen.
- Zwischenspeicherung von Monatsdaten zur beschleunigten Navigation.
- Aktualisierung der Kalenderdaten nach einem Import oder Datenbank-Reset.

### 🌙 3. Schlafanalyse

- Darstellung der erfassten Schlafzeiträume.
- Auswertung der vorhandenen Schlafphasen:
  - Wach
  - REM
  - Kernschlaf
  - Tiefschlaf
- Tages- und Zeitraumzusammenfassungen.
- Einzelnacht-Auswertung mit Bezug auf den ausgewählten Kalendertag.
- Sichtbare Datenlücken, statt nicht vorhandene Messungen als Nullwerte darzustellen.
- Ein Apple-Schlafindex wird nur ausgewiesen, wenn ein entsprechender Wert tatsächlich im importierten Datensatz vorhanden ist. Es wird kein Ersatz- oder Fantasiewert berechnet.

### ❤️ 4. Herz-Kreislauf- und Vitalwertanalyse

Grafische Zeitreihen und – soweit gespeichert – auswählbare Einzelmesspunkte für:

- Herzfrequenz
- Ruheherzfrequenz
- Herzfrequenzvariabilität (HRV)
- Sauerstoffsättigung (SpO₂)
- Atemfrequenz

Messpunktdetails können Datum, Uhrzeit, Messwert, Einheit und Quellenkontext enthalten. Die Darstellung richtet sich nach den tatsächlich importierten Daten; nicht jeder Datentyp wird von jeder Apple-Watch-Generation oder in jedem Export bereitgestellt.

### 📈 5. Interaktive Messpunktdiagramme

- Zeitliche Darstellung einzelner Messwerte.
- Auswahl einzelner Datenpunkte, sofern entsprechende Rohmesspunkte vorhanden sind.
- Detailinformationen beim Überfahren oder Auswählen eines Datenpunkts.
- Anzeige von Datum, Uhrzeit, Messwert, Einheit und Messpunktkontext.
- Langzeitdiagramme über den gesamten ausgewählten Zeitraum.
- Keine künstliche Verbindung über fehlende Messintervalle, wenn dadurch eine kontinuierliche Messung suggeriert würde.

### 🚶 6. Aktivitätsanalyse

Grafische Auswertung der verfügbaren Aktivitätsdaten, insbesondere:

- Schritte
- Aktive Energie
- Trainingsdauer
- Geh- und Laufdistanz

Die verfügbaren Diagramme und Zusammenfassungen hängen davon ab, welche Werte im Apple-Health-Export vorhanden und eindeutig der Apple Watch zugeordnet sind.

### 🧮 7. Datenabdeckung und Datenqualität

- Übersicht über vorhandene Datentage und Messwertkategorien.
- Darstellung von Messpunktzahlen und zeitlicher Abdeckung.
- Erkennbare Datenlücken.
- Trennung zwischen fehlenden Messwerten und tatsächlich gemessenen Nullwerten.
- Verständliche Bezeichnungen und Einheiten statt technischer HealthKit-Kennungen.
- Quellen- und Zeitstempelkontext, soweit die Quelldaten diese Angaben enthalten.

### 🗂️ 8. Datenbibliothek und Kategorien

- Gruppierung der verfügbaren Datentypen in verständliche Kategorien.
- Grafische Darstellung von Kategorien und Messpunktumfang.
- Benutzerfreundliche Namen und Einheiten.
- Einordnung der Datensätze anhand ihrer Quelle und ihres Zeitbezugs.
- Anzeige nur der Daten, die im ausgewählten Bestand tatsächlich vorhanden sind.

### 📥 9. Apple-Watch-Datenimport

- Verarbeitung von Apple-Health-Exporten im XML-Format beziehungsweise eines ZIP-Exports mit `export.xml`.
- Übernahme ausschließlich von Datensätzen, die eindeutig der Apple Watch zugeordnet werden können.
- Keine Vermischung mit nicht eindeutig zuordenbaren iPhone-, Drittanbieter- oder sonstigen Quellen.
- Inkrementeller Import: Bereits gespeicherte Messpunkte werden nicht erneut als neue Datensätze übernommen.
- Deduplizierung über die Identität der Messpunkte.
- SHA-256-Fingerprinting zur Erkennung identischer Export-, Zeitraum- und Kategorieauswahlen.
- Erneute Verarbeitung geänderter Exporte mit anschließender Datenbank-Deduplizierung.
- Fortschritts- und Statusinformationen während umfangreicher Importvorgänge.

### 📋 10. Tagesprotokoll

- Eigenständiger Bereich für ein verständliches Gesundheits-Tagesprotokoll.
- Zusammenfassung der für den ausgewählten Tag tatsächlich vorhandenen Schlaf- und Vitaldaten.
- Tages- und Zeitraumdarstellung.
- Verständliche Beschriftungen und Einheiten.
- Hinweise auf fehlende oder nicht verfügbare Messwerte.
- Sachliche Aufbereitung für die persönliche Dokumentation und als Gesprächsgrundlage für einen Arzttermin.

### 📄 11. PDF-Bericht

- Mehrseitiger PDF-Bericht aus dem Tagesprotokoll und den ausgewählten Zeitraumdaten.
- Übersichtliche Zusammenfassungen und Diagramme.
- Einbindung relevanter Schlaf-, Vital- und Verlaufsinformationen, soweit Daten vorhanden sind.
- Vektorlogo und dynamische Copyright-Angabe im Format `© {Jahr} Malte Speck`.
- Kennzeichnung von Datenlücken und Datenhinweisen.
- Keine Diagnose, keine medizinische Risikoeinstufung und keine erfundenen Messwerte.

### 🔐 12. Lokale Datenspeicherung und Datenschutz

- Lokale Speicherung auf dem Windows-Rechner.
- SQLite-basierte Gesundheitsdatenbank mit Verschlüsselung über SQLite3MC/ChaCha20.
- Schutz des Datenbankschlüssels über Windows DPAPI im Kontext des jeweiligen Windows-Benutzerkontos.
- Benutzerbezogene Datenhaltung: Windows-Konten erhalten getrennte lokale Datenbestände.
- Gesundheitsdatenbank und Schlüssel werden nicht als Cloud-Datenbestand vorausgesetzt.
- Der DPAPI-geschützte Schlüssel ist an den jeweiligen Windows-Benutzerkontext gebunden. Das bloße Kopieren der Datenbank auf ein anderes Benutzerkonto macht sie nicht lesbar.

### 🌐 13. Sprache und Benutzeroberfläche

- Deutsch und Englisch.
- Einheitliche Bezeichnungen in Navigation, Diagrammen und Auswertungen.
- Fokus auf grafische Arbeitsbereiche und verständliche Messwertdarstellung.
- Datums- und Zeitbezug für die lokale Auswertung.
- Dynamische Jahreszahl im Copyright.

### 🧹 14. Deinstallation und Datenkontrolle

- Separater Uninstaller mit eigenem Programmsymbol.
- Entfernen der Programmdateien und des Programmverzeichnisses.
- Persönliche Gesundheitsdaten bleiben bei einer normalen Deinstallation standardmäßig erhalten.
- Eine vollständige Löschung der lokalen Daten ist eine gesonderte, ausdrücklich zu bestätigende Aktion.
- Die Datenlöschung muss klar zwischen dem aktuellen Windows-Benutzerkonto und einer optionalen rechnerweiten Bereinigung unterscheiden.

## 🛠️ Technologie und Architektur

| Bereich | Technologie / Umsetzung |
|---|---|
| Programmiersprache | C# |
| Desktop-Oberfläche | WPF und XAML |
| Plattform | Windows x64 |
| Zielframework | `.NET 10` / `net10.0-windows` |
| Veröffentlichungsziel | `win-x64` |
| Release-Format | Self-contained Single-File-Anwendung |
| Lokale Datenhaltung | SQLite-basierte Datenbank |
| Datenbankverschlüsselung | SQLite3MC / ChaCha20 |
| Schlüssel- und Einstellungsabsicherung | Windows DPAPI |
| Importformat | Apple-Health-XML-Export |
| Integritätsprüfung von Importen | SHA-256-Fingerprints |
| Berichtsausgabe | PDF |

### 📦 Laufzeitvoraussetzungen der veröffentlichten Anwendung

Das vorgesehene Release ist als **self-contained Single-File-Anwendung für Windows x64** konfiguriert. Die .NET-Laufzeit wird damit in die veröffentlichte Anwendung eingebunden; eine separat installierte .NET-Runtime ist für dieses konkrete Veröffentlichungsprofil nicht vorgesehen.

Die konkrete Release-Datei muss nach jedem Build auf Zielsystemen geprüft werden. Insbesondere müssen Start, Datenbankzugriff, Import, Diagramme, PDF-Ausgabe und Deinstallation getestet werden.

## 🔒 Grenzen und fachliche Einordnung

- Die Anwendung ist auf Daten aus der Apple Watch beschränkt, die im Apple-Health-Export eindeutig zugeordnet werden können.
- Nicht jeder Export enthält jeden Messwert oder jede Messfrequenz.
- Fehlende Messungen werden nicht durch erfundene Werte ersetzt.
- Ein vorhandener Apple-Schlafindex wird nicht durch einen selbst berechneten Score ersetzt.
- Diagramme und Zusammenfassungen sind deskriptive Auswertungen und keine medizinische Diagnose.
- Persönliche Daten bleiben lokal und sind nicht mit einem automatischen Cloud-Synchronisationsdienst gleichzusetzen.

## 🚫 Bewusst nicht Bestandteil des Produkts

- Keine KI-Funktionen oder Anbindung.
- Kein Online-KI-Dienst.
- Kein Update-Agent und keine integrierte Update-Verwaltung.
- Keine automatische Übermittlung persönlicher Gesundheitsdaten an einen externen Analysedienst.

---

<div align="center">

**Apple Health Sleep Studio 2.4.3**  
*Schlaf- und Gesundheitsdaten verständlich visualisieren. Lokal auswerten. Datenhoheit behalten.*

---
<img width="2542" height="1362" alt="2026-11-05 09_32_47-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/4372b050-5325-4aa0-adf1-a5018f1ac5f8" />
<img width="2542" height="1362" alt="2026-11-05 09_33_02-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/df27dd58-1630-4cb4-b12e-76d1134cb794" />
<img width="2542" height="1362" alt="2026-11-05 09_33_14-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/01a87663-7fcf-412d-b2ea-f86b7eae081a" />
<img width="2542" height="1362" alt="2026-11-05 09_33_32-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/324e4842-ae54-40c5-82e6-caf915e9c847" />
<img width="2542" height="1362" alt="2026-11-05 09_35_30-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/9196f8e5-a144-4b9e-9027-10e65e88f36c" />
<img width="2542" height="1362" alt="2026-11-05 09_33_49-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/c3f537c7-7b4c-4fbc-be5b-a8652621ef61" />
<img width="2542" height="1362" alt="2026-11-05 09_33_56-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/dbc29df7-41bf-4867-8798-a0c0bcffca5f" />
<img width="2542" height="1362" alt="2026-11-05 09_34_04-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/9682c9ee-5f48-416e-be27-7dd09ad99afd" />
<img width="2542" height="1362" alt="2026-11-05 09_34_11-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/6f003a46-0da4-497d-94e5-5d027fa6b669" />
<img width="2542" height="1362" alt="2026-11-05 09_34_24-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/ccf2fa47-e23d-45b1-80b8-0d1c0f43b578" />
<img width="2542" height="1362" alt="2026-11-05 09_34_30-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/8459a202-18c4-427b-844d-a59f6747ed62" />
<img width="2542" height="1362" alt="2026-11-05 09_34_51-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/245ef5bd-c471-4a83-aeec-db4167e5d2bd" />
<img width="2542" height="1362" alt="2026-11-05 09_35_01-Apple Health Sleep Studio" src="https://github.com/user-attachments/assets/15345e18-8869-47a6-ab9d-ed1768bb4864" />
</div>
