# <a name="Inhaltsverzeichnis"></a> Projektpräsentation von Tabea und Juliane

## Informatikprojekt 2

[Erstes Projekt: Pong Spiel](#1)

[Zweites Projekt: Shooting Game](#2)

[Drittes Projekt: Cross the Road](#3)

In diesem Repositorie stellen wir die Projekte, welche wir in den vergangenen Wochen bearbeitet und deren Fortschritte wir im "<a href="https://github.com/Tabea000/2.Informatikprojekt-Stundenblog-">Stundenblog</a>" festgehalten haben, ausführlich vor. Alle verwendeten Bilder sind in dem "<a href="https://github.com/Tabea000/2.Informatikprojekt-Stundenblog-/tree/master/Bildverzeichnis">Bildverzeichnis</a>" unseres Stundenblogs hinterlegt. Bei den drei Projekte, die wir in den vergangenen zwei Monaten entwickelt haben, handelt es sich um sehr bekannte Minispiele, deren Funktionsweisen, wir im Kleinen gerne nachvollzeiehen wollten.

Über die Links, die den Zugriff auf das jeweilige Projekt im das Internet für alle möglich macht, die über die Webadresse verfügen, können die Spiele ausprobiert und die genaue Funktion der Blöcke mit den hier vorliegenden Beschreibungen verglichen werden. Hierfür haben wir auf Snap!, dem Programm, mit dem wir mithilfe der Blockschrift, die Minispiele programmiert haben, das jeweilige Projekt publiziert ("share").


## <a name="1"></a>Erstes Projekt: Das Pong Spiel


Das erste Projekt, dass wir im Unterricht bearbeitet haben, war der 
Klassiker "<a href="https://snap.berkeley.edu/snapsource/snap.html#present:Username=Juliane000&ProjectName=Pong%20endg%C3%BCltige%20Version%2015.12">Pong</a>". Das Ziel dieses Spieles ist, den Ball des Gehners mit einem Paddle abzuwehren, damit dieser nicht die Wand hinter einem berührt und der Gegner einen Punkt erlangt.

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/P%202_%20stage%20mit%20sprites.png?raw=true "stage mit sprites")

Für dieses Spiel benötigt man vier Sprites: einen Ball, zwei Paddles und ein Bild mit der Aufschrift "you won". Die Stage, der Hintergrung, wir mit zwei unterschiedlich farbigen Balken an der linken und rechten Wand versehen, denn berührt der Ball eine Farbe wird der jeweilige score erhöht. Hinzu kommen zwei Anzeigetafeln für die Punkte, "score" und "score 2".

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/P%203_Block%20des%20Balls.png?raw=true "Block des Balls")

Der Block für den Ball beschäftigt sich in den ersten vier BAusteinen mit dem Spielanfang bzw. dem Neustart. Hier wird der Punktestand auf Null gestezt, der Ball versetzt sich in die Mitte des Spielfeldes und dessen "Laufrichtung" wir auf -45° festgelegt.

Die Zeitschleife "repat until" ist für den Spielablauf da, der bei Erreichen von fünf Punkten endet und somit dieser Spieler gewonnen hat. InnerHalb diese Bausteins wird zunächst die Bewegung des Balles eingestellt: "move 10 steps". DAmit dieser nicht das Feld verlässt, benötigt man der Baustein "if on edge, bounce".

Der erste if-Baustein beschreibt, dass, wenn der Ball die Farbe des Paddles (hier: grün) berührt,ein zufälliger Ausfallswinkel zwischen -130° und 120° gewählt wird. Um eine Veränderung des scores hervorzurufen, benötigt man zwei weitere if-Bausteine. Diese funtionieren so, dass sobald der Ball nicht vom Paddle abgewehrt werden konnte und er auf den farbigen Balken dahinter trifft, der score vom Gegner um eins erhöht wird: "if touching (blau/pink)"-&"change score 2/score) by 1"-&"point in direction 90°/-45°". Der letzte BAustein gibt den Ausfallswinkel an. Es wurden verschiedene eingebaut(pick random,-45,90), um etwas Variation ins Spiel zu bringen.

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/P%204_Steuerung%20paddle1.png?raw=true "Steuerung paddle 1")

Die Steurung der Paddles ist simpler aufgebaut. Diese übernimmt man mit zwei Pfeiltasten("When...key pressed"). Damit auch dieser nicht das Feld verlässt, wird "if on edge, bounce" eingesetzt. Zur senkrechten Bewegung benötigt man den Baustein " change y by..." einmal für einen positiven Wert und einmal für einen negativen. Diese Zahl kann man beliebig aussuchen, je nachdem wie schnell sich das Paddle bewegen soll. Für das zweite Paddle sieht der Block gleich aus, jedoch werden anstatt Pfeiltasten beliebige andere, zum Beispiel "a" und "q", zum steuern verwendet.

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/P%206_Bl%C3%B6cke%20%E2%80%9EYou%20won%201%262%E2%80%9C.png?raw=true"Blöcke-You won! 1/2")

Erreicht man die Punktzahl fünf, soll ein Bild mit dem Schriftzug "you won" erscheinen. Dafür benötigt man zunächst solch ein Bild; unseres ist zweimal aus dem Internet importiert und beide costumes jeweils mit einer eins oder zwei individualisiert. Wenn das Startsymbol, die Fahne, angeklickt wurde, soll sich das Bild solange verstecken, bis der Gewinnerstand von fünf Punkent erreicht wurde. Dafür sind zwei Blöcke vorhanden: ist der score von Spieler1 gleich fünf, so wird das costume "you won 1" gezeigt. Gewinnt Spieler2, wechselt das costume zu "you won 2": "When flag clicked"-&"hide"-&"forever-&"if score 2=5"-&"switch to costume "you won 2"-&"show".

Der Klassiker "Pong" ist nun vollends programmiert und kann gespielt werden.

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/P%207_Costumes%20%E2%80%9EYou%20won%201%262%E2%80%9C.png?raw=true "costumes-You won! 1/2")

[→Inhaltsverzeichnis](#Inhaltsverzeichnis)



## <a name="2"></a>Zweites Projekt: Das Shooting Game

Das zweite fertiggestellte Minispiel war ein "<a href="https://snap.berkeley.edu/snapsource/snap.html#present:Username=Juliane000&ProjectName=Shooting%20Game%20Versuch%20Won">Shooting Game</a>". Hierbei gilt es "fliegende Oktopusse" durch gezielte Schüsse zunächst die Farbe wechseln und in Folge verschwinden zu lassen. Wird vor Ablauf der Zeit die notwendige Punktzahl von 6 erreicht, bzw. sind alle Oktopusse verschwunden, gewinnt der Spieler die Runde.


![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/SG%202%20stage-timer%26points.png?raw=true "stage: points&timer")

Ein erster wichtiger Schritt ist es, zunächst die stage zu gestalten. Hierfür kann man beispielsweise aus den Vorlagen wählen, die im Programm Snap unter dem Punkt stage -> backgrounds findet. Außerdem gehören in das script der stage die Grundblöcke der selbsterstellten Variablen "points" und "timer". Erstere hängt eng mit den Blöcken der abzuschießenden Objekte zusammen und wird deshalb einzig zu Beginn einer neuen Runde, wie oben abgebildet auf 0 gesetzt. Der "timer" setzt einen zeitlichen, jedoch variablen Rahmen um das Spiel. 

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/SG%203%20sprites%20auf%20der%20stage.png?raw=true "stage mit sprites")

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/SG%204%20Bl%C3%B6cke%20der%20Oktopusse.png?raw=true "Blöcke der Oktopusse")

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/SG%205%20costumes%20der%20Oktopusse.png?raw=true "costumes der Oktopusse")

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/SG%206%20Linse.png?raw=true "Linse")

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/SG%207%20Game%20Over%20und%20Won.png?raw=true "Game over! und Won!")





[→Inhaltsverzeichnis](#Inhaltsverzeichnis)

## <a name="3"></a>Drittes Projekt: Cross the Road

Bei dem dritten Projekt handelt es um das Spiel "<a href="https://snap.berkeley.edu/snapsource/snap.html#present:Username=juliane000&ProjectName=Crossy%20road%2015.12-">Cross the Road</a>". Dabei lenkt man eine Maus über eine Straße, auf der sich verschiedene Jäger befinden, zum Ziel, um zu gewinnen. Wird das Ziel nicht innerhalb der ablaufenden Zeit erreicht, oder wird die Maus von einem der Jäger gefasst, verliert man das Spiel. 

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/CtR%202_%20stage%20mit%20sprites.png?raw=true "stage mit sprites")

Zu Beginn erstellt man einen Hintergrund mit der Funktion "paint a background", wofür man die Möglichkeit nutzt, rechtwinklige Figuren mit einer bestimmten Farbe auszufüllen ("filled rectangle") und gerade Lininen zu zeichnen ("line tool"). Außerdem importiert man verschiedene sprites auf die stage und wählt für diese passende costumes aus. Man benötigt beliebig viele Jäger, die sich senkrecht auf der Straße auf und abwärts bewegen, in diesem Fall eine Katze und vier Käfer. Zudem wir eine Figur (hier: eine Maus), die im finalen Spiel die Straße überqueren soll. dabei bewegt sie sich im 90° Winkel zur Laufrichtung der Jäger.

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/CtR%203_Bewegungsablauf.png?raw=true "Bewegungsablauf Jäger")

Der oben abgebildete Bewegungsablauf der Jäger ist recht simpel. Er besteht aus den Bausteinen "When flag clicked"->"forever ("move (x)-steps"->"if on edge bounce")". Die Anzahl der steps kann je nach Bedarf variiert werden, sodass die Geschwindigkeit der Jäger individuell angepasst werden kann. Je höher die Anzahl der steps, desto höher die Geschwindigkeit.


![bsp 
applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/CtR%204_%20Maus.png?raw=true 
"Maus-script")

Im Gegensatz dazu ist das script der Maus um einiges vielfältiger. Zum einen besteht es aus der Steuererung der Maus über die Pfeiltasten durch den Baustein "when...key pressed". Hier kann man auch eine eine beliebig andere Taste zur Steuerung einsetzen. Zur senkrechten Bewegung wird "change y by...", zur waagerechten Bewegung "move...steps" angefügt und mit 10/-10 als Wert versehen. Durch eine höhere oder niedrigere Einstellung kann man hier, wie bei den Jägern, die Schnelligkeit variieren.

Der große Block beschreibt das Verlieren durch Berührung mit einem der Jäger. Dafür wir für jeden einzelnen ein Block erstellt, der besagt, dass, im Falle einer Berührung, das costume der Maus zu einem "Game over"-costumee wechselt, sich dieses zentriert und das Spiel gestoppt wird. Das Bild für "Game over"(siehe nächstes Bild) wurde aus dem Internet importiert, man kann es auch selber malen, wie im "Shooting-Game". Diese if-Blöcke werden in die Zeitschleife "repeat until timer=0" gesetzt, damit dieser Block nach Ende des Spiels nicht mehr abläuft.

Der Block für den Fall, dass man das Ziel (hier: Muffin) erreicht, beruht auf dem selben Prinzip. Berührt die Maus den Muffin, wechselt sich ihr costume, mit dem "switch to costume..."-Baustein, zu einem Bild mir einer "You won"-Aufschrift(siehe nächstes Bild). Dieses wurde ebenfalls importiert. Zudem lässt der Block den sprite zur Mitte der stage springen und das Spiel stoppen; dieser if-Block lauft ebenfalls in einer Zeitschleife."When flag clicked"-�&"forever(if touching sprite)"-&"go to x:0 y:0"-&"switch to costume you won"-&"stop all" fässt diese Befehle für die Maus zusammen.

Zuletzt wird ein Block für den Neustart des Spiels erstellt. Damit die Maus zu ihrer Anfangsposition zurückkehrt und ihr ursprüngliches Maus-costume anlegt, wird der Block so erbaut: "when flag clicked"-&"go to x:-180 y:0"-&"switch to costume mouse".

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/CtR%205_%20costumes%20Maus.png?raw=true "maus-costumes")

Hier einmal die die costumes "mouse", "Game over" und "you won" für den Maus-sprite

![bsp applab](https://raw.githubusercontent.com/Tabea000/2.Informatikprojekt-Stundenblog-/master/Bildverzeichnis/CtR%206_script%20game%20over.png?raw=true "Game over!-script")

Der fehlende Block zur Vollendung von "Cross the road" ist für das "Game over" durch Ablaufen der Zeit, und der Einstellung des Timers zuständig. Dieser wir auf dem script des sprites "Game over" programmiert.in dem zu sehendem Blog wir der Timer im Baustein "set timer to..." auf zehn eingestellt. Damit dieser von zehn Sekunden herunter zählt, benötigt man die Zusammensetzung "repeat 10"-&"wait 1 secs"-&"change timer by -1". Da das "Game over"-Bild erst erscheinen soll, wenn der Timer abgelaufen ist, setzt man noch die Bausteine "hide" vor, und "show" nach dem Block des Timers. Am Ende wird erneut ein "stop all"-Baustein angefügt, damit alle Bewgungsabläufe stoppen.

Nun ist das Spiel "Cross the road" fertig programmiert und man kann es 
in der Praxis spielen.

[→Inhaltsverzeichnis](#Inhaltsverzeichnis)

