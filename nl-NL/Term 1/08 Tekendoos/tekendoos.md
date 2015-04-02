Niveau 3

#Tekendoos

__Inleiding:__
In dit project maak je zelf een tekendoos waarmee je je eigen kunst kunt maken. Je kunt de kleur van de lijnen veranderen, het scherm weer schoonmaken, stempels maken en nog veel meer! 
￼
##STAP 1: Sleep en teken

We beginnen met een pen die tekent wanneer je hem over het scherm sleept. 

1. Start een nieuw Scratch-project. Verwijder de kat door er met de rechter muistoets op te klikken en verwijderen te klikken. 
2. Klik op  __Scherm__ en dan op de tab  __Achtergronden__. Importeer de achtergrond  __binnen/chalkboard__.
3. Maak een nieuwe sprite die je  __potlood__ noemt, en gebruik daarvoor het plaatje  __dingen\pencil.__
4. Ga naar de  __uiterlijken__ tab. In het Tekenen-paneel klik je helemaal rechts boven op het kruisje voor 'Middelpunt van tekening'. Sleep het middelpunt naar het puntje van de tekening van het potlood. __LET OP: Zet het kruis iets buiten de punt van het potlood__ (anders krijg je strak problemen met het klikken op andere sprites)
5. Zorg er voor dat het potlood je muisaanwijzer volgt met een __herhaal__ en een __richt naar__ muisaanwijzer blok.

```scratch
wanneer VLAG wordt aangeklikt
herhaal
	ga naar muisaanwijzer
(einde herhaal)
```

__Nu willen we deze potloodsprite als een echt potlood kunnen gebruiken.__   

Als je kijkt naar de blokken onder __pen__ dan zie je allerlei blokken die te maken hebben met tekenen. De blokken die we als eerste zullen gebruiken zijn __pen neer__ en __pen op__.

6. We willen de knop van de muis gebruiken om het potlood te besturen. Als de muisknop is ingedrukt, moet het potlood op het papier staan. Als de knop niet is ingedrukt is het potlood van het papier af. Dat kunnen we doen met een __als … dan anders___ blok en een __muis ingedrukt?__ blok. 

```scratch
wanneer VLAG wordt aangeklikt
herhaal
	ga naar muisaanwijzer
	als muis ingedrukt? dan
		pen neer
	anders
		pen op
	(einde als)
(einde herhaal)
```

##Test Je Project
__Klik op de groene vlag.__ Volgt het potlood de muis? Wat gebeurt er als je op de muisknop klikt en de muis beweegt? Negeer voorlopig de kleur waarmee het potlood tekent. 

7. Uiteindelijk komt je scherm behoorlijk vol te staan met getekende lijntjes. Je kunt het __wis alles__ blok gebruiken om het scherm weer schoon te maken.  

```scratch
wanneer VLAG wordt aangeklikt
wis alles
herhaal
	ga naar muisaanwijzer
	als muis ingedrukt? dan
		pen neer
	anders
		pen op
	(einde als)
(einde herhaal)
```

##Test Je Project
__Klik op de groene vlag.__

Verdwijnt je tekening als je op de groene vlag klikt? 

Sla je project op.

##STAP 2: Opruimen

Misschien is het mooier als je niet je hele project hoeft te stoppen en te starten om de tekening te wissen. Laten we een knop toevoegen waarmee je de tekening kunt wissen. Dat doen we ook met het __wis alles__ blok. 

1. Maak een nieuw sprite met het plaatje __voorwerpen/button 5__ als uiterlijk (dit is een kruis). 
2. Verander de naam van de sprite in __wis__ en maak hem iets kleiner.
3. Zet de sprite in de buurt van de linker onderhoek van het scherm.
4. Geef dit simpele script aan deze nieuwe sprite:


```scratch
wanneer op deze sprite wordt geklikt
wis alles
```

##Test Je Project
__Klik op de groene vlag.__

Zorgt de wis-knop er voor dat je hele tekening gewist wordt?

Sla je project op

##STAP 3: De kleur veranderen

We kunnen nu alleen blauwe lijntjes tekenen. Laten we daar eens wat meer kleuren aan toevoegen! We voegen wat sprites toe onderaan het scherm. Die sprites zullen er uitzien als gekleurde knoppen. Als we op zo'n knop klikken, verandert de kleur van de lijn die we tekenen. 

1. Voeg een nieuwe sprite toe, die je __rood__ noemt, met het plaatje __voorwerpen/button3__. 
2. Ga naar de Uiterlijken tab en vul de binnenkant van de sprite op met rood.
3. Zet hem ergens aan de onderkant van het scherm, bij de __wis__ knop, en maak hem iets kleiner.
4. Als je klikt op de rode sprite, moet hij het signaal __rood__ zenden.

```scratch
wanneer op deze sprite wordt geklikt
zend signaal rood
```

__Ja, dat is alles wat hij moet doen. Het moeilijke werk wordt gedaan door het potlood.__

4. Voeg een nieuw script toe aan het potlood. Als het potlood het signaal __rood__ ontvangt, moet hij de penkleur naar rood wijzigen (gebruik hiervoor het __maak penkleur__ blok).

__Hint:__ als je klikt op het gekleurde blokje in het __maak penkleur__ blok, kun je het druppelaartje gebruiken om precies de goede rode kleur te selecteren. 

```scratch
wanneer ik signaal rood ontvang
maak penkleur (rood)
```

##Test Je Project
__Klik op de groene vlag.__

Teken eerst een stukje lijn. Klik dan op de rode knop en teken nog een stukje. Krijgt het potlood een andere kleur? En tekent hij nu een rode lijn? Komt de lijn uit het puntje van het potlood?

Sla je project op

5. Herhaal wat je net gedaan hebt met nieuwe sprites om buttons te maken zie ervoor zorgen dat de pen in blauw, geel en groen kan schrijven (__tip: kopieer sprite rood__). 

##Test Je Project
__Klik op de groene vlag.__

￼Werken alle knoppen? Tekent het potlood in de goede kleur?  

Sla je project op

##STAP 4: Alleen binnen de rand tekenen

Het is je misschien al opgevallen dat je op het hele scherm kunt tekenen, ook op de randen. Maar dat willen we niet. We willen dat de tekening in het midden van het scherm blijft. We kunnen dat doen door er voor te zorgen dat het potlood niet buiten het tekenveld mag komen - het lichtgrijze gedeelte van het scherm.

Misschien weet je nog dat Scratch punten definieert met een x- en een y-as. Ons tekengebied ligt tussen 230 en -230 op de x-as en 170 en -120 op de y-as. We kunnen deze waarden gebruiken in een __als__ blok, waarbij we eerst zeker moeten weten dat de muis in dit gebied is voor we het potlood er naartoe bewegen. 

Om dit te regelen heb je een nieuw __als dan__ blok nodig om je bestaande __ga naar … als__ blok heen. In dit nieuwe __als dan__ blok moet je het volgende controleren: 
muis y is groter dan -120 en muis y is kleiner dan 170
en muis x is groter dan -230 en muis x is kleiner dan 230

__Let op__ om dit te doen moet je meerdere __en__ blokken gebruiken, een voor de twee muis x-voorwaarden, een voor de twee muis y voorwaarden, en een laatste om ze allemaal aan elkaar te maken

Omdat we toch niet buiten het tekengebied kunnen tekenen, kunnen we het potlood ook wel verbergen als we buiten dat gebied komen. Om dat te doen kun je beter een __als dan …  anders__ blok gebruiken. De voorwaarden blijven gelijk, en gebruik __verschijn__ om het potlood zichtbaar te maken als de voorwaarden waar zijn. Als ze niet waar zijn, wordt het potlood verborgen.

```scratch
wanneer VLAG wordt aangeklikt
pen op
wis het scherm
herhaal
	als muis y > -120 en muis y < 170 en muis x > -230 en muis x < 230
		ga naar muisaanwijzer
		verschijn
		als muis ingedrukt? dan
			pen neer
		anders
			pen op
		(einde als)
	anders
		verdwijn
	(einde als)
(einde herhaal)
```

##Test Je Project
__Klik op de groene vlag.__

Kun je nog tekenen in het tekengebied? Kun je buiten het tekengebied tekenen? Wat gebeurt er met het potlood als je buiten het tekengebied komt en daarna er weer overheen gaat? 
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
Sla je project op

##STAP 5: Gum

__Het tekenen van lijnen is leuk, maar soms maak je een foutje en wil je dat uitgummen.__ We kunnen dat doen door een nieuw potlood toe te voegen dat grijs tekent (dezelfde kleur als de achtergrond).

Voeg een nieuwe knop-sprite toe aan het scherm om de gum te selecteren. Gebruik weer de __resources/button3__ sprite, maak hem smaller zodat hij onderaan het scherm past, en geef hem de kleur grijs. Het moet hetzelfde werken als de andere knoppen om een kleur te kiezen, namelijk het zenden van het signaal "gum".

De pen-sprite moet reageren op het "gum"-signaal door de penkleur te veranderen naar grijs (je kan de __kleurkiezer__ gebruiken om de kleur van de achtergrond te selecteren).

##Test Je Project
__Klik op het groene vlaggetje.__

Gumt de gum de lijnen uit? Werkt hij tot de randen? Kun je wisselen tussen de gum en de potloden?

Sla je project op

##STAP 6: Stempels

De volgende stap is om een stempel toe te voegen om kleine mee te stempelen op de tekening.

1. Voeg een nieuwe sprite toe met een plaatje of uiterlijk naar keuze. Verklein de sprite en plaats hem aan de onderkant van het scherm naast de andere gereedschappen. Als de sprite wordt aangeklikt moet die het __signaal stempel zenden__.
2. Voeg een nieuw uiterlijk voor de potlood-sprite toe, hetzelfde als je voor de __stempel__ knop hebt gekozen.
3. Selecteer de potlood-sprite en maak een nieuwe variabele aan met de naam __tekenModus__ voor alleen deze sprite. We zullen deze variabele gebruiken om bij te houden of we aan het tekenen of aan het stempelen zijn.
4. Voeg een nieuw script toe om te reageren op het stempel signaal. Het moet het uiterlijk naar de stempel veranderen en __tekenModus__ naar __uit__.
5. Verander de andere scripts die reageren op het kiezen van een gereedschap (rood, groen, blauw en de gum) zodat ze allemaal __tekenModus__ naar __aan__ zetten.
6. Als laatste moeten we deze variabele controleren __als de muis ingedrukt wordt__ om te zien of we aan het tekenen of stempelen zijn. Als tekenModus = aan moeten we de huidige __pen neer_ gebruiken, anders moeten de stempel gebruiken.

##Test Je Project
__Klik op het groene vlaggetje.__
￼￼
Werkt de stempel goed?

Wat gebeurt er als je teruggaat naar het normale potlood?

Sla je project op

__Goed gedaan, je hebt de basis van dit project af.
Probeer deze uitdagingen!__
￼￼￼
##Uitdaging 1: Regenboog potlood

Laten we een speciaal potlood toevoegen dat tekent in de kleuren van de regenboog. Dat is iets dat je niet met normale pennen of potloden kan, dus dat is leuk om te laten zien dat je met tekenen op de computer andere dingen kan. Het geheim om het werkend te krijgen is het "verander penkleur met"-blok.

Voeg als eerste een sprite toe om het regenboog potlood te kiezen en het regenboog uiterlijk aan de pen-sprite:

1. Maak een nieuwe sprite om het gereedschap te kiezen en plaats die onderin het scherm, naast de andere sprites om een penkleur te kiezen. Gebruik het resources/rainbow-selector uiterlijk en laat die een "regenboog"-signaal uitzenden als die aangeklikt wordt.
2. Voeg het resources/rainbow-pencil uiterlijk toe aan de pen-sprite.

Je moet een script maken dat de kleur van de pen meerdere keren per seconden veranderen om het regenboog-effect te maken (de kleur iedere 0.05 tellen veranderen met 5 werkt goed, maar je kunt andere getallen proberen). De "Timer" Scratch Card laat je zien hoe je iets kan maken dat om de zoveel tellen verandert. Gebruik een "verander penkleur met 5"-blok in plaats van een "verander timer met -1"-blok binnen de herhaling.

Je moet er ook voor zorgen dat de herhaling de kleur alleen verandert als het regenboog potlood geselecteerd is, anders krijgen alle potloden dat effect! Je kunt dit doen op dezelfde manier als het potlood verandert tussen de potloden en de stempel. Je moet een variabele aanmaken met de naam regenboogModus die de waarde aan heeft wanneer je het regenboog-effect wil en anders uit. Iedere keer dat het potlood reageert op het kiezen van een gereedschap moet het de waarde van regenboogModus goed zetten.

Gebruik wat je hierboven geleerd hebt van het maken van de stempel voor het regenboog-effect. De scripts die reageren op de signalen van het kiezen van een gereedschappen moeten twee variabelen instellen: tekenModus en regenboogModus.

##Test Je Project
__Klik op het groene vlaggetje.__

Werkt het regenboog potlood goed?

Wat gebeurt er als je teruggaat naar een van de normale potloden?

SLA JE PROJECT OP

##Uitdaging 2: Sneltoetsen

In plaats van de sprites om een gereedschap te selecteren onderin het scherm te gebruiken, kun je het toetsenbord gebruiken om een ander gereedschap te selecteren.  
Je kunt het "wanneer [] wordt ingedrukt"-blok gebruiken om te reageren op het toetsenbord. Voor iedere toets die je wil gebruiken moet je zo'n blok toevoegen dat hetzelfde signaal uitzend als de bijbehorende sprite om dat gereedschap te kiezen. Voeg deze scripts toe aan het scherm.

Ik heb deze sneltoetsen gebruikt:
* Alles verwijderen - a
* Gum - e
* Rood potlood - r 
* Blauw potlood - b
* Geel potlood - y
* Groen potlood - g
* Regenboog potlood - w
* Stempel - s

##Test Je Project
__Klik op het groene vlaggetje.__

Worden alle gereedschappen geselecteerd met de juiste sneltoets? Werken alle gereedschappen als je ze met het toetsenbord selecteert? Worden de juiste gereedschappen nog geselecteerd als je op de sprites daarvoor in het scherm klikt?

SLA JE PROJECT OP

##Uitdaging 3: Groot en klein
Een andere mogelijkheid die de meeste tekenprogramma's hebben is de mogelijkheid om de grootte van het potlood te veranderen. Laten we dat toevoegen.  
De moeilijkheid is dat soms de grootte van het potlood gewijzigd moet worden en soms de grote van het uiterlijk. Dat is afhankelijk van of je tekent op stempelt.

Maak twee nieuwe sprites aan om gereedschap mee te selecteren, genaamd groter en kleiner. Ze moeten de resources/bigger-selector en resources/smaller-selector uiterlijk krijgen en de signalen groter en kleiner uitzenden.

De potlood sprite kan reageren op de signalen door of de pen grootte met 1 te veranderen of de grootte van het uiterlijk met 10, afhankelijk van de waarde van tekenModus (gebruik een "als-anders"-blok, net als hoe de sprite kiest tussen tekenen of stempelen).
Vergeet geen sneltoetsen te maken voor de gereedschappen om de pen groter of kleiner te maken. Ik heb pijltje-omhoog en pijltje-omlaag gebruikt.

SLA JE PROJECT OP

Wat je opgevallen zou moeten zijn is dat het veranderen van de grootte van de stempel ook de grootte van het potlood op het scherm verandert als je dat gereedschap kiest.  
Om dat te voorkomen moet je de grootte naar 100% veranderen iedere keer als je een potlood kiest zodat de gereedschappen de juiste grootte hebben.

Om het nog beter te maken kun je de stempel zijn grootte laten onthouden en deze weer aan laten nemen nadat je een potlood hebt gebruikt. De makkelijkste manier om dat te doen is een nieuwe variabele aan te maken die stempelGrootte heet die wordt geüpdate met de huidige grootte van de stempel iedere keer dat die gewijzigd wordt.  
Als de stempel geselecteerd wordt, kan die zijn grootte instellen op basis van die variabele.
￼￼￼￼￼￼￼￼
￼
##Test Je Project
__Klik op het groene vlaggetje.__

Werken de knoppen om de grootte van het potlood te veranderen?

Wat gebeurt er als je de stempel kiest, de grootte veranderen en dan weer een potlood kiest?

SLA JE PROJECT OP

__Goed gedaan, je bent klaar, je kan nu genieten van het spel!__

Vergeet niet dat je je spel kunt delen met je vrienden en familie door te klikken op __Publiceren__ in het menu!
