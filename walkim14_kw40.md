# *Protokoll*  
## *Thema: AVR-Studio*
 Name:   Kilian Franz Rudolf Waltl 
 Klasse: 4AHME  
 Datum: 26.09.2017  
 Anwesend: Strutz,Tuttner, Uhl, Waltl, Wieser, Zitz  
 
 ### *Mikroprozessor (µP)*
 Als erstes besprachen wir den prinzipiellen Aufbau:  
 ![CPU Blockdiagramm](https://github.com/strsem13/test1/blob/master/Blockdiagramm_CPU.png)  
 Befehlsablauf (Von-Neumann-Architektur):  
 * Reset -> Versetzt die CPU in einen Ausgangszustand, es setzt den Befehlszähler auf 0, und die Bits im Status-Flag werden zurückgesetzt.
 * Takt oder Clock -> Bestimmt wie schnell die einzelnen Befehle ausgeführt werden.  
 * Steuerwerk -> Lädt den nächsten befehl aus dem Speicher.  
 * Befehls-Decoder -> Übersetzt den geschrieben Quelltext in Maschinensprache.  
 * ALU -> "Arithmetic Logic Unit" -> Führt die Rechenoperationen durch.
 * Programcounter -> Wird mit jedem neuen Programmablauf aktualisiert. 
 
 
 ### *Atmel Studio*  
Atmel Studio (früher AVR-Studio) ist eine Open-Source Software zur Programmierung der AVR-Mikroprozessoren. Es basiert auf der Visual Studio Shell von Microsoft und besteht aus einer Projektverwaltung, einem Editor, einem Debugger und Werkzeugen zum Beschreiben eines Mikroprozessors.  

In Atmel Studio kann man C/C++ sowie mit Assembler programmieren.  
Durch Atmel Studio kann das geschriebene Programm zuerst Simuliert werden um es nicht immer mit einem Mikroprozessor testen zu müssen. Durch diese Simulation erhält detaillierte Informationen über die Maschinenbefehle, die aus dem Quellcode kompiliert wurden, außerdem hat man Einblick in die Register des Controllers.  

### *ATmega328p*  
Wir verwenden im Unterricht den Mikrocontroller ATmega328p von Atmel, da dieser in Atmel Studio nicht verfügbar ist, verwendeten wir den Mikrocontroller ATmega328.  
[Datenblatt-ATmega238p](http://www.atmel.com/Images/Atmel-42735-8-bit-AVR-Microcontroller-ATmega328-328P_Datasheet.pdf) 

#### **Produktdaten**  
* CPU-Register: 32 (jedes Register bestaht aus 8 bit)  
* EEPROM: 1kB  
* Frequenz: 16MHz   
* SRAM: 2kB 
* Flash Speicher: 32kB 

#### **XYZ-Register**  
Wird benötigt um Werte zu speichern, die größer als 255 sind.  
Setzt sich zusammen aus:  
* X= 26 & 27  
* Y= 27 & 28  
* Z= 30 & 31  

### *Stack*  
Im Stack-Speicher werden Daten nach dem LIFO Verfahren (last-in-first-out) gespeichert. Das heißt, die Daten werden von unten nach oben abgelegt, gelesen können die Daten aber nur von oben nach unten.  
Um mit dem Speicher zu kommunizieren, benötigt man folgende Operanten:  
* push: "Legt" die Datei auf den Stapel.
* pop: Liest das oberste Objekt aus, und entfernt es vom Stack.  
* peek: Liest das oberste Objekt aus, und behält es am Stack. 

#### *Stackpointer*  
Der Stackpointer zeigt immer auf den nächsten freien Platz im Stack-Speicher. Das gefährliche an einem Stack ist der sogennante "**Stackoverflow**". **Stackoverflow** bedeutet, dass der Stack-Speicher voll ist, und wenn das passiert, ist es möglich bzw. sehr wahrscheinlich, dass das System abstürtzt.

### *Debugger*  
Der Debugger findet und zeigt dem Programmierer Fehler im Quellcode. Außerdem zeigt er auch Verbesserungsvorschläge an.
