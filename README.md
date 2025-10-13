# Wir schreiben ein Kochbuch
Jeder Tisch schreibt gemeinsam ein kleines Kochbuch. Ziel ist es am Ende ein gemeinsames kleines Kochbuch erstellt zu haben :)

# Aufgaben

### Aufgabe 1
- Bestimmt eine Person als Teamleitung
- Die Teamleitung erstellt das Repo für euren Tisch und lädt alle anderen dazu ein
- Alle anderen ziehen das Repo auf den eigenen Rechner und vergewissern sich, dass sie in der IDE ihrer Wahl mit dem Repo verbunden sind

### Aufgabe 2
- Jede/r erstellt einen eigenen Branch für sein Lieblingsrezept (benennt den Branch hierbei am einfachsten nach euch selbst). KEINER ARBEITET IN MAIN!!!
- Erstellt eine Datei, die passend zu eurem Rezept ist (z.B. Pizza.txt - die Datei kann gerne im Hauptverzeichnis bleiben)

### Aufgabe 3
- Wenn euer Rezept fertig ist, dann bringt es in euer Repo, damit es die anderen auch sehen können
- Wartet bis alle anderen aus eurem Team fertig sind

### Aufgabe 4
- Vollzieht gemeinsam an einem Computer den Merge in Main

### Aufgabe 5
- Die Teamleitung erstellt in Main eine Datei namens "UnserRezept.txt"
- Alle ziehen die geänderten Daten des aktuellen Main in ihren eigenen Branch
- Jeder schreibt in das leere Dokument "UnserRezept.txt" genau 3 Zusaten (z.b. wie folgt:)
```bash
Zwiebeln
Gummibärchen
Schokolade
```
- Wenn ihr fertig seid, schiebt ihr eure Version von "UnserRezept.txt" zurück ins Repo.

### Aufgabe 6
- Schaut wieder gemeinsam an einem PC wie und ob der Merge klappt

# 🟢 Git & GitHub Cheat-Sheet für VS Code
*Für den Workshop "Unser Lieblings-Rezeptbuch"*

---

## 📋 Die wichtigsten Git-Befehle

### Erste Schritte
```bash
# Repository klonen (nur einmal am Anfang)
git clone https://github.com/username/repository-name.git

# In den Projekt-Ordner wechseln
cd repository-name

# Aktuellen Status prüfen (sehr wichtig!)
git status
```

### Änderungen speichern
```bash
# Einzelne Datei hinzufügen
git add dateiname.txt

# ALLE geänderten Dateien hinzufügen
git add .

# Commit erstellen (Snapshot speichern)
git commit -m "Beschreibung was ich geändert habe"

# Änderungen zu GitHub hochladen
git push origin main
```

### Mit Branches arbeiten
```bash
# Neuen Branch erstellen und dorthin wechseln
git checkout -b mein-neuer-branch

# Zu anderem Branch wechseln
git checkout main
git checkout branch-name

# Alle Branches anzeigen
git branch

# Branch zu GitHub hochladen
git push origin branch-name
```

### Änderungen von anderen holen
```bash
# Neueste Änderungen herunterladen
git pull origin main

# Nur schauen was es Neues gibt (ohne zu ändern)
git fetch
```

### Im Notfall
```bash
# Alle lokalen Änderungen verwerfen (VORSICHT!)
git reset --hard HEAD

# Letzten Commit rückgängig machen
git reset --soft HEAD~1

# Datei aus Staging Area entfernen
git reset dateiname.txt
```

---

## 🎯 VS Code + Git Integration

### VS Code Git-Panel verwenden
- **Source Control Panel** (Strg+Shift+G): Zeigt alle Änderungen
- **"+" Button**: Entspricht `git add`
- **Commit Message Box**: Nachricht eingeben und Strg+Enter
- **"..." Menü**: Weitere Git-Optionen (Push, Pull, etc.)

### Nützliche VS Code Shortcuts
- `Strg+Shift+G` → Source Control öffnen
- `Strg+Shift+P` → Command Palette (Git-Befehle suchen)
- `Strg+K Strg+O` → Ordner öffnen

---

## ⚠️ Häufige Fehlermeldungen & Lösungen

### 1. Git ist nicht installiert
**Fehlermeldung:** 
```
'git' is not recognized as an internal or external command
```
**Lösung:**
- Git von https://git-scm.com/ herunterladen und installieren
- VS Code neu starten
- Terminal öffnen und `git --version` testen

### 2. Git-Identität fehlt
**Fehlermeldung:**
```
Author identity unknown
Please tell me who you are
```
**Lösung:**
```bash
git config --global user.name "Dein Name"
git config --global user.email "deine.email@beispiel.de"
```

### 3. GitHub-Authentifizierung fehlgeschlagen
**Fehlermeldung:**
```
Authentication failed
Permission denied (publickey)
Support for password authentication was removed
```
**Lösung in VS Code:**
1. `Strg+Shift+P` → "Git: Clone" wählen
2. Repository-URL eingeben
3. Wenn GitHub-Login erscheint → anmelden
4. Personal Access Token erstellen falls nötig:
   - GitHub → Settings → Developer settings → Personal access tokens
   - "repo" permissions auswählen

### 4. Repository nicht gefunden
**Fehlermeldung:**
```
Repository not found
fatal: could not read from remote repository
```
**Lösung:**
- Überprüfe Repository-URL (kopiere von GitHub)
- Stelle sicher, dass du als Collaborator eingeladen wurdest
- Prüfe ob Repository public oder privat ist

### 5. Push wird abgelehnt
**Fehlermeldung:**
```
Updates were rejected because the remote contains work
hint: Updates were rejected because the tip of your current branch is behind
```
**Lösung:**
```bash
git pull origin main
# Falls Merge-Konflikt: lösen und dann:
git push origin main
```

### 6. Merge-Konflikt
**VS Code zeigt:**
```
Both modified: dateiname.txt
```
**Lösung:**
1. Datei in VS Code öffnen
2. Konflikt-Marker suchen: `<<<<<<<`, `=======`, `>>>>>>>`
3. Entscheiden welche Version du behalten willst
4. Marker löschen, Datei speichern
5. In Source Control Panel: Datei "stagen" (+)
6. Commit erstellen

### 7. VS Code erkennt Git-Repository nicht
**Problem:** Source Control Panel ist leer
**Lösung:**
1. `File → Open Folder` → Den richtigen Git-Ordner wählen
2. Oder: `Strg+Shift+P` → "Git: Initialize Repository"

### 8. Terminal funktioniert nicht in VS Code
**Problem:** Git-Befehle funktionieren nicht im VS Code Terminal
**Lösung:**
1. `Strg+Shift+P` → "Terminal: Select Default Profile"
2. "Command Prompt" oder "PowerShell" wählen
3. Neues Terminal öffnen: `Strg+Shift+ö`

---

## 🔧 VS Code Extensions für Git

### Empfohlene Extensions (optional):
- **GitLens**: Zeigt wer welche Zeile geändert hat
- **Git Graph**: Visualisiert Git-History
- **GitHub Pull Requests**: Pull Requests direkt in VS Code

### Extensions installieren:
1. `Strg+Shift+X` → Extensions öffnen
2. Name eingeben und "Install" klicken

---

## 🚨 SOS - Wenn gar nichts mehr geht

### Kompletter Neustart:
```bash
# 1. Ordner löschen
# 2. Neu klonen
git clone https://github.com/username/repository-name.git
cd repository-name
```

### VS Code Git-Einstellungen zurücksetzen:
1. `Strg+Shift+P` → "Preferences: Open Settings (JSON)"
2. Alle Git-bezogenen Einstellungen löschen
3. VS Code neu starten

### Hilfe holen:
- 🙋‍♀️ **Zuerst:** Workshopleiter fragen
- 📋 **Dann:** `git status` ausführen und Ausgabe zeigen
- 🔍 **Screenshots:** Von Fehlermeldungen machen

---

## 💡 Pro-Tipps für den Workshop

### Bevor du etwas machst:
1. **Immer** `git status` ausführen
2. **Immer** schauen in welchem Branch du bist
3. **Immer** pullen bevor du pushst

### Wenn du unsicher bist:
- Frage lieber einmal zu viel als zu wenig
- Kopiere wichtige Dateien als Backup
- `git status` ist dein bester Freund

### Git-Workflow Merksatz:
**"Add → Commit → Push → Wiederholen"**

---

*🎯 Ziel: Jeder im Team erstellt mindestens einen erfolgreichen Commit!*
