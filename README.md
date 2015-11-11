# Information Security 5
Deze README zal proberen te voorspellen wat Dhr.Dams zal vragen op het examen (M1). Ik heb deze vragen opgesteld d.m.v. de samenvatting van Hannelore, waarvoor dank!    

**Dit zal niet zoals mijn vorige REPO (Embedded 5), een antwoord geven op alle vragen! Ik kan daarom niet garanderen dat dit genoeg informatie / leerstof is om erdoor te zijn!**


#Hoofdstuk 1


###1.1 Wat is het voordeel van een private cloud
Een private cloud is een cloud die je zelf moet beheren! Je data is dan wel beschikbaar via het internet (cloud) maar je hebt zelf controle op de beveiling van je data!

###1.2 Waarom worden vuldnerabilities verkocht? En wat is hier zo erg aan?
Het is slimmer dat een hacker zijn "kunsten" verkoopt dan ze zelf toe te passen, zo is hij zelf minder vatbaar en loopt hij dus minder risico! Prijzen voor exploits kunnen hoog oploppen en zijn afhankelijk van hoeveel gebruikers er getrefd kunnen worden.
Bijvoorbeeld, een exploit voor Vista zal nu niet meer waardevol zijn (bijna niemand gebruikt Vista nog).

Dat hacks verkocht worden zorgt ervoor dat veel meer mensen (niet technische), ook kunnen "hacken". En hacken dus op grote schaal gebeurd!!!

###1.3 Waarom is het moeilijker geworden om je te verdedigen tegen aanvalen?
* Aanvallen worden makkelijker te gebruiken of worde verkocht (zie vorige vraag)
* Aanvallen worden steeds beter
* Aanvallen worden sneller (botnets, betere hardware, ...)
* Patches zijn trager dan kwetsbaarheden (patch vereist veel testen, ...)
* Gebruikers zijn dom (makkelijk wachtwoord, geen patches, ...)

###1.4 Wat is Windows of vulnerability?
De tijd tussen het ontdekken van een exploit en de patch die zorgt dat de exploit onschadelijk gemaakt! Bijvoorbeeld *Patch Tuesday*, maandelijkse release van (beveiliginspatches) bij Windows Update. Veel "hackers" releasen hun exploits op de woensdag erna (Exploit Wednesday). Zo hopen hierdoor een lange Window of vulnereability. Omdat de volgende "Patch Tuesday" pas volgende maand is!

###1.5 Wat is Information Security?
De taak om digitale informatie te beveiligen, er dus voor zorgen dat er berschermende maatregelen zijn geïmplementeerd.
Deze gaan vaak via het CIA model (zie volgende vraag)! Bijvoorbeeld zorgen voor encryptie op je data, ...

###1.6 Wat houdt het CIA model in?
####C = Confidentiality (Confidentieel)
Data mag enkel bekeken worden voor wie er toestemming voor heeft! Dit zorgt er dus voor dat er privacy gewaarborgt is!

Confidentiele data kan afgedwongen worden door het gebruik van encryptie!

####I = Integrity (Integriteit)
Data mag niet aanpast worden als het verzonden wordt van punt A naar punt C via punt B!

We kunnen dit doen door een simeple CRC of een complexe hash (zie later)

####A = Availability (Beschikbaarheid)
Digitale data heeft tegenwoordig een grote impact op ons leven! Bijvoorbeeld indien je geld wilt afhalen met je bankkaart. Er  wordt verwacht dat deze systemen altijd werken!!!

Je data moet ook nog bechikbaar kunnen zijn tijdens een zware load! Je moet dus bijvoorbeeld zorgen dat DDoS aanvallen geen invloed hebben! => Load balancers, firewalls,... 

###1.7 Wat is het Information Security Model?
Je kunt niet alles weten aka ik ben te tam omdat te leren!

###1.8 Welke twee types van aanvallen hebben we?
* Passieve aanvallen
  * Ondedecteerbaar 
  * Minder resultaat
  * Minder gevaarlijk / minder "illegaal"

* Actieve aanvallen
  * Detecteerbaar
  * Kan veel resultaat opleveren
  * Gevaarlijk => zo goed als altijd illegaal!

### 1.9 Geef voorbeelden van een passieve aanval.
**Meeluisteren => sniffing** </br>
D.m.v. bijvoorbeeld WireShark kijken wat er verzonden wordt, en naar wie.

**Verkeers analyse**
Een raport maken van wat de persoon bezoekt, hoe frequent, ... En hier dan patronen inzoeken. 

### 1.10 Geef voorbeelden van een actieve aanval.
#####Masquerade
U eigen voordoen als iemand anders! Je zend bijvoorbeeld data naar persoon X en je doet alsof je persoon Y bent. Indien er geen controle gebeurd zal persoon X nooit vragen stellen bij de data! Persoon X zal de data als correct beschouwen!

#####Replay
Geavanceerdere variant van "Masquerade". Je vangt/snift een pakketje dat van persoon X naar persoon Y gaat. Je onthoud wat hierin stond. En stuurt later wat daar in stond terug naar persoon Y. 

Waarom? Stel persoon X heeft juist de hash doorgestuurd van zijn wachtwoord naar persoon Y. Eve (Persoon B) wilt nu inloggen als persoon X (Alice), zij maakt verbinding met Bob (Persoon Y). Bob vraagt om een wachtwoord. Eve stuurt gewoon de "gevangen" hash door, Bob accepteert deze. Eve is ingelogd als Alice! </br>
Oplossen door gebruik te maken van sessies (zie OWASP)

#####MiTM (Man - In - The - Middle)
Je vangt de communicatie van persoon Y (Bob). Je manipuleert deze en zend deze dan door naar persoon X (Alice). Wat is nu het verschil? Bij een MiTM zorg je ervoor dat de oorspronkelijke informatie nooit de ontvanger bereikt maar dat alle communicatie via persoon B gaat (Eve).

Bijvoorbeeld: Je speelt default gateway in het netwerk! Alle informatie komt naar jouw, je kunt deze data inlezen, aanpassen voor je het naar de echte bestemming stuurt!

#####DoS (Denial of Service)
Persoon B (Eve) zorgt ervoor dat persoon X (Alice) niet meer bereikbaar is voor persoon Y (Bob). 

### 1.11 Wie voert er allemaal aanvallen (hacks) uit?
#####Hackers
Mensen die inbreken op systemen! </br>

*White hat hackers:* </br>
Geloven erin dat ze niet illegaal zijn omdat ze niets stuk maken! Ze zullen hun expetises melden aan de instantie die ze gehackt hebben. Zij vragen ook meestal om toestemming.

*Gray hat hackers:* </br>
Zelfde als white hat hackers buiten het feit dat ze het na x aantal tijd de hack ook publiceren. Dit doen ze om meer druk uit te oefenen op het bedrijf. Ze durven geld te vragen om de hack niet te publiceren of te tijd te verlengen. Zij vragen ook geen toestemming aan de instantie.

*Black hat hackers:* </br>
Zij hacken een instantie zonder iets te laten weten aan de instantie. Zij verkopen hun vondston door zonder dat het bedrijf het dus weet. Het bedrijf kan hier grote schade van ondervinden. Deze hackers zijn 100% illegaal bezig!

*Blue hat hackers:* </br>
Dit zijn mensen die ingehuurd worden door bedrijven om security te testen (pen - testing). A.d.h.v een contract worden zij toegelaten om hun systemen te hacken (of allesinds te proberen).

#####Script kddies
Ongetalenteerde gebruikers van hacking software. Ze hebben geen technische kennis, en gebruiken tools die op het internet beschikbaar zijn om systemen aan te vallen (kan ook gekocht worden, zie vraag 1.2)

#####Spionnen / Privé detectivies
Privé detectivies worden ingehuurd om mensen te hacken en informatie te stelen! </br>
Spionen, de overheidsdiensten hebben online ook spionen die "geregulariseerd" hacken (NSA, AIVD, ...)

#####Werknemers
Kunnen vaak een grote bedreiging zijn! 
* Ze zijn het niet eens, en kunnen zo gegevens lekken (ontslagen, ...)
* Bedrijfsspionage
* Blackmailing => Werknemers worden afgeperst voor informatie van bedrijf
* Social Engineering

#####Cybercriminelen
Netwerk van hackers die (veel) geld ermee proberen te verdienen! Hun acties bestaan uit veel illegale zaken maar vooral uit bankzaken te kraken!

#####Cyberterroristen
Zelfde als cybercriminelen maar niet gericht op geld maar op principes of geloof.

### 1.12 Welke 5 stappen doen we in een netwerk aanval?
* Zoeken naar informatie (sniffen)
* Verdediging doorbreken
* Aanpassen van beveiligings instellingen
* Andere systemen in het netwerk aanpassen (eerst minst beveiligde systeem hacken en dan van daar verder gaan)
* Andere systemen / netwerken plat leggen (firewall neerhalen bijvoorbeeld)

### 1.13 Hoe verdedigen we ons tegen een netwerk aanval?
####Lagen (Layers)
Één defensie syteem kan relatief gemakkelijk zijn om te omzeilen. Werk daarom met lagen maakt de kans kleiner dat een aanvaler door alle lagen heen door geraakt!

####Limiteren (Limiting)
Geef enkele diegene die het nodig hebben toegang tot bepaalde data!

####Verschillend (Diversity)
Zorg ervoor dat de lagen verschillend beveiligd zijn! Het zou stom zijn mocht de aanvaller meerdere lagen kunnen omzeilen met dezelfde techniek!

####Onduidelijkheid (Obscurity)
Een bekend voorbeeld hiervan is dat je niet onthuld welke computers in je bedrijf staan, welk OS ze hebben, netwerktopologie. Indien de hacker dit op voorhand al weet, of makkelijk kan achterhalen. Kan hij gerichter aanvallen!

####Simpel (Simplicity)
Hoe je systemen simpel van binnen, maar complex aan de buiten zijde! Dit zorgt ervoor dat de gebruikers het makkelijker hebben maar dat je ook makkelijker kunt troubleshooten, ...

### 1.14 Wat is malware?
Malware is een verzamelnaam voor softwaren die als doel heeft om de computer te infecteren. En hierna zijn voordeel uit kan halen! Malware is een software gebaseerde aanval!

### 1.15 Geef enkele voorbeelden van malware, en geef een woordje uitleg
#####Virus
Wordt gebundeld bij een uitvoerbaar bestand (.doc, .exe, ...). Vanaf dit bestand uitgevoerd wordt zal de computer geïnfecteerd geraken! Vanaf nu zal het virus zich ook proberen te verspreiden. Uiteraard zal het virus ook "schade" aanrichten aan de computer waar het op uitgevoerd wordt (bv: bestanden verwijderen, meer virussen downloaden, lid worden van een botnet, ...)

#####Worm
Een worm is een verbeterende variant van een virus. Het heeft hetzelfde effect maar vereist niet dat de gebruiker het eerst uitvoerd. Het kan dus vanaf het aanwezig is op je computer, schade aanrichten, en zich zelf verspreiden!

#####Trojan Horse
Verschilt t.o.v. de vorigz dat het niet bijgevoegd wordt bij een bestand. Het is eerder een bestand zelf (vooral een installer). Het zal zich adverteren als een goed, normaal werkend programma! Maar in de achtergrond doet het iets anders. Zoals bijvoorbeeld virussen, worms downloaden of backdoors openen!

####Rootkits
De naam komt van root in de Linux wereld. Rootkits draaien "dieper" in het system dan normale malware software. Ze zijn instaat om andere programma's te manipuleren. Ook bestaan er rootkits die op kernel niveau (drivers) werken. Deze hebben evenveel rechten als het OS zelf en zijn moeilijk te verwijderen, meestal eindigd dit op format C:\. Om dit laatste te vermijden op Windows kunnen normale gebruikers tegenwoordig enkel ondertekende drivers installeren. 



####Logic bomb
Wachten op een bepaalde trigger zoals de datum, voordat ze schade gaan toerichten op een systeem.

####Spyware
Software die de privacy van de gebruiker schendt. Volgt wat je doet (online / offline), keylogger (onthoud wat je typt), adware (overal reclame, popups). </br>
Deze software kan de computer onbruikbaar makn (traag, pop-ups, toolbars, ...).
Makers verkopen deze informatie voor geld of gebruiken gegevens voor te profiteren (bank account).


###1.16 Welke software maakt gebruik van malware?
####Spam
Ongewente email die malware kan bevatten!

####Backdoors
Zoals de naam zegt, zorgt ervoor dat er makkelijk in je computer (opnieuw) kan ingebroken worden. Wordt vaak geplaats door malware.

####Botnet
"Zombie" computers die onder de controle zijn de aanvaller (bot herder). Computers worden lid van een botnet door infectie via malware. Deze malware plaats een backdoor en zo kunnen de aanvallers de computer overnemen en lid maken van zijn botnet.

Een botnet kan gebruikt worden voor spam mails, Ddos, verspreiden van malware, online pols manipuleren, ...

### 1.17 Met welke hardware kun je systemen aanvallen / hacken
#####BIOS Aanvallen
Combinatie software / hardware. Malware die het geheugen van het BIOS aanpast! De kans dat je computer omzeep is, is zeer groot. Het BIOS was vroeger het stuk software die zorgde dat een OS kon geladen worden. Tegenwoordig gebruiken we UEFI! Dit is veel moeilijker te hacken (nog geen gevallen geweest), en zorgt d.m.v. safeboot dat er geen andere software opgestart kan worden buiten een vertrouwd OS.

#####USB Sticks
Kunnen voor alles gebruikt worden. Ze kunnen dienen om malware te verspreiden (virussen, maar vooral keyloggers). Ze zijn tegenwoordig zeer klein, en kunnen onopvallend in een PC geplaatst worden! Ook worden ze vaak doorgeven waardoor het een makkelijke manier is om malware te verspreiden!

#####Hardware keylogger
Klein apparaat dat tussen computer en toetsenbord geplaatst kan worden. Onthoudt elke karakter die is ingetypt!

### 1.18 Leg SQL Injection uit! (BELANGRIJK)
TODO


# Hoofdstuk 2: Cryptologie
### 2.1 Wat is het doel van cytrografie?
Geheime communicatie tussen twee personen zonder de derde er iets van begrijpt!

### 2.2 Geef het blok schema van de verschillende soorten crypto algoritmes.
![Blokschema crypto](http://i.imgur.com/jehu3a8.png)

### 2.3 Wat is een "Substitution Cipher"? + geef een voorbeeld.
Is een encryptiemethode om tekst te encrypteren! Bij deze encyrptie wordt betekend een leter gewoon een andere leter in het alfabet. Bijvoorbeeld => A komt overeen met Z!

Het makkelijkste voorbeeld hiervan is gewoon het alfabet te roteren. A wordt N, B wordt O, C wordt P, ... Ceaser heeft dit gebruikt in het oude Romeinse rijk. Vandaar dat dit vaak **Ceaser Cipher** genoemd wordt. Een andere naam is **Rotation Cipher**

### 2.4 Hoe kun je een "Substitution Cipher" kraken?
Door patronen te zoeken in de ciphertext kun je mogelijk deze encrytiecode makkelijk kraken! Deze patronen zoeken, noemen we **crypto analyse**. Je zou de key kunnen zoeken maar dit doen we niet, we gaan gewoon proberen om het volledige alfabet op te stellen (rosseta stone). 

Je kunt dit doen door te zoeken naar de meest voorkomende letters, lettercombinaties. In het Engels komen bijvoorbeeld de letters a en I het vaakst voor. De meest voorkomende 2 letter woord is of, to, ... en zo verder. D.m.v. wat puzzelwerk kun je dus gokken met welke letter bijvoorbeeld de A wordt voorgesteld. Als je dit doet voor het volledig alfabet, kun je dus de tekst decrypteren. Dit wordt moeilijker als we er transposition cipher bijgebruiken!

Natuurlij is social engineering ook altijd een mogelijkheid (mensen blijven dom), maar dit is voor volgend examen!

#### OEFENING OEFENEN VAN SLIDES!
=> Ik ga ervan uit dat we niet van buiten moeten kennen welke letter het vaakst voorkomt in het Engels woordenboek...

### 2.5 Wat is een "Transposition Cipher"? + geef een voorbeeld
Dit is ook een encryptiemethode voor tekst. Je verplaatst de letters gewoon van plaats.

Voorbeeld **Rail - fence cipher**
![Transpotion cipher example](http://i.imgur.com/GVJXKpR.png)

Vroeger werd er vaak een combinatie van een subtitution cipher en transposition ciher gebruikt, dit zorgde voor moeilijkere cryptoanalyse.

### 2.6 Wat is een Brute Force Search?
Is een manier van cryptoanalysis. Deze manier is iets minder subtiel, het probeerd iets te kraken door gewoon alle combinaties af te gaan.

Wat er probeerd gekraakt te worden hangt af van de situatie. Soms wordt er geprobeerd een key te kraken. Maar meestal een wachtwoord (tegenwoordig woorden wachtwoorden gehasht, geen key). Computers kunnen vaak tegen enorme snelheden "wachtwoorden" invullen. Maar door "nieuwe" technieken (hash, salt, betere standaarden, ...) wordt het ook altijd moeilijker.

### 2.7 Wat zegt Kerckhoff princiepe? + verklaar!
Kerchoff zegt dat de sterkte van een encryptie niet mag afhangen van het feit dat bekend is met welke encytptie methode de data geïncrypteerd is! En dat de sleutel dus veel belangrijker is!

Waarom is dit? Dit is omdat een goede encryptie een totale andere uitgang geeft voor een kleine verandering van ingang. Je moet er dus eigenlijk voor zorgen dat er geen verband te leggen is tussen de ingang en de uitgang zonder dat je de sleutel weet! Indien het geval is maakt het niet uit of je weet met welke encryptiemethode de data geïncrypteerd is!

### 2.8 Wat is symetrische encryptie, welke twee types bestaan er?
Encryptie waarbij de sleuten om data te encrypteren dezelfde is als te dencrypteren.

Je hebt **stream ciphers** en **block ciphers**

### 2.9 Wat is het nadeel aan symetrische encryptie?
De sleutel voor encryptie en decryptie is dezelfde. Dat betekend dat je als je met meerdere personen informatie geencrypteerd wilt uitwisselen je voor elke persoon en andere key zult moeten gebruiken!

Indien je dit niet doet zullen alle personen waar mee je informatie deelt, jouw communicatie kunnen deencrypteren. Terwijl dit misschien niet de bedoeling is. (Ik wil praten met Bob en ik wil praten met Alice maar ik wil niet als ik praat met Bob dat Alice dit ook kan lezen).

Hierdoor heb je dus snel een moeilijkheid bij, namelijk je keys gaan onderhouden. Ook heb je bij symetische encryptie dat beide partijen verantwoordelijk zijn voor de key! Dit in geen enkel geval publiek mag worden!
