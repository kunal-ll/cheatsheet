# Cheatsheet
### Git Cheat Sheet auf Deutsch

#### SETUP & INIT
Konfigurieren von Benutzerinformationen, Initialisieren und Klonen von Repositories

- `git config --global user.name "[Vorname Nachname]"`
  - Setze einen Namen, der zur Identifikation bei der Versionshistorie verwendet wird.
- `git config --global user.email "[gültige Email]"`
  - Setze eine E-Mail-Adresse, die mit jedem Versionshinweis verbunden wird.
- `git config --global color.ui auto`
  - Setze automatische Befehlszeilen-Farbgebung für Git für einfache Überprüfung.
- `git init`
  - Initialisiere ein bestehendes Verzeichnis als Git-Repository.
- `git clone [URL]`
  - Lade ein gesamtes Repository von einem gehosteten Standort über die URL herunter.

#### STAGE & SNAPSHOT
Arbeiten mit Snapshots und dem Git-Staging-Bereich

- `git status`
  - Zeige modifizierte Dateien im Arbeitsverzeichnis an, die für deinen nächsten Commit vorgemerkt sind.
- `git add [Datei]`
  - Füge eine Datei, wie sie jetzt aussieht, deinem nächsten Commit hinzu (Stage).
- `git reset [Datei]`
  - Entferne eine Datei aus dem Staging-Bereich, behalte aber die Änderungen im Arbeitsverzeichnis.
- `git diff`
  - Zeige Unterschiede zwischen Arbeitsverzeichnis und Staging-Bereich.
- `git diff --staged`
  - Zeige Unterschiede zwischen Staging-Bereich und letztem Commit.
- `git commit -m "[beschreibende Nachricht]"`
  - Committe deinen vorgemerkten Inhalt als neuen Commit-Snapshot.

#### BRANCH & MERGE
Isolieren von Arbeiten in Branches, Wechseln des Kontextes und Integrieren von Änderungen

- `git branch`
  - Liste deine Branches auf. Ein * erscheint neben dem aktuell aktiven Branch.
- `git branch [Branch-Name]`
  - Erstelle einen neuen Branch an der aktuellen Commit-Stelle.
- `git checkout`
  - Wechsle zu einem anderen Branch und checke ihn in dein Arbeitsverzeichnis aus.
- `git switch [Branch-Name]`
  - Wechsel zu einem anderen Branch (ab Git 2.23).
- `git merge [Branch]`
  - Führe die Geschichte des angegebenen Branches in den aktuellen Branch ein.
- `git log`
  - Zeige alle Commits in der Geschichte des aktuellen Branches an.

#### SHARE & UPDATE
Abrufen von Updates aus einem anderen Repository und Aktualisieren lokaler Repositories

- `git remote add [Alias] [URL]`
  - Füge eine Git-URL als Alias hinzu.
- `git fetch [Alias]`
  - Lade alle Branches von diesem Git-Remote herunter.
- `git merge [Alias]/[Branch]`
  - Führe einen Remote-Branch in deinen aktuellen Branch ein, um ihn zu aktualisieren.
- `git push [Alias] [Branch]`
  - Übertrage lokale Branch-Commits in den Remote-Repository-Branch.
- `git pull`
  - Hole und merge alle Commits vom verfolgten Remote-Branch.

#### TRACKING PATH CHANGES
Versionierung von Datei-Entfernungen und Pfadänderungen

- `git rm [Datei]`
  - Lösche die Datei aus dem Projekt und markiere die Entfernung für den Commit.
- `git mv [existierender Pfad] [neuer Pfad]`
  - Ändere einen bestehenden Dateipfad und markiere die Änderung für den Commit.
- `git log --stat -M`
  - Zeige alle Commit-Logs mit Angabe aller verschobenen Pfade an.

#### TEMPORARY COMMITS
Temporäres Speichern modifizierter, getrackter Dateien, um Branches zu wechseln

- `git stash`
  - Speichere modifizierte und vorgemerkte Änderungen vorübergehend.
- `git stash list`
  - Zeige die gestapelten Änderungen an.
- `git stash pop`
  - Schreibe das Arbeitsverzeichnis aus dem obersten Stash-Stack.
- `git stash drop`
  - Verwerfe die Änderungen vom obersten Stash-Stack.

#### REWRITE HISTORY
Branches umschreiben, Commits aktualisieren und Geschichte bereinigen

- `git rebase [Branch]`
  - Wende alle Commits des aktuellen Branches vor dem angegebenen Branch an.
- `git reset --hard [Commit]`
  - Leere den Staging-Bereich und schreibe den Arbeitsbaum ab dem angegebenen Commit neu.

#### INSPECT & COMPARE
Untersuchen von Logs, Unterschieden und Objektinformationen

- `git log`
  - Zeige die Commit-Historie für den aktuell aktiven Branch an.
- `git log branchB..branchA`
  - Zeige die Commits auf BranchA an, die nicht auf BranchB sind.
- `git log --follow [Datei]`
  - Zeige die Commits an, die die Datei geändert haben, auch über Umbenennungen hinweg.
- `git diff branchB...branchA`
  - Zeige die Unterschiede, die auf BranchA vorhanden sind, aber nicht auf BranchB.
- `git show [SHA]`
  - Zeige jedes Objekt in Git in einem menschenlesbaren Format an.

#### IGNORING PATTERNS
Verhindern von unbeabsichtigtem Staging oder Commit von Dateien

- `git config --global core.excludesfile [Datei]`
  - Systemweites Ignore-Muster für alle lokalen Repositories.
- Speichere eine Datei mit den gewünschten Mustern als `.gitignore` mit entweder direkten String-Matches oder Platzhalter-Globs.
