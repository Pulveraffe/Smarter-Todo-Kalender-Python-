# Smarter-Todo-Kalender-Python-
Schulprojekt im Fach Programmieren meiner Ausbildung zum Fachinformatiker

INFO: 
Dies ist eine minimal lauffähige Smarte ToDo-Liste gesteuert über die Eingabeaufforderung oder PowerShell. Durch Verwendung eines kleinen Sprachmodells (qwen2.53:b instruct) werden die chaotischen, Stichwortartigen eingaben geordnet und in ein Standartisiertes JSON-Format gebracht. Für eine übersichtliche Anzeige der Termine im Browser wird der Flask-Server benötigt.
Das Programm ist allerdings auch ohne Flask-Server lauffähig. Die gespeicherten Termine werden dann ausschließlich in der JSON-Datei gespeichert und können in eigene Projekte integriert werden.

INSTALLATION:
 -Speicherpfad für die Ergebnisse im Quellcode von todo_app.py anpassen:
 -Rechtsklick auf todo_app.py -> öffnen mit -> z.B. Visual Studio Code.
Zeile suchen: 

 [ Originalzeile: SAVE_PATH = r"C:\Users\user-vITA17\Desktop\Projekt#\Speicher"   ]

Ollama downloaden und installieren von: https://ollama.com/search

Python 3.11 (Wichtig: Aktiviere das Häkchen bei "Add Python to PATH". Unter Customize Installation sichergehen dass PIP mit installiert wird.)

JQ-windows ein Mal starten. (es öffnet sich nichts -das muss so)

Eingabeaufforderung starten und requests nachladen mit:

 python -m pip install requests

(falls nicht funktioniert; pip nachladen mit :
py -m ensurepip --upgrade
oder:
py -m pip install --upgrade pip
)
danach noch mal versuchen mit: 

python -m pip install requests

ansonsten hier weiter machen:

-Qwen2.5:3b-instruct Sprachmodell runterladen mit:

Eingabeaufforderung:

ollama pull qwen2.5:3b-instruct


-Ollama funktionstest:
Browser:
 http://localhost:11434

-qwen2.5 Modell funktionscheck:

Eingabeaufforderung:
ollama run qwen2.5:3b-instruct "Sag nur: OK"

Ausgabe: "OK"  - alles gut; Qwen läuft.

-Date Parser runterladen für chaotische Datumserkennung mit:
Eingabeaufforderung:

pip install dateparser

-Programm starten in Eingabeaufforderung oder PowerShell mit:

 python "Pfad-zu-todo_app.py"

Ausgabe: 
Gib deinen chaotischen ToDo-Text ein: 

-testen mit Beispiel: "Morgen Hund Gassi" oder "15. okt Arzt" 

-Die Einträge werden dann automatisiert als JSON im Ordner Speicher unter dem angegebenen Pfad gespeichert und können mit einem Server oder Manuell abgerufen werden.

-Jeder weiteren Eingabe muss ein Start des Programms vorausgehen  


-Für Flask-Server und abrufen der Liste im Browser: 

Eingabeaufforderung: 
pip install flask

Dann den Server starten mit:
 
Eingabeaufforderung:

python "Pfad-zu-Server.py"

Über Server Kalender abrufen mit: http://127.0.0.1:8000


