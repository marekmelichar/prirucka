# HTML prototypování

Když řekneme „prototyp“ dejme tomu v hospodě – a nebude přitom  zrovna plná webařů – asi si ostatní u stolu představí testovací model nějakého výrobku. 

Prototyp je obvykle definován jako *raný* vzorek, který byl vytvořen pro *otestování* myšlenkového konceptu nebo pracovního procesu během práce na produktu. Na výsledek testu se buď naváže v reálné výrobě nebo se z něj poučíme a zkusíme to jinak.

Každý dobrý řemeslník věci nejprve promýšlí a pak teprve vyrábí. Samotná výroba ale bývá v některých oborech velmi drahá. Přísloví „třikrát měř, jednou řež“ platí i u webů.

Proto třeba výrobci automobilů, ale dnes právě i webů, sahají k nějaké formě zkušebních modelů. Prototypů. Přísloví si proto upravme: 

## Dvakrát měř, jednou to zkus na prototypu a pak teprve řež

Díky prototypu si můžeme naživo „osahat“ věci, které nám na „papíře“ dávaly smysl. V našem případě hlavně otestovat složité nebo inovativní prvky uživatelského rozhraní. Nebo zkusit si výrobní postupy, které běžně neděláte. 

Prototypování je učení na produktu, který je co nejpodobnější tomu cílovému. Způsobů jak testovat vymyšlené je ale ve webdesignu hodně. Já tady budu hájit svou oblíbenou cestu – prototypování přímo v HTML, CSS a Javascriptu.

## Co je to HTML prototyp a jak se liší třeba od Axure?

Exporty do prohlížečové verze dnes nabízí leckteré „klikací“ nástroje – například Axure RP. Exporty jsou ovšem limitované tím, co zvládá klikací rozhraní. Plnohodnotné HTML, CSS a Javascript nabídnou vždy výrazně větší možnosti vyjádření. Ale mají i jiné výhody, za chvíli se k nim dostaneme.

Nicméně – Axure RP považuji za nástroj vhodnější pro návrh webového designu nikoliv grafiky než třeba Photoshop, který je graficky zaměřený. Kromě snadnější práce pro designéra také umožňuje testovat interakce a další věci. V mnoha týmech mají podobné nástroje nezastupitelnou roli. S HTML prototypováním se nevylučuje a může hezky doplňovat. [axure.com](https://www.axure.com/)

HTML prototypy, o kterých tady mluvím, jsou prostě plnohodnotné webové stránky vytvořené technologiemi, které jsou v dnešních prohlížečích po ruce. Jen jsou cíleně zjednodušené – ořezané o některé atributy, které by finální stránka mít měla a prototyp nemusí.

![](dist/images/original/html-prototypovani-1.png)

*Obrázek: Jeden z raných HTML prototypů VašeČočky.cz a finální stránka webu.*

## HTML prototypy mají své výhody

Jsou totiž:

* **Brzy v prohlížeči**  
Vzpomeňte na slovo „raný“ v definici prototypu. Máme problém složitý k vymýšlení na papíře nebo v Photoshopu? Pak co nejdříve do reálného prostředí s tím – do prohlížeče! Výrobci aut také s testem na silnicích nečekají až sjedou první hotová auta z výrobních linek.
* **Plnohodnotné**  
Prototypy tvořené webovými technologiemi jsou ze stejného těsta jako hotové weby. Je tedy možné dosáhnout až absolutní míry věrnosti s konečným produktem.
* **Znovupoužitelné**  
Výstupy z jiných prototypovacích nástrojů po skončení práce zahazujeme. V případě HTML prototypů na ně mohou vývojáři i designéři navázat. Vždyť je to pořád jedno těsto.
* **Snadno udržovatelné**  
Snadné provádění globálních změn, zbytečné neopakování se… Parametry efektivní práce, kterých je v běžných prototypovacích nástrojích složitější dosáhnout. Co se týká efektivity práce, je webový kód bezkonkureční. 

Nebudu vás ale tahat za nos, HTML prototypy mají samozřejmě také své nevýhody. Ještě chvíli vydržte, povím vám něco o svých zkušenostech s nimi. Nejdříve si ale prototypy pojďme zasadit do kontextu dalších webařských modelovacích nástrojů.

## Prototyp versus drátěný model a maketa

Nástroje, používané pro demonstraci a odzkoušení nějaké myšlenky použít,  můžeme rozdělit do tří skupin:

*TODO obrázek.*

### Drátěný model (wireframe)

* Je to vlastně kostra pro webový design. Ukazuje obsah, možnosti jeho rozložení a případně základní interakce. „Dráťák“ je rychle hotový, ale velmi zjednodušuje. Obvykle je to levná volba, ideální pro úvodní fáze projektů.
* Model nízké věrnosti s finálním webem. 
* Nejméně časově náročné.
* Nástroje: ruční skicování nebo programy jako UXPin nebo Balsamiq Mockups.

### Statická maketa (mockup)

* Na jednu stranu velmi detailní, jiné atributy prototypu ignorující. Typická maketa je výstup z Photoshopu, který obvykle detailně popisuje vizuální design, ale interakce nebo chování v různých rozlišeních naopak zcela nedostatečně.
* Model střední až vysoké věrnosti. 
* Časově středně a hodně náročné.
* Nástroje: Photoshop, Sketch.

### Interaktivní prototyp

* Důraz na interaktivitu a tedy například možnost otestovat uživatelské scénáře. Hezky dokáže otestovat i typické frontendové problémy. Vizuální design ale obvykle moc neřeší. 
* Opět střední až vysoká věrnost. 
* Časově ze všech možností nejnáročněší.
* Nástroje: Naše HTML prototypování nebo zčásti Axure RP. 

Zjednodušeně řečeno: HTML prototypování nabízí nejvyšší možnou míru věrnosti, ale za cenu nejsložitější práce.


## Výhody pro designéry

Designéři uživatelského rozhraní a weboví grafici myslím dost ocení možnost na prototypech testovat následující:

1. **Responzivnost**  
Častý problém maket z grafických programů: návrh je statický a UI komponentu není možné otestovat na všech rozlišeních. Rychlý HTML prototyp konkrétní komponenty to řeší.
2. **Testování na uživatelích**  
Uživatelsky můžete testovat klidně i papírové skici nebo výstupy z Axure a Photoshopu. Jen HTML prototypy vám ale nabízejí volitelnou míru věrnosti konkrétního instrumentu uživatelského rozhraní.
3. **Animace**  
Nástroje pro tvorbu maket jako Photoshop tady nepomohou. Klikací animační nástroje s výstupem do plnohodnotných CSS animací zatím nemáme. I tohle si můžete v rychlosti otestovat s pomocí svého kodéra.
4. **Pokročilé interakce**  
Nemyslím tím jen „kliknu a přejdu na jinou stránku“. V HTML se skvěle prototypují třeba ajaxové interakce, klidně spojené s animací.
5. **Pokročilé SVG vlastnosti**  
Výplně, výřezy, filtry, efekty… tady opravdu nevím, jak jinak než přímo v HTML si to zkusit. [vrdl.cz/prirucka/svg-inspirace](http://www.vzhurudolu.cz/prirucka/svg-inspirace)

Ohromě ale z HTML prototypování mohou těžit vývojáři, kteří mají na starost zpracování výstupů designérů. Cílem totiž není jen dostat produkt co nejdříve do prohlížeče, ale také vtáhnout vývojáře do dřívějších fází procesu. Tak, aby si zavčasu otestovali časté problémy, které na drátěném modelu ani maketě prostě vidět nejsou.

## Frontendisti ošetří své rizikové faktory

Každá správná frontendistka, každý správný frontendista mají prototypování rádi. I pro ně jsem našel pět otázek, na které jim HTML prototyp dokáže dát odpověď. Seznamu, který následuje, občas říkám „Pět obvyklých podezřelých na podkladech od designérů“. 

### 1. Rychlost načítání  
Komponenta vypadá hezky, ale – nezpomalí zásadně načítání stránky? Karusel na úvodní stránku do drátěného modelu šoupnete raz dva, že? Jen až během prototypování nebo nedejbože finální implementaci zjistíte, že se díky němu úvodní stránka načítá děsně pomalu. To nechcete.


### 2. Výkon v prohlížeči  
Nebude se stránka při posouvání „trhat“? Je myšleno i na výkon při práci s načtenou stránkou? To, že klient je nadšený z krásných paralax efektů, které chce na webu pouštět zároveň s videem na pozadí, neznamená, že jeho pocity budou sdílet návštěvníci webu. Prototypem zjistíte, jak je jeho myšlenka problematická co do výkonu v prohlížeči.

### 3. Přístupnost  
Jaký dopad bude komponenta mít na přístupnost zrakově postiženými? I karusel může být přístupný. Ale je přístupný zrovna ten váš? Dobré si to otestovat.

### 4. Zobrazování v exotických prohlížečích  
Jak se bude zobrazovat ve starších a exotičtějších prohlížečích? Půjde snadno vymyslet náhradní řešení pro ně? Úžasné 3D WebGL efekty, které váš grafik někde viděl, jsou fajn. Jak to ale poběží v Exploreru 8, jehož uživatelé jsou třeba pro váš projekt ještě stále zásadní? Nepoběží. Jak bude vypadat náhradní řešení? Opět zjistíte a grafikovi demonstrujete rychlým prototypem.

### 5. Udržovatelnost  
Nezkomplikuje řešení celkovou udržovatelnost projektu? Shlédl se váš designér v Bootstrapu, ale vy zjišťujete, že z něj využijete jen tlačítka a formuláře? Pokud vaše argumenty nepadají na úrodnou půdu, udělejte rychlý prototyp, na které komplikaci se špatnou udržitelností složité knihovny v rámci vašeho projektu ukážete. 

Všimněte si, že kromě čtvrtého a pátého bodu, které jsou ryze technické, spadají všechny ostatní do kompetencí dobrého webového designéra.  Takže, milí designéři, nejde jen o „nějaké problémy ve vzdálené části vývojářského týmu a pro lidi, o nichž nic nevíme“, abych parafrázoval Chamberlainův výrok o Československu po Mnichově.

Klikací prototypovací nástroje jako Axure nám pachatele mezi obvyklými podezřelými najít nepomohou. Kód nemáme od začátku pod kontrolou, takže si na nich rizikové faktory neotestujeme. Výstupy z naklikaných prototypů navíc v produkční fázi projektu použít nemůžeme.

## Nevýhody HTML prototypů: časově náročné a vyžadují zkušenější tým

Celou dobu tady o plnohodnotných prototypech básním, takže si teď pojďme říci, v čem tkví jejich problémy:

* **Jsou časově náročné a tedy dražší.**  
Nehodí se tedy pro použití kdekoliv a kdykoliv. Rozumný kompromis budu hledat v dalším textu.
* **Vyžadují určitou zkušenost na straně designéra i frontendisty.**  
Hlavně u nezkušených frontendistů se může protypování zbytečně prodražit. Pokud v týmu máte hlavně juniory, dávejte dvakrát pozor, zda se nezaměřují spíše na nástroje nebo věci, které jste na prototypech testovat nechtěli.
* **Vyžadují intenzivní spolupráci designérů a frontendistů.**  
Prostě si spolu musíte sednout a pracovat na prototypech dohromady.
* **Těžší rozhodování u znovupoužitelnosti.**  
Moje vlastní zkušenost. U VašeČočky.cz jsem tak moc stál o znovupoužitelnost psaného kódu, že jsem u některých částí prototypovaného uživatelského rozhraní dosahoval závratně hlemýždího tempa. Někdy je prostě kvůli rychlosti lepší prototypový kód zahodit a pro finální web napsat znovu. Ještě se k tomu vrátím.

## Kdy HTML prototypování použít a kdy spíše ne? Nemusíte prototypovat celé weby

Ano, HTML prototypování je časově nejnáročnější varianta modelování webu. Na druhou stranu umožňuje otestovat všechny rizikové faktory na straně designu, frontendu i vývoje obecně. Kód je možné připravovat už v kvalitě, využitelné pro produkční nasazení.

Na svých projektech HTML prototypování používám kdykoliv je to možné. Mluvím do designu rozhraní i frontend kódování a jak už jsem ukázal, pro obě části mé profesní osobnosti jsou prototypy výborné. Obvykle jsem najímán na projekty, kde je očekávaná špičková kvalita a nepočítá se každá hodina stráveného času. 

Pro HTML prototypování se ale také rozhodují často týmy pracující dlouhodobě na jednom produktu. Tam se vyplatí. V případě agenturní práce pro mnoho klientů doporučuji HTML prototypy dělat tam, kde zkoušíte nové věci nebo je rizikovost návrhu vysoká. 

Vezměme teď dvě části rozhraní už hotového webu VašeČočky. U jedné bych HTML prototyp dělal znovu, u druhé si  myslím, že by stačilo připravit drátěný model. 

![](dist/images/original/html-prototypovani-2.png)

*Obrázek: dvě komponenty uživatelského rozhraní. První patička je napohled složitější, ale detailní HTML prototypování je nutné hlavně u druhé.*

* **Patička**  
Navigační patička společná pro všechny veřejné stránky zase tak složitá není. Je to obyčejná komponenta, kterou by šlo zkušenějším designérem navrhnout pro všechna rozlišení v drátěném modelu a po konzultaci s frontendistou ošetřit i jeho možné kritické faktory. Tady bych propříště za HTML prototyp klidně ušetřil.
* **Výběr parametrů čoček**  
Fakt složitá komponenta rozhraní. Může mít mnoho variant, různě se zobrazující na různých rozlišeních obrazovky a na různých místech webu – v detailu produktu nebo v košíku. Navíc v mnoha jazykových verzích! Jasný kandidát pro otestování přímo v HTML v co nejvyšší míře věrnosti.

Z této mé zkušenosti je také hezky vidět, že obvykle není nutné v HTML prototypovat všechny stránky celého webu. Prostě si vyberte jen ty části, které svou složitostí vybočují a spadají do pěti designérských nebo vývojářských možných rizik.

Teď jedna odbočka. Podíváme se do blízké budoucnosti návrhu uživatelského rozhraní. Na atomické systémy designu, kde weby netvoříme po stránkách, ale po jednotlivých komponentách. 

## Atomický design má prototypování v krvi

Ještě poznámka k progresivním směrům návrhu uživatelského rozhraní. Systémy atomických designů jsou tvořeny skládáním menších komponent do větších. Návrh a testování se z velké části odehrává přímo v prohlížeči, takže z HTML prototypování dělají neoddělitelnou součást pracovního procesu. 

O systémech atomického designu jsem psal na Vzhůru dolů. [vrdl.cz/prirucka/pattern-lab](http://www.vzhurudolu.cz/prirucka/pattern-lab)

U systémů atomického designu to bez intenzivní spolupráce designéra s vývojářem nejde. A podobné to je u celého HTML prototypování.

## V jakých nástrojích dělám HTML prototypy: Bootstrap a CodePen

Prototypování je dobré dělat v nástroji, který zvládáte ovládat rychle a který vám neklade překážky. Moje nástroje vám tedy vnucovat nechci. I když…

![](dist/images/original/html-prototypovani-3.png)

*Obrázek: Bootstrap a další frontend frameworky je ideálním pomocníkem pro prototypování celých webů. CodePen používám pro rychlý nástřel menších komponent.*

### Rychlý online editor CodePen

Editor, kde dělám jednoduché a přímočaré prototypy na pár řádků kódu. Je to rovnou online, takže se to dobře sdílí nebo posílá do mobilních zařízení.


### Frontend knihovna Bootstrap

Všechny mé projekty z posledních let vznikly nejprve jako HTML prototyp postavený na Bootstrapu. Ten obsahuje dostatečně robustní sadu komponent proto, abych velmi rychle dokázal poskládat prvotní verzi webu k proklikání. S postupným iterativním vývojem webu se pak postupně jeho komponenty nahrazují komponentami navrženými na míru konkrétního projektu. 

Bootstrap podporuje stavebnicový vývoj. Zároveň dodává řadu principů (prostřednictvím proměných a mixinů), na kterých pak snadno můžeme stavět své vlastní komponenty. 

Čtěte „Jak správně navázat na typografické principy Bootstrapu?“ na Vzhůru dolů. [vrdl.cz/prirucka/bootstrap-typografie](http://www.vzhurudolu.cz/prirucka/bootstrap-typografie)

Workflow postavené na Bootstrapu má také třeba Adam Kudrna. Ve firmě VisionApps si je doplnili dalšími nástroji, postavenými na míru svých projektů. Jako příklad uvedu [bootstrap-ui.com](http://www.bootstrap-ui.com/), jejich rozšíření Bootstrapu, vylepšující vzhed a přidávájící další komponenty. Adam ostatně o HTML prototypování hezky povídal na Frontendisti.cz. [https://youtu.be/A71kFP8I_qY](https://youtu.be/A71kFP8I_qY)

Pojďme si shrnout to nejdůležitější:

* HTML prototypy umožní volit míru věrnosti a otestovat myšlenku v raných fázích projektu. 
* Ukazují jak problémy designérské, tak vývojářské.
* Pokud řešíte cokoliv neobvyklého a nemáte příliš nízký rozpočet, vyzkoušejte je.
* V týmu se nic nepokazí, když designéři poprosí vývojáře o konzultace už v raných fázích návrhu.