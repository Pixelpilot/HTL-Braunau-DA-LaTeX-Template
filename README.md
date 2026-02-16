# HTL-Braunau-DA-LaTeX-Template

LaTeX-Vorlage für Diplomarbeiten an der HTL Braunau

**GitHub Repository:** https://github.com/Pixelpilot/HTL-Braunau-DA-LaTeX-Template

---

## Übersicht

Diese Vorlage ist eine professionelle LaTeX-Umgebung für die Erstellung von Diplomarbeiten an der HTL Braunau. Sie bietet eine strukturierte Grundlage mit automatischer Verwaltung von Literaturverzeichnis, Abbildungsverzeichnis und Listingsverzeichnis.

### Besonderheiten
- KOMA-Script Dokumentenklasse (`scrbook`)
- Deutsche Lokalisierung (Babel)
- Placeholder-Box für Beispielinhalte (roter Rahmen mit `\placeholderbox`)
- Numerische Zitationen mit BibTeX
- Automatische Verzeichnisse (Inhalts-, Abbildungs-, Listings-, Literaturverzeichnis)
- Code-Highlighting mit `listings`
- Professionelle Kopf- und Fußzeilengestaltung
- Unterstützung für Subfiguren
- Modular strukturierte Kapitel mit Author-Includes für Multi-Autor Arbeiten

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
│   ├── 01_einleitung.tex        # Einleitung
│   ├── 02_grundlagen.tex        # Grundlagen (Begriffsdefinitionen, State of the Art, etc.)
│   ├── 03_konzepte.tex          # Konzepte und Lösungsansätze
│   ├── 03_konzepte_authorA.tex  # Konzept A (Autor A)
│   ├── 03_konzepte_authorB.tex  # Konzept B (Autor B)
│   ├── 04_implementierung.tex   # Implementierung
│   ├── 04_implementierung_authorA.tex  # Implementierung A (Autor A)
│   ├── 04_implementierung_authorB.tex  # Implementierung B (Autor B)
│   ├── 05_prototyp.tex          # Prototyp und Ergebnisse
│   ├── 05_prototyp_authorA.tex  # Prototyp A (Autor A)
│   ├── 05_prototyp_authorB.tex  # Prototyp B (Autor B)
│   ├── 06_conclusion.tex        # Fazit und Schlussfolgerungen
│   ├── 07_projectmanagement.tex # Projektmanagement (Planung, Zeiterfassung)
│   ├── 99_acknowledgements.tex  # Danksagungen
│   ├── 99_authors.tex           # Autorenangaben
│   ├── 99_beispielhafte_inhalte.tex  # Beispielkapitel (Best Practices)
│
├── includes/                    # Konfiguration und Definitionen
│   ├── htl_definintions.tex    # LaTeX-Pakete und Konfigurationen
│   └── htl_c_cmyk_rein.pdf     # HTL-Logo
│
├── media/                        # Medienresourcen
│   ├── images/                 # Abbildungsdateien (.pdf, .png, .jpg)
│   └── code_snippets/          # Code-Beispiele (.cpp, .php, .js, .css, .html)
│
└── build/                        # Build-Verzeichnis
    ├── diplomarbeit.pdf        # Generiertes PDF

```



## Schnelleinstieg

### Arbeiten mit Online-Editoren
Um mit Online-Editoren wie z.B. https://de.overleaf.com/ arbeiten zu können müssen alle Dateien hochgeladen werden.

### Lokaler Editor

#### Voraussetzungen
- **TeX Live** oder **MikTeX** (aktuelle Version)
- **latexmk** (Automatisiertes Build-System)
- Editor: VS Code mit LaTeX Workshop oder ähnlich

#### Build durchführen

```bash
# Im Projektverzeichnis:
cd HTL-Braunau-DA-LaTeX-Template
latexmk -pdf -g -output-directory=build diplomarbeit.tex
```

Das PDF wird unter `build/diplomarbeit.pdf` generiert.



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
% Website
@misc{bib:latexintro,
  author = {T. Oetiker, et al.},
  title = {The not so short introduction into LaTeX},
  howpublished = "\\\url{https://tobi.oetiker.ch/lshort/lshort.pdf}"
}

% Book
@book{bib:uhlenbruck1,
  author = {Gerhard Uhlenbruck},
  year = {2005},
  title = {Kein Blatt vor den Mund nehmen},
  publisher = {Ralf Reglin Verlag Köln}
}
```

Zitate im Text: `\cite{bib:latexintro}` → wird automatisch zu [1]

### Kapitel: `chapters/`

#### Titelseiten und Metadaten (keine Bearbeitung nötig)
- `00_deckblatt.tex` – Automatisierte Titelseite
- `00_abstract.tex` – Abstract und Kurzfassung
- `00_ee.tex` – Erklärung/Eidesstattliche Versicherung

#### Hauptkapitel (zum Bearbeiten)

**01_einleitung.tex** – Einleitung  
Motivation, Problemstellung und Zielsetzung mit Kapitelgliederung.

**02_grundlagen.tex** – Grundlagen  
Begriffsdefinitionen, State of the Art, theoretische und technologische Grundlagen.

**03_konzepte.tex** – Konzepte und Lösungsansätze  
Führt mehrere Konzeptansätze zusammen (Autor A, B, ...) mit Evaluierungstabelle.
- `03_konzepte_authorA.tex` – Konzept A
- `03_konzepte_authorB.tex` – Konzept B  

**04_implementierung.tex** – Implementierung  
Technische Implementierungsdetails und verwendete Technologien.
- `04_implementierung_authorA.tex` – Implementierung A
- `04_implementierung_authorB.tex` – Implementierung B

**05_prototyp.tex** – Prototyp und Ergebnisse  
Prototypbeschreibung, Testverfahren und erreichte Ergebnisse.
- `05_prototyp_authorA.tex` – Prototyp A
- `05_prototyp_authorB.tex` – Prototyp B

**06_conclusion.tex** – Zusammenfassung und Fazit  
Zusammenfassung der Ergebnisse, kritische Würdigung und Ausblick.

**07_projectmanagement.tex** – Projektmanagement  
Meilensteinplan, Zeiterfassung und Projektdokumentation (deutsche Beschreibungen).

#### Spezielle Kapitel
- `99_acknowledgements.tex` – Danksagungen (deutsch)
- `99_authors.tex` – Autorenangaben
- `99_beispielhafte_inhalte.tex` – Beispielkapitel mit Best Practices  
  Demonstriert: Korrekte Zitationen, Abbildungseinbindung, Code-Listings, Fußnoten

### Konfiguration: `includes/`

#### `htl_definintions.tex`
Im Regelfall ist es nicht notwendig diese Datei anzupassen

Zentrale Konfigurationsdatei mit:
- LaTeX-Paketen (graphicx, listings, hyperref, etc.)
- Farb- und Schriftdefinitionen
- Placeholder-Box Befehl für Beispielinhalte
- Listings-Konfiguration
- Kopf- und Fußzeilen-Einstellungen
- Makros und Befehle

### Medien: `media/`
- `images/` – Abbildungsdateien (.pdf, .png, .jpg)
- `code_snippets/` – Quellcode-Dateien (.cpp, .php, .js, .css, .html)

Verwendung in Dokumenten:
```latex
\includegraphics[width=0.5\textwidth]{./media/images/myimage.pdf}
\lstinputlisting[language=Python]{./media/code_snippets/example.py}
```



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

### 2. Mit Placeholder-Boxen arbeiten (Beispielinhalte ersetzen)

Das Template enthält rote Placeholder-Boxen, die zeigen, wo Beispielinhalte von den Studierenden hinzugefügt werden sollen:

```latex
\placeholderbox{Beispieltitel}{
Dies ist ein Beispielinhalt, der ersetzt werden soll.
Die Box zeigt visuell, wo eigene Inhalte eingefügt werden.
}
```

**Zum Ersetzen:**

1. Öffnen Sie das betreffende Kapitel
2. Ersetzen Sie den Text in den `\placeholderbox{...}{...}` Befehlen
3. Sie können die Box auch komplett durch normalen Text ersetzen:

```latex
% VOR (mit Box):
\placeholderbox{Mein Titel}{Beispieltext}

% NACH (ohne Box):
Der echte Inhalt der Diplomarbeit...
```

**Beispiele:** In jedem Kapitel von 01 bis 07 finden Sie Placeholder-Boxen mit thematischen Vorlagen.

### 3. Literaturquellen hinzufügen
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

### 4. Abbildungen und Code einfügen

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

### 5. Bauen und Überprüfen
```bash
latexmk -pdf -g -output-directory=build diplomarbeit.tex
```

Das PDF wird unter `build/diplomarbeit.pdf` erzeugt.


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

## Projektmanagement-Dokumentation (Kapitel 07)

Das Kapitel `07_projectmanagement.tex` dokumentiert die Projektplanung und wird auf Deutsch verfasst.

### Meilensteinplan
Eine Übersicht über die wichtigsten Projektphasen mit Zeitplänen:

| Meilenstein | Beschreibung | Termin |
|---|---|---|
| Requirement-Analyse | Anforderungen definieren und dokumentieren | KW 22 |
| Konzeptphase | Verschiedene Lösungsansätze entwickeln und bewerten | KW 25 |
| Implementierung Phase 1 | Kernfunktionalitäten umsetzen | KW 33 |
| Implementierung Phase 2 | Optimierung und erweiterte Features | KW 36 |
| Prototyp & Testing | Tests durchführen und Ergebnisse dokumentieren | KW 50 |
| Dokumentation | Diplomarbeit finalisieren | KW 04 |
| Abgabe | Finale Abgabe | KW 13 |


### Zeiterfassung
Dokumentiert die wöchentliche Arbeitszeit und den Fortschritt:

| Woche | Schule (h) | Freizeit (h) | Aufgabenbeschreibung |
|---|---|---|---|
| KW 22 | 10 | 2 | Anforderungsanalyse, Meetings mit Betreuung |
| KW 23 | 10 | 4 | Recherche State of the Art, Literature Review |
| KW 24 | 12 | 3 | Konzepterstellung und Designphase |
| KW 25 | 14 | 5 | Implementierung und Coding |
| KW 26 | 11 | 6 | Testing und Dokumentation |


---

## Zusammenarbeit mit mehreren Autoren

Dieses Template unterstützt Multi-Autor-Projekte durch eine modular Struktur:

### Kapitel mit Autor-Spezifischen Versionen

Einige Kapitel haben separate Versionen für verschiedene Autoren:

- **Konzepte:** `03_konzepte_authorA/B.tex` – Jeder Autor entwickelt einen Lösungsansatz
- **Implementierung:** `04_implementierung_authorA/B.tex` – Implementierungsdetails pro Autor
- **Prototyp:** `05_prototyp_authorA/B.tex` – Ergebnisse und Tests pro Autor

Das Hauptkapitel (z.B. `03_konzepte.tex`) führt alle Autor-Dateien zusammen.

### Workflow für Mehrautoren-Projekte

1. **Aufgaben verteilen:** Jeder Autor arbeitet an seiner eigenen `_authorX.tex` Datei
2. **Parallel entwickeln:** Keine Konflikte, da jeder seine eigene Datei hat
3. **Im Hauptkapitel zusammenführen:** Die Partner-Datei (`03_konzepte.tex`) nutzt `\input` um alle Versionen einzubinden
4. **Evaluation/Vergleich:** Im Hauptkapitel können Vergleichstabellen die Unterschiede hervorheben

**Tipp:** Nutzen Sie Git für Versionskontrolle und um Konflikte zu vermeiden!

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
- Verwendung beschreibender Caption-Texte
- Referenzierung jeder Abbildung im Text
- Verwendung von PDF-Format für Vektorgrafiken
- Aussagekräftige Benennung von Dateien

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

## Lizenz

Diese Vorlage ist unter der [MIT-Lizenz](LICENSE) verfügbar.
