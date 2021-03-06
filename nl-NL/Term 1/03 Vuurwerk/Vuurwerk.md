Level 1

#Vuurwerk

__Introductie:__
In dit project maken we een vuurwerk spectakel boven de stad.

##￼STAP 1: Maak een raket die naar de muis toe vliegt

__Laten we de benodigde beelden voor de oefening importeren__

1. Begin een nieuw Scratch project. Rechtermuisklik op de kat en kies dan Verwijderen
2. Vervang de achtergrond door buiten/city-with-water
3. Gebruik de __een sprite uit een bestand kiezen__ knop om een sprite van een Raket toe te voegen
aan het project (gebruik Bronnen/Raket.png).
4. Laat de raket verdwijnen als er op de groene vlag wordt geklikt.

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
```

Nu willen we de raket naar de muis toe laten bewegen als er op de muis wordt geklikt.

5. Voeg een wanneer spatiebalk wordt ingedrukt besturen blok, en laat hieronder de raket verschijnen en richting de muis schuiven

```scratch
	wanneer spatiebalk wordt ingedrukt
	verschijn
	schuif in 1 tellen naar x: muis-x y: muis-y
```
		
###Test Je Project
__Klik op het groene vlaggetje, plaats je muis op het scherm en druk op de spatiebalk.__

Verschijnt de raket en beweegt ze naar je muis toe?
Wat gebeurt er als je beweegt en als je nogmaals de spatiebalk indrukt?


6. Vuurwerk vliegt normaal gezien niet zijdelings, dus laten we ervoor zorgen dat het steeds van de bodem van het scherm naar de muis toe vliegt. Voordat we de raket laten verschijnen, gebruiken we het `ga naar` blok om het vuurwerk naar de onderkant van het scherm te sturen, maar zo blijft het wel horizontaal op dezelfde plaats.

```scratch
	wanneer spatiebalk wordt ingedrukt
	ga naar x: muis-x y: -200
	verschijn
	schuif in 1 tellen naar x: muis-x y: muis-y
```

###Test Je Project
__Klik op het groene vlaggetje, plaats je muis op het scherm en druk op de spatiebalk.__
Vliegt de raket richting de muis vanaf de onderkant van het scherm? Wat gebeurt er als je de muis verplaatst en nogmaals op de spatiebalk drukt?

7. Vanaf nu kunnen we dit ook laten afspelen door op de muis te klikken in de plaats van de spatiebalk te gebruiken. Om dit te kunnen doen, plaatsen we ons script tussen een __herhaal als muis ingedrukt__.
Vervang dan het __wanneer spatiebalk wordt ingedrukt__ besturen blok door __wanneer VLAG wordt aangeklikt__ en tenslotte zorg je ervoor dat de raket niet zichtbaar is als het geheel opstart.

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal
	  als <muis ingedrukt?> dan
		  ga naar x: muis-x y: -200
		  verschijn
    	schuif in 1 tellen naar x: muis-x y: muis-y
  	(einde als)
	(einde herhaal)
```

###Test Je Project
__Klik op het groene vlaggetje en klik met je muis op het scherm. Klik nog eens, maar op een andere plek.__ 

###Om te proberen
1. Probeer de baan van de raket bij te sturen met de muis, zodat die in een klein boogje vliegt.
2. Probeer een paar raketten trager en sneller te laten vliegen.

Sla je project op.

##STAP 2: De raket laten exploderen

￼1. De eerste stap om een raket te laten exploderen is een soort knal geluid te laten afspelen voordat de raket begint te bewegen. En dan laat je de raket verbergen wanneer hij de muis bereikt. 

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal
    als <muis ingedrukt?> dan
		  ga naar x: muis-x y: -200
  		start geluid 'cymbal crash'
		  verschijn
    	schuif in 1 tellen naar x: muis-x y: muis-y
  		verdwijn
  	(einde als)
	(einde herhaal)
```
2. Vervolgens laat je de raket een signaal zenden op het moment dat hij explodeert. We zullen verder in deze oefening gaan luisteren of we dit signaal ontvangen.

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal
    als <muis ingedrukt?> dan
		  ga naar x: muis-x y: -200
  		start geluid 'cymbal crash'
		  verschijn
    	schuif in 1 tellen naar x: muis-x y: muis-y
  		verdwijn
  		zend signaal explodeer
  	(einde als)
	(einde herhaal)
```

###Test Je Project
__Klik op het groene vlaggetje.__ 
Ga na of de raket geluid maakt en of hij verdwijnt wanneer hij de muis bereikt.

3. Importeer een nieuwe sprite van Bronnen/vuurwerk1.png
4. Wanneer het explodeer signaal wordt ontvangen, zou deze moeten verdwijnen en zichzelf verplaatsen naar de positie van de raket door middel van een `ga naar` blok, om vervolgens te verschijnen, en tot slot onzichtbaar te worden een seconde later.

```scratch
	wanneer ik signaal explodeer ontvang
	verdwijn
	ga naar x: x-positie van Raket y: y-positie van Raket
	verschijn
	wacht 1 tellen
	verdwijn
```
###Test Je Project
__Lanceer een nieuwe raket.__ 
Wordt deze vervangen door een beeld van een explosie op de moment dat de explosie plaatsvindt?
Wat gebeurt er als je de muisknop indrukt terwijl je de muis beweegt? (Geen paniek, dit herstellen we later wel).

Sla je project op.

##￼STAP 3: Maak elke explosie uniek

1. Nu kunnen we elke explosie uniek maken door middel van een zet kleur-effect blok, waarbij je een willekeurige kleur laat kiezen tussen 1 en 200.

```scratch
	wanneer ik signaal explodeer ontvang
	verdwijn
	zet effect kleur op willekeurig getal tussen 1 en 200
	ga naar x: x-positie van Raket y: y-positie van Raket
	verschijn
	wacht 1 tellen
	verdwijn
```

###Test Je Project
__Klik op het groene vlaggetje.__ 

Heeft elke explosie een verschillende kleur?

2. Laat het uiterlijk van de explosie afwisselen door Bronnen/vuurwerk2.png en Bronnen/vuurwerk3.png te gebruiken. En laat dit afwisselen bij iedere raket.

###Test Je Project
__Klik op het groene vlaggetje.__ 

Heeft elke raket een explosie met een ander uiterlijk?

3. Als laatste, laten we iedere explosie toenemen in grootte gedurende een korte tijd. In plaats van 1 tel te wachten, zetten we de grootte van de sprite op 5% voordat we die laten verschijnen. En vanaf dat die verschijnt, laten we de grootte vijftig keer toenemen met 2 door middel van een herhaal blok.

```scratch
	wanneer ik signaal explodeer ontvang
	verdwijn
	zet kleur-effect op willekeurig getal tussen 1 en 200
	ga naar x: x-positie van Raket y: y-positie van Raket
	maak grootte 5%
	verschijn
	herhaal 50
		verander groote met 2
		(eindig herhaal)
	verdwijn
```

###Test Je Project
__Klik op het groene vlaggetje.__

Neemt het beeld van de explosie geleidelijk toe vanuit het midden van de raket?

###Om te proberen
Waarom niet elke explosie nog unieker maken door de grootte en de snelheid van de explosie te laten afwisselen?

Sla je project op.

##STAP 4: De bug van het signaal zenden herstellen
Weet je nog dat we eerder een bug hadden als we de muis ingedrukt hielden?
Dit gebeurt omdat wanneer de raket haar explosie signaal zendt, ze onmiddelijk de als lus zal herhalen en een nieuw exploseer signaal zal uitzenden, nog voor dat de vorige explosie klaar was.


1. Om dit te herstellen, kunnen we het zend signaal blok vervangen door een zend signaal en wacht blok. Op deze manier zal de lus niet herhalen tot dat de explosie klaar is met afspelen.

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal als muis ingedrukt?
		ga naar x: x-positie y: -200
		start geluid bang
		verschijn
		schuif in 1 tellen naar x: x-positie y: y-positie
		verdwijn
		zend signaal explodeer en wacht
	(eindig herhaal)
```
###Test Je Project
__Klik op het groene vlaggetje, houd de muis ingedrukt en beweeg de muis rond over het scherm.__ 

Verschijnt het beeld van de explosie op de juiste plek en op het juiste moment?

Sla je project op.