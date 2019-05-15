# Comments go/no go

* M. Marx
* 2019-05-15


## Algemeen

* Gaat goed, je bent goed bezig met echt gave en big data.
* **verbeterpunten** 
    * Echt precies worden
    * Consisietnt zijn.
    * Vraag om hulp en feedback van je peers en van de mensen bij NPO.

### notebook

1. Formulas
    2. **Try making them more precise please.** Dus bijvoorbeeld
$$ P@k = \frac{|\{i \in TP\mid i\mbox{ ranked in top k}\}|}{k}$$
    3. Je geeft niet aan wanneer een item relevant is. 
    4. Ahem: _It assesses the precision at each rank and multiplies it with the total amount of TPs._ Je deelt door TP...
    5. $AP@k$ klopt niet. Ik ken die maat ook niet. Wel AP gewoon, en dat is wat jij hebt opgeschreven. Ik zou dat dan maar doen. Maar dan moet je wel TPseen vervangen door $|\{i \in TP\mid i\mbox{ ranked in top k}\}|$ en verder overal de i door een $k$.
    6. P@k and AP zijn nu gedefinieerd voor 1 user. Maar jij gaat ze toch voor alle users gebruiken, denk ik? Je moet dus laten zien hoe je die maat berekent. In IR gebruik je MAP (je neemt het **gemiddelde** over alle vragen). Voor P@k lijkt me het gemiddelde ook het beste.
        7. Wel is het goed om hier eens een distributieplot van te maken: hoe vaak komt elke waarde van P@k nou voor in jouw verzameling users? Geef dus ook de std, naast het gemiddelde.
    8. CTR: _opposed to times the ribbon was offered._ opposed??? toch gewoon _gedeeld door_
        9. Zoals ook besproken in de klas is je uitleg niet hetzelfde als je formule. Je zegt proportion of users, maar dat is niet waar, want een user kan meerdere offers gehad hebben.
2. **Engels** Zoek hulp hiermee. Je schrijft best goed, maar het is te vaak krom en daardoor niet goed te begrijpen. Ook hier weer _The data for the recommendation systems consist out of interaction and item information._ _out_ hoort niet in deze zin. Ik zou ook liever van _input data_ spreken. Of _features_ want daar gaat dit notebook over. 
3. **Precies en consistent** Je zegt _the total amount of items in a row_ Maar eerder spreek je van _ribbon_ (zonder dat uit te leggen trouwens, ik dacht aan een lintje zoals vrouwen tegen borstkanker dragen), nu noem je het _row_. Of is dit weer iets anders?
4. **Data** Dit is nu erg kort en dat is hier prima. Maar in je scriptie wil ik het echt graag heel precies zien. Dus voor elke variabele geef je ook heel exact aan hoe je die hebt gecodeerd in een vector. Voor de omroepen snap ik de one-hot encoding. Voor titels eigenlijk niet, want elke titel lijkt me uniek... Maar goed, wie weet heb ik het mis. Mijn eerste gedachte zou zijn om de **woorden in de titel** als features te nemen. Dus dit behoeft echt uitleg.
5. **Experimental setup** Idema als voor data: veel uitgebreider in je scriptie.
    6. De stappen hebben een gekke volgorde. Stap 4 moet meteen na stap 1.
    7. Stap 3 is verwarrend. Doe je nu 5 fold CV, of 1 keer trainen en 1 keer testen?
6. **Results** 
    7. Hoeveel cijfers achter de komma? Mijn gevoel zegt dat je er veel te veel geeft. Kijk eens naar <http://onlinestatbook.com/2/estimation/mean.html>. En maak eens een inschatting van je confidence breedte. Al zou je maar 1 std er onder en erboven gaan zitten (meestal wordt er 1.96 genomen) dan heb je een P@k tussen .11 en punt .21. Is het dan nuttig om die waarde te geven als .1677? Idem voor de std's? 
    8. Je gaat heel veel cijferstjes geven. Rond het dus maar af, anders wordt de lezer hyper, of iets anders ;-)
7. **Zijn dit de juiste experimenten gegeven je hoofdvraag?** Je wilt kijken wat content based kan **toevoegen**. Ik zou dus verwachten dat je altijd None+ verzameling content features gaat bekijken. Maar hier bekijk je die verzamelingen los. 
    8. Of heb ik het gewoon niet goed gelzen? In je tekst lijkt het alsof het wel bovenop de coll. filt aanpak komt. **Maar hoe komt het dan dat ie het SLECHTER gaat doen?**

### Thesis sectie 3.1

1. Graag regelnummers
2. **3.1.1 en 3.1.2** Probeer consistent te zijn. Bij de interactie data spreek je over *items*, bij de content data ook, maar ook over *series*. Uiteindelijk lijkt je analyse eenheid *series* te zijn. Wat wordt er nu eigenlijk in die ribbons aangeboden, en waar heb je interactie data over? Als het om *series* gaat rada ik je aan alleen daar op te focusen en ook alleen op de 8 content features die jij gaat gebruiken. 
3. **Figures** Graag goede captions. Figur 1 gaat over missende data: zet dat dan ook in de caption. Je kan het figuur ook omdraaien en het in percantages missende data zetten: dat maakt het veel duidelijker en de lezre hoeft geen inferentie te plegen. Goede caption zou dan zijn "Percentage items met missende waardes voor elk van onze 8 content features."
    4. Figuur 2: volgorde op x-as is raar. Bij Fig 3 is dat wel goed. Caption is onvoldoende, en y-as label is nietsszeggend (laat dan liever weg). Caption voor figur 2 is toch gewoon "Number of items for each value of the variable age-rating. Ook hier zijn percentages allicht nuttiger."
    5. **Elk figuur moet te snappen zijn zonder dat je de tekst hoeft te lezen.**
    6. Leuk, tabel 1: maar is dit nu berekend inclusief de missende waardes of niet? Ik hoop van niet. Verneld het er graag bij! Maak de caption beter.
    7. Gaaf Figuur 4, maar haal de missende waardes er uit. Dit zijn populatie distributies, en daar horen die niet in. Het vertekent de boel ook heel erg. 
        8. log schaal voor x-as is allicht nuttig voor descition en subtitles. 
        9. Bij titel lengte gebeurt iets raars: er lijken waardes in te zitten die tussen de integers inzitten. Maar die bestaan niet!!! Toch? Je verwacht hier alleen spikes te zien in het histogram. 
        10. Caption ook weer te gek maken.
11. **Data description versus encoding** Op het eind haal je die 2 door elkaar. Ik zou dat niet doen. Maak liever een aparte subsectie getiteld "encoding" waarin je uitlegt hoe je de feautures opslaat in vectoren. Dan kan je ook aangeven hoe lang je verctoren worden, etc. 
