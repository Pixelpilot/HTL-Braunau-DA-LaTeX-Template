# HTL-Braunau-DA-LaTeX-Template

LaTeX-Vorlage für Diplomarbeiten an der HTL Braunau

**GitHub Repository:** https://github.com/Pixelpilot/HTL-Braunau-DA-LaTeX-Template

---

## Übersicht

Diese Vorlage ist eine professionelle LaTeX-Umgebung für die Erstellung von Diplomarbeiten an der HTL Braunau. Sie bietet eine strukturierte Grundlage mit automatischer Verwaltung von Literaturverzeichnis, Abbildungsverzeichnis und Listingsverzeichnis.

### Besonderheiten
- KOMA-Script Dokumentenklasse (`scrbook`)
- Deutsche Lokalisierung (Babel)
- Numerische Zitationen mit BibTeX
- Automatische Verzeichnisse (Inhalts-, Abbildungs-, Listings-, Literaturverzeichnis)
- Code-Highlighting mit `listings`
- Professionelle Kopf- und Fußzeilengestaltung
- Unterstützung für Subfiguren

---

## Projektstruktur

```
HTL-Braunau-DA-LaTeX-Template/
├── diplomarbeit.tex              # Hauptdatei (Einstiegspunkt)
├── literature.bib                # Bibliographiedatenbank
├── README.md                     # Diese Datei
├── LICENSE                       # Lizenz
│
├── chapters/                     # Kapitelinhalte
│   ├── 00_deckblatt.tex         # Titelseite
│   ├── 00_abstract.tex          # Abstract und Kurzfassung
│   ├── 00_ee.tex                # Erklärung und Eidesstattliche Versicherung
│   ├── 01_introduction.tex      # Einleitung
│   ├── 02_systemoverview.tex   # Systemüberblick
│   ├── 03_contenta.tex         # Inhalt A
│   ├── 04_contentb.tex         # Inhalt B
│   ├── 05_contentc.tex         # Inhalt C
│   ├── 06_evaluation.tex       # Evaluierung
│   ├── 07_projectmanagement.tex # Projektmanagement
│   ├── 08_futurework.tex       # Zukünftige Arbeiten
│   ├── 09_relatedwork.tex      # Verwandte Arbeiten
│   ├── 10_conclusion.tex       # Fazit/Schlussfolgerung
│   ├── 99_acknowledgements.tex # Danksagungen
│   ├── 99_authors.tex          # Autorenangaben
│   ├── 99_beispielhafte_inhalte.tex  # Beispielkapitel (Zitate, Abbildungen, Code)
│   └── Post-01-literatur.tex   # Literaturverzeichnis
│
├── includes/                     # Konfiguration und Definitionen
│   ├── htl_definintions.tex    # LaTeX-Pakete und Konfigurationen
│   └── htl_c_cmyk_rein.pdf     # HTL-Logo
│
├── media/                        # Medienresourcen
│   ├── images/                 # Abbildungsdateien (.pdf, .png, .jpg)
│   └── code_snippets/          # Code-Beispiele (.cpp, .php, .js, .css, .html)
│
└── build/                        # Build-Verzeichnis
    ├── diplomarbeit.pdf        # Generiertes PDF
    ├── diplomarbeit.aux        # Hilfsdaten
    ├── diplomarbeit.bbl        # Bibliographie-Daten
    ├── diplomarbeit.fdb_latexmk # Build-Cache
    └── literature.bib          # Symlink zur Bibliographie
```

---

## Schnelleinstieg

### Voraussetzungen
- **TeX Live** oder **MikTeX** (aktuelle Version)
- **latexmk** (Automatisiertes Build-System)
- Editor: VS Code mit LaTeX Workshop oder ähnlich

### Build durchführen

```bash
# Im Projektverzeichnis:
cd HTL-Braunau-DA-LaTeX-Template
latexmk -pdf -g -output-directory=build diplomarbeit.tex
```

Das PDF wird unter `build/diplomarbeit.pdf` generiert.

---

## Dateienbeschreibungen

### Hauptdatei: `diplomarbeit.tex`
Die zentrale Datei, die alle Komponenten zusammenführt:
- Definiert die Dokumentklasse und grundlegende Eigenschaften
- Lädt alle Kapitel mit `\input{./chapters/XX_*.tex}`
- Integriert Konfigurationen aus `includes/`
- Erstellt automatisch Verzeichnisse

**Bearbeiten Sie normalerweise nicht diese Datei** – passen Sie stattdessen die Kapitel und Konfiguration an.

### Bibliographie: `literature.bib`
BibTeX-Format-Datei für alle Quellenangaben:

```bibtex
@article{bib:haller2004npr,
  author = {Haller, Martin and others},
  title = {Non-photorealistic Rendering Techniques},
  journal = {Computer Graphics Forum},
  year = {2004}
}

@misc{bib:bradleys1,
  author = {Bradley, Steven},
  title = {Website Navigation and User Experience},
  url = {https://www.vanseo-design.com},
  year = {2015}
}
```

Zitate im Text: `\cite{bib:haller2004npr}` → wird automatisch zu [1]

### Kapitel: `chapters/`

#### Struktur-Kapitel (keine Bearbeitung nötig)
- `00_deckblatt.tex` – Automatisierte Titelseite
- `00_abstract.tex` – Abstract und Kurzfassung
- `00_ee.tex` – Erklärung/Eidesstattliche Versicherung
- `Post-01-literatur.tex` – Wird automatisch generiert

#### Inhalts-Kapitel (zum Bearbeiten)
- `01_introduction.tex` – Einleitung (Motivation, Problemstellung, Gliederung)
- `02_systemoverview.tex` – Überblick über das System/Projekt
- `03_contenta.tex` bis `05_contentc.tex` – Hauptinhalte
- `06_evaluation.tex` – Evaluierung und Ergebnisse
- `07_projectmanagement.tex` – Projektmanagement, Zeitplan
- `08_futurework.tex` – Zukünftige Erweiterungen
- `09_relatedwork.tex` – Verwandte Arbeiten, State of the Art
- `10_conclusion.tex` – Fazit und Schlussfolgerungen
- `99_acknowledgements.tex` – Danksagungen
- `99_authors.tex` – Autorenangaben

#### Beispiel-Kapitel: `99_beispielhafte_inhalte.tex`
Demonstriert Best Practices für:
- **Korrekte Zitationen** (Paraphrasen vs. direkte Zitate)
- **Abbildungseinbindung** (Bilder, Subfiguren)
- **Code-Listings** (mit Syntax-Highlighting)
- **Fußnoten** vs. Zitate
- Unterschiede zwischen `\cite{}` und `\footnote{}`

### Konfiguration: `includes/`

#### `htl_definintions.tex`
Zentrale Konfigurationsdatei mit:
- LaTeX-Paketen (graphicx, listings, hyperref, etc.)
- Farb- und Schriftdefinitionen
- Listings-Konfiguration
- Kopf- und Fußzeilen-Einstellungen
- Makros und Befehle

**Wichtige Einstellungen anpassen:**
```tex
% Sprache
\usepackage[german]{babel}

% Schriftart (optional)
% \usepackage{helvet}  % Helvetica verwenden

% Code-Highlighting
\lstset{...}  % Farben, Schriften, Sprachen konfigurieren
```

### Medien: `media/`
- `images/` – Abbildungsdateien (.pdf, .png, .jpg)
- `code_snippets/` – Quellcode-Dateien (.cpp, .php, .js, .css, .html)

Verwendung in Dokumenten:
```latex
\includegraphics[width=0.5\textwidth]{./media/images/myimage.pdf}
\lstinputlisting[language=Python]{./media/code_snippets/example.py}
```

---

## Arbeitsablauf

### 1. Kapitel bearbeiten
Öffnen Sie die entsprechenden `.tex`-Dateien in `chapters/`:
```tex
\chapter{Mein Kapitelname}
\section{Erste Sektion}
Lorem ipsum...
\subsection{Untersektion}
...
```

### 2. Literaturquellen hinzufügen
Fügen Sie Einträge in `literature.bib` hinzu:
```bibtex
@book{doe2020,
  author = {Doe, John},
  title = {My Great Book},
  publisher = {Publisher},
  year = {2020}
}
```

Zitieren im Text:
```tex
Laut einer Studie \cite{doe2020} ...
```

### 3. Abbildungen und Code einfügen

**Abbildungen:**
```latex
\begin{figure}[H]
  \centering
  \includegraphics[width=0.7\textwidth]{./media/images/diagram.pdf}
  \caption{Kurze Beschreibung der Abbildung}
  \label{fig:mydiagram}
\end{figure}

Siehe Abbildung \ref{fig:mydiagram}.
```

**Code-Listings:**
```latex
\lstinputlisting[language=JavaScript,caption={My Code}]{./media/code_snippets/app.js}
```

### 4. Bauen und Überprüfen
```bash
latexmk -pdf -g -output-directory=build diplomarbeit.tex
```

Das PDF wird unter `build/diplomarbeit.pdf` erzeugt.

---

## Wichtige LaTeX-Befehle

### Struktur
```latex
\chapter{Kapitelname}      % Hauptkapitel
\section{Sektion}          % Hauptsektion
\subsection{Untersektion}  % Untersektion
\subsubsection{Details}    % Weitere Gliederungsebene

\chapter*{Spezialkapitel}  % Kapitel ohne Nummer
\addcontentsline{toc}{chapter}{Name}  % Zur Inhaltsverz. hinzufügen
```

### Zitate und Verweise
```latex
\cite{key}                 % Zitation [1]
\footnote{Text}            % Fußnote
\label{sec:name}           % Referenzpunkt setzen
\ref{sec:name}             % Referenz einfügen
\pageref{sec:name}         % Seitennummer einfügen
```

### Formatierung
```latex
\textbf{Fettgedruckt}      % Fetten Text
\textit{Kursiv}            % Kursiven Text
\texttt{Monospace}         % Code/Monospace
\emph{Hervorgehoben}       % Hervorgehoben
```

### Listen
```latex
\begin{itemize}
  \item Punkt 1
  \item Punkt 2
\end{itemize}

\begin{enumerate}
  \item Punkt 1
  \item Punkt 2
\end{enumerate}
```

---

## Best Practices

### Zitationen – So geht's richtig
1. **Paraphrasen bevorzugen** – Fassen Sie den Gedanke mit eigenen Worten zusammen
2. **Immer belegen** – Jede Aussage aus einer Quelle benötigt `\cite{}`
3. **Ellipsen kennzeichnen** – Verwenden Sie `[...]` bei Auslassungen
4. **Eigene Interpretation hinzufügen** – Erklären Sie, warum die Quelle wichtig ist

Beispiel:
```latex
Der Autor betont, dass Nutzer Navigation oft mit klassischen Menüs 
gleichsetzen \cite{bradley1}. Für unser Projekt bedeutet das, dass 
klare Orientierungspunkte notwendig sind.
```

### Abbildungen
- Verwenden Sie beschreibende Caption-Texte
- Referenzieren Sie jede Abbildung im Text
- Nutzen Sie PDF-Format für Vektorgrafiken
- Benennen Sie Dateien aussagekräftig

### Vergebenheit von Labels
1. **Abbildungen:** `\label{fig:deskriptivername}`
2. **Code:** `\label{code:deskriptivername}`
3. **Kapitel:** `\label{sec:deskriptivername}`

### Künstliche Intelligenz in akademischen Arbeiten

Der Einsatz von KI-Tools wird zunehmend in akademischen Arbeiten verwendet. Diese können bei Recherche, Ideenfindung, Code-Generierung und Texterstellung unterstützen. **Transparenz ist essentiell:** Jeder Abschnitt oder jede Information, die mit KI-Unterstützung erstellt wurde, muss als **Fußnote** gekennzeichnet werden.

**Erforderliche Informationen in der Fußnote:**
- Verwendetes KI-Modell/Tool (z.B. Claude Haiku 4.5, ChatGPT-4, GitHub Copilot)
- Datum der Anfrage
- Kurze Beschreibung des Prompts/der Anfrage
- Art der Bearbeitung durch den Autor (überprüft, angepasst, verändert, etc.)

**Beispiel einer KI-Kennzeichnung im Text:**

```latex
KI-Systeme revolutionieren die Art und Weise, wie wir Informationen 
verarbeiten.\footnote{Dieser Absatz basiert auf einer Anfrage an 
Claude Haiku 4.5 vom 12.02.2026 mit dem Prompt: 
\glqq Schreibe einen Absatz über KI.\grqq ~Das Ergebnis wurde überprüft 
und für akademische Zwecke angepasst.}
```

**Wichtig:**
- Der Autor bleibt verantwortlich für alle Inhalte, auch wenn KI verwendet wurde
- KI-generierte Inhalte müssen kritisch überprüft und angepasst werden
- Achten Sie auf Plagiate und Genauigkeit der KI-Ausgaben
- Verwenden Sie KI-Tools transparent und ethisch korrekt

---

## Häufige Probleme und Lösungen

### Bibliographie zeigt [?]
- **Problem:** BibTeX kann `literature.bib` nicht finden
- **Lösung:** Stellen Sie sicher, dass `build/literature.bib` als Symlink existiert
  ```bash
  ln -sf ../literature.bib build/literature.bib
  ```

### Abbildungen werden nicht angezeigt
- Überprüfen Sie, dass der Pfad korrekt ist: `./media/images/filename.pdf`
- Verwenden Sie `[H]` für feste Positionierung: `\begin{figure}[H]`
- Stellen Sie sicher, dass die Bilddatei existiert

### Build-Fehler
- Löschen Sie den `build/`-Ordner und bauen Sie neu: `rm -rf build && latexmk ...`
- Überprüfen Sie die Syntax in Ihren `.tex`-Dateien
- Konsultieren Sie die Logdatei: `build/diplomarbeit.log`

---

## Lizenz

Diese Vorlage ist unter der [MIT-Lizenz](LICENSE) verfügbar.

---

## Kontakt und Support

Bei Fragen oder Verbesserungsvorschlägen:
- **GitHub:** https://github.com/Pixelpilot/HTL-Braunau-DA-LaTeX-Template
- **Issues:** Bitte erstellen Sie ein Issue im Repository

---

**Viel Erfolg beim Schreiben Ihrer Diplomarbeit!**
