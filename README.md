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

###1.3 Waarom zijn persoongegevens (indentiteit) zo belangrijk (niet zo belangrijk)?
Reclame bureau vinden deze zeer belangrijk bijvoorbeeld, om gericht reclame te kunnen zenden naar jouw. Ook de concurentie wilt zaken over jouw weten om misschien te misbruiken! Overheid is er ook in geïntresseerd in welke porno je kijkt (NSA, ... => spionnen)

Maar criminelen vinden ze ook interssant. 2 categorieën:
*  **True name theft:** nuttig om rekeningen te openen, officiele documenten te ondertekenen allemaal in naam van jou (je leven wordt overgenomen)
*  **Account takeover:** illegale toegang op accounts verkrijgen (hacken). Zo kan de crimineel hier voordeel uitslaan, backaccount: geld overzetten naar een andere rekeinging. Of deze accounts verkopen!

###1.4 Waarom is het moeilijker geworden om je te verdedigen tegen aanvalen?
* Aanvallen worden makkelijker te gebruiken of worden verkocht (zie vorige vraag)
* Aanvallen worden steeds beter
* Aanvallen worden sneller (botnets, betere hardware, ...)
* Patches zijn trager dan kwetsbaarheden (patch vereist veel testen, ...)
* Gebruikers zijn dom (makkelijk wachtwoord, geen patches, ...)

###1.5 Wat is Windows of vulnerability?
De tijd tussen het ontdekken van een exploit en de patch die zorgt dat de exploit onschadelijk gemaakt! Bijvoorbeeld *Patch Tuesday*, maandelijkse release van (beveiliginspatches) bij Windows Update. Veel "hackers" releasen hun exploits op de woensdag erna (Exploit Wednesday). Zo hopen hierdoor een lange Window of vulnereability. Omdat de volgende "Patch Tuesday" pas volgende maand is!

###1.6 Wat is Information Security?
De taak om digitale informatie te beveiligen, er dus voor zorgen dat er berschermende maatregelen zijn geïmplementeerd.
Deze gaan vaak via het CIA model (zie volgende vraag)! Bijvoorbeeld zorgen voor encryptie op je data, ...

###1.7 Wat houdt het CIA model in?
####C = Confidentiality (Confidentieel)
Data mag enkel bekeken worden voor wie er toestemming voor heeft! Dit zorgt er dus voor dat er privacy gewaarborgt is!

Confidentiele data kan afgedwongen worden door het gebruik van encryptie!

####I = Integrity (Integriteit)
Data mag niet aanpast worden als het verzonden wordt van punt A naar punt C via punt B!

We kunnen dit doen door een simeple CRC of een complexe hash (zie later)

####A = Availability (Beschikbaarheid)
Digitale data heeft tegenwoordig een grote impact op ons leven! Bijvoorbeeld indien je geld wilt afhalen met je bankkaart. Er  wordt verwacht dat deze systemen altijd werken!!!

Je data moet ook nog bechikbaar kunnen zijn tijdens een zware load! Je moet dus bijvoorbeeld zorgen dat DDoS aanvallen geen invloed hebben! => Load balancers, firewalls,... 

###1.8 Wat is het Information Security Model?
Je kunt niet alles weten aka ik ben te tam omdat te leren!

###1.9 Welke twee types van aanvallen hebben we?
* Passieve aanvallen
  * Ondedecteerbaar 
  * Minder resultaat
  * Minder gevaarlijk / minder "illegaal"

* Actieve aanvallen
  * Detecteerbaar
  * Kan veel resultaat opleveren
  * Gevaarlijk => zo goed als altijd illegaal!

### 1.10 Geef voorbeelden van een passieve aanval.
**Meeluisteren => sniffing** </br>
D.m.v. bijvoorbeeld WireShark kijken wat er verzonden wordt, en naar wie.

**Verkeers analyse**
Een raport maken van wat de persoon bezoekt, hoe frequent, ... En hier dan patronen inzoeken. 

### 1.11 Geef voorbeelden van een actieve aanval.
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

### 1.12 Wie voert er allemaal aanvallen (hacks) uit? (Minder belangrijk)
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

### 1.13 Welke 5 stappen doen we in een netwerk aanval? (Minder belangrijk)
* Zoeken naar informatie (sniffen)
* Verdediging doorbreken
* Aanpassen van beveiligings instellingen
* Andere systemen in het netwerk aanpassen (eerst minst beveiligde systeem hacken en dan van daar verder gaan)
* Andere systemen / netwerken plat leggen (firewall neerhalen bijvoorbeeld)

### 1.14 Hoe verdedigen we ons tegen een netwerk aanval?
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

### 1.15 Wat is malware?
Malware is een verzamelnaam voor softwaren die als doel heeft om de computer te infecteren. En hierna zijn voordeel uit kan halen! Malware is een software gebaseerde aanval!

### 1.16 Geef enkele voorbeelden van malware, en geef een woordje uitleg
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


###1.17 Welke software maakt gebruik van malware?
####Spam
Ongewente email die malware kan bevatten!

####Backdoors
Zoals de naam zegt, zorgt ervoor dat er makkelijk in je computer (opnieuw) kan ingebroken worden. Wordt vaak geplaats door malware.

####Botnet
"Zombie" computers die onder de controle zijn de aanvaller (bot herder). Computers worden lid van een botnet door infectie via malware. Deze malware plaats een backdoor en zo kunnen de aanvallers de computer overnemen en lid maken van zijn botnet.

Een botnet kan gebruikt worden voor spam mails, Ddos, verspreiden van malware, online pols manipuleren, ...

### 1.18 Met welke hardware kun je systemen aanvallen / hacken? (Minder belangrijk)
#####BIOS Aanvallen
Combinatie software / hardware. Malware die het geheugen van het BIOS aanpast! De kans dat je computer omzeep is, is zeer groot. Het BIOS was vroeger het stuk software die zorgde dat een OS kon geladen worden. Tegenwoordig gebruiken we UEFI! Dit is veel moeilijker te hacken (nog geen gevallen geweest), en zorgt d.m.v. safeboot dat er geen andere software opgestart kan worden buiten een vertrouwd OS.

#####USB Sticks
Kunnen voor alles gebruikt worden. Ze kunnen dienen om malware te verspreiden (virussen, maar vooral keyloggers). Ze zijn tegenwoordig zeer klein, en kunnen onopvallend in een PC geplaatst worden! Ook worden ze vaak doorgeven waardoor het een makkelijke manier is om malware te verspreiden!

#####Hardware keylogger
Klein apparaat dat tussen computer en toetsenbord geplaatst kan worden. Onthoudt elke karakter die is ingetypt!

### 1.19 Leg SQL Injection uit! (BELANGRIJK)
TODO


# Hoofdstuk 2: Cryptologie
### 2.1 Wat is het doel van cytrografie?
Geheime communicatie tussen twee personen zonder de derde er iets van begrijpt!

### 2.2 Geef het blok schema van de verschillende soorten crypto algoritmes.
![Blokschema crypto](http://i.imgur.com/sY7AioE.png)

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

Indien je dit niet doet zullen alle personen waar mee je informatie deelt, jouw communicatie kunnen decrypteren. Terwijl dit misschien niet de bedoeling is. (Ik wil praten met Bob en ik wil praten met Alice maar ik wil niet als ik praat met Bob dat Alice dit ook kan lezen).

Hierdoor heb je dus snel een moeilijkheid bij, namelijk je keys gaan onderhouden. Ook heb je bij symetische encryptie dat beide partijen verantwoordelijk zijn voor de key! Dit in geen enkel geval publiek mag worden!

### 2.9 Leg PRNG uit
PRNG staat voor **Pseudorandom Number Generators**

Je zijn zo goed als random maar niet volledig, ze zijn afhankelijk van een seed. Deze seed wordt gebruikt als intilisatie van de PRNG's. Bij een zelfde seed zullen twee PRNG dezelfde random getallen genereren. Bijvoorbeeld C#.


### 2.10 Leg de basiswerking van stream cipher uit plus geef een encryptie standaard die dit gebruikt!
##### Stap 1: Sleutelgeneratie
Eerst moeten we onze sleutel ontwerpen. Dit doen we door een Pseudorandom Number Generator (PRNG) te gebruiken. We gebruiken als seed een key die we hebben afgesproken op ontvanger en zender (deze moet dezelfde zijn). 

##### Stap 2: Encrypteren + Decrypteren
Nu gaat je bit voor bit de data XOR'en met de gegenereerde sleutel. Je data in nu geïncrypteerd. 

Indien je wilt decrypteren, genereer je terug een sleutel d.m.v. een PRNG die als seed de de gekozen key heeft. Hierna XOR je deze met de inkomende geecrypteerde data. Indien de key juist was zal de gegenereerde steutel dezelfde zijn als bij de zender. XOR is omkeerbaar door terug te XOR'en met hetzelfde, dus indien de key dus juist was komt hier terug de originele bit uit!

RC4 is een bekend voorbeeld, was long één van de encryptiemethoden. Werd gebruikt in https en wifi. Maar nu is toch gebleken dat deze niet zo veilig is dan gedacht!

### 2.11 Wat is DES?
DES staat voor Data Encryption Standard. Het is een synchrone cipher dat gebruikt maakt van **block cipher**. Het is voor lange tijd de standaard geweest voor encryptie. DES gebruikt blokken van 64 bit met een sleutel van 56 bit.

### 2.12 Is DES nog veilig?
DES wordt al lang niet meer gezien als veilig! Eerst was het mogelijk om DES te brute forcen met krachtige computers, hierna kwamen er ASIC uit met als specifieke taak DES kraken. Deze konden DES in minder dan een uur kraken.

Het probleem bij DES was dat dezelfde plaintext met dezelfde key, in dezelfde ciphertext genereert. Dit kan "dodelijk" zijn voor de veiligheid. Zo kunnen we de data beter cryptoanalyseren (patronen vinden). Dit probleem wordt opgelost d.m.v. de **block cipher mode** (zie 2.16). 

De oplossing was 3DES, dit is DES 3 keer achter elkaar gedaan. Het maakt DES een pak beter, maar uiteindelijk is deze ook vervangen door AES!

### 2.13 Wat is AES?
AES staat voor Advanced Encryption Standard. Het is de nieuwe standaard voor symetrische encryptie van data. Het is gebaseerd op Rijndael (Belgische encryptie). Het gebruikt een 128 bit data block en 128/192/256 bit sleutel. Deze sleutels zijn een pak langer dan DES, en hierdoor is het op dit moment nog niet mogelijk deze te brute-forcen.

### 2.14 Hoe werkt DES?
TODO, gaat ik waarschijnlijk niet meer geraken...

### 2.15 Hoe werkt 3DES anders dan DES?
3DES is eigenlijk DES 3 keer achter elkaar. DES is een veilig algoritme (indien geen ECB gebruikt werd) enkel was de key was nogal kort (56 bit). Dit was makkelijk te brutoforcen!

Door 3 keer DES achter elkaar te doen krijgen we een key van 168 bit. Voor tragere apparaten kan er ook een 112 bit key gebruikt worden en dan is intern K1 == K3.

De eerste stap encrypteren we de block met K1, daarna decrypten we hem met K2. Als laatste encrypteren we de block met K3

![3DES](http://i.imgur.com/7FGh7mf.png)

Decrypteren met 3DES is gewoon andersom! We kunnen met 3DES ook DES ondersteunen dan zijn K1 == K2 == K3!

### 2.16 Wat zijn "Block Ciphers modes"?
Een block cipher symetrische encryptie zegt enkel hoe de blocken van x aantal bits geencrypteerd worden. Je moet echter nog deze blokken kunnen genereren. Dit wordt a.d.h.v. **Block Cipher mode** gedaan. 

Om brute force aanvallen te voorkomen, zijn er veel block cipher modes die de data samenvoegen met een unieke id (**Initial Vecor, IV**). Dit zorgt dat dezelfde data niet deze cypher text geeft! (Hetzelfde als salt, bij hashing!!!)

### 2.17 Leg ECB uit!
ECB, Electronic Codebook Block. De simpelste **block cipher mode**. De plaintext wordt in blokken gebroken. De grote van deze blokken is afhankelijk van de gebruikte encryptie (DES => 64). 

Daarna worden deze blokken stuk voor stuk geencrypteerd d.m.v. je encryptie algoritme (DES, AES, ...). De blokken worden dus onafhankelijk van elkaar geencrypteerd! ECB maakt ook geen gebruik van de unieke id (*IV*), dit zorgt ervoor dat dus het probleem blijft bestaan van dezelfde plaindata dezelfde cipherdata geeft!

![Problem ECB](http://i.imgur.com/9O2HTyx.png)

### 2.18 Leg CBC uit!
CBC staat voor Cipher Block Chaining! Data wordt gebroken in blokken. De eerste keer dat dit gebeurd zal er een IV gegeneerd worden. Deze IV wordt d.m.v. XOR samen gevoegd met de plaindata in de 1ste blok. Dit wordt dan geencrypteerd met een symetrische encryptie (DES, AES, ...). Het resultaat hiervan wordt bij de volgende block gebruikt als IV (ketting).

Dit heeft dus als gevolg dat dezelfde plaindata niet dezelfde cypherdata geeft bij dezelfde key. Het is nu "onmogelijk" om patronen te gaan zoeken.

![Solution CBC](http://i.imgur.com/3veLpJH.png)

### 2.19 Wat is Message Authentication?
Is eigenlijk een hash functie met een key! Een hash functie (zie later) werd oorspronkelijk gebruikt om *Integrity* in te bouwen. Message Authentication voegt een extra sleutel toe om Authentication af te dwingen.

Werking: Bob stuurt een tekst door naar Alive maar aan zijn plaintext wordt een MAC (Message Authentication Code) gehangen. Deze MAC is gegeneerd geweest met een geheime sleutel. Alive ontvangt de boodschap, en zal het MAC algoritme toepassen mijn zijn sleutel op de ontvangen plain text! Als de tekst onderweg is aangepast, dan zal de gegeneerde MAC niet dezelfde zijn als de ontvangen MAC. Dit zorgt dus voor Integrity! Indien de sleutel niet dezelfde was zal de gegeneerde MAC ook niet dezelfde zijn als de ontvangen MAC. Dit zorgt dus voor Authentication!

Let op, MAC zorgt niet voor *confidentiality*! De onderligende tekst kan geïncrypteerd zijn maar dit is niet de taak van MAC! Indien je dit dus niet doet kunnen mensen (EVE) nog steeds lezen wat er verzonden wordt!!!

### 2.20 Wat is een hash?
Een hash is een functie waarbij je de ingang niet meer terug kan reconstueren uit de uitgang. Een hash zorgt er ook voor de uitgang "onafhankelijk" is van de ingang. Als je 1 letter veranderd in de ingang moet de uitgang volledig anders zijn.

### 2.21 Geef een paar bekende hash algrotimes.
MD5 => 128 bits
SHA 1 => 160 bits
SHA 256 => 256 bits

SHA familie is trager als MD5. Dit is een voordeel in cryptologie. Hoe langer het duurt om een hash te nemen, hoelanger een brute force aanval tijd ins belag zal nemen! Pas op SHA is nog steeds te "snel", gebruik daarom liever bijvoorbeeld bcrtypt.

### 2.22 Waarvoor kan een hash gebruikt worden?
Een hash werd oorspronkelijk gebruikt om de *integrity* te checken. Indien de hash dezelfde was, was de data niet onderweg aangepast! Indien niet, was de data dus wel onderweg aangepast.

Nu worden hashes ook gebruikt om wachtwoorden op te slagen. Hashen kun je in tegen stelling niet terug decrypteren. Hoe werkt dit dan? Je vult je wachtwoord in, we nemen hier de hash van en slaan dit op in onze database. Het wachtwoord wordt nooit opgeslagen! Indien de gebruiker wilt inloggen, wordt zijn ingevuld password terug gehasht met dezelfde werkwijze. Indien die hash dezelfde is als de opgeslagen hash is het wachtwoord correct!

### 2.23 Wat is "doodelijk" in een hashing functie.
Collisions zijn een teken van een niet veilige / betrouwbare hash functie. Collisions willen zeggen dat verschillende ingangen resulteren op dezelfde uitgang! Indien dit het geval is, kunnen hackers hier misbruik van maken!

### 2.24 Wat bedoelen we met een hash ketting (chain)?
In plaats van hash 1 keer te nemen van het oorspronkelijke wachtwoord nemen we dit x aantal keer. Dit zorgt dat / rainbowtables moeilijker worden (niet onmogelijk!!!). Indien je het password nuwilt checken moet je evenveel keer de hash nemen als bij het registeren van de gebruiker.

Aangezien een hash nemen met MD5 of de SHA familie relatief snel is kunnen we heel wat loops maken voor de gebruiker het zal merken in snelheid!

### 2.25 Wat is een rainbow table aanval? En hoe lossen we het op?
Een zelfde ingang zorgt bij een hash functie voor eenzelfde uitgang. Als we "hello world" hashen zal het resultaat hiervan altijd hetzelfde zijn!!! 

Dit betekend dus dat als we op voorhand vaak gebruikte wachtwoorden hashen en dan vergelijken met de gehashte wachtwoorden in de databank dat we nog steeds kunnen weten welk wachtwoord er is ingevuld.

Natuurlijk is het niet zo simpel, en gebruiken we een "ketting" van hashes (zie vraag hierboven). Nu kunnen wij ook hetzelfde doen een onze hashes van de meestvoorkomende wachtwoorden in onze rainbow table beginnen te hashen en deze blijven te hashen tot we een hash tegen komen die gebruikt wordt in de DB. Onze rainbow table attack is geslaagd!

We kunnen dit oplossen met een salt (zie volgende vraag)!

### 2.26 Wat is een salt?
Een salt is een vaste of random waarde die je toevoegd aan je wachtwoord voor je deze hasht! Je slaagt in je databank dan de gehashte waarde op. En de gebruikte salt. Het spreekt voor zich dat een random salt veel beter is! 

Waarom slaag je de salt op denk je misschien, anders is het onmogelijk te kijken of de gebruiker het juiste wachtwoord invult. Indien de gebruiker zijn wachtwoord nu invult zal de salt er eerst aan toegevoegd worden voor de hash genomen wordt. Indien nu de hash dezelfde is als de opgslagen hash is het wachtwoord correct.

Dit zorgt er voor dat er geen rainbowtables aanvallen meer kunnen gebeuren. Er bestaat namelijk geen rainbow table van elke salt. Pas op dit lost nog altijd niet het probleem op van dictionary aanvallen. De hacker weet op voorhaand welke salt er gebruikt is kan hij dus ipv de hash van 123456 te vergelijken met de hash in de databank, de hash van 123456salt vergelijken met de de hashes in de databank. Maar nu moet de aanvaller elke hash zelf genereren (in rainbow table stonden deze al), en dit kost tijd veel tijd. Maar daarom is het dus nog steeds belangrijk om een moeilijk passwoord te gebruiken en geen 123456 :)

### 2.27 Wat is public key encryption?
Dit is **encryptie** waarbij de key voor te encrypteren niet dezelfde is als diegene om te decrypteren!

De sleutel voor encrypteren wordt de publieke sleutel genoemd, iedereen kan deze bemachtigen. </br>
De sleutel voor decrypteren wordt de private sleutel genoemd, deze mag niet "lekken" op het internent en moet strikt geheim blijven!

Belangrijkste algoritme die gebruikt wordt hiervoor: **RSA**

### 2.28 Wat is de werking van public key encryption?
Je kunt de werking vergelijken met volgende analogie:

Bob en Alice willen communiceren zonder dat Eve kan meeluisteren. Bob zend een lege schatkist door met een openhangslot (public key). Alice steekt haar data in de schatkist, en doe het hangslot dicht. Bob ontvangt de schatkist en d.m.v. zijn sleutel (private key), kan hij de data bekijken!

Je kunt een public key ook anders om gebruiken om authentication te verzekeren (zie vraag 2.30 over Digital signatures)

### 2.29 Wat is het voordeel van public key encryption?
Je moet niet met sleutels zitten "prutsen", je maakt je publieke sleutel openbaar. Iedereen kan deze gebruiken maar enkel jij kunt de data decrypteren. Je moet dus geen schrik hebben dat mensen die je publieke sleutel hebben ook data kunnen decrypteren!

Je moet nooit een sleutel doorzenden tijdens de communicatie die niet geweten mag zijn (private key blijft gewoon op de server staan). Bij synchrone encryptie moet dit wel! 

### 2.30 Wat is een digital signature?
Dit een een digitale handtekening, het verzekerd je dat je met de juiste persoon aan het praten bent! In de digitale banksector zeer belangrijk. Indien je ergens geld moet storten wil je wel zeker zijn dat die site de echte / juiste site is.

Je kunt dit doen d.m.v. public key encryption (asymmetric key encryption). I.p.v. de vorige keer de private key te gebruiken voor te decrypten, gebruiken we deze nu voor de encrypteren! We hebben data die verzonden wordt, deze wordt gehasht. Deze hash wordt nu geëncrypteerd met de private sleutel van bv. Google. Pas op de data wordt niet geëncrypteerd, dit zou toch geen nut hebben met de private sleutel iedereen kan deze decrypteren met de publieke sleutel van Google. Indien je encryptie van de data wilt zul je dit zelf moeten doen (HTTPS doet dit, maar dit wordt niet uitgelegd in de slides!). 

Als de ontvanger nu de data ontvangt plus de hash, zal hij deze hash decrypteren met de publieke sleutel! Daarna neemt hij de hash van de data. Indien deze dezelfde zijn is de data niet veranderd onderweg, en is de data ook afkomstig van Google!

Met een digital signature hebben we dus authenticatie en integrity! Maar iedereen kan onze data lezen (sniffen)! Dit is dan ook niet het doel van een digital signature!

### 2.31 Wat is de zwakte van een digital signature?
Het systeem werkt enkel als de publieke sleutel echt wel diegene is van Google! Indien Eve aan Alive een andere publieke key verkoopt als de publieke key van Google (Bob). En Alice gelooft dit. Dan kan vanaf nu Eve berichten verzenden uit de naam van Google!!! Indien Eve dan ook nog de echte berichten van Google tegenhoudt hebben we een succesvole MiTM aanval gepleegd!

Dit is uiteraard niet de bedoeling en lossen we op d.m.v. **digital certificates!**

### 2.32 Wat is een Digital Certificate?
Is iets dat een publieke key bind (toe eigend) aan een persoon / orginistatie! Met een certificaat weet een persoon dus dat de key bij de juiste persoon, organistatie hoort!

Ze bestaan uit volgende informatie:

*  Owner’s name or alias
* 	Owner’s public key
*  Name of the issuer
* 	Digital signature of the issuer
* 	Serial number of the digital certificate
* 	Expiration date of the public key

### 2.33 Hoe werkt een Digital Certificate? Hoe kunnen we zeker zijn?
Indien je dus als persoon een certificaat wilt hebben zodanig mensen je site kunnen vertrouwen, gaat je dus naar een **Registration Authority (RA)**. Daar zul jij je gegevens moeten achter laten (persoonlijke gegevens zoals naam, adres, ...).
Zij zullen een dossier om maken en nakijkeken of alles klopt en betrouwbaar is! Ze zullen dan je dosier doorsturen naar een **Certificate Authority (CA)**. Dit zijn bedrijven die een enorme verzameling certificaten heeft. 

#####Hoe kunnen we nu zeker zijn dat de CA wel betrouwbaar is?
Dit kunnen we doen omdat een CA zelf een certificaat heeft dat bij een andere CA zit. Indien deze zelf niet bij een CA zit kun je ze niet vertrouwen. Deze lus kan even door gaan tot je aan de Root CA zit. Deze organisatie bestaat er dus uit om te zoeken of een CA wel betrouwbaar is. Er is hier geen niveau meer boven. Indien deze dus zeggen dat de laatst gewone CA betrouwbaar is, en deze zegt dat de CA eronder betrouwbaar was, .... kun je er dus van uit gaan dat dit zo is. Mocht later blijken dat een (R)CA niet betrouwbaar meer is / was. Dan vallen alle CA's onder hun ook weg als betrouwbaar! (https => rood!)

![Root CA](http://i.imgur.com/JzMf3ZT.png)

Om de CA te controleren zijn er dus ook nog een VA (Validation Authority). Deze doen niets anders dan te kijken is dit certificaat bekend bij een CA, is deze CA bekend bij een andere CA, ... </br>
Elke keer je een site bezoekt die https gebruikt wordt dit gedaan om zo zeker te zijn dat fb wel fb is (denk ik).

![VA](http://i.imgur.com/abEYZ1r.png)

### 2.34 Wat zijn CRL en CR?
#####CRL => Certificate Revocation List
Een lijst van certificaten die ingetrokken zijn en dus niet meer geldig zijn! Elke CA heeft er normaal zo één en kan publiekelijk bekeken worden.

#####CR => Certificate Repository
Een publiek toegankelijke map waaron alle certificaten en CRL's van een CA instaan!

### 2.35 Waar worden deze digitale certificaten nu gebruikt?
Voornamelijk bij het gebruik van https, hierdoor kun je dus zeker zijn dat een bepaalde site wel degelijk de site is dieje je bedoeld / nodig hebt. Dit is om phising tegen te gaan (kopie van bestaande site)!

Echter kunnen ze online gebruikt worden voor alle zaken om te kunnen bewijzen dat je wel degelijk persoon X bent. Elke persoon met een EID heeft bijvoorbeeld een certificaat. Zo kun je via e-mail je jezelf ook bewijzen dat je wel degelijk die persoon bent! Maar ook voor andere zaken zoals belastingsbrief en etc. is het belangrijk dat de server weet dat je 100% de juiste persoon bent om fraude tegen te gaan!


## Hoofdstuk 3; WLAN Security

###3.1 Wat is het grootste veiligheidsprobleem bij WiFi?
WLAN heeft geen fysieke grenzen, bij LAN heb je fysieke toegang nodig. Bij WLAN niet, je WiFi van thuis kunnen je buren ook ontvangen!

Waar je bij LAN dus minstens toegang nodig had tot een ethernet poort is dit bij WLAN niet meer! Het wordt een stuk minder moeilijk!

###3.2 Wat zijn de grootste problemen bij WiFi zonder beveiliging?
*  Sniffen (Eavesdropping)
*  Denial of service attacks 
  * Access point makkelijk "plat" te leggen => RTS / CTS aanval
  * Fysische aanval op 2,4 GHz => Kan zelf met een microgolf oven!
*  **Rogue AP**
  * Access point die niet behoord tot de netwerk infrastructuur van het netwerk (bedrijf, organisatie, persoon, ...)
  * Kan misbruikt worden voor MiTM aanval => Zelfde SSID mensen verbinden zich via jouw AP naar het internet!
  
###3.3 4 stappen om verbinding te maken via WiFi
1.  Scannen => Zijn er AP's in de buurt => Geven SSID terug
2.  Joining => Connectie vragen met AP => fysische instelling juist zetten (correct kanaal, ...)
3.  Authentication => Mag ik verbinding maken?
    * Geen beveiliging => stap overslaan
    * Beveiling => AP stuurt challange naar client, client encrypeert deze met key => stuurt dit terug => AP encrypteerd ook de challange => Indien beide geëncrypteerde challanges dezelfde zijn => Clinet is geathentiseerd!
    * MAC gebaseerde beveiling => Vergelijkbaar met port security => Nuteloos door mac spoofing! => En wifi wordt niet afgesloten zoals bij portsecurity wel het geval kan zijn voor een ethernet poort!
4. Association => Analoog met: steek de kabel in de poort
    * Afpsraken sturen (IP, Default gateway) => DHCP
5. Je bent verbonden!

###3.4 Hebben we CIA bij WiFi
Zonder beveilings methode hebben we niets van CIA. Buiten het feit dat de beveiling dus zorgt voor wie mag er met de access point verbinden zal het dan ook aan encryptie en integriteits checks van de data doen!

1 ste standaard => WEP (Wireless Equivalent Privacy)

# Effectief gestelde vragen op examen (November 2015)
* Een public-private key cryptografisch systeem kan gebruikt woorden voor zowel Confidentiality als voor Authentication. Verklaar hoe dit in z’n werk gaat. (3p)
* Wat is een Rainbow tables attack? Wat is een eenvoudige manier om deze aanval te voorkomen? (2p)
* Wat is het principe van Kerkhoff? Waarom is dit principe een nadeel voor symmetrische crypto-systemen? (2p)
* Waarom kan je niet anders dan de Root CA in een PKI vertrouwen? Leg uit wat een CA doet. (3p)
* Welke dag is dé ideale dag om een nieuwe exploit op je slachtoffers los te laten? Waarom? (1p)
* Wat is het verschil tussen een root kit en eenvoudige malware? (2p)
* Hoe kan je heel eenvoudig de sessie van een andere gebruiker op bol.com overnemen? Beschrijf je ‘aanval’? [owasp] (2p)
* Hoe kan je data leakage door onveilige data opslag voorkomen? [owasp] (2p)
* Wordt de XOR functie gebruikt in WEP encryptie bij Wifi? En bij WPA1? Teken het encryptieschema van WEP. (3p)


# 2de module

Aantal leerstof in deze module is klein. Hoofdleerstof bestond uit 7u Pluralsight + PPT Social engineering + PPT Metasploit + PPT Autereursrechten

## Scanning

### Wat is het doel van 'Scanning'?
Meer informatie te weten komen dan bij 'Reconnaissance' . Bij deze stap hadden we gezocht uit welke IP-ranges het netwerk bestond. Bij scanning willen we weten hoe het netwerk eruit ziet. We willen weten wat de functies zijn van onze hosts (server, DC, ...) we willen weten welke besturingssystemen (+versie) onze targets hebben. </br>
Als laatste zoeken we al uit welke 'kwetsbaarheid' bekend is bij onze targets.

### Hoe doen we dit!?
#### PING: MOTHER OF EVERYTHING
We beginnen standaard met een pingsweep van heel het netwerk. 'PING' is en ICMP echo, indien er een ICMP reply terug komt weten we dat er op dat specifieke IP adress en host live is.

ICMP is een IP protocol (Netwerk laag). Het speciefiert geen transport laag. Het werkt dus met 'geen' poorten. (ICMP's zijn altijd poort '1'.) Het is dus heel gemakkelijk om deze te blokkeren in een firewall!

Pingen kun je standaar in CMD. Maar dit is maar één adres tegelijk. Wil je volledige network ranges af gaan kun je beter gebruik maken van Angry IP Scanner of nmap (Zenmap).

Deze stap is dus niet genoeg...

#### TRANSPORT LAYER
Voor we verder kunnen moeten we 3-way handshake van TCP begrijpen. Als je dit niet kent, Yves Masset komt je halen :)

Indien twee computers willen communiceren met elkaar kun je gebruik maken van TCP / UDP als transport protocol. TCP is het lieve, zachtaardig protocol. UDP is het 'maakt mij niet uit' protocol! Waarom?

Bij TCP ben je zeker dat er een connectie tussen beide computers is (what is love?). TCP zal er ook voor zorgen dat pakketjes sowieso aankomen en dat ze in volgorde aankomen. TCP heeft ook flow - control. Dit wilt zeggen als het allemaal een beetje te snel gaat, de host ervan verwittigd wordt en deze trager zal beginnen zenden!

UDP is hier het tegenovergestelde van! UDP maakt het niets uit, je zend er naar klaar. Je bent nooit zeker of je data aankomt. Laat staan dat je zeker bent dat data in de juiste volgorde toekomt! Het voordeel van UDP is wel dat het sneller is! En het minder overhead heeft!

#### 3 - way handshake
3 - way handshake is de manier waarop TCP een connectie opsteld tussen beide computers. Vanaf dan kunnen ze zenden met elkaar!
(was het in het echte leven ook maar zo simpel).

De zender stuurt een **'SYN'** pakketje naar de ontvanger. Dit heeft een bepaalde random ID laat ons zeggen 31. Als de ontvanger toegang toelaat zal hij een **'SYN-ACK'** terug sturen. Deze heeft ook een random ID (bv. 58). maar heeft nog een andere id ook de 'ACK' id. Deze zal de id van de zender hebben +1! In ons geval dus 32. Nu weet de zender ook over welke communicatie het gaat. De ontvanger heeft de zender dus geaccepteerd. Als bewijs sturen wij (zender) nog eens een **'ACK'** terug deze zal als ID onze 32 hebben maar als 'ACK' id de ID van de SYN-ACK + 1! In ons geval dus 59. Nu weet de server ook bij welke communicatie dit pakketje hoort.

De zender en ontvanger zijn nu 'vrienden' en er kan een TCP connectie beginnen (Bv. HTTPS).

![3 - way handshake](http://thumbs.dreamstime.com/z/tcp-way-handshake-model-30635805.jpg)

#### TCP scan
We kunnen nu door een 3 way handshake te doen op elke poort van een host te weten komen of de host live is, en wat zijn taak in het netwerk is.

Dit is veel moeilijker te firewallen. Stel je hebt een webserver (poort 80 / 443). Je kunt deze poort niet dicht doen. Anders heeft je webserver niet veel nut. 3 - way handshake kun je ook niet verbieden, anders kan er niemand verbinding mee maken.

Het enigste hoe je dit kun oplossen. Is kijken hoeveel tries een client doet ligt dit abonormaal hoog kun je de hacker van je netwerk smijten. Pas op dit vertraagd enkel de hacker! En de hacker heeft veel tijd...

##### Open poort
Indien de poort open is zal de 3 - way handshake gelukt zijn! 

##### Gesloten poort
Indien je een 'RST' terug krijgt i.p.v. een 'ACK' dan is de poort gesloten!

##### Firewall
Indien je 'SYN' pakket niet aankomt en je dus geen enkel pakket terug krijgt dan heeft de firewall het geblokkeerd!

#### UDP scan
Veel moeilijker! Geen 3 - way handshake! Je weet dus nooit of een poort nu dicht is, ze gefirewalled wordt of je pakketje gewoon nooit is aangekomen! Je bent bij UDP dus verplicht om altijd x - aantal tijd te wachten...

##### Open poort
Je stuurt een **'request'**, je krijg een **'response'** terug! 

##### Gesloten poort, firewall, gedropt pakketje
Je krijgt gewoon niets terug!

#### Tijd
Port scanning kan lang duren (2 * 65535 poorten). Zeker UDP scanning kan lang duren. Er is een commnado in nmap dat je enkel de belangrijkste poorten scant!

> --top-ports

Deze zal de 2000 meest voorkomende open TCP poorten scannen en de 500 meest voorkomende open UDP poorten scannen!

#### Nut?
Indien je weet welke poorten openstaan. TODO
