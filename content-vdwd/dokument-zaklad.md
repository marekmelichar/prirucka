# Dokument jako základ

Dokument je základ všeho, co na webu stavíte. Ať už to berete technicky nebo designérsky.

Blogy se vizuálně od dokumentů moc nevzdalují, e-shopy už trochu více. Čistokrevné aplikace jako třeba redakční systémy, kalkulačky nebo dashboardy už docela hodně. 

Nic to ale nemění na tom, že někde dole, i pod napohled složitým rozhraním nebo komplexní javascriptovou aplikací žije strukturovaný dokument se styly, ať už v podobě vygenerované na serveru nebo až v prohlížeči. 

To, že si *můžete* zvolit variantu jednoduchého dokumentu předgenerovaného na serveru je unikátní vlastnost webu. Ta mimojiné umožňuje zachovávat vynikající zpětnou i dopřednou kompatibilitu. 

Podíváme se teď, co může filozofie „začni dokumentem“ přinést vývojářům a co designérům. 

## „Začni dokumentem“ pro vývojáře: stavění na HTML je stabilnější

Samozřejmě, některé webové aplikace je neefektivní na statickém HTML dokumentu stavět. Současný technologický stav webdesignu to také nečiní efektivním. Serverová rozšíření frontendových frameworků jako je Angular nebo React nejsou ve webových týmech moc častá a taky zatím jsou prostě příliš nová.

Velmi často je ale stavění na serveru předgenerovaném dokumentu výhodné. A to hned z několika důvodů:

### Rozšiřuje to kompatibilitu a možnosti náhradních řešení

Selže javascriptová aplikační vrstva? I ten nejexotičtější nebo prastarý prohlížeč vám stále zobrazí stylovaný HTML dokument. Jeremy Keith takto na WebExpo 2015 citoval Jake Archibalda:

> Když selže výtah, je nepoužitelný. Když ale selžou jezdící schody, stanou se z nich prostě schody. Měli bychom budovat jezdící schody, ne výtahy.

Jeremyho přednáška „Enhance!“ je dostupná online. [vrdl.in/enhance](https://www.webexpo.cz/praha2015/prednaska/enhance/)

### Je to výhodnější pro indexování vyhledávači

I přes to, že se Google v získávání informací o stránce z verze vygenerované Javascriptem stále zlepšuje, kvalitní HTML podklad je spolehlivější zdroj. Nemluvě o tom, že Seznam ke dni psaní neumí obsah generovaný Javascriptem indexovat. Podívejte se na přednášku Jana Tichého „Vyhledávače a Javascript“. [youtu.be/kU_M1elyunw](https://youtu.be/kU_M1elyunw)

### Zpřístupňuje to obsah širší cílové skupině

Přístupnost. Široká škatule, do které patří první i kompatibilita a vyhledávače, ale také usnadnění přístupu hendikepovaným uživatelům. A pozor, nejsou to jen lidé s oční vadou nebo jiným fyzickým omezením. Hendikepovaná může být i zdravá dvacetiletá studentka, které některé rozšíření v prohlížeči zablokuje zrovna váš javascriptový soubor. Tohle je web, takové věci se stávají běžně.

Web má dokument v DNA, ať se nám to líbí nebo ne. Vznikl přeci jako síť vzájemně provázaných dokumentů. Ostatně – někdy se stačí podívat hned na první řádku HTML kódu. Mluví o typu *dokumentu*. Heydon Pickering v knize „Inclusive Design Patterns“ říká:

> `<!DOCTYPE html>` slouží jako důležitá připomínka toho, že i když navrhujete interakčně složité a dynamické rozhraní, stále prostě jen vkládáte obsah do okna prohlížeče.

Mít pod aplikací statické HTML není žádná vývojářská povinnost. Všichni bychom ale měli vědět, co přesně to uživatelům přináší. Snad mi rozumíte. Pojďme se na to ještě podívat z pohledu návrhu rozhraní.


## „Začni dokumentem“ pro designéry: navrhujeme od obsahu, nikoliv od layoutu

Asi většina webů dnes vzniká v kreslícím nástroji jako je Photoshop nebo Sketch. Grafici si otevřou prázdný dokument, plochu jako ruzyňská přistávací dráha. 

Ta svádí k tomu, že první věc, kterou tam udělají je rozvržení, layout. Až pak se přes komponenty rozhraní propracují k obsahu a jeho vlastnostem. Poznáváte se? Nedivím se, je to intuitivní proces, který vám nenápadně nadiktoval nástroj, který používáte. 

Když jsem někdy před rokem 2000 dělal své první weby za peníze, zadání bylo jednoduché: vezmi tenhle tištěný katalog a převeď jej do HTML. Vzniklý web měl pevně dané rozměry a všelijak napodoboval vzhled katalogu, který jsem měl položený vedle monitoru s rozlišením 640 na 480 pixelů. Webdesign byl v té době naprosto v područí tiskového designu. 

Responzivní design je ovšem zásadní emancipační vlnou. Teď už víme, že pracujeme na novém médiu. Médiu, které nemá pevné rozměry. Proč tedy napodobovat procesy tiskařů a navrhovat nejprve layout? 

Layout má vznikat až z potřeb obsahu, vycházet z dokumentu. Pojďme to v knížce vzít právě tímto postupem. Vyladit obsah, vymyslet typografii a grafický charakter. Pak teprve navrhnout komponenty typu navigace a až nám obsah začne přetékat z Ruzyně, teprve pak jej zalomit layoutem.