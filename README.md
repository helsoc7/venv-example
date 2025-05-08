# Anleitung für die venv
1. Erstelle dir dein Projekt mit `mkdir <Projekt-Name>`
2. Lege dir eine venv an, also ein cleanes, virtuelles Environment
```bash
python -m venv <Name der venv>
```
Im Hintergrund passiert dann folgendes:
- Es wird ein Ordner mit dem Namen der venv angelegt
- Hier befinden sich dann alle Binaries und Site-Package-Daten nur für deine Virtuelle Umgebung
- d.h. ganz am Anfang, also jetzt, ist das fast leer. Wir haben hier nur Links auf Pip und den Python-Interpreter
3. Aktiviere die venv mit folgenden Befehl
Linux/macOS
```bash
source <Name der venv>/bin/activate
```
Windows in Git Bash
```bash
<Name der venv>\Scripts\Activate
```
- Achtung nach de Aktivieren befindet sich im Terminal vor dem Command Prompt der Name der venv in ().
4. Deaktiviere die venv im Zweifel mit dem Befehl `deactivate`
5. Installiere dir die Abhängigkeiten, die du brauchst für das Projekt mit dem Befehl `pip install <Paketname>`. Das Ganze kannst du dann überprüfen, indem du ein `pip list` ausführst und siehst, welche Pakete nun in deiner venv drin sind.
6. Wir wollen natürlich nicht in einem Git-Repository den Ordner der venv mit pushen. Daher legen wir uns mit `touch .gitignore` eine Datei an, in der wir explizit angeben, dass der Ordner ignoriert werden soll bei der git-Versionierung. 
```bash
cat <Name der venv> >> .gitignore
```
7. Damit wir aber dennoch die Abhängigkeiten dokumentieren können, erstellen wir mit folgenden Befehl eine Datei, wo diese drin sind.
```bash
pip freeze > requirements.txt
```
8. Wenn jetzt jemand das Repository klont und sich in seiner selbst angelegten venv die Abhängigkeiten installieren möchte, dann macht er ein 
```bash
pip install -r requirements.txt
```


