# Unreal Engine

Am Anfang habe ich mit verschiedenen Game-Engines experimentiert. **Unreal Engine** sah dabei extrem beeindruckend aus. Ich hatte damals ein recht leistungsfähiges Gaming-Notebook und habe mir aus Spaß die MegaCity-Demo heruntergeladen. Wie groß war die noch gleich? Etwa 100 GB? Ich weiß es nicht mehr genau, aber die Stadt im Beispiel war ungefähr so groß wie **Los Santos** aus GTA V.

Was mich wirklich erstaunt hat: Unreal konnte diese riesige Welt rendern, ohne dass dafür ein Mainframe nötig war – also diese sehr großen und sehr schnellen Computer aus der Steinzeit der IT.

Als ich Unreal allerdings auf meinem **Mac mini mit 8 GB RAM** ausprobiert habe, wusste ich sofort:
Ach nee … ich schaue mir lieber mal Godot an.

Und Godot war dann auch sofort sympathisch: Es startete extrem schnell, und wenn man mit **GDScript** arbeitet, muss man nicht einmal kompilieren.

Nichtsdestotrotz habe ich meinen alten PC aufgerüstet, um mir Unreal wenigstens einmal richtig anschauen zu können – allein schon, um daraus zu lernen. Mit **32 GB RAM** und **8 GB VRAM** sah die Sache schon deutlich besser aus, aber die alte HDD war permanent am Limit, was die IO-Last anging.

Also bestellte ich mir eine **1-TB-SSD** und versuchte darauf **Pop!_OS (Linux)** zu installieren.
Aber irgendwie waren mein BIOS, die Platte und Linux schlicht inkompatibel. Selbst eine längere Session mit ChatGPT brachte keine Lösung. Ich konnte die Platte einfach nicht partitionieren. Wir probierten das Installationsprogramm, gparted, parted – nichts half.

Also installierte ich Windows, mit dem Gedanken:
„Geil, dann kann ich auf dem Rechner wenigstens auch zocken.“

Das nächste Problem: Ich hatte nur einen Monitor und musste ständig das Kabel zwischen Mac und PC umstecken.
Bis ich durch ChatGPT von **Moonlight** und **Sunshine** erfuhr – im Prinzip eine Remote-Desktop-Lösung für Gamer. Ich konnte am Mac sitzen und hatte den Windows-Desktop direkt auf meinem Mac-Screen. Den Controller hatte ich direkt am PC angeschlossen, also ganz nativ.

Auf diese Weise installierte ich **Battle.net**, um WoW zu spielen, und stellte schnell fest: Installationen sind der absolute Killer für Sunshine, was die Bandbreite angeht. Die Maus ruckelte so stark, dass Arbeiten praktisch unmöglich war.

Frustriert suchte ich erneut nach einer Lösung für mein Linux-Partitionierungsproblem, denn eigentlich wollte ich doch lieber unter Linux entwickeln. Du kennst das sicher: Plötzlich geht der Lüfter deines PCs los, obwohl du gar nichts machst.
Dann scannt Windows vermutlich wieder irgendetwas, schreibt Indizes neu, sammelt Telemetriedaten – oder was auch immer.

Also suchte ich auf Stack Overflow weiter – und wurde fündig. Im BIOS war der SATA-Controller auf **IDE** gestellt. Umgestellt auf **SATA**, neu gestartet – und bumm: Pop!_OS ließ sich problemlos auf der neuen Platte installieren.

Natürlich wollte ich jetzt auch Unreal installieren. Allerdings gibt es keinen Unreal-Launcher für Linux. Stattdessen sollte man ein **30-GB-ZIP** herunterladen. Als der Download nach etwa 20 GB abbrach und sich nicht fortsetzen ließ, fragte ich ChatGPT nach einer Alternative.

Die Antwort: Man kann sich den **Unreal-Sourcecode direkt von GitHub holen**.

Aha. Die haben den Sourcecode veröffentlicht!

Aber was ich dann in der README las, war noch viel besser:

Modify the code in any way you can imagine, and share your changes with others!

„Ich darf den Code sogar anpassen? Wie geil ist das denn?“

Ich könnte also das Repository forken, den ganzen Ballast entfernen, den ich gar nicht brauche, und den Rest gezielt auf meine Bedürfnisse zuschneiden. Und weißt du was? **Über 57.000 andere Leute haben das bereits gemacht.**

Darüber musste ich erst einmal nachdenken. Eigentlich ist in Unreal bereits alles vorhanden. Ich muss keine Engine neu bauen – nicht bei einem einzelnen Dreieck anfangen, das ich mühsam mit OpenGL rendere. Ich kann Unreal einfach nutzen.

Ich muss auch keine Blueprints selbst zusammenklicken, sondern kann Codex sagen, was geändert werden soll. Ich sieze Codex übrigens – ich finde, sie ist manchmal ein bisschen zickig. 😉

Wenn ich also die Anpassungen der Engine an eine KI delegieren kann – was mit Blueprints deutlich schwieriger wäre – dann kann ich Unreal tatsächlich für meine Zwecke umbauen oder erweitern lassen.

Und wenn ich meine Level und Game-Elemente auch noch in meiner Lieblingssprache **SML** beschreiben kann, dann geht mir das alles erstaunlich leicht von der Hand.

Ich sollte es einfach ausprobieren.
Und selbst wenn es am Ende nicht passt: Unreal kann ich immer noch nutzen, um von ihr zu lernen.