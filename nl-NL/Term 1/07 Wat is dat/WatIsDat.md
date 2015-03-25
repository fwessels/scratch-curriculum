Level 3

#Wat is dat

__Introductie__ 
Een willekeurig object wordt helemaal vervormd op het bord gezet. Je moet raden wat het is door onderaan op de juiste afbeelding te klikken. Hoe sneller je het raad, hoe hoger je score!

##STAP 1: Laat verschillende dingen verschijnen op het bord

We willen een aantal afbeeldingen laten verschijnen op het bord.

1. Start een nieuw Scratch project en verwijder de kat sprite.
2. Klik op de stage en dan op de Achtergronden tab. Importeer de binnen/chalkboard achtergrond.
3. Importeer een nieuwe sprite en geef het een uiterlijk dat je leuk vindt. Je kan bijvoorbeeld iets kiezen uit de Voorwerpen map.
4. Plaats de nieuwe sprite in het midden van het bord. Maak het groter of kleiner als dat nodig is.
5. Klik op de Uiterlijken tab en importeer 4 andere dingen. Je mag kiezen wat je maar wilt, hoera! Laten we nu een willekeurig uiterlijk laten verschijnen.
6. Maak dit script:

```scratch
	wanneer VLAG wordt aangeklikt
	herhaal willekeurig getal tussen 1 en 5		
		volgende uiterlijk
	(einde herhaal)
```

### Test Je Project
__Klik op het groene vlaggetje__

Heeft de sprite nu een ander uiterlijk?

__Klik nog een aantal keer__
 Krijg je telkens andere uiterlijken? Soms zal je hetzelfde uiterlijk twee keer krijgen, maar dat is niet erg. Je zult zien dat de sprite even flikkert als het van uiterlijk verandert. Dat zullen we oplossen in de volgende stap.
￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼￼
Sla je project op

##STAP 2: Vervorm de afbeeldingen

__Laten we nu de afbeelding vervormen wanneer die verschijnt en duidelijker worden na een aantal seconden.__
We gebruiken een score variabele om te controleren hoeveel vervorming er optreed. Als de score hoog is, is er veel vervorming. Als de score kleiner wordt, zal er minder en minder vervorming zijn. De score zal ook gebruikt worden als timer, zoals in de  __Timer Scratch Card.__

1. Maak een nieuwe variabele genaamd score aan in het variabelen palet. 
2. Verander het script als volgt:

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal willekeurig getal tussen 1 en 5		
		volgende uiterlijk
	(einde herhaal)
	maak score 110
	herhaal tot score = 0
		verander score met -10
		zet effect pixeleren op score
		zet effect kleur op score
		verschijn
		wacht 1 tellen
	(einde herhaal)
```

Voeg het verdwijn blok bovenaan toe, en zet dan alles onder het maak score 110 blok.

### Test Je Project
__Klik op het groene vlaggetje__

Verschijnt er een willekeurig vervormde afbeelding?  

Wordt de vervorming minder in stappen?  

Wordt de score minder als de afbeelding minder vervormd wordt?  

Krijg je een onvervormde afbeelding als de score 0 is?  

Krijg je nog steeds een andere afbeelding als je op de groene knop duwt?  

Sla je project op  

##Om te proberen

__Probeer de start score en hoeveel die verandert eens aan te passen in de loop.__ 
Hoe verandert dit het uitzicht van de afbeelding? Wordt het moeilijker of makkelijker om te raden welke afbeelding het is?
__Probeer eens een aantal andere grafische effecten uit het lijstje.__ 
Hoe verandert dat de moeilijkheid?

##STAP 3: Laat de speler toe om de afbeelding te raden

Tot nu toe hebben we een willekeurige afbeelding die traag zichtbaar wordt en een score die vermindert met de tijd, maar hoe win je het spel? We zullen een aantal sprites toevoegen onderaan het scherm om op te klikken. Als ze op de juiste klikken, winnen ze het spel. Als ze op de foute klikken, verdwijnt de sprite en gaat het spel verder.

Eerst moeten we weten wat het juiste antwoord is.

1. Maak een nieuwe variabele genaamd __antwoord__. Zorg ervoor dat die voor alle sprites is.
2. Verander het script dat je geschreven hebt om het juiste antwoord op te slaan. Voeg het maak antwoord uiterlijk # blok toe na de eerste herhaal loop.

```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal willekeurig getal tussen 1 en 5		
		volgende uiterlijk
	(einde herhaal)
	maak antwoord uiterlijk #
	maak score 110
	herhaal tot score = 0
		verander score met -10
		zet pixeleren effect op score
		zet kleur effect op score
		verschijn
		wacht 1 tellen
	(einde herhaal)
```

__Nu moeten we nog de sprites toevoegen waar de speler op kan klikken.__

3. Dupliceer de sprite op de stage en sleep de kopie naar de linker onderhoek van de stage.
4. Hernoem deze sprite tot __antwoord1.__ (Dat maakt het makkelijker om over te praten.)
5. Verwijder het script op __antwoord1__ en verwijder al zijn uiterlijken behalve het eerste.
6. Herhaal deze drie stappen, maar plaats de __antwoord2__ sprite naast __antwoord1__ en verwijder al zijn uiterlijken, behalve het tweede.
7. Herhaal dit nog drie keer voor __antwoord3__, __antwoord4__ en __antwoord5__

Je zult nu een rij met vijf antwoord sprites hebben onderaan de stage. Elke sprite toont een ander uiterlijk dat de hoofd sprite kan zijn. 

__Let op: Geen enkel van de antwoord sprites mag een script bevatten.__

Nu willen we dat elke sprite iets doet als er op geklikt wordt afhankelijk van of het het juiste antwoord is of niet.

8. Voeg dit script toe aan de __antwoord1__ sprite
```scratch
	wanneer deze sprite wordt aangeklikt
	als antwoord=1 dan
		zend signaal gewonnen
	anders
		verdwijn
	(einde als)
```

9. Sleep dit script naar de andere antwoord sprites. __Verander in elke sprite de antwoord=1 naar 2, 3 enzovoort.__
10. We moeten nu nog iets toevoegen dat reageert op de gewonnen boodschap. Ga terug naar sprite1, die op het bord. Voeg dit extra script toe:
```scratch
	wanneer ik signaal gewonnen ontvang
	zeg voeg "Proficiat! Je hebt gescoord :" en <score> samen
```

### Test Je Project
__Klik op het groene vlaggetje__

Als je het spelletje test, kan je de __antwoord monitor__ op de stage gebruiken om te kijken wat het juiste antwoord is. Gemakkelijk om te testen.

Wat gebeurt er als je klikt op het __juiste antwoord__?

Wat gebeurt er als je klikt op het __foute antwoord__?

Wat gebeurt er met het foute antwoord als je __een nieuw spel start__?

De test toont twee problemen aan. Ten eerste: foute gokken verschijnen niet opnieuw als je het spel opnieuw start. Ten tweede: de score stopt niet met verminderen wanneer we juist geantwoord hebben.

11. Om het eerste probleem op te lossen, voeg je dit script toe aan alle 5 de antwoord sprites:
```scratch
	wanneer VLAG wordt aangeklikt
	verschijn
```

Om het tweede probleem op te lossen moeten we het herhaal tot blok van de __vraag sprite__ stoppen als de speler op het juiste antwoord klikt. Daar gebruiken we een nieuwe variabele voor. We zetten die op _nul_ als het spel start en op _één_ als het spel gewonnen is. We laten het herhaal tot blok stoppen als de score __nul__ wordt OF als de __spel-gewonnen vlag__ op __één__ staat.

12. Maak een nieuwe variabele gewonnen
13. Verander de scripts tot ze er zo uitzien:
```scratch
	wanneer VLAG wordt aangeklikt
	verdwijn
	herhaal willekeurig getal tussen 1 en 5		
		volgende uiterlijk
	(einde herhaal)
	maak antwoord uiterlijk #
	maak score 110
	maak gewonnen 0
	herhaal tot score = 0 of gewonnen = 1
		verander score met -10
		zet pixeleren effect op score
		zet kleur effect op score
		verschijn
		wacht 1 tellen
	(einde herhaal)

	wanneer ik signaal gewonnen ontvang
	maak gewonnen 1
	zet alle effecten uit
	zeg voeg Proficiat! Je hebt score gescoord samen
```

Sla je project op

__Goed zo, je bent klaar met de basis van het spelletje.__ 

Er zijn echter nog een aantal dingen die je kunt veranderen aan je spel. Probeer deze uitdagingen eens!


##Uitdaging 1: Maak het spel moeilijker of gemakkelijker

Verander de moeilijkheidsgraad van het spelletje.

* Probeer de snelheid waarmee de afbeelding verschijnt en de snelheid waarmee de score vermindert te veranderen.
* Probeer de vervorming op de afbeeldingen aan te passen.
* Probeer de afbeeldingen die geraden moeten worden aan te passen, om ze meer op elkaar te laten lijken, of ze meer van elkaar te laten verschillen. Als je dit doet, vergeet dan niet om het uiterlijk van de antwoord sprite aan te passen. 

Sla je project op
￼￼￼
##Uitdaging 2: Vervorm de afbeelding anders in elk spelletje

Tot nu toe gebruiken we altijd dezelfde vervorming op elke afbeelding. In Stap 2 heb je misschien een aantal andere vervormingen gebruikt die minstens even goed werken als de kleur + pixelatie combinatie die we gebruikt hebben.

Zoek een aantal vervormingen die goed werken. 
Verander het spel zo, dat elk spel een andere vervorming gebruikt in het herhaal tot blok.

__Hint:__ Maak een nieuwe variabele __vervorming__. Zet deze op een willekeurige waarde aan het begin van het spel. Gebruik als blokken in het herhaal tot blok om de juiste vervorming toe te passen in dat spel.
￼
Sla je project op

##Uitdaging 3: Laat het spel meerdere rondes bevatten

Tot nu toe, staat elk spel op zich. Verander dit, zodat het spel meerdere rondes bevat. Verander het bijvoorbeeld naar een spel met drie rondes, zodat de speler 3 afbeeldingen juist kan raden en tot 300 punten kan scoren.

__Hint:__ Je hebt een extra variabele nodig om de volledige totaalscore bij te houden over de verschillende rondes heen. Je zult ook een loop nodig hebben om door de verschillende rondes te gaan.

__Hint:__ Je zult ook foute gokken opnieuw moeten laten verschijnen per ronde. Misschien kan je daarvoor een zend signaal gebruiken?
￼￼￼￼￼
Sla je project op
￼￼￼
##Uitdaging 4: Maak latere rondes moeilijker

Maak het spel moeilijker als je door de verschillende rondes gaat.

Moet elke ronde dezelfde score te behalen zijn? Of moet je meer punten krijgen als je snel kan raden in de latere, moeilijkere rondes?

__Hint:__ Hoe weet je in welke ronde je zit? Hoe kan je dat gebruiken om de score aan te passen en de moeilijkheid te beïnvloeden?

Sla je project op
￼￼
##Uitdaging 5: Blijf spelen tot de speler het fout heeft

Blijf spelen tot de speler het fout heeft, in plaats van een vast aantal rondes te hebben. Dit werkt waarschijnlijk alleen als het spel moeilijker wordt naarmate je meer rondes speelt (anders houdt het spel nooit op!).

Sla je project op

##Uitdaging 6: Maak het spel moeilijker of gemakkelijker alnaar gelang hoe goed de speler het doet

Verander de moeilijkheidsgraad van het spel afhankelijk van hoe goed de speler kan raden, in plaats van het spel altijd moeilijker te maken. Als je een afbeelding snel kunt raden, maak het spel dan een beetje moeilijker. Als je het niet of te laat kunt raden, maak het spel dan een beetje makkelijker.

Dit idee werkt alleen echt als je de score van de speler niet optelt door de rondes heen.

Sla je project op

##Uitdaging 7: Houd de hoogste score bij

Houd de hoogste score bij. Als iemand die score kan breken, vraag dan de naam van de speler en pas de hoogste score aan. Zorg er voor dat de naam van de speler en diens score getoond worden.

Sla je project op

##Uitdaging 8: Straf foute gokken af

Tot nu toe kan je gewoon heel snel op alle antwoord sprites klikken zo snel als je kan, zonder dat daar een straf aan verbonden is. Verander het spel zodat de score telkens een beetje verminderd als je een foute gok doet.

Maakt dit het spel beter?
￼￼￼￼￼
Sla je project op

__Goed zo, je bent helemaal klaar! Geniet van je spel!__

Vergeet niet dat je je spelletje kan delen met al je vrienden en je familie door op __Publiceren__ in de menu balk te klikken!
