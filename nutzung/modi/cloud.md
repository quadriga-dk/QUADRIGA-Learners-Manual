(nutzung:modi:cloud)=
# Cloud-Ausführung

## Was ist Cloud-Ausführung?

Bei der Cloud-Ausführung laufen die Notebooks auf einem Server. Sie öffnen die OER im Browser und starten ein Notebook über den Launch-Button (🚀). Auf Ihrem eigenen Gerät müssen Sie dafür nichts installieren.

Welcher Dienst sich öffnet, hängt von der OER und dem gewählten Button ab. Die wichtigsten Dienste sind Google Colab, Binder und JupyterHub.

```{admonition} Voraussetzungen
:class: hinweis

Für die Cloud-Ausführung benötigen Sie eine Internetverbindung. Google Colab setzt ein Google-Konto voraus; Binder ist ohne Konto nutzbar; JupyterHub erfordert ein Konto auf dem jeweiligen Hub.
```

## Google Colab

### Notebook öffnen und ausführen

1. Öffnen Sie das gewünschte Kapitel im Lesemodus.
2. Klicken Sie auf **Launch (🚀) → Colab**.
3. Warten Sie, bis Colab das Notebook geöffnet hat.
4. Führen Sie zuerst die Setup-Zellen am Anfang des Notebooks aus.
5. Bearbeiten und starten Sie die weiteren Zellen in der vorgegebenen Reihenfolge.

Colab öffnet nur das ausgewählte Notebook, nicht den gesamten Projektordner. Andere Dateien der OER sind daher nicht automatisch verfügbar.

### Fehlende Pakete installieren

Wenn ein Paket fehlt, erscheint eine Meldung wie `ModuleNotFoundError`. Installieren Sie das Paket dann am Anfang des Notebooks:

```python
%pip install paketname
```

Führen Sie die Zelle einmal aus und starten Sie anschließend die betroffene Zelle erneut. Bei mehreren fehlenden Paketen können Sie sie in einem Befehl zusammenfassen.

### Zugriff auf Dateien

Da Colab nur das Notebook öffnet, müssen Sie zusätzliche Dateien selbst bereitstellen:

- **Aus dem OER-Repository laden:** Wenn die Datei öffentlich auf GitHub liegt, können Sie sie mit `wget` herunterladen:

  ```bash
  !wget https://raw.githubusercontent.com/organisation/repository/main/pfad/datei.csv
  ```

- **Selbst hochladen:** Klicken Sie links auf das Ordner-Symbol und laden Sie die Datei per Drag-and-drop oder über den Upload-Button hoch.

Achten Sie darauf, dass die Datei im gleichen Ordner liegt, den das Notebook erwartet, oder passen Sie den Pfad im Code an.

### Ergebnisse speichern

Colab-Sitzungen sind temporär. Speichern Sie wichtige Ergebnisse deshalb:

- in Google Drive,
- als Download auf Ihrem Computer,
- oder indem Sie das Notebook mit den Ergebnissen herunterladen.

Nach einer längeren Inaktivität oder einem Neustart der Laufzeit müssen Sie die Zellen erneut ausführen.

## Binder

Binder erstellt aus dem Git-Repository der OER eine passende Rechenumgebung. Dabei werden die im Repository definierten Pakete und Versionen installiert.

### Notebook öffnen

1. Öffnen Sie das gewünschte Kapitel.
2. Klicken Sie auf **Launch (🚀) → Binder**.
3. Beim ersten Start kann der Aufbau der Umgebung einige Minuten dauern.
4. Nach dem Start steht Ihnen die vollständige Jupyter-Oberfläche mit allen Dateien der OER zur Verfügung.

### Was Sie wissen sollten

- **Gesamtes Repository verfügbar:** Anders als bei Colab stehen Ihnen alle Dateien der OER zur Verfügung.
- **Temporäre Sitzung:** Änderungen werden nicht in das Repository zurückgeschrieben. Laden Sie wichtige Ergebnisse herunter.
- **Zeitlimit:** Binder-Sitzungen enden nach einer gewissen Inaktivität.
- **Öffentlich zugänglicher Dienst:** Verwenden Sie keine personenbezogenen oder vertraulichen Daten.

## JupyterHub

JupyterHub ist ein Dienst, den Ihre Hochschule oder Organisation selbst betreibt. Sie melden sich mit Ihrem Konto an und erhalten eine eigene Jupyter-Umgebung.

### Notebook öffnen

1. Öffnen Sie das gewünschte Kapitel.
2. Klicken Sie auf **Launch (🚀) → JupyterHub**.
3. Melden Sie sich mit Ihrem Konto auf dem Hub an.
4. Die Dateien der OER werden in Ihre Umgebung kopiert; das Notebook öffnet sich im Browser.

### Was Sie wissen sollten

- **Konto erforderlich:** Nur Personen mit Zugang zum Hub können die Notebooks starten.
- **Pakete:** Welche Pakete installiert sind, legt die Administration des Hubs fest. Fehlt ein Paket, können Sie es in vielen Fällen mit `%pip install paketname` nachinstallieren. Ob es dauerhaft verfügbar bleibt, hängt vom Hub ab.
- **Speicherplatz:** Ob Ihre Dateien nach der Sitzung erhalten bleiben, ist unterschiedlich geregelt. Laden Sie wichtige Ergebnisse herunter, wenn Sie unsicher sind.
- **Unterstützung:** Wenden Sie sich bei Zugangs- oder Speicherproblemen an die IT-Administration Ihres Hubs.

## Vergleich der Cloud-Dienste

| Merkmal | Google Colab | Binder | JupyterHub |
|---|---|---|---|
| **Betreiber** | Google | Binder-Projekt oder eigener BinderHub | Ihre Organisation |
| **Konto** | Google-Konto | kein Konto | Konto auf dem Hub |
| **Dateizugriff** | einzelnes Notebook; Dateien manuell bereitstellen | gesamtes Repository | Dateien werden in Ihre Umgebung kopiert |
| **Umgebung** | vorinstallierte Pakete von Google | aus den Konfigurationsdateien der OER | von der Administration festgelegt |
| **Speichern** | Google Drive oder Download | Download, Sitzung temporär | je nach Konfiguration |
| **Datenschutz** | Ausführung auf Google-Servern | Öffentlich zugänglicher Dienst | Regeln der Organisation |
| **Startzeit** | kurz | beim ersten Mal mehrere Minuten | abhängig vom Hub |

## Datenschutz und Kosten

- Die Nutzung von Colab, Binder und den meisten JupyterHubs ist kostenlos. Für einzelne Dienste können Zugangs- oder Nutzungsbedingungen gelten.
- Verwenden Sie in öffentlichen Cloud-Diensten keine vertraulichen, personenbezogenen oder urheberrechtlich geschützten Daten.
- Für sensible Daten ist die {ref}`lokale Ausführung<nutzung:modi:lokal>` die sicherere Wahl.
- Prüfen Sie vor dem Hochladen, ob Sie die Daten weitergeben dürfen.

## Probleme lösen

| Problem | Mögliche Ursache | Lösung |
|---|---|---|
| Kein Launch-Button sichtbar | Die OER unterstützt diesen Modus nicht | Kapitel lesen oder lokal ausführen |
| `ModuleNotFoundError` | Paket fehlt in der Umgebung | `%pip install paketname` ausführen |
| Datei nicht gefunden | Notebook und Datei liegen nicht im selben Ordner | Datei hochladen, Pfad anpassen oder Repository lokal klonen |
| Sitzung wurde beendet | Zeitlimit oder Inaktivität | Notebook erneut öffnen und Setup-Zellen ausführen |
| Kernel startet nicht | Ressourcenlimit oder technisches Problem | Laufzeit neu starten; bei JupyterHub die Administration kontaktieren |
| Falscher Kernel ausgewählt | Notebook erwartet Python, R oder SPARQL | Kernel im Menü *Kernel* auswählen |

Wenn ein Problem bleibt, nutzen Sie die Feedback-Möglichkeit der OER oder die Support-Angebote des jeweiligen Dienstes.

```{admonition} Für OER-Erstellende
:class: seealso

Wie Sie Launch-Buttons für Colab, Binder und JupyterHub einrichten, steht in der <a href="https://quadriga-dk.github.io/QUADRIGA-OER-Manual/technologie/einleitung.html" class="external-link" target="_blank">QUADRIGA-OER-Anleitung</a>.
```
