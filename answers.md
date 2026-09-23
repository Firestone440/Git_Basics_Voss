# Antworten – Git-Aufgabe Steckbrief

## 1. Unterschied zwischen Working Directory, Staging Area und Repository
- **Working Directory:** Der Projektordner, in dem ich die Dateien bearbeite. Hier sind die Änderungen noch nicht vorgemerkt.
- **Staging Area:** Hier landen die Änderungen, die ich mit `git add` für den nächsten Commit vormerke.
- **Repository:** Hier werden die Commits mit `git commit` dauerhaft gespeichert (im Ordner `.git`).

## 2. Woran erkenne ich, ob ein Merge Fast-Forward war?
- Bei `git merge` steht in der Ausgabe **„Fast-forward“**.
- Es gibt **keinen extra Merge-Commit**. In `git log --oneline --graph` ist der Verlauf eine gerade Linie ohne Verzweigung.

## 3. Warum kann `git merge --ff-only` fehlschlagen?
Wenn `main` seit dem Abzweigen von `dev` **neue Commits bekommen hat**, sind die beiden Branches auseinandergelaufen. Dann kann Git `main` nicht einfach nach vorne schieben und bräuchte einen Merge-Commit. Den verbietet `--ff-only`, deshalb bricht der Merge ab.

## 4. Vorteil, Änderungen zuerst auf einem Branch wie `dev` zu machen
- `main` bleibt **stabil und funktionsfähig**.
- Ich kann in Ruhe testen und ausprobieren, ohne etwas kaputt zu machen.
- Erst wenn alles passt, wird es in `main` übernommen. Wenn etwas schiefgeht, lösche ich einfach den Branch.
- Mehrere Leute können parallel an verschiedenen Sachen arbeiten.

## 5. Befehl, um den aktuellen Branch zu sehen
```bash
git branch
```
Der aktuelle Branch ist mit `*` markiert. Alternativ geht auch `git status` („On branch …“) oder `git branch --show-current`.

## 6. Änderungen sichtbar und dauerhaft machen (Staging & Commit)
```bash
git status                           # Änderungen anzeigen
git diff                             # genaue Änderungen ansehen
git add <datei>                      # Änderungen stagen (vormerken)
git commit -m "Aussagekräftige Nachricht"   # dauerhaft im Repository speichern
```
