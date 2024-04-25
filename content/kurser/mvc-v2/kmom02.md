---
author:
    - mos
revision:
    "2023-04-04": "(D, mos) Genomgången inför vt23."
    "2022-04-05": "(C, mos) Nytt kmom inför mvc-v2 och vt22."
    "2021-05-26": "(B, mos) Läsresurs om semantisk versionshantering."
    "2021-04-02": "(A, mos) Första utgåvan i mvc-v1."
...
Kmom02: Objektorientering
==================================

Vi skall bygga grunderna till ett kortspel i vår webbplats för att träna på objektorientering och hur man skapar egna klasser och applikationer i ramverket Symfony.

Vi skall programmera med objektorienterade konstruktioner för att bygga ett antal klasser som samverkar. Det handlar om klasser i PHP med metoder och medlemsvariabler. Vi försöker använda både arv och komposition så vi ser skillnader och likheter mellan dessa konstruktioner. Lyckas vi även få in konstruktioner som interface och traits så är det bonus.

<small><i>(Detta är instruktionen för kursmomentet och omfattar det som skall göras inom ramen för kursmomentet. Momentet omfattar cirka **20 studietimmar** inklusive läsning, arbete med övningar och uppgifter, felsökning, problemlösning, redovisning och eftertanke. Läs igenom hela kursmomentet innan du börjar jobba. Om möjligt -- planera och prioritera var du vill lägga tiden.)</i></small>

<!-- more -->


<!--
TODO

* Uppdatera kort-uppgiften så att det blir mer ett "spel" där man visar hela kortleken, man kan blanda och sortera, visa hur många kort som är kvar i leken, vilka som är slängda och vilka som ligger på bordet. Det skall bli en webbsida där man kan testa allt via flera knappar. Poängtera även så att både arv och komposition finns inkluderade i koden som krävs.

-->



Läs & Studera  {#lasanvisningar}
---------------------------------

*(ca: 4-6 studietimmar)*

För att lösa uppgifterna och redovisningen bör du studera enligt följande.



### Föreläsning {#flas}

Titta igenom följande föreläsningar.

1. [Klasser och objekt i PHP - arv, komposition, interface och trait](./../forelasning/klasser-och-objekt-i-php-arv-komposition-interface-trait) där vi studerar konstrukturer för arv, komposition, interface och trait. Vi pratar också om hur man skall tänka när man kodar objektorienterat och vad som är god kodsed och riktlinjer när man designar och implementerar sina klasser.



### Litteratur  {#litteratur}

Läs enligt följande.

1. Jobba igenom guiden "[Kom igång med Objektorienterad programmering i PHP](guide/kom-igang-med-objektorienterad-programmering-i-php)" för att främst lära dig hur arv och komposition fungerar. Trait och interface kan du göra som överkurs. Välj själv om du enbart använder guiden som läsresurs eller om du kodar dess övningsprogram.

    * [Arv och Komposition](guide/kom-igang-med-objektorienterad-programmering-i-php/arv-och-komposition)
    * [Trait och Interface](guide/kom-igang-med-objektorienterad-programmering-i-php/trait-och-interface)

1. Komplettera med att översiktligt titta igenom referensmanualen där dessa ämnen hanteras, "[Classes and Objects](https://www.php.net/manual/en/language.oop5.php)".

    * [Object Inheritance](https://www.php.net/manual/en/language.oop5.inheritance.php)
    * [Object Interfaces](https://www.php.net/manual/en/language.oop5.interfaces.php)
    * [Traits](https://www.php.net/manual/en/language.oop5.traits.php)

1. Titta översiktligt på någon av de guider som ligger i dokumentationen för Symfony "[The Symfony Framework Best Practices](https://symfony.com/doc/current/best_practices.html)". När du tittar så bör du ha i åtanke att "best practice" ibland behöver sättas in i sammanhanget av just den webbplats man själv bygger och den kunskapsnivå man själv står på. Det kan finnas alternativa lösningar som är mer lämpliga för just din specifika applikation.

1. I dokumentet [PHP The Right Way](http://www.phptherightway.com/), finns en sektion som berör kodstil i PHP. Läs igenom den.

    * [PHP The Right Way: Code Style Guide](https://phptherightway.com/#code_style_guide)



### Git och skriva bra commits {#gitcommit}

Det kan vara en konst att skriva bra commit-meddelande så att man får en bra historik när man tittar på koden via ens commits.

* Läs artikeln "[How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/)" för att få sju gyllene regler som kan hjälpa dig till bättre commit-meddelanden.



Övningar & Uppgifter  {#ovningar_uppgifter}
-------------------------------------------

*(ca: 8-14 studietimmar)*

Jobba igenom övningar för att träna. Uppgifterna skall utföras och redovisas.



### Övningar {#ovningar}

Jobba igenom övningarna, de förbereder dig inför uppgifterna.

Spara dina filer under `me/report` och bygg vidare på den webbplatsen.

1. Jobba igenom övningen "[Kodstil med Symfony](https://github.com/dbwebb-se/mvc/tree/main/example/symfony-codestyle)" för att skriva koden på rätt sätt och få hjälp att formattera din kod.

1. Jobba genom övningen "[Write your application code in Symfony](https://github.com/dbwebb-se/mvc/tree/main/example/symfony-write-application-code)" för att träna på hur du kan skriva applikationskod i Symfony och hur du jobbar med HTML formulär och sessionen.

<!--
TODO

* JSON route som visar innehållet i sessionen?

* Visa hur man kan döda sessionen för att testa.
* Lägg till om POST/GET på json routes som uppdaterar state.
* Visa hur man visar utf-8 tecken i json

* Övningen blev lite stor, kanske dela i två delar?
* MVC-begreppet igen, fokus "modellklasser".
    * Liten kontroller
* Sökformulär

* Jobba mer med patterns? Creational patterns är nog lämpliga att lära ut.
* Fundera igenom hur man lär ut kodkvalitet och patterns så det blir ett bra flöde.
* Prata mer om MVC-mönstret, kanske föreläsningsmaterial.

-->



### Uppgifter {#uppgifter}

Följande uppgifter skall utföras och resultatet skall redovisas.


1. Lös uppgiften "[Bygg kort och kortlek i PHP och Symfony enligt MVC](uppgift/bygg-kort-och-kortlek-i-php-och-symfony-enligt-mvc)". Spara dina filer under `me/report` och bygg vidare på den webbplatsen.

<!--
TODO

* Inkludera joker?

* Generera dokumentation, phpdoc, uml
* Generera UML diagram som ett verktyg

* CSS med bilder svg för att visa kort, gör exempel.

* JSON route som visar innehållet i sessionen?
-->



Resultat & Redovisning  {#resultat_redovisning}
-----------------------------------------------

*(ca: 1-2 studietimmar)*

Läs [instruktionen om hur du skall redovisa](./../redovisa).

Se till att följande frågor besvaras i din redovisningstext.

* Förklara kort de objektorienterade konstruktionerna arv, komposition, interface och trait och hur de används i PHP.

* Berätta om din implementation från uppgiften. Hur löste du uppgiften, är du nöjd/missnöjd, vilken förbättringspotential ser du i din koden och dina klasser?

* Vilka är dina reflektioner så här långt med att jobb i Symfony med applikationskod enligt MVC?

* Vilken är din TIL för detta kmom?


<!--
* Berätta kort om din syn på kodstandarder och om det kan bidra till att erhålla snyggare kod.

* Berätta om ditt spel från uppgiften. Hur löste du uppgiften, är du nöjd/missnöjd, vilken förbättringspotential ser du i koden/spelet, var uppgiften svårt/enkelt/utmanande, håller din kod god/hög kvalitet?

* Vad är PHP FIG och finns det standarder i PHP?

* Berätta och förklara MVC med en bild.
-->

<!--stop-->





Resurser bra-att-ha {#resurser}
---------------------------------

Här anges övriga resurser som kan användas för vidare studier i det som kursmomentet omfattar.



### Om design av algoritmer {#algo}

Via följande resurser kan du fördjupa dig i metoder för problemlösning.

* Artikel "[Polya’s Problem Solving Techniques](https://math.berkeley.edu/~gmelvin/polya.pdf)" om hur man kan tänka när man löser problem.
* Artikel "[Pseudocode Standard](http://users.csc.calpoly.edu/~jdalbey/SWE/pdl_std.html)" om exempel på hur man skriver pseudokod.

Wikipedia har artiklar om följande.

* [Top-down and bottom-up design](https://en.wikipedia.org/wiki/Top-down_and_bottom-up_design)
* [Flowchart](https://en.wikipedia.org/wiki/Flowchart)
* [Pseudocode](https://en.wikipedia.org/wiki/Pseudocode)

Verktyg för att rita flödesdiagram.

* [App.diagrams.net](https://app.diagrams.net/) är ett online ritverktyg där du kan rita flödesscheman utan att installera en applikation.

* [Dia Diagram Editor](http://dia-installer.de/) är en desktopapplikation som kan installeras på din dator. Det är gratis, öppen källkod och plattform.

    * Så här kan [ett flödesschema se ut i Dia](http://dia-installer.de/shapes/Flowchart/index.html.en).



### Standardisering och PHP-FIG {#phpfig}

PHP-FIG är ett standardiseringsorgan för att skapa standarder för PHP och moduler för PHP-baserade ramverk.

I detta kursmoment berör vi moduler som har implementerat följande standarder.

* [PSR-7 HTTP Message Interface](https://www.php-fig.org/psr/psr-7)
* [PSR-15 HTTP Handlers](https://www.php-fig.org/psr/psr-15)
* [PSR-17 HTTP Factories](https://www.php-fig.org/psr/psr-17)



### Router till ramverket {#router}

Vi använder en modul för routern [FastRoute - Fast request router for PHP](https://github.com/nikic/FastRoute).

Det finns en bloggartikel som förklarar hur routern är implementerad, "[Fast request routing using regular expressions](https://www.npopov.com/2014/02/18/Fast-request-routing-using-regular-expressions.html)".



### Request och Response till ramverket {#reqresp}

Vi använder en modul för att hantera response-objektet, "[PSR-7 implementation](https://github.com/Nyholm/psr7)". I den modulen finns även stöd för att hantera ett request-objekt och att skapa länkar.

För att skicka tillbaka response-objektet använder vi en emitter via modulen "[laminas-httphandlerrunner](https://github.com/laminas/laminas-httphandlerrunner)".



### Controller i ramverk {#controller}

Hur controllers implementeras och konfigureras i ramverk kan skilja åt i detaljer men grundprincipen med en controller-klass är densamma.

Här är ett par olika implementationer i PHP ramverk.

* [Symfony Controller](https://symfony.com/doc/current/controller.html)
* [Laravel Controller](https://laravel.com/docs/8.x/controllers)
* [Yii Controller](https://www.yiiframework.com/doc/guide/2.0/en/structure-controllers)
* [Phalcon Controller](https://docs.phalcon.io/4.0/nl-nl/controllers)



<!--
### Model, View, Controller (MVC) {#mvc}

MVC pattern
-->



### Git Workflow {#gitflow}

Att jobba med branches när man utvecklar sin kod kan göra det enklare att jobba många i samma repo och även när man är ensam kan det underlätta att hålla ordning och reda samt att man alltid har fungerande kod i sin mainbranch.

Här kan du läsa om ett par alternativa sätt att jobba med branches för ny kod.

* "[Introduction to GitLab Flow](https://docs.gitlab.com/ee/topics/gitlab_flow.html)"
* "[Understanding the GitHub flow](https://guides.github.com/introduction/flow/)"
* "[Git Feature Branch Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow)"
* "[Gitflow Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow)"



### Semantisk versionshantering {#version}

I dokumentet om "[Semantisk versionshantering 2.0.0](https://semver.org/lang/sv/)" kan man läsa hur man kan tänka när man sätter en viss version med ett versionsnummer på din kod. Dokumentet visar och ger en innebörd till vad de olika siffrorna betyder i ett sammanhang.



<!--
### Modellering och UML {#uml}

När man pratar om objektorienterad programmering så underlättar det om man har en viss bas i objektorienterad modellering. Därför kan du läsa kort om UML, "Unified Modelling Language". En bra plats att starta är någon av följande:
    * Andreas artikel "[Vad är UML?](kunskap/vad-ar-uml)" som är en del av kursen oopython.
    * [Wikipedia om UML](http://en.wikipedia.org/wiki/Unified_Modeling_Language).
-->
