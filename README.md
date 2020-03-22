
## Inspiration

Wir haben einen Hilferuf einer Bäckerei in der [Tagesschau](https://twitter.com/klee_lina/status/1240992740890025985)  gesehen, die kurz vor dem Bankrott steht. Der Grund dafür ist, dass die Kunden in Zeiten von Social Distancing keine Produkte mehr in lokalen Geschäften kaufen. Wir wollen ihnen helfen, indem wir ihnen einen neuen Vertriebskanal - Lieferemma - zur Verfügung stellen, um die Nachfrage in Zeiten der sozialen Distanzierung zu befriedigen.

 
##  What it does

Wir bringen Kunden mit lokalem Handel, wie zum Beispiel Bäckereien und lokalen Geschäften zusammen.

In der aktuellen Zeit ist soziale Distanz gefordert. 

Das heißt aber auch, Menschen wie Max gehen nicht zum Bäcker oder ins lokale Geschäft. 
Teilweise sind Läden auch von Schließungen betroffen. 
Das stellt lokale Geschäfte wie die Bäckerei von Laura vor existentielle Herausforderungen.
Lieferemma bringt Max und Laura zusammen. 
Max kann Produkte per App bestellen.
Laura liefert die Vorbestellungen von Max mit dem Lastenfahrrad aus.
Laura fährt mit ihren Backwaren die Route ab, die ihr von Lieferemma aus den Kundenbestellungen erstellt wird.
Max bezahlt seine Produkte dann kontaktlos per App.
Zusätzlich kann Laura virtuelle Lieferpunkte anfahren, die mit Kunden wie Max von lieferemma auf einer Karte geteilt werden.
Anstatt weite Wege zu Fuß oder mit dem Auto zurückzulegen und in Schlangen zu warten, kann Max so zu vorgegebenen Zeiten den jeweiligen Händler am geteilten Standort treffen. 
Per App kann Max sich ansehen welche lokalen Geschäfte über Lieferemma zustellen und welche Produkte sie anbieten.
lieferemma.de ist kein kommerzieller Plattformansatz. 
Wir wollen lokale Geschäfte unterstützen. 
Lieferanten und Kunden können den Dienst kostenlos nutzen.
Verringere Menschenmengen in Läden oder auf Märkten, ohne deinen Einkauf ausfallen zu lassen. 

## Differenzierung

Wir wollen das Rad nicht neu erfinden, deshalb hier einige Differenzierungskriterien:

- Das Projekt hat kein kommerzielles Interesse (zumindest nicht auf der Seite der Plattform)  
- Im Gegensatz z.B. zum Pizza-Lieferservice soll der Shop mobil sein. Der Kunde kann neue Artikel nur innerhalb eines bestimmten Zeitfensters an einer vorgegeben Stelle abholen.
- Lieferemma verarbeitet keine personenbezogenen Daten, es wird mit anonymen Transaction IDs gearbeitet
- Virtuelle Lieferpunkte als temporäre Marktstände
- Die Nutzung der Plattform ist für Anbieter und Kunde kostenlos
- Das Projekt ist Open Source 

Lieferemma positioniert sich damit zwischen einem klassischen Lieferdienst und dem Marktschreier, um in Zeiten von Corona lokale Anbieter zu unterstützen ohne zusätzliche Investitionen in Technologie tätigen zu müssen.

## How we built it

Lieferemma entstand im Rahmen des [#WIRVSVIRUS Hackathons](https://wirvsvirushackathon.org/) als komplette Neutentwicklung.
Für das Projekt haben Experten aus den Bereichen Buisness, Software, Design und Marketing zusammengearbeitet um innerhalb von zwei Tagen ein erlebbares Produkt zu entwickeln. 

Lieferemma besteht aus 4 Komponenten den Sourcecode der Komponenten findet man auf Github unter den folgenden Links:

1. [Website](https://github.com/lieferemma/website) 
2. [App](https://github.com/lieferemma/frontend)
3. [Backend](https://github.com/lieferemma/backend)
4. [API](https://github.com/lieferemma/api)


Im Folgenden ein kurzer Überblick über die Komponenten.

### Website

Die Webseite [lieferemma.de](lieferemma.de) informiert Kunden und Händler über das Produkt. Händler können sich später über die Webseite als Produzenten registrieren. Kunden finden dort links zu den Apps im Playstore/Appstore. Außerdem kann man als Händler eine Flyer herunterladen um die Kunden auf lieferemma aufmerksam zu machen. 
Die Webseite wurde mit dem opensource framework [HUGO](https://gohugo.io/) erstellt.


### App

Die App wird vom Endkunden und dem Fahrer genutzt. Unten sieht man den Start Bildschirmt 


![](https://github.com/lieferemma/overview/raw/master/res/customer/001_index.png)

Hier sieht man den Bestellprozess des Kunden. Der Kunde wählt auf der Karte den Lieferpunkt aus. Danach kann er Bestellen. Auf der Karte wird ihm die Position des Lieferwagens und seine Abholzeit und Code am Abholpunkt gezeigt

<table>
 <tr>
<td><img src="https://github.com/lieferemma/overview/raw/master/res/customer/002_map.png" alt="start"
	title="Start Bildschirm"   /></td>
<td><img src="https://github.com/lieferemma/overview/raw/master/res/customer/003_order.png" alt="start"
	title="Start Bildschirm"   /></td>
    <td><img src="https://github.com/lieferemma/overview/raw/master/res/customer/004_map.png" alt="start"
	title="Start Bildschirm"   /></td>
    
</tr>
</table>



Entwickelt mit [Ionic](https://ionicframework.com/) einem Open Source Framework, dass die Entwicklung von hybriden Apps ermöglicht.
Dadurch können wir unsere App als Android, iOS -und Web-App anbieten. 



### Backend

Das Backend verwaltet das Inventar des mobilen Shops, die Routen der Fahrer und die Bestellungen der Kunden.


Der Fokus wurde bei der Architektur und Implementierung auf gute Skalierbarkeit gelegt. 
Durch die Verwendeung von Cloud nativen Technologien wie minIO, Postgres, pgadmin und Docker lässt sich das Backend leicht in der Cloud
oder auf einem Server deployen und durch die Verwendung von Kubernetes skalieren. 
Für die Implementierung der Backendlogik wurde [Rust](https://www.rust-lang.org/) verwendet. Rust ermöglicht als Systemprogrammiersprache die optimale Nutzung von Rechenleistung auf dem Server.  
Das Backend kommuniziert mit den verschiedenen Clients via gRPC. Dadurch ist eine sichere und gut skalierbare Verbindung
zwischen Clients und Server möglich.


### API

Das Backend und die verschieden Clients kommunizieren via [gRPC](https://grpc.io/).
gRPC basiert auf dem Standard HTTP/2 und Protocol Buffers und ist ein Verfahren zum  Aufruf von Funktionen in verteilten Computersystemen. Im Vergleich zu z.B. REST + JSON oder XML hat gRPC folgende Vorteile:

- HTTP2 bietet höhere Übertragungsgeschwindigkeit und Sicherheit
- gRPC lässt sich durch loadbalancing leicht vertikal skalieren 
- Durch Code-Generierungs Tools kann man leicht neue Clients für verschiedene Plattformen einbinden
- Protocol Buffers ermöglicht eine effizientere Datenübertragung als XML und JSON
- Eine stark typisierte API verhindert Doppeldeutigkeiten 



## Challenges we ran into

Die wir hatten im Rahmen vom Hackerthon viele verschiedene Herausforderungen.
Die größte Herausfordeung die wir hatten war Zeit. Wir mussten in zwei Tagen:
- Ein Team bilden
- Eine Idee generieren
- Den Fokus der Umsetzung festlegen um in kurzer Zeit ein erlebares Produkt zu bauen.

Dadurch das alle Teammitglieder Remote arbeiteten mussten wir uns koordinieren, dabei waren Tools wie jitsi und Slack sehr hilfreich. 
Beim Arbeiten haben wir auch festgestellt, dass es sehr schwer ist etwas leicht nutzbares zu bauen.


## Accomplishments that we're proud of

Trotz der oben erwähnten Herausforderungen ist uns in zwei Tagen einiges gelungen:
1. Wir haben ein neues dömänenübergreifendes Team aus Fachexperten gebildet. 
2. Die Zusammenarbeit zwischen den Designern, Buisness Developern, Softwareentwicklerung und Marketingexperten hat hervoragend funktoniert
3. Wir konnten einen großen Teil der Webseite (ca. 80%) ink. Flyern und Video bereits erstellen
4. Bei der App haben wir einen vorführbaren Stand mit Dummy Daten 
5. Wir haben eine Docker-Compose Datei mit allen Backend-Komponenten und können das Projekt dadurch schnell deployen
6. Die Backend Architektur ist bereits spezifiziert
7. Wir haben die API für die Nutzer: Endkunde und Fahrer definiert 

Wir haben unser Ziel erreicht ein erlebbares Produkt zu bauen. 

## What we learned

Wir waren sehr glücklich darüber, lernen zu können, dass es Möglich ist innerhalb kurzer Zeit, ein remote arbeitendes
Team zu Formen, welches sehr schnell eine Idee umsetzen  kann. 

## What's next for 1_001_a_lebensmittel-matching_31_Lieferemma

*Lieferemma ist jetzt zwar erlebbar aber noch nicht fertig.*

In den zwei Tagen haben wir zwar schon sehr gute Fortschritte erzielt. Allerdings werden wir noch ca. 2 Wochen Zeit investieren müssen
um eine für Kunden und Händler nutzbare Lösung zu pilotieren. Wir wollen noch an den folgenden Themen arbeiten:
- Weiterentwicklung und Deployment des Backends
- Weiterentwicklung der App-UI
- Implementierung der API zur Kommunikation zwischen App und Backend 
- Einbindung von bargeldlosen Bezahldiensten ( z.B. Paypal oder Stripe)

Unserer nächster Meilenstein ist der Beginn einer Beta-Testphase ab dem 27.03 dafür werden wir uns mit Early Adoptern zusammen tun. 
