# HCI – Die Schicht zwischen Gedanke und Code

Ich habe Human–Computer Interaction studiert.  
Damals hieß HCID für mich ganz selbstverständlich:

**Mensch Computer Interaktions Design.**

---

## Was HCID ursprünglich bedeutete

HCID wurde klassisch so gelehrt:

Ein Mensch interagiert mit einem technischen System  
über eine **Benutzungsoberfläche**.

Typische Themen waren:
- Buttons, Menüs, Fenster
- Maus, Tastatur, Touch
- Wahrnehmung, Aufmerksamkeit, Gedächtnis
- Fehlertoleranz und Feedback
- Konsistenz und mentale Modelle

Kurz gesagt:

> *Wie muss ein Computer aussehen und reagieren,  
> damit ein Mensch ihn möglichst gut bedienen kann?*

Der Fokus lag auf:
- UI-Elementen
- Interaktionsabläufen
- visueller Gestaltung
- ergonomischer Anordnung
- Reaktionszeiten

Das war wichtig.  
Aber es war **nicht vollständig**.

---

## Was damals gefehlt hat

Was in der klassischen HCID-Lehre kaum vorkam, war diese Frage:

> **Wie interagiert ein Mensch mit einer Idee,  
> bevor es überhaupt eine Oberfläche gibt?**

Der Mensch denkt nicht in:
- Widgets
- APIs
- Klassen
- Frameworks

Der Mensch denkt in:
- Bedeutungen
- Beziehungen
- Absichten

Und genau hier beginnt der Teil von HCI,  
den ich damals noch nicht sehen konnte.

---

## Die Erkenntnis: HCID ist nicht zwingend Mensch ↔ Computer

Mit zunehmender Erfahrung wurde mir klar:

HCI muss keine direkte Verbindung  
zwischen Mensch und Maschine sein.

Man kann eine **Schicht dazwischen ziehen**.

Eine Schicht, in der:
- Gedanken formuliert werden
- Bedeutungen beschrieben werden
- Strukturen entstehen

Eine Schicht, die:
- nicht an eine Engine gebunden ist
- nicht an eine Plattform gebunden ist
- nicht an eine konkrete Implementierung gebunden ist

Diese Schicht ist bei mir **SML**.

---

## SML als Ausdruck von Absicht

SML ist keine klassische Programmiersprache.  
Und es ist auch kein UI-Framework.

SML beschreibt **was manifestiert werden soll**.

Zum Beispiel:

```qml
Button {
    texture: "wall.png"
    offset: 4,5
}
```

Das sagt nicht:
- wie der Button gerendert wird
- wie Events gebunden werden
- wie die Engine intern arbeitet

Es sagt nur:
- Es gibt einen Button.
- Er hat diese visuelle Bedeutung.
- Er ist dort positioniert.

Oder:

```qml
RessourceBar {
    color: "0xFFFF0000"
}
```

Das ist keine konkrete Progressbar-Implementierung.
Es ist die Absicht, eine Ressource sichtbar zu machen.

Oder:
```qml
Minimap {
    mask: circle
}
```

Hier steht nicht:
- welche Shader
- welche Rendertechnik
- welche Texturen

Sondern nur:

>Diese Information soll als Minimap erscheinen,
>und ihre Bedeutung ist kreisförmig begrenzt.

---

## Manifestation statt Implementierung

Aus SML entsteht Code.
Aber dieser Code ist nicht das Primäre.

Das Primäre ist die Beschreibung der Absicht.

Wenn sich etwas ändert:
- ändere ich nicht den Code
- ich ändere das SML

Und daraus kann:
- neuer Code generiert werden
- bestehender Code angepasst werden
- eine andere Plattform entstehen

Der Gedanke bleibt stabil.
Die Manifestation ist austauschbar.

---

## Ein reales Beispiel: Ein Fenster als Absicht

Das folgende SML beschreibt das komplette Grundlayout des RaidBuilder:
```qml
Window {
    title: "RaidBuilder"
    position: 20,20
    size: 1280,720

    state {
        persist: user
        pos: true
        size: true
        maximized: true
        lastFilePath: true
        docking: true
        theme: "dark"
    }

    MainMenu {
        Menu {
            label: "File"

            MenuItem { label: "Open" }
            Separator {}
            MenuItem { label: "Save" }
            MenuItem { label: "Save As" }
            Separator {}
            MenuItem {
                label: "Exit"
                clicked: "exit"
                useOnMac: false
            }
        }
    }

    ToolBar {
        height: 48
        ToolButton { icon: play }
    }

    StatusBar {
        height: 24
    }

    DockLayout {
        Left {
            label: "Toolbar"
            width: 56
            Column {
                ToolButton { icon: select }
                ToolButton { icon: move }
                ToolButton { icon: paint }
            }
        }

        Right {
            label: "Properties"
            width: 400
            PropertyPanel { }
        }

        Center {
            label: "Viewport"
            Box {
                Viewport3D { }
                Overlay {
                    // gizmos, hints, selection rect
                }
            }
        }
    }
}
```

Dieses Fragment ersetzt über 1900 Zeilen Vulkan-Code.

---

## Was hier nicht steht

In diesem Text steht kein Hinweis auf:
-Vulkan
- Swapchains
- Command Buffers
- Pipelines
- Descriptor Sets
- Render Passes
- Plattform-spezifische Window-Handles
- Event-Loops
- DPI-Scaling
- Docking-Implementierungen

Und doch entsteht dieselbe Oberfläche.

Nicht, weil der Code verschwindet,
sondern weil er nicht mehr die Ausdrucksform ist.

---

TODO: Bild vo Vulkan-Sample

Abbildung: Screenshot eines Vulkan-Beispiels, das allein für Fenster, Layout, Menü, Toolbar und Statusbar über 1900 Zeilen Code benötigt.

Diese 1900 Zeilen Code beschreiben:
- Initialisierung
- Render-Pipelines
- Event-Verteilung
- Zustandsverwaltung
- Plattformabstraktion

Alles korrekt.
Alles notwendig.

Aber nichts davon ist die eigentliche Idee.

---

## Warum das HCID ist

Klassische HCID fragt:

>Wo klickt der Benutzer?

Diese Schicht fragt:

>Was ist dieses Werkzeug?
>Welche Teile hat es?
>Wie hängen sie zusammen?

Der Mensch interagiert hier nicht mit:
- Pixeln
- Events
- APIs

Sondern mit:
- Struktur
- Bedeutung
- Absicht

Das ist HCID vor der Oberfläche.

---

## Die Rolle der KI

Die KI ist kein Autor.
Sie ist ein Übersetzer.

Sie übersetzt:

>Absicht → Struktur → Code

Sie erzeugt:
- wiederverwendbaren Code
- anpassbaren Code
- austauschbare Implementierungen

Die Autorenschaft bleibt im SML.

---

## HCID neu verstanden

Ich habe HCID studiert,
ohne zu wissen,
dass HCID nicht zwingend
Mensch ↔ Computer bedeuten muss.

Heute weiß ich:

>Die wichtigste Interaktion ist die
>zwischen Gedanke und Manifestation.

SML ist diese Schicht.
KI ist das Werkzeug.
Code ist das Ergebnis.

Und genau hier fühlt sich HCI
zum ersten Mal vollständig an.