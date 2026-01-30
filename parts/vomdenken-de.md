# Vom Denken ins Machen

Als Jugendlicher habe ich mir immer ein Spiel gewünscht, das wirklich süchtig macht.
Nicht so eines wie Elite – das war zwar großartig, aber ich habe es bis zur Stufe „Tödlich“ gespielt, diesen Status bereits nach wenigen Wochen erreicht und dann eigentlich keine Motivation mehr gehabt. Die nächste Stufe wäre Elite gewesen … aber was dann?

Seit über 20 Jahren spiele ich nun **World of Warcraft**, ein MMO-RPG von Blizzard.
Dieses Spiel hat mich damals – nach meinem Umzug nach Zürich – komplett in seinen Bann gezogen. Meine ganze Familie hat es gespielt. Einmal saßen wir zu dritt im Wohnzimmer, jeder an seinem Rechner, und jeder von uns hat parallel einen Raid geleitet.
Und wir haben uns über Bosstaktiken ausgetauscht.

Ich weiß ziemlich genau, wie ein WoW-Killer aussehen müsste. Nach 20 Jahren dasselbe Spiel reicht irgendwann einfach. Zwischendurch habe ich **Age of Conan**, **Rift** und **Aion** gespielt – aber nichts kam wirklich an WoW heran.

Ich glaube ehrlich gesagt, der einzige, der einen echten WoW-Killer bauen könnte, ist …
Blizzard selbst.

Man müsste einfach den besten Release-Stand nehmen – für mich ganz klar WotLK – und darauf komplett neuen Content entwickeln.
Nicht nochmal in Azeroth starten, so wie Blizzard es offenbar mit Classic Plus plant, sondern eine komplett neue Welt. Und natürlich wieder bei Stufe 1 anfangen.

Das wäre dann ein völlig neues Spiel. Ohne Guides, ohne Datenbanken wie damals Thottbot. Wieder echtes Entdecken.

Da Blizzard das nicht macht – und ich selbst niemals ein derart riesiges Projekt starten würde – habe ich nach einfacheren Wegen gesucht, ein Spiel auf den Markt zu bringen.
Candy Crush, Tower Wars und ähnliches kamen für mich nicht infrage. Die machen zwar kurzfristig Spaß, aber dieses Genre ist so stark auf Werbung und Monetarisierung optimiert, dass mir diese Sparte gestohlen bleiben kann.

Also suchte ich nach einer Idee.

Ich fragte mich: Was gefällt mir eigentlich an WoW?
Ganz klar: die soziale Komponente. Die war vor 20 Jahren, als das Spiel neu war, wirklich stark. Heute ist davon kaum noch etwas übrig. Es geht um Boosting, GDKP, GearScore – aber nicht mehr ums gemeinsame Erkunden.

Was gefällt mir noch?
Raids. Und zwar schwierige Raids. Raids, bei denen man eine Taktik braucht und nicht einfach nur Tank and Spank.
Das gibt es in WoW Classic so nicht mehr, weil man alle Raids und Bosse längst kennt. Retail spiele ich ohnehin nicht mehr – das fühlt sich für mich einfach falsch an.

Also dachte ich: Ich möchte etwas mit Raids machen.
Und was ich extrem spannend fände: Wenn man statt echter Spieler auch Bots einladen könnte. Eigene Charaktere, die man auf einfache Weise skripten kann.
Rotationen festlegen. Entscheiden, wann ich mit Blitzheilung heile, wann mit der großen Heilung. Oder ob ich noch einen Frostblitz caste oder lieber einen Cooldown zünde.

Dann kam die nächste Frage:
Muss so ein Spiel überhaupt ein klassisches 3D-Spiel sein? Oder reicht mir eine Simulation?

Natürlich möchte man es fühlen. Aber ich wollte auch kein 2.5D-Spiel wie Diablo, bei dem man immer aus derselben Perspektive schaut. Man sollte mittendrin sein können.

Ich habe daraufhin mit den Third-Person-Controllern in Godot, Unity und Unreal Engine experimentiert. Was fühlt sich besser an?

Unity hat mir gar nicht gefallen. Vor jedem Testlauf gab es erst einmal einen Compile-Durchgang, der den Flow komplett ausgebremst hat.
Godot hingegen machte richtig Spaß. Schnell gestartet, direkt spielbar – zumindest solange man mit GDScript arbeitet.

Unreal Engine wiederum: Das Animations-Pack aus UE 5.7 fühlt sich unfassbar real an. Aber …
ich sitze hier an einem Mac Mini mit M2 und 8 GB RAM. Das ist keine Maschine, um ernsthaft mit Unreal zu arbeiten.

Dann hatte ich Glück: Ein Kumpel schenkte mir seinen inzwischen zehn Jahre alten PC. Der brauchte nur ein neues Netzteil, weil er bei Hitze einfach abgeschaltet hat – der Lüfter war defekt.

Inzwischen stecken darin 32 GB RAM, eine RTX 5050 mit 8 GB VRAM und eine 1-TB-SSD.
Keine High-End-Workstation mit DDR5, aber das kann und will ich mir aktuell auch nicht leisten. Und ehrlich gesagt: So kann ich wenigstens testen, ob das Spiel später auch auf älteren Rechnern läuft.

Trotzdem blieb ich zunächst bei Godot, einfach weil es Spaß machte.
Ich dachte mir, man könnte auch ein Low-Poly-Spiel bauen. Weniger Dreiecke, weniger Overhead – vielleicht sogar etwas in Richtung Minecraft. Das ist nicht nur Low Poly, das ist extrem minimalistisch. Notch hat das damals sogar in Java geschrieben.

Also habe ich mir das genauer angeschaut und Luanti heruntergeladen – einen Open-Source-Klon von Minecraft.
Und da war mir klar: So möchte ich meine Level bauen. Dungeons, Räume, Strukturen. Das machte unglaublich viel Spaß.

Zuerst schrieb ich ein Mod für Luanti, um die Level speichern zu können. Und zwar diffbar als Text.
Dafür habe ich SML (Simple Markup Language) verwendet, das ich ursprünglich für meinen NoCodeDesigner entwickelt hatte.
Plötzlich hatte ich komplette Level in Textform – und konnte daraus Szenen für Godot generieren.

Aber das Arbeiten mit Luanti war am Ende doch nicht ganz das, was ich wollte.
Bevor ich Luanti forke, umbenenne, branden, Optionen entferne und alles auf mein Projekt zuschneide, dachte ich mir: Warum nicht gleich einen eigenen Level-Editor bauen?

Die erste Version habe ich mir mit Codex direkt in Visual Studio Code schreiben lassen.
Relativ schnell sind wir dabei an Grenzen gestoßen. Also habe ich Nägel mit Köpfen gemacht, das Vulkan SDK installiert und Codex gebeten, die Godot-App in C++ nachzucoden.

Wenn ich mir heute die Logs anschaue, hat das Ganze etwa zwei Tage gedauert.
Wobei ich zugeben muss: Eine Nacht davon habe ich durchgemacht, weil es einfach zu spannend war, zuzusehen, was da entsteht.

Wir haben Dear ImGUI für die UI verwendet. ImGUI rendert direkt auch in 3D – passt also perfekt.
Um den gigantischen ImGUI-Code-Wald zu vermeiden, haben wir die UI wieder in SML deklariert, zur Laufzeit geparst und daraus gerendert.

Mein Part bestand im Wesentlichen darin, die UI in SML zu beschreiben.
Den gesamten C++-Code hat Codex geschrieben.
Und ganz ehrlich: Wenn man einmal gesehen hat, wie man UI in ImGUI „klassisch“ schreibt, weiß man diese Abstraktion extrem zu schätzen.
Da ist man selbst mit Qt schneller – und das will schon was heißen.

Schon früh haben wir Tests gemacht, um zu prüfen, ob die Probleme, die wir mit Godot hatten, in Vulkan besser laufen.
Und ja: Sie liefen nicht nur besser, sondern deutlich schneller.
Features, für die wir in Godot Stunden gebraucht hatten, hat Codex in Vulkan innerhalb weniger Minuten umgesetzt.
Es lief einfach.

Dann kam aber der Punkt, an dem ich „nur mal schnell“ einen Block anvisieren und mit den Pfeiltasten rotieren wollte.
Ich hatte explizit gesagt: Bau es genau so wie in Godot.

Und es funktionierte nicht.

Stand ich vor einem Block und drückte Pfeil nach oben, rollte der Block sauber über die X-Achse.
Drehte ich ihn vorher um die Y-Achse und wollte ihn danach wieder rollen, rotierte er plötzlich über die Z-Achse.

Wir haben stundenlang nach dem Fehler gesucht.
Ich habe mir sogar ein physisches Modell aus einer Schachtel gebaut, um Codex exakt erklären zu können, welche Seite nach welcher Rotation oben ist.
Wir haben Gizmos gebaut, die Rotation visualisiert, alles.

Nach gefühlten acht Stunden sagte ich frustriert:
„Scheiß drauf, wir rollen alles zurück und machen es komplett anders.“

Dann kam mir noch eine letzte Idee.
Ich fragte: „Erklär mir bitte mal, wie du verstanden hast, was du bauen sollst.“

Und da war es.
Ein Missverständnis. Mein Prompt war nicht präzise genug. Oder wir hatten in Godot selbst einen Bug, den ich nie sauber getestet hatte.

Kurz darauf kam dann diese Meldung:

> „Du hast keine Codex-Nachrichten mehr. Kaufe mehr, um fortzufahren, oder warte bis …“

Ich war ehrlich gesagt davon ausgegangen, dass Codex-Nutzung mit ChatGPT Plus flat ist.
War sie nicht.

Also: Adrenalin runterfahren. Analysieren. Neu denken.

Ich nutze ChatGPT übrigens genau für solche Reflexionen. Gemeinsam sind wir auf die Idee gekommen, einen Prozess ähnlich dem **RUP** (Rational Unified Process) zu etablieren.
Codex wird dabei wie ein temporäres Teammitglied behandelt, das jeden Tag neu ins Projekt kommt und sich selbstständig einarbeitet.

Die Session – also der große KI-Context – muss dadurch nicht permanent gehalten werden.
Stattdessen resetten wir bewusst, verlieren unnötige Informationen und starten wieder klein.
Dafür lege ich Artefakte an, mit denen Codex sich schnell orientieren kann. Dann schreiben wir konkrete Tasks ins Backlog und lassen sie gezielt implementieren.

Eine Mischung aus RUP und Scrum.
Wir nennen es **CWUP – CrowdWare Unified Process**.

Und wenn das Kontingent für diese Woche wieder ausgeschöpft ist, mache ich drei Dinge:
	1.	Ich schreibe an diesem Buch weiter.
	2.	Ich plane die nächsten Tasks mit ChatGPT.
	3.	Ich mache Pause.

Das ist wichtig. Ich habe bereits zwei Burnouts hinter mir. Einen dritten brauche ich nicht.

Wenn du übrigens selbst einmal in so eine Situation mit KI kommst, sag nicht:
„Oh Mann, bist du dumm“ oder „Kannst du nicht mal einfache Aufgaben erledigen?“

Eine KI ist immer nur so gut wie dein Prompt.
Du sprichst nicht mit einem Menschen. KI hat kein Bewusstsein.
Sie folgt Mustern – und vor allem versucht sie, dir zu helfen.