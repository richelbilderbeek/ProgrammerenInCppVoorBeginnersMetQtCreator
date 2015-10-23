# Dag 1

Vandaag gaan we leren werken met Qt Creator. 
We leren componenten kennen. Componenten hebben eigenschappen en gebeurtenissen.
Eigenschappen kunnen we bij bijvoorbeeld een muisklik (een gebeurtenis) wijzigen. Door creatief te spelen met deze
eigenschappen kunnen we een plaatje over het beeldscherm
laten stuiteren. Als enige 'pure C++' wordt het if statement
geleerd.

## Over C++

C++ is een programmeertaal die haar naam kreeg in 1983 (!) waarin
alle denkbare programma's in geprogrammeerd kunnen worden.
Bijvoorbeeld Windows XP en Vista zijn grotendeels in C++
geprogrammeerd, maar ook het schietspel Quake.
Ook is C++ een multi-paradigmataal: een programmeur kan elke
denkbare (soms 'vieze') taalconstructie doen, omdat C++ geen
werkwijze oplegd. In C++ kan 'object georienteerd' worden
geprogrammeerd, maar dit hoeft niet.

![Bjarne Stroustrup](BjarneStroustrup.png)

```
Ik laat je helemaal vrij. Wel geef ik je de
mogelijkheid schonere code dan in C te schrijven.
```

Daarnaast is de C++ syntax (zinsbouw) kort met vaak
leestekens in plaats van woorden. De layout van C++ is vrij.
C++ is case gevoelig.

C++:
```
for (int i=0; i!=10; ++i)
{
  //Doe dingen
}
```

BASIC
```
for i = 0 to 10 step 1
rem doe dingen
next
```

Vergelijking syntax van C++ met BASIC
Standaard C++ is relatief beperkt: er kan alleen met tekst
(één kleur, zonder knippereffecten) gewerkt worden. Om met
kleur te kunnen werken zijn er vele bibliotheken ontwikkeld,
waaronder de Qt bibliotheek, die door Qt Creator wordt gebruikt.

![Bjarne Stroustrup](BjarneStroustrup.md)
```
C++ is ontwikkeld om platform onafhankelijk te
zijn. C++ neemt zelfs niet aan dat de gebruiker
een toetsenbord of beeldscherm heeft!
```

121.1. Over Qt en Qt Creator

Qt Creator is een programmeeromgeving.
Qt is een grafische bibliotheek, die ingebouwd is in Qt Creator.
Qt en Qt Creator zijn door TrollTech ontwikkeld.


Een grafische programmeeromgeving helpt de programmeur met
programmeren. In deze cursus wordt zwaar van deze hulp
gebruik gemaakt.


## Overzicht van de belangrijkste
vensters
Bij het starten van Qt Creator zijn er meteen veel vensters te
zien. De 'Object Treeview' en 'Project Manager' hebben we
niet nodig, dus die kunnen we wegklikken. Dan blijven er nog
5 vensters over.
De 5 belangrijkste vensters (in Qt Creator).
Waar
1
2
3
4
5
Wat
Menubalk
Component
Palette
Object
Inspector
Form
Code Editor
Waarvoor
Menu opties
Bevat alle
componenten
Bekijken van een
component
'Werkblad', design
Schrijven code
Sneltoets
Alt
Geen
F11
F12
F12


## Een programma beheren

Er is wat bestandsbeheer en discipline nodig om goed en
zonder problemen met je programma's te kunnen werken.
Gebruik onderstaande richtlijnen tot je doorhebt wat er
gebeurt als je je niet aan deze richtlijnen houdt.

## Een nieuw programma beginnen

Als je een nieuw programma wilt maken, doe ALTIJD eerst
'File | Close All'.

## Een programma opslaan

Kies 'File | Save All' of CTRL-SHIFT-S. Er gaan nu twee
bestandsnamen gevraagd worden: de naam van het Project en de
naam van de Unit. Deze moeten NIET dezelfde naam krijgen.
Leer je aan de naam van je project met 'Project' en de naam
van je unit met 'Unit' te laten beginnen, bijvoorbeeld
'Project1' en 'Unit1'.

## Een programma laden

Als je een nieuw programma wilt laden, doe ALTIJD eerst
'File | Close All'. Kies dan ALTIJD 'File | Open Project'.
151.7. Applicatie 0
Je eerste applicatie maken is simpel. Begin een nieuw
programma. Doe ALTIJD eerst 'File | Close All'. Druk op 'Run
| Run' of F9.
Kort verschijnt dit schermpje:
Daarna komt 'Applicatie 0' tevoorschijn:
Hoe weinig spectaculair ook, dit is een volwaardige
windowsachtige applicatie.

## Het Component Palette

Het Component Palette bevat Componenten. Een Component is
'een ding dat je met de Object Inspector kunt veranderen'.
Elk Component hoort bij of op een Form, behalve Form zelf.
Het Component Palette
Klik op een Component, bijvoorbeeld een Button (onder de tab
'Standard' en klik dan op het Form. Er staat nu een knop op
het Form. Druk op 'Run | Run' of F9 om deze iets
uitgebreidere applicatie te starten. Op de knop kan gedrukt
worden, maar hij doet nog niets.
Kijk eens welke Components er allemaal aanwezig zijn en
welke nuttig zouden kunnen zijn.
Een Form met alle Standard Components

## De Object Inspector

Met de Object Inspector kan er 'design time' geprogrammeerd
worden. Klik op het Form. In de Object Inspector verschijnt
dan bovenaan de tekst 'Form1'. In het tabblad 'Properties'
staan de eigenschappen van dit Component.
Sommige eigenschappen zijn woorden (bijvoorbeeld Caption),
andere getallen (Width), weer andere zijn 'true' of 'false'
(Visible) en bij sommigen verschijnt zelfs een pop-up menu
(Color).
Maar wat je ook kiest, het Form past zich meteen aan de
nieuwe waarde aan als dit nuttig/mogelijk is.
Voorbeeld van een Form waarin de Caption en Color gewijzigd
is en dit meteen zichtbaar is
Alle Components kunnen per definitie tijdens 'design-time'
worden gewijzigd. Omdat Components verschillen, verschillen
ook hun Properties.

## Events
Programma's reageren op gebeurtenissen. Dit worden in Kylix
'Events' genoemd. De bekendste Event is de 'OnClick' Event
van een Button.
Enkele Events van een Button. De OnClick Event is
zichtbaar, maar nog leeg.
Onder de Events komt de C++ code te staan van wat er bij een
Event moet gebeuren.

## Een Event programmeren

Selecteer in de Object Inspector een Component. Ga naar het
tabblad 'Events'. Dubbelklik op het lege hokje rechts van de
Event naam, bijvoorbeeld 'OnClick' van een Button. De Code
Editor verschijnt met een stuk voorgeprogrammeerde code.
Een lege OnClick event van een Button. Merk op dat de naam
rechts van de Event naam overeenkomt met de de naam in de
voorgeprogrammeerde code.
De code tussen de accolades wordt aangeroepen als op de knop
geklikt wordt. De rest van de 'moeilijke' regel wordt later
duidelijk. De regel die begint met '//' is een commentaar
regel.
Nu kunnen Properties run-time worden gewijzigd.

## Properties run-time wijzigen
Het wijzigen van Properties onder run-time is iets moeilijk
dan tijdens design-time.
Het duidelijkst is een voorbeeld:

```
void __fastcall TForm1::Button1Click(TObject *Sender)
{
//Deze regel is een commentaar regel
//Verander de Caption van Button1 naar de tekst 'Hallo'
Button1->Caption = "Hallo";
//Zet Button1 100 pixels links van de rand van het Form
Button1->Left = 100;
//Zet de kleur van Form1 op groen, oftewel clLime
Form1->Color = clLime;
}
```

Als je 'Button1->' toets, verschijnt een pop-up menu met
alle mogelijke 'dingen' die je kunt kiezen. Dit wordt
'Class Browsing' genoemd en voorkomt veel typefouten.
21Merk de volgende dingen op:
* Commentaar begint met een dubbele delen-door-streep,
oftewel een dubbele slash. De rest van de regel wordt
niet gelezen door de computer
* Elke 'echte' regel eindigt met een puntkomma
* Eerst wordt de naam van het Component gegeven, dan een
pijltje, dan de Property, dan een is-teken, dan de nieuwe
waarde van de Property, dan een puntkomma.
* Is de type van het Property tekst, bijvoorbeeld een
Caption, dan moet de tekst tussen dubbele
aanhalingstekens.
* Getallen en 'speciale woorden' hebben geen
aanhalingstekens. Deze 'speciale woorden' worden later
'enumeraties' genoemd en zijn eigenlijk getallen in een
wat leesbaarder jasje. De naam van deze enumeraties
kunnen ook uit de Object Inspector worden gelezen.
Bovenstaande code is al 'echte' C++ code. Er kunnen dan ook
al dingen misgaan. Dit wordt een compile error genoemd.
Merk op dat deze code alleen maar Properties toekent aan
Components, in plaats van deze te lezen.

## Properties lezen

Properties kunnen ook gelezen worden om vervolgens ergens
anders weer geschreven te worden.
Hier onder een voorbeeld met een Form met twee Buttons, elk
met een eigen OnClick Event.

```
void __fastcall TForm1::Button1Click(TObject *Sender)
{
  //Button 1 is geklikt
  //Wissel de Captions van Button1 en Button2 om
  //Gebruik de Caption van Form1 als 'bruggetje'
  Form1->Caption
  = Button1->Caption;
  Button1->Caption = Button2->Caption;
  Button2->Caption = Form1->Caption;
}
void __fastcall TForm1::Button2Click(TObject *Sender)
{
  //Button 2 is geklikt
  //Laat Button2 naar rechts lopen
  Button2->Left = Button2->Left + 10;
}
```

Merk de volgende dingen op:

* C++ heeft een vrije layout. Daarom moet met een puntkomma
aan worden gegeven waar een zin eindigd. Bij Button1Click
heb ik de is-tekens mooi onder elkaar gezet. Dit verhoogt
(in mijn ogen) de leesbaarheid van de code. Leesbaarheid
gaat (meer) een rol spelen bij moeilijkere code.
* Om Button2 naar rechts te laten lopen, wordt eerst de
Property Left gelezen, hier tien bij opgeteld en dit
getal wordt weer naar de Left van dezelfde Button
weggeschreven. Later leren we een verkorte schrijfwijze.
* Een Caption van "10" kan niet toegekend worden aan een
Left Property. Een Caption is een woord en Left is een
getal. Op Dag 2 zien we hoe we deze types naar elkaar
kunnen converteren. Soms gaat zo'n conversie toch
automatisch, bijvoorbeeld als je een Left aan een Caption
wilt toekennen. Dit is dan een keuze van de Borland
programmeurs geweest.
Het plus-teken ('+') wordt een 'wiskundige operator'
genoemd. C++ kent er meerdere, hier de belangrijkste:
Wat
+
-
/
*
%
!
Waarvoor
Optellen
Aftrekken
Delen
Vermenigvuldigen
Rest bij deling
Niet
Voorbeeld
16 + 10
16 - 6
16 / 5
16 * 4
16 % 5
!true
Uitkomst
26
10
3
64
1
false
Nu kunnen we Components laten bewegen, maar voor een leuk
programma is het nog nodig wat-als-dan-statement, oftewel
if-statements, te kunnen maken.

## Het if-statement

De syntax van een if-statement is als volgt:
```
if ( /* iets */ )
{

}
```

Of

```
if ( /* iets */ )
{
  //Doe dit als 'iets' waar is
}
else
{
  //Doe dit als 'iets' niet waar is
}
```

De '/* iets */' is een multi-line commentaar (hoewel deze
hier toch single-line is) en dit is een commentaar dat
begint bij '/*' en eindigd bij de '*/'.
Op de plaats van '/* iets */' moet een conditie komen te
staan.

```
//Is Button1 te ver naar rechts?
if ( Button1->Left > 100 ) //Hier GEEN puntkomma's!!!
{
//Zet Button1 weer naar links
Button1->Left = 0;
}
else
{
//Laat Button1 naar rechts lopen
Button1->Left = Button1->Left + 10;
}
```

Merk het volgende op:
* Een conditie staat tussen ronde haken.
* Na een conditie staat geen puntkomma.
* Na de ronde haken komt geen puntkomma.
* Een single-line commentaar kan ook op dezelfde regel van
'echte code' staan.
* Het groter-dan teken in het if-statement ('>') leest als
'groter-dan'. De conditie lees je dan ook als 'als de
Left van Button1 groter is dan 110, dan ...'.
* Tussen de accolades van een if-statement springt de code
naar rechts. Dit is om de leesbaarheid te vergroten.

![Herb Sutter](HerbSutter.md)
```
Er zijn meerdere manieren van inspringen.
Gebruik een consistente manier van inspringen,
zoals Richel. Sommige programmeerteams
verbieden het gebruik van tabs om in te
springen.
```

Er zijn meerdere relaties tussen twee dingen dan een groter-
dan relatie:
Relatie
Gelijk
Ongelijk
Groter
Kleiner
Groter of gelijk
Kleiner of gelijk
Teken
==
!=
>
<
>=
<=
26if-statements kunnen ook aan elkaar gekoppeld worden:
if ( Edit1->Text == "Richel"
&& Edit2->Text == "Bilderbeek") //Mooie layout
{
//Als beide waar zijn
Form1->Caption = "Welkom Richel!";
ButtonSuperGeheim->Visible = true;
}
else
{
Form1->Caption = "Haha! Jij komt niet verder!";
}
if ( Button1->Left < -100
|| Button1->Left > 1000)
{
//Als een van beide waar is
Form1->Caption = "Oei, Button1 is het scherm uit!";
}
Merk de volgende dingen op:
* 'en' wordt geschreven als '&&', ofwel een dubbele
ampersand.
* 'of' wordt geschreven als '||', ofwel een dubbele pijp.
* C++ layout is vrij, dus beide condities kunnen ook op een
regel. In dit document paste dit niet.
* Tussen de accolades van een if-statement springt de code
naar rechts. Dit is om de leesbaarheid te vergroten.
* Een Button kan 'ButtonSuperGeheim' heten als de Name
Property zo heet.
27Ook kan een if-statement weer in een if-statement staan:
if ( Edit2->Text == "Bilderbeek)
{
//Een familielid
if (Edit1->Text == "Richel")
{
//Ikzelf
Form1->Caption = "Welkom Richel!";
ButtonSuperGeheim->Visible = true;
}
else
{
//Een ander familielid
Form1->Caption = "Welkom!";
ButtonFamilieOnly->Visible = true;
}
}
else
{
//Geen familielid
Form1->Caption = "Haha! Jij komt niet verder!";
}
Merk het volgende op:
* Tussen de accolades van een if-statement springt de code
naar rechts. Dit is om de leesbaarheid te vergroten.
* De Property Visible heeft in de Object Inspector alleen
de mogelijke waarden 'true' en 'false'. De Code Editor
gebruikt een bold font voor deze woorden omdat dit
officiele C++ sleutelwoorden zijn. Een waarde als
bijvoorbeeld 'clLime' is geen C++ sleutelwoord.
281.15. Compile fouten
Bij het programmeren worden er soms typefouten gemaakt,
waardoor de computer 'het niet meer snapt'. De mate hoe
duidelijk de foutmelding is, hangt af van de fout.
29De compiler (datgeen wat de foutmelding vind) heeft ALTIJD
GELIJK. Er is altijd een logische reden waarom deze zijn
werk niet kan doen. Leer de feedback van de compiler
waarderen en herkennen.

![Andrei Alexandrescu](AndreiAlexandrescu.png)

```
Geef de voorkeur aan compile-time fouten boven
run-time fouten. Oftewel: wees blij dat je
compiler je fout ontdekt, inplaats van dat jij
die moet gaan zoeken.
```

Soms geeft de compiler een waarschuwing. Zorg dat deze
waarschuwing verdwijnt, want waarschijnlijk heeft de
compiler een typefout van je ontdekt.

![Herb Sutter](HerbSutter.png)
```
Compileer schoon, dus zonder waarschuwingen op
het hoogste warning level.
```

Er is een uitzondering: als het geheugen van de computer 'in
de war is' (programmeurs veroorzaken dit vaker dan
gebruikers). Save het programma, 'File | Close All', 'File |
Open Project' en probeer opnieuw. Sluit anders Kylix een
keer af. In het ergste geval: herstart de computer. Is de
fout nog steeds aanwezig, dan heeft de compiler echt gelijk.


![Andrew Koenig](AndrewKoenig.png)
```
Zit je te lang naar een fout te staren, vraag dan
iemand om een frisse blik of neem een pauze.
```

301.16. Linker errors

Als je Kylix een Event aan laat maken, dan moet je Kylix
deze ook zelf op laten ruimen. Als je de tekst in een Event
weghaalt, dan verwijdert Kylix de Event.
Verwijder je met de hand een Event, dan krijg je
onderstaande foutmelding (met een OnClick Event van
Button1):
[Linker Error] Unresolved external '__fastcall
TForm1::Button1Click(System::TObject *)' referenced from
D:\PROGRAM FILES\BORLAND\CBUILDER6\UNIT1.OBJ
Ga naar 'Unit1.h' met behulp van CTRL-F6 of op het tabblad
onderaan de Text Editor te klikken. Zoek naar de genoemde
regel, in dit geval 'void __fastcall Button1Click(TObject
*Sender);' en haal deze weg.
311.17. Een echte applicatie
Nu weten we genoeg om met wat creativiteit een echte
applicatie te bouwen!
Enkele tips:
* Een Timer is een Component die een OnTimer Event heeft.
Deze OnTimer Event gaat elke ingestelde tijd (zelf
uitzoeken!) af. Nuttig voor animaties.
* De Property Tag is handig om getallen in op te slaan,
want deze wordt nergens voor gebruikt. Tag is hier zelfs
voor bedoeld!
* Kom je een 'opslagplaats' te kort, maak dan bijvoorbeeld
een extra Label aan. Dan kun je dit Label eventueel
onzichtbaar maken.
Enkele applicaties die nu mogelijk zijn:
* Een plaatje laten stuiteren, zie eventueel Appendix A
voor een voorbeeld.
* Een kluiscombinatieslot programma
* Memory
* Drie op een rij


## Volgende week
Volgende week leren we hoe we getallen naar woorden kunnen
converteren en vice versa. Ook leren we hoe deze data typen
officieel heten. Ook leren we het switch en while statement
en een manier om onze eigen 'Events' te maken.