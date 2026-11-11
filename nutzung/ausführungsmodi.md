(nutzung:modi)=
# Ausführungsmodi

QUADRIGA-OERs sind Jupyter Books. Je nach OER und Aufgabe können Sie die Inhalte auf drei Arten nutzen:

- **Lesen (Book-Only):** Sie lesen die OER im Browser, ohne etwas zu installieren. Code wird nicht ausgeführt.
- **Cloud-Ausführung:** Sie starten einzelne Notebooks über einen Launch-Button in Google Colab, Binder oder einem JupyterHub. Die Ausführung findet auf einem Server statt.
- **Lokale Ausführung:** Sie laden die OER auf Ihren Computer und führen die Notebooks in Ihrer eigenen Python-Umgebung aus.

Nicht jede OER bietet alle drei Modi an. Kapitel mit ausführbaren Notebooks sind in der Regel durch ein Raketen-Symbol (🚀) gekennzeichnet. Fehlt das Symbol, können Sie das Kapitel trotzdem lesen, aber den Code nicht direkt im Buch ausführen.

## Vergleich der Modi

| Merkmal | Lesen | Cloud | Lokal |
|---|---|---|---|
| **Installation** | keine | keine | Python, Jupyter und ggf. weitere Kernel |
| **Internetverbindung** | erforderlich | erforderlich | nur zum Herunterladen von OER und Paketen |
| **Code ausführen** | nein | ja | ja |
| **Eigene Daten nutzen** | nein | nur eingeschränkt | ja |
| **Änderungen dauerhaft speichern** | nein | je nach Dienst und Konfiguration | ja, auf Ihrem Gerät |
| **Rechenleistung** | – | vom Dienst begrenzt | von Ihrem Gerät abhängig |
| **Typischer Aufwand** | sofort loslegen | Konto bzw. Startzeit des Dienstes | einmalige Einrichtung |

## Welcher Modus passt zu mir?

- **Lesen** ist sinnvoll, wenn Sie sich einen Überblick verschaffen, Inhalte nachschlagen oder nur theoretische Abschnitte bearbeiten möchten.
- **Cloud** ist sinnvoll, wenn Sie Code ausprobieren möchten, ohne Python zu installieren, oder wenn Ihr Gerät für aufwendige Berechnungen nicht ausreicht.
- **Lokal** ist sinnvoll, wenn Sie eigene Daten verwenden, längere Berechnungen durchführen, offline arbeiten oder die OER dauerhaft anpassen möchten.

Sie können jederzeit zwischen den Modi wechseln. Ein im Lesemodus begonnenes Kapitel können Sie später in der Cloud oder lokal erneut öffnen.

## Weiterlesen

- {ref}`Lesen (Book-Only)<nutzung:modi:lesen>`
- {ref}`Cloud-Ausführung<nutzung:modi:cloud>`
- {ref}`Lokale Ausführung<nutzung:modi:lokal>`
- {ref}`Assessment nutzen<nutzung:assessment>`

```{admonition} Hinweis für OER-Erstellende
:class: seealso

Diese Seite richtet sich an Lernende. Wie Sie die Launch-Buttons für Colab, Binder und JupyterHub in einer OER konfigurieren, steht in der <a href="https://quadriga-dk.github.io/QUADRIGA-OER-Manual/technologie/einleitung.html" class="external-link" target="_blank">QUADRIGA-OER-Anleitung</a>.
```
