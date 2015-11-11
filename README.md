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



