# M239 Mail Protokolle


## Einführung

Wenn man ein E-Mailkonto auf dem PC einrichten will, kommt schnell die Frage, mit welchem Verfahren die E-Mails vom Server heruntergeladen werden sollen. Hier gibt es verschiedene Varianten, aber die gängigsten sind sicher POP und IMAP. Über diese Protokolle kommunizieren die Clients (Outlook, Thunderbird, usw.) mit den Servern (Bluewin, GMX usw.)

### Konkretes Beispiel

Wen zum Beispiel Peter seine Emails über Microsoft Outlook von Zuhause aufruft, dan wird POP benutzt um die neusten E-mails herunterzuladen. Je nach dienstleister ist das Mailprotokoll anders und nathürlich gibt es auch besser und schlechtere.  

### Was ist ein Mailserver

Jede gesendete E-Mail durchläuft auf ihrem Weg zum Empfänger eine Reihe von Mailservern. Auch wenn es den Anschein hat, dass eine Nachricht sofort versendet wird, so findet in Wirklichkeit eine komplexe Reihe von Übertragungen statt. Ohne diese Reihe von Mailservern könnten Sie nur E-Mails an Personen senden, deren E-Mail-Adressdomänen mit Ihren eigenen übereinstimmen - d. h. Sie könnten nur Nachrichten von einem example.com-Konto an ein anderes example.com-Konto senden.

## Mailserver ausfindig machen

Der Mailserver lässt sich einfach über das CMD herausfinden. Dort kan man mit dem telnet befehl die MX-Records ganz einfach finden.

BILD


### SNTP

SMTP (Simple Mail Transfer Protocol) legt fest und steuert, wie Ihre E-Mail vom MTA Ihres Computers zu einem MTA auf einem anderen Computer oder sogar auf mehreren Computern weitergeleitet wird. Mit der bereits erwähnten "Speichern und Weiterleiten"-Funktion kann die Nachricht schrittweise von Ihrem Computer zu ihrem Ziel gelangen. Bei jedem Schritt verrichtet das Simple Mail Transfer Protocol seine Arbeit. Zum Glück für uns läuft das alles im Hintergrund ab, und wir müssen SMTP nicht verstehen oder bedienen.

### Telnet

Mit Telnet ist es auch möglich ein Mail komplett von Hand zu versenden und nein ich meine damit nicht den Inhalt sondern auch das ganze Runherum. Dafür sind folgende Befehle notwendig:

Befehl | Funktion | 
|----------|:-------------:|
| Helo | Name vom Client wird definiert 
| Mail FROM: | Absenderadresse wird festgelegt 
| RCPT TO: | Empfängeradresse wird festgelegt 
| Data | Inhatl des mails wird gestartet 
| Quit | Verbindung zu Server wird getrennt 

Ein Mail ist so aufgebaut: 

1. From:
2. To:
3. Subject:
4. Date:
5. Inhalt des Mails
   
Diese Sachen sollten in jedem Mail stehen. 

### POP3

POP3 (Post Office Protocol 3) ist die neueste Version des POP Standardprotokolls zum Empfang von E-Mails. POP3 ist ein Client/Server-Protokoll, bei dem E-Mails von Ihrem Internet-Server empfangen und für Sie vorgehalten werden. In regelmäßigen Abständen überprüfen Sie (oder Ihr Client-E-Mail-Empfänger) Ihr E-Mail-Postfach auf dem Server und laden alle E-Mails herunter, wahrscheinlich mit POP3. Dieses Standardprotokoll ist in den meisten gängigen E-Mail-Produkten, wie z. B. Eudora und Outlook Express, integriert. Es ist auch in den Browsern Netscape und Microsoft Internet Explorer integriert.

### Base64

Base64 ist ein Binär-zu-Text-Kodierungsschema, das im Allgemeinen für die Übertragung inhaltsbasierter Nachrichten über das Internet verwendet wird. Es funktioniert, indem alle drei Bits der binären Daten in sechs Bit-Einheiten unterteilt werden. Die neu erzeugten Daten werden in einem 64-stelligen Zahlensystem und als sieben Bit langer ASCII-Text dargestellt. Da jedes Bit in zwei Bits aufgeteilt wird, sind die konvertierten Daten 33 Prozent oder ein Drittel größer als die ursprünglichen Daten.


Picture

In diesem obigen Beispiel wird die Zeichenkette "THS" mit dem base64-Operator (<<<) auf der Linux-CLI in das base64-Format kodiert. Wir können sehen, dass wir die kodierte Ausgabe erhalten, d. h. VEhTCg==.

### IMAP

Internet Message Access Protocol ist ein Protokoll zum Abrufen und Speichern von E-Mails, das 1986 von Mark Crispin an der Stanford University als Alternative zu POP entwickelt wurde. IMAP erlaubt im Gegensatz zu POP insbesondere, dass mehrere Clients gleichzeitig mit demselben Postfach verbunden sind. Durch auf dem Server gespeicherte Flags können verschiedene Clients, die zur gleichen oder zu unterschiedlichen Zeiten auf dasselbe Postfach zugreifen, Zustandsänderungen durch andere Clients erkennen.

### POP3 im Vergleich zu IMAP

IMAP bietet im Vergleich zu POP3 zahlreiche Vorteile, besonders für Fernzugriff auf E-mails. In Produktieven bereichen wird heuzutage praktisch nur noch IMAP vewendet. POP3 wird nur eigentlich nur werwendet wen, man keine andere möglichkeit hat oder nicht umstellen möchte. 
