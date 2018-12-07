---
---
05 Laddningstid
=========================

Laddningstid på utvalda webbplatser
=======================

De flesta har upplevt en viss frustration i väntan på att webbplatser laddar. Det kan
skilja sig mycket trots att innehållet visuellt ser liknande ut. Här kommer ett antal webbplatser jämföras och vi kollar på vad som gör skillnaden för denna väntan.

Urval
-----------------------

Tre webbplatser inkluderas i denna analys, som användarmässigt hamnar i samma katergori.
Det är tre väderprognos-sidor som de flesta mött i sin vardag och fungerar på liknande sätt.
I dessa webbplatser tillkommer även tre ytterliggare undersidor, som även de går i samma riktning. En första-sida, en vädersökning på Stockholm och en undersida inom hav och kust-rapporter,

Metod
-----------------------

Som utgångspunkt har jag besökt de tre webbplatserna, inklusive undersidor från min egen dator.
Med samma webblässare användes det inbyggda verktyget "Dev tools" för att mäta inladdningshastighet, antal resurser som måste laddas, samt den totala storleken för webbplatsen. Denna mätning görs i Google Chrome.

En mer grundläggande mätning görs i Google Pagespeed för samtliga sidor. En laddning utav webbplatsen ger ett resultat från ett till hundra och en förklaring till vad som tar tid. Denna mätning körs för både desktop och mobil variant utav dessa sidor. Samtliga mätningar körs fem gånger i denna analys för att ta ut ett medelvärde, för att reducera slumpmässiga resultat.

Resultat
-----------------------
Dessa resultat kommer från 5 inladdningar utav samtliga sidor från verktyget Devtools, detta är medelvärdet presenterat för samtliga undersidor. Medelvärdet från Googles verktyg Google Pagespeed presenteras även. [Resultat presenterat i Google spreadsheet.](https://docs.google.com/spreadsheets/d/1fnEKmnzjyZ9-_5PkUyF_BusmNtnzosasv9-mL0FIHLA/edit?usp=sharing)

#### www.yr.no

![Studiopress](img/yr-no.png)

Sidor inkluderade i analysen:
[Startsida](https://www.yr.no)
[Stockholms väderprognos](https://www.yr.no/place/Sweden/Stockholm/Stockholm/)
[Havsrapport](https://www.yr.no/hav_og_kyst/)

Laddningstid: 4.73 s.
Storlek på nerladdad data: 763 KB.
Antal requests: 83.

Google Pagespeed score: 89.7 (desktop), 72 (mobilt).

Denna webbplats presterar bra på samtliga test, men faller något på den mobila versionen.
Den hade kunnat använda sig utav media queries för att anpassas till mobilt bruk, istället för
som nu en extra redirect för den mobila varianten.

#### www.smhi.se

![Studiopress](img/smhi-se.png)

Sidor inkluderade i analysen:
[Startsida](https://www.smhi.se/)
[Stockholms väderprognos](https://www.smhi.se/vadret/q/Stockholm/2673730#tab=0,chart=1)
[Havsrapport](https://www.smhi.se/vadret/hav-och-kust/sjorapporten#ws=wpt-a,proxy=wpt-a,lang=sv,area=none)

Laddningstid: 14.73 s.
Storlek på nerladdad data: 1.8 MB.
Antal requests: 132.

Google Pagespeed score: 85 (desktop), 37.3 (mobilt).

En okej prestation i desktop mijlö, men desto sämre för en mobil variant. JavaScript filen
skulle kunna minifieras och möjligen effektiviseras, då den utgör en stor del utav tiden som
inladdningen utgår ifrån. Det finns mycket bilder som även de drar ner hastigheten och förhindrar annan viktig information att visas. Möjligen kunde antalet minska, speciellt vid mobilt bruk.

#### www.dmi.dk

![Studiopress](img/dmi-dk.png)

Sidor inkluderade i analysen:
[Startsida](http://www.dmi.dk/vejr/)
[Stockholms väderprognos](http://www.dmi.dk/vejr/til-lands/byvejr/by/vis/SE/2673730/)
[Havsrapport](http://www.dmi.dk/hav/)

Laddningstid: 17 s.
Storlek på nerladdad data: 1.3 MB.
Antal requests: 139.

Google Pagespeed score: 70 (desktop), 29 (mobilt).

Medioker prestation i desktop miljö och än sämre för den mobila varianten.
Javascript är den främsta anledningen för den långsamma inladdningen. De använder
tillägget jQuery och möjligen kunde detta unvikas för ett snabbare resultat.


#### Bäst resultat

En klar vinnare är yr.no. Webbplatsen hade bäst resultat i desktop-miljö såväl mobilt.
De använde sig utav lägst antal filer och storleken var det lägsta vi fann.

Trots det relativt låga värdet för mobilt brukt hamnar smhi.se på andra plats.
De ha den största storleken men kunde ändå använde informationen hyffsat effektivt.

På sista plats kommer dmi.dk med lägst resultat i desktop-miljö såväl mobilt.

Analys
-----------------------

För att i grunden tillföra liknande tjänster skillde sig resultaten mer än jag kunde föreställa mig.

Jag satte innan testet ett värde på sju sekunder som inladdningstid, ett värde som kunde reflektera en tid jag anser att den webbplats jag besöker ska vara färdigladdad vid besök.
Endast en utav sidorna klarade den gränsen. Ett något chockerande resultat.

För de två sämst presterande webbplatserna trodde jag alla bilder, i platsens sammanhang men även reklam skulle ha större inverkan. De båda har mycket som ska presenteras, men de är väl anpassade efter webben. Dock skulle man t.ex. kunna minska mängden vid bland annat mobilt bruk, av sådant som inte är direkt relevant. Men i största allmänhet var det skripten på sidan som stod för de längsta väntetiderna. För den ena användes inte en minifierad JavaScript fil och den andra brukade sig utav jQuery. Detta medför extra information som användaren måste ladda ner vid ett besök på sidan, vilket gör att det i min mening tar allt för lång tid för en användare att navigera runt.



Referenser
-----------------------

[https://developers.google.com/](https://developers.google.com/)

Övrigt
-----------------------

Rapport av Jesper Nyhlén
