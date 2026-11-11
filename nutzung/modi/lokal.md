(nutzung:modi:lokal)=
# Lokale Ausführung

## Wann lokal arbeiten?

Die lokale Ausführung bietet Ihnen die größte Kontrolle. Sie können offline arbeiten, eigene Daten verwenden, längere Berechnungen durchführen und die OER dauerhaft anpassen. Dafür müssen Sie einmalig eine Python-Umgebung einrichten.

Die lokale Ausführung empfiehlt sich, wenn Sie:

- eigene oder vertrauliche Daten verwenden möchten,
- ohne Zeitlimit und ohne Internetverbindung arbeiten möchten,
- die Notebooks dauerhaft verändern oder erweitern möchten,
- mehr Rechenleistung oder Speicher benötigen, als Cloud-Dienste bieten.

## Voraussetzungen

- Ein Computer mit Windows, macOS oder Linux
- Python 3.9 oder neuer
- Internetzugang für die einmalige Installation der Pakete
- Optional: Git, um das Repository zu klonen
- Für einzelne Kapitel: R oder der SPARQL-Kernel

```{admonition} Python installieren
:class: hinweis

Wenn Python noch nicht installiert ist, laden Sie es von <a href="https://www.python.org/downloads/" class="external-link" target="_blank">python.org</a> herunter. Alternativ können Sie die Anaconda-Distribution verwenden. Achten Sie bei der Installation unter Windows darauf, die Option zum Hinzufügen von Python zum Systempfad zu aktivieren.
```

## 1. OER-Dateien herunterladen

Sie benötigen die Notebooks und alle zugehörigen Dateien aus dem Repository der OER. Das ist nicht das Repository dieser Lernhinweise und auch nicht das `Book_Template`.

**Variante A: Download als ZIP**

1. Öffnen Sie das GitHub-Repository der OER.
2. Wählen Sie **Code → Download ZIP**.
3. Entpacken Sie die ZIP-Datei an einem Ort Ihrer Wahl.

**Variante B: Git clone**

Wenn Git installiert ist, können Sie das Repository klonen:

```bash
git clone https://github.com/organisation/repository-der-oer
```

Ersetzen Sie die Adresse durch die URL der OER, die Sie bearbeiten möchten.

## 2. Python-Umgebung einrichten

Richten Sie im Ordner der OER eine eigene Umgebung ein. So bleiben die Pakete der OER von anderen Python-Projekten getrennt.

### Variante mit `venv`

```bash
cd repository-der-oer
python3 -m venv .venv
```

Aktivieren Sie die Umgebung:

- **macOS oder Linux:**

  ```bash
  source .venv/bin/activate
  ```

- **Windows:**

  ```bat
  .venv\Scripts\activate
  ```

Installieren Sie anschließend die Pakete der OER:

```bash
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

### Variante mit Anaconda

Wenn Sie Anaconda verwenden, können Sie ein projektbezogenes Environment anlegen:

```bash
conda create -p ./conda python=3
conda activate ./conda
python -m pip install -r requirements.txt
```

Der Ordner `conda` bleibt lokal und wird in der Regel nicht in Git gespeichert.

## 3. Jupyter starten

Starten Sie JupyterLab oder Jupyter Notebook im Ordner der OER:

```bash
jupyter lab
```

oder

```bash
jupyter notebook
```

Es öffnet sich ein Browserfenster mit der Dateiübersicht. Navigieren Sie zu dem Notebook, das Sie bearbeiten möchten.

## 4. Notebook öffnen und Kernel auswählen

Öffnen Sie das Notebook und prüfen Sie oben rechts, welcher Kernel ausgewählt ist. Für die meisten Kapitel ist das ein Python-Kernel. Führen Sie die Zellen in der vorgegebenen Reihenfolge aus.

Wenn der Kernel nicht passt, wählen Sie im Menü **Kernel → Change Kernel** den passenden Eintrag.

## Weitere Kernel: R und SPARQL

Einige Kapitel verwenden R oder SPARQL. Diese Kernel müssen zusätzlich installiert werden.

### R

1. Installieren Sie <a href="https://cran.r-project.org/" class="external-link" target="_blank">R</a>.
2. Installieren Sie den R-Kernel in einer R-Konsole:

   ```r
   install.packages("IRkernel")
   IRkernel::installspec(user = FALSE)
   ```

3. Starten Sie Jupyter neu und wählen Sie den R-Kernel aus.

### SPARQL

Installieren Sie den SPARQL-Kernel und registrieren Sie ihn:

```bash
jupyter sparqlkernel install --user
```

Starten Sie Jupyter anschließend neu. Welche Pakete genau benötigt werden, steht in der `requirements.txt` der OER.

## Daten und Dateien

- **Relative Pfade beibehalten:** Die Notebooks erwarten Dateien oft in bestimmten Unterordnern. Verschieben Sie Dateien nur, wenn Sie die Pfade im Code anpassen.
- **Datensätze:** Größere Datensätze sind nicht immer im Repository enthalten. Laden Sie sie aus der OER oder aus dem dort verlinkten Datenrepositorium herunter.
- **Ergebnisse:** Speichern Sie Ihre Ergebnisse in einem eigenen Ordner oder außerhalb des Repositories, wenn Sie die OER nicht verändern möchten.
- **Vertrauliche Daten:** Lokale Ausführung schützt nicht automatisch vor Datenverlust. Erstellen Sie regelmäßig Sicherungen.

## Einzelnes Notebook ausführen

Wenn Sie nur ein Kapitel ausprobieren möchten, können Sie die `.ipynb`-Datei direkt aus der OER herunterladen und in Jupyter öffnen. Das funktioniert gut für in sich geschlossene Notebooks.

Bei Notebooks, die auf andere Dateien oder Datensätze zugreifen, ist die vollständige Repository-Kopie in der Regel der zuverlässigere Weg.

## Probleme lösen

| Problem | Mögliche Ursache | Lösung |
|---|---|---|
| `jupyter: command not found` | Umgebung nicht aktiviert oder Jupyter nicht installiert | Umgebung aktivieren, `python -m pip install jupyterlab` ausführen |
| `ModuleNotFoundError` | Paket fehlt | `python -m pip install -r requirements.txt` ausführen |
| Kernel nicht gefunden | Kernel nicht registriert | Kernel installieren, Jupyter neu starten |
| R-Kernel fehlt | `IRkernel` nicht installiert | `IRkernel::installspec(user = FALSE)` ausführen |
| SPARQL-Kernel fehlt | Kernel nicht registriert | `jupyter sparqlkernel install --user` ausführen |
| Datei nicht gefunden | Falscher Ordner oder fehlender Datensatz | Pfad prüfen, Datensatz herunterladen |
| Notebook läuft sehr langsam | Rechenleistung oder Speicher begrenzt | Zellen einzeln ausführen, andere Programme schließen |

## Für OER-Erstellende

Wie Sie die lokale Entwicklungsumgebung für die Erstellung einer OER einrichten und Jupyter Book bauen, steht in der <a href="https://quadriga-dk.github.io/QUADRIGA-OER-Manual/entwicklung/jupyter_book.html" class="external-link" target="_blank">QUADRIGA-OER-Anleitung</a>.
