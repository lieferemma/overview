# Introduction

You can read the story in english [below](#englisch).


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
- Lieferemma verarbeitet keine personenbezogenen Daten, es wird mit anonymen  Transaciton IDs gearbeitet
- Virtuelle Lieferpunkte als temporäre Marktstände
- Die Nutzung der Plattform ist für Anbieter und Kunde kostenlos
- Das Projekt ist opensource 

Lieferemma positioniert sich damit zwischen einem klassischen Lieferdienst und dem Marktschreier, um in Zeiten von Corona lokale Anbieter zu unterstützen ohne zusätzliche Investitionen in Technologie tätigen zu müssen.

## How we built it

Lieferemma entstand im Rahmen des [#WIRVSVIRUS Hackathons](https://wirvsvirushackathon.org/) als komplette Neutentwicklung.
Für das Projekt haben Experten aus den Bereichen Buisness, Software, Design und Marketing zusammengearbeitet um innerhalb von zwei Tagen ein erlebares Produkt zu entwickeln. 

Lieferemma besteht aus 4 Komponenten den Sourcecode der Komponenten findet man unter den folgenden Links auf github

1. [Website](https://github.com/lieferemma/website) 
2. [App](FIXME)
3. [Backend](https://github.com/lieferemma/backend)
4. [API](https://github.com/lieferemma/api)


FIXME: hier kurz erklären wie alles technisch verbunden ist 

Im folgenden ein kurzer überblick über die Komponenten 

### Website

Die Webseite [lieferemma.de](lieferemma.de) informiert Kunden und Händler über das Produkt. Händler können sich später über die Webseite als Produzenten registrieren. Kunden finden dort links zu den Apps im Playstore/Appstore. Außerdem kann man als Händler eine Flyer herunterladen um die Kunden auf lieferemma aufmerksam zu machen. 
Die Webseite wurde mit dem opensource framework [HUGO](https://gohugo.io/) erstellt.


### App

Die App wird vom Endkunden und dem Fahrer genutzt. 



Entwickelt  mit [Ionic](https://ionicframework.com/) einem opensource framework, dass die Entwicklung von hybriden Apps ermöglicht.
Dadruch können wir unsere App als Android, iOS -und web-App anbieten. 

FIXME: flow mit bildern 


### Backend

FIXME:badsf
Der 
cloud nativ tooling: minio, pgadim
Datenbanken: postgres
Blob-Storage :minio
api: gRPC sicherer verbindung zum backend load

Kubernetes ready
architektur technologien skalierbarkeit

in rust 

FIXME: bilder mit flow zum erklären


### API

gRPC
- http2 ermöglicht einfache skalierung ( buzzwords für http2 , bessere verbindungsparallität )
- stub code generierung ( gut für opensource contribtuions, man kann leicht contribtue) neue clients lassen sich einfach einbinden z.B für verschiedene Plattformen
- ap
- tech stack 
- komponenten 
- 

- 

## Challenges we ran into

- time restriction
- building something that is easy to use is hard 
- remote work ( jitsi, slack super toll )

## Accomplishments that we're proud of

- website und flyer bereits fertig ( 80%)
- neues team. 
- gut funktionierende domainübergreifende arbeit ( zusammen arbeit zwischen Designern, Buisness Developer, Software entwickler, Marketingexperten )
- app angefangen 
- video 
- started development of backend (Architecuter defined, docker container deployed on Server  ) 
- 
- Docker-compose mit allen componenten ( minio, postgres, pgadmin, backend-logik kubernetes ready! )
- Backend A
- API definiert 
- 

## What we learned

- nicht trival da zeit und raum achse 
- 

## What's next for 1_001_a_lebensmittel-matching_31_Lieferemma

- entwicklung weiterführen backend und frontent 
- emma ist erlebbar aber noch nicht fertig 
- beta test phase ab 27.03 
- einbindung von bezahl diensten ( paypal, stripe)

# Englisch


## Inspiration

We saw a bakery claiming they are close to become bankrupt. The reason is that customers don't buy products in local stores anymore, like in this specific case a bakery. We want to help them by providing a new sales channel to meet demand in times of social distancing.

https://twitter.com/klee_lina/status/1240992740890025985

## What it does

We match customers with their local bakeries and farmers. Customers can order products from travelling market booths (by cargo bike, cars, vans). 

Rather than have people wait in queues or walk to shops have basically one person distribute the articles to them. The inspiration is basically the flying boat restaurant in the movie “The Fifth Element”. A more realistic example than a flying restaurant is a bakery car that either has a static preplanned route notifying registered customers that it will pass by soon, allowing  customers to reserve bread and buns via their cellphone or even allow them to reserve in advance (e.g. a night before). The second way would be dynamically planning the route based on customer orders.

## Differentation

We don’t want to reinvent the wheel so here some differentation criteria:
Unlike e.g. the pizza delivery service the idea is that the shop is mobile and should seldomly have to pick up new articles from a central place
Project must be open source
Project does not have commercial interest (at least not on the platform side) 
Project can be hosted by anyone (might require some reasonable amount of effort)






