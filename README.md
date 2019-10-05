## 1. Text-Editor der Wahl

Gewählt wurde ATOM in der Version 1.40.1

## 2. Eine Python-Bibliothek

### OpenCV
<p>OpenCV beschäftigt sich vor dem Hintergrund von Big Data und künstlicher Intelligenz mit Computer Vision. Hierdurch wird eine Objekt- und Personenerkennung ermöglicht. Dem Computer wird dabei ein Bild als multidimensionales Array repräsentiert und mit Algorithmen/Methoden verknüpft (vgl. Moser, Oliver: Einführung in Computer Vision mit OpenCV und Python, in "codecentric Blog", URL: https://blog.codecentric.de/2017/06/einfuehrung-in-computer-vision-mit-opencv-und-python/).</p>
<p>Danach ist es möglich, etwa durch eine Kamera im Auto, ein Straßenschild zu erkennen und die dort angegebene Geschwindigkeitsbegrenzung für das Fahrzeug zu übernehmen, so dass die Geschwindigkeit automatisch nicht übertreten wird.</p>
<p>In Bibliotheken könnte dies für eine automatische Titelerkennung genutzt werden, was mit entsprechenden Metadaten des Mediums verknüpft werden könnte. Ferner könnten auch Barcodes eingelesen werden, ohne dabei ein Lasergerät zu verwenden.</p>

## 3. Eine Fehlermeldung und Ihre Lösung

### Aufgetretener Fehler:

<p>NameError                                 Traceback (most recent call last) <br>
<ipython-input-4-c81f64490007> in <module> <br>
----> 1 for PMID in PMIDs: <br>
      2     full_url = base_url + PMID <br>
      3     PMID_json_data = urllib.request.urlopen(full_url).read() <br>
      4     PMID_data = json.loads(PMID_json_data) <br>
      5     print("TITEL:            " + PMID_data ["result"] ["PMID"]["title"]) <br>

NameError: name 'PMIDs' is not defined </p>

### Problem:

Die zuvor in einer Liste angegebenen Pub-Med-IDs können nicht abgerufen werden, da das Programm nicht weiß, worum es sich bei der bloßen Bezeichnung "PMID" in Zeile 5 handelt.

### Lösung:

 print("TITEL:            " + PMID_data ["result"] [str(PMID)]["title"])

### Begründung:

Die in der Liste als Strings angelegten Pub-Med-IDs werden durch die Verwendung von str() in Zeile 5 als Strings gekennzeichnet. Das Programm erkennt nun, dass es sich bei der Angabe um die Strings aus der Liste in der vorangegangenen Definition handelt und kann diese abrufen.

## 4. Was ist JupyterLab?

<p>JupyterLab kann als Weiterentwicklung von Jupyter Notebook angesehen werden.</p>

<p>Jupyter Notebook ist eine web-basierte, interaktive Computerumgebung und dient vorwiegend zur Datenanalyse und der Visualisierung von Daten (vgl. Stack Overflow: URL: https://stackoverflow.com/questions/50982686/what-is-the-difference-between-jupyter-notebook-and-jupyter-lab).</p>

<p>JupyterLab bietet im Gegensatz zu Jupyter Notebook eine Arbeitsumgebung, in der Texteditoren, Terminals und Data-file-viewers sowie mehrere Notebooks nebeneinander ausgeführt werden können. Während es mit Umständen verbunden ist, in Jupyter Notebook Anpassungen vorzunehmen und Erweiterungen hinzuzufügen, ist es eine der Stärken von JupyterLab, aufgrund einer modularen Struktur Anpassungen und Erweiterungen vorzunehmen.
JupiterLab ist zu bestehenden Jupyter Notebooks vollständig kompatibel, sodass diese in JupyterLab implementiert werden können (vgl. JupyterLab is Ready for Users, in: "Jupyter Blog", URL: https://blog.jupyter.org/jupyterlab-is-ready-for-users-5a6f039b8906).</p>

Zudem ist JupyterLab eher als IDE konzipiert (vgl. Stack Overflow).
