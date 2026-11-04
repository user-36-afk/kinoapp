 A1: Auf welchem Branch bist du, und welche Branches gibt es noch?
 - main branch, weitere:   
  feature/neuer-titel
  feature/snacks


 A2: Welche Dateien meldet git status als „untracked“? Was bedeutet das?
        kasse.log
        test/
-> Dateien, die Git bekannt sind, aber noch nicht commited wurden (neu erstellt bzw. Änderungen)

 A3: ls -a zeigt einen Ordner .git. Was steckt darin, und was passiert, wenn man ihn löscht?
Ordner enthält Informationen zur Versionsverwaltung: 
commits (die gesamte Historie), branches, tags, Konfigurationen, Staging Area, Informationen über das aktuelle Checkout (HEAD)
Bei der Löschung des.git-Ordners geht die gesamte Git-Historie, Branches und Konfiguration des Repositories verloren. Die eigentlichen Projektdateien bleiben aber erhalten.

B1: Woran erkennst du in der Ausgabe und im Log, dass es ein Fast-Forward war?
Es entsteht kein zusätzlicher Merge-Commit. Stattdessen wird der Branch-Zeiger einfach auf den neueren Commit verschoben.

B2: Warum war hier ein Fast-Forward möglich?
Ein Fast-Forward ist möglich, wenn der Ziel-Branch keine eigenen neuen Commits besitzt und hinter dem zu mergenden Branch liegt.

C1: Beschreibe in einem Satz, wo der Fehler steckt und was er bewirkt.
Vorher: Alter <14, nach der Änderung: Alter >14, Also bekommen alle Personen, die älter als 14 Jahre sind den Kinderpreis.

C2: Nach git add zeigt git diff nichts mehr an, git diff --staged aber schon. Warum?
git diff zeigt standardmäßig die Unterschiede zwischen Working Directory und Staging Area.
Nach git add sind beide identisch, daher zeigt git diff nichts an.

D1: Ist der Commit „Werbebanner eingefügt“ nach dem Revert noch in der Historie? Was ist dazugekommen?
der Befehl git revert löscht den Commit nicht, es wird ein neuer Commit erstellt, der die Änderungen des alten Commits rückgängig macht.

D2: Warum nimmt man in einem Team-Repo git revert statt Commits einfach zu löschen?
git revert ist sicher, weil die Historie unverändert bleibt, alle Änderungen nachvollziehbar sind, keine Probleme für andere Teammitglieder entstehen.

E1: Was ist der Unterschied zwischen > und >> beim echo-Befehl?
> überschreibt den Inhalt einer Datei.
>> hängt den Text an die Datei an.

E2: Was zeigt git status vor und nach dem Anlegen der .gitignore?
Git zeigt vorher Dateien an, die noch nicht versioniert werden
Dann werden diese Dateien von Git ignoriert und erscheinen nicht mehr bei den untracked files.

F1: Warum ist git merge --ff-only hier gescheitert?
Ein Fast-Forward-Merge ist nur möglich, wenn main seit der Abzweigung keine eigenen Commits erhalten hat.

F2: Was bedeuten HEAD und feature/neuer-titel in den Konfliktmarkern?
HEAD = die aktuelle Version aus dem Branch (main)
feature/neuer-titel = die Version aus dem Branch
-> keine eindeutige Einordnung, welcher Branch ausgegeben werden soll

F3: Warum konnte Git den Konflikt nicht allein lösen?
Git konnte nicht erkennen, welche Änderung richtig ist, weil dieselbe Zeile in beiden Branches unterschiedlich geändert wurde.

G1: Beim ersten git status steht „Your branch is up to date with 'origin/main'“, obwohl es auf GitHub eine neue Änderung gibt. Warum?
Weil das lokale Git die neuen Änderungen auf GitHub noch nicht kennt.
git status vergleicht den lokalen Branch main nur mit dem lokalen Verweis auf origin/main. Dieser Verweis wird erst durch einen Kontakt zum Remote-Repository aktualisiert.

G2: Was hat git fetch gemacht, was hat git pull zusätzlich gemacht?
git fetch:
Lädt neue Commits vom Remote-Repository (GitHub) herunter.
Aktualisiert die Remote-Referenzen, ändert nicht den aktuellen Branch.

git pull:
git fetch + anschließend automatisch git merge
-> Änderungen herunterladen und in den aktuellen Branch integrieren

