Hallo.

Quake 3 Movie Maker's Edition ist eine spezielle Version der Quake 3 Engine,
die es erleichtern soll, Game Movies zu erstellen. Sie macht es m�glich,
Aufgaben einfacher durchzuf�hren und f�gt neue Funktionen zur Engine hinzu,
die sich auf Moviemaking beziehen.

Diese Version - 1.33.4.1.

Unterschiede zu Quake 3:
  * Es gibt die M�glichkeit, die Skybox mit einer beliebigen soliden Farbe zu
    f�llen, auch bei 'Space' Maps, ohne etwas an der Map zu ver�ndern.
  * Einer beliebigen Spielernummer kann ein bestimmtes Model zugewiesen
    werden.
  * TGAs k�nnen mit RLE Kompression komprimiert werden.
  * W�hrend Avidemo k�nnen JPEG Screenshots gemacht werden.
  * W�hrend Avidemo kann WAV sound gespeichert werden.
  * Die Pr�zision der Avidemo Frame Rate wurde erh�ht, jetzt wird genau in der
    gleichen Zahl FPS aufgenommen, wie cl_avidemo spezifiziert wurde. 24FPS
    werden kein 24,39FPS Output und 300FPS kein 333FPS Output mehr erstellen.
    (sehr n�tzlich im Bezug auf TGA_Hook)
  * Eine Demo wird bei Dr�cken einer beliebigen Taste nicht mehr gestoppt.
  * Einige Bugs in der Engine wurden behoben.
  * Die Anzahl der m�glichen Screenshots ist nicht mehr auf 10000 begrenzt.
  * Fenstermodus schaltet die Hardware Overbright Unterst�tzung nicht aus, das
    wird helfen, bei jeder beliebigen Aufl�sung zu rendern, komplett ohne den
    Vollbildmodus zu verwenden.
  * Screenshots werden im Unterverzeichnis mit dem Namen der Demo platziert.


Es funktioniert mit OSP, Defrag, CPMA und jeder anderen Quake 3 Mod, die mit
dem originalen Quake 3 v1.32 gut l�uft.

Als zus�tzliches Plus l�uft es auch mit TGA_Hook: W�hle TGA Screenshot Format
und schalte TGA RLE Kompression aus. Wahrscheinlich musst du den TGA_Hook
exe Dateipfad in der Registry modifizieren. Gehe in der Registry zum Schl�ssel
"HKEY_LOCAL_MACHINE\SOFTWARE\14K\Hooker\ExeLocation" und gib statt dem Pfad
der quake3.exe den Pfad deiner quake3mme.exe ein. Das Feature der Screenshot-
Benennung wird wegen offensichtlicher Gr�nde nicht funktionieren: TGA_Hook
generiert die Namen der Screenshots.

Sei vorsichtig mit dem Export bei Fenstermodus: Du musst immernoch Quake3MME
im Vordergrund lassem, damit du korrekte Screenshots bekommst.

Viele Leute finden es schade, dass das Rendern mit Avidemo nicht Realzeit ist.
Es rendert, bis es fertig ist und die Frame Rate der Ausgabedatei h�ngt dabei
nicht davon ab, wie gut deine Hardware ist.


Neue Konsolenbefehle in Quake3MME:
  * mme_skykey <Nummer>   - Wenn nicht gleich Null, dann wird Skybox mit einer
                            soliden Farbe gef�llt.
                 (standard) 0 = ausgeschaltet
                            1 = rot
                            2 = gr�n
                            3 = gelb
                            4 = blau
                            5 = cyan
                            6 = magenta
                            7 = weiss
                            8 = schwarz

  * mme_playernumbers     - Zeigt die einem Spieler zugeordnete Spielernummer.
                            Spielernummern werden f�r die folgenden Konsolen-
                            Befehle gebraucht.

  * mme_forcemodelplayerX - Force Model f�r Spieler X. Insgesamt 16 Spielern
                            k�nnen bestimmte Models zugewiesen werden. ACHTUNG:
                            Damit dies funktioniert m�ssen 'cg_enemymodel' und
                            'cg_forcemodel' ausgeschaltet sein.

  * mme_wavdemo_enabled   - Kontrolliert die Aufnahme von .wav Sound w�hrend
                            Avidemo. Als Nebeneffekt gibt es keinen Sound mehr
                            durch die Soundkarte. Der Sound wird nach
                            "screenshots/wav" exportiert.
                 (standard) 0 = es wird kein Sound exportiert
                            1 = Sound wird w�hrend Screenshooting exportiert.
                            2 = Screenshooting wird �bersprungen und es wird
                                nur Sound exportiert

  * mme_screenshot_format - Selbsterkl�rend - Das Format der Screenshots.
                 (standard) tga  = Screenshots werden in TGA exportiert
                            jpeg = Screenshots werden in JPEG exportiert

  * mme_tga_rle_compress  - TGA RLE Kompression einschalten. Spart ein
                            bisschen Speicherplatz.
                            0 = TGA RLE Kompression ausschalten
                 (standard) 1 = TGA RLE Kompression einschalten

  * mme_jpeg_quality      - Stellt den Level der Kompression f�r JPEG
                            Screenshots ein, sofern JPEG Screenshots
                            verwendet werden.
                            0-100 = Kompressionslevel
                               90 = standard

  * mme_jpeg_optimize_huffman_tables
                          - Spart ein bisschen Platz auf der Festplatte
                            durch Optimierung der Screenshots, doch
                            dadurch wird das Screenshooting ein wenig
                            verlangsamt.
                            0 = Schaltet "optimized huffman tables" aus
                 (standard) 1 = Schaltet "optimized huffman tables" ein

  * mme_jpeg_downsample_chroma
                          - Schreibt den Farbbestandteil mit niedrigerer
                            Aufl�sung, spart Platz in Kompromiss mit der
                            Qualit�t. Sollte ausgeschaltet bleiben, ausser
                            es wird mit sehr hoher Aufl�sung aufgezeichnet.
                 (standard) 0 = Schaltet 'chroma downsample' aus
                            1 = Schaltet 'chroma downsample' ein

  * mme_anykeystopsdemo   - Verhindert, dass das Dr�cken beliebiger Tasten
                            das Abspielen der Demo stoppt. Diese Tasten
                            k�nnen stattdessen mit Funktionen belegt werden.
                            0 = Tastendruck beendet Abspielen der Demo
                 (standard) 1 = Tastendruck beendet Abspielen der Demo nicht

  * mme_roundmode         - Wenn auf 1 gesetzt, wird die Berechnung der Phsyik
                            genauer ausgef�hrt, weil der Rundungsprozess wie
                            in C verl�uft. Beeinflusst Strafejumping w�hrend
                            des Spiels (bei Demo Wiedergabe nicht), also habe
                            ich eine Option eingebaut, die das Umschalten zum
                            alten Q3 Style m�glich macht.
                            0 = Berechnung der Spielphysik wird nicht ge�ndert
                 (standard) 1 = Berechnung der Spielphysik wird genauer durch-
                                gef�hrt. Beeinflusst Demo Aufnahme, nicht Demo
                                Wiedergabe.

----------------------------
Kontakt: HMage - hmd@mail.ru

http://hmd.c58.ru/muwiki/quake3mme
http://sourceforge.net/projects/quake3mme

------
Thanks

Ich m�chte jrb von shaolinproductions f�r seine Unterst�tzung und das
Bearbeiten der englischen Version dieser Datei danken.

Ich m�chte Auri f�r seine Unterst�tzung und die Bearbeitung der
deutschen Version dieser Datei danken.

----------
Change Log

1.33.4:
  * Probleme beim Verwenden mit TGA_Hook beseitigt.
  * Fenstermodus deaktiviert das Overbright Bits Feature nicht.
  * Screenshots werden basierend auf dem Namen der Demo benannt und in einem
    Unterverzeichnis abgelegt.
  * WAV Sound wird in einem Unterverzeichnis mit dem Namen der Demo abgelegt.
  * Bugfixes von icculus.org/quake3 angef�gt.

1.33.3:
 * Export von WAV Sound erm�glicht.
 * Pr�zision der Avidemo Frame Rate erh�ht.
 * W�hren Avidemo k�nnen JPEG Screenshots gemacht werden.
 * Alpha Buffer Initialisierungscode angef�gt, wird aber noch nirgends
   verwendet.
 * Bug "Unknown Client Command" am Anfang einer Map behoben.
 * Englische Readme-Datei angef�gt.

1.33.2:
 * Russische Readme-Datei angef�gt.
 * Die Skybox kann mit einer soliden Farbe gef�llt werden.
 * Ein beliebiges Model kann einer bestimmten Spielernummer zugeordnet werden.
 * Wiedergabe einer Demo wird nicht durch Dr�cken beliebiger Tasten gestoppt.
 * Qualit�t des Rundungsprozesses bei Berechnung der Spielphysik kann mit
   Hilfe eines Konsolenbefehls erh�ht werden.

1.33.1:
 * Begrenzung von 10000 Screenshots entfernt.
