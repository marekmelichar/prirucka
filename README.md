# Příručka pro VzhůruDolů.cz

Texty o technikách a technologiích moderní webové kodéřiny.

## Autorství

Autorem Příručky je Martin Michálek: [vrdl.cz/martin]([http://www.vzhurudolu.cz/martin).

Opravy, bugreporty, změny jsou vítány: [github.com/machal/prirucka/issues](https://github.com/machal/prirucka/issues).

## Používáme Markdown Extra

- http://parsedown.org/extra/
- https://michelf.ca/projects/php-markdown/extra/

## Pravidla psaní

Texty zde vložené se čtou nebo mohou být čteny na různých místech:

1. V tomto veřejném repozitáři.
2. V Příručce na VzhůruDolů.cz: [vrdl.cz/prirucka/css3](http://www.vzhurudolu.cz/prirucka/css3).
3. V eboocích, nyní jen „Vzhůru do CSS3”: [vrdl.cz/ebook](http://www.vzhurudolu.cz/ebook)
4. V tištěných knihách, což je zatím jen v plánu.

Před každým zveřejněním na těchto místech prochází Markdown obsah určitými transformacemi a proto je potřeba držet se jednotného způsobu psaní. 

V prvé řadě je potřeba psát obecně ve stylu například „v době psaní tohoto textu“, nikoliv „v době psaní tohoto článku“.

### Formátování

Pro ebooky je lepší co nejjednodušší formátování, proto:

- Pro zvýrazňování slov v textu nepoužíváme tučný řez, ale kurzívu. Jedinou výjimkou jsou „nadpisy“ v `ul`/`ol` seznamech. Tučný řez jinak rezervujeme pro nadpisy.
- `ul`/`ol` seznamy nepoužíváme pro texty delší než jedna věta. V eboocích se pak rozpadají na více řádek.
- Kombinace nadpisu a podnadpisu nevypadá dobře. Stejně jako nadpis a ukázka kódu. Prostě by pod každým nadpisem měl být nějaký text a až pak teprve jiný typ obsahu.

### Odkazy

V textu odkazujeme obecně jen interně - přímo na Markdown soubory, které jsou v eboocích, externí jako celé url. Aby to v ebooku bylo jasné. Na co lze klikat a co vede ven. A taky kvůli případnému tisku odkazy ven pomocí celých url.

- **Interní** v rámci stejného ebooku - uvnitř textu:  
```markdown
Lorem ipsum [odkaz](odkaz.md) lorem ipsum.
```
- **Důležité interní i externí** - nakonci odstavce ve zkrácené verzi - odkaz ale vede na plnou, abychom šetřili přesměrování:  
```markdown
Lorem ipsum lorem ipsum:
([vrdl.cz/p/grunt](http://www.vzhurudolu.cz/prirucka/grunt)).
```
- **Méně důležité** - bez odkazu (máme Google, že…)

A pozor, zápis odkazu na konci odstavce nesmí začínat `http://` např. `[http://vrdl.cz…]`. Vždy `[vrdl.cz…]`. Jednak kvůli stručnosti a jednak kvůli možným chybám v XHTML pro ePub.

Pozor také na to, že ne vždy je čtenář online. K důležitým odkazům tedy dávat do textu shrnutí.

### Obrázky

- Zatím jen JPG nebo PNG.
- Bílé pozadí. Obsah až ke krajům.
- Ideálně bez efektů jako stíny na pozadí screenshotů z Maca.
- 16:9. Minimálně 2000 pixelů široké v 300dpi. Kvůli případnému tisku.
- Zezhora může být odsazení a barevný rámeček (ebooky). Zezdola zase odsazení a text.
- Font vždy Foro Extra Bold a Light a jeho varianty. Minimální velikost písma 40pt.
- Informace nebo jejich vazba nesmí být závislá jen na barvě. Kůli černobílým Kindle čtečkám.

Standardně vkládáme jako obrázek:

```html
![Podíl mobilů](dist/images/original/statistika-mobily.jpg)
```

Alternativně s popiskem jako `<figure>`:

```
<figure>
<img src="dist/images/original/pagespeed-insights.jpg" alt="PageSpeed Insights">
<figcaption markdown="1">    
*Google PageSpeed Insights zobrazí skóre webu, ale také rovnou návrhy na vylepšení*
</figcaption> 
</figure>
```

### Video

Ideální je vložení pomocí HTML kódu. Markdown je tady nespolehlivý:

```html
<p class="video">
Video: <a href="https://www.youtube.com/watch?v=VN8CFG-YajE">BrowserStack</a> ~ Jak testovat web ve všech prohlížečích a nemuset řešit virtuály a emulátory.
</p>
```

Pro případné přímé vložení iframe z Youtube je na webu potřeba obalit jej pomocí `.rwd-media`. Jinak se nechová responzivně k velikost okna:

```html
<div class="rwd-media">
<iframe width="560" height="315" src="https://www.youtube.com/embed/eywi0h_Y5_U" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>
</div>
```

### CodePen

Ukázky vkládáme v `<iframe>`. Doporučované vložení přes HTML není kompatibiliní s AMP.

### Tabulka

Jednodušší:

```
| Prvek      | Vzhled | Klik/touch |
|------------|:------:|:----------:|
| `<span>`   |  +     |            |
```

Pro dvoustavové značky v tabulkách používáme `+`, protože je dostupné ve všech písmech, kterými se obsah vykresluje.

Složitější tabulky ideálně jako `<figure>`:

```html
<figure>

<div class="rwd-scrollable"  markdown="1"> 
| Prvek      | Vzhled | Klik/touch | Focus | Význam | Mezerník |
|------------|:------:|:----------:|:-----:|:------:|:--------:|
| `<span>`   |  +     |      +     |       |        |          |
| `<a>`      |  +     |      +     |    +  |        |          |
| `<button>` |  +     |      +     |    +  |    +   |      +   |
</div>  

<figcaption markdown="1">    
*Tabulka: Přidáním třídy můžeme nastavit vzhled tlačítka na jakýkoliv element*
</figcaption> 

</figure>
```

Třída `rwd-scrollable` zajišťuje rolování do stran na blogu u širších tabulek.


### Podcast

Vložení opět pomocí HTML kódu. 

```html
<p class="podcast">
Podcast: <a href="https://soundcloud.com/vzhurudolu/s-robinem-pokornym-o-css-v-js" data-id="296642310">S Robinem Pokorným o CSS v JS</a>
</p>
```

### Související články

Vložení opět pomocí HTML kódu. 

```html
<div class="related" markdown="1">
- [S Robinem Pokorným o CSS v JS](/blog/link)
- [Nějaký další odkaz na článek z příručky](/prirucka/link)
</div>
```

### Ukázky kódu

Značku `<code>`, respektive její Markdown obdobu používáme jen výjimečně:

- V bloku kódu.
- Uvnitř textu. Např. „Značka `<html>` slouží…“. Možné to je uvnitř odstravců, odrážek, ale i uvnitř tabulek.


`<code>` naopak nepoužíváme:

- V nadpisech, protože jsou vyvedené tučným řezem (kód není), vypadají nehezky atd. Jediná výjimka jsou situace, kdy nadpis tvoří jen samotný kód. [Příklad](https://www.vzhurudolu.cz/prirucka/pruzna-media)
- V citacích (`blockquote` a `cite`) a `figcaption`, protože jsou vyvedené kurzívou.

HTML značky lze opsat kapitálkami („Značka HTML slouží…“). JS a CSS kód prostě uvedeme bez `<code>` tak jak je. Vyplývá z toho samozřejmě, že je lepší se kódu na takovýchto místech vyhnout.


### Zobrazení jen na webu

Prostě odstavec s třídou `.web-only`. V ebooku bude při předzpracování textu odstraněno.

```markdown
<div class="web-only" markdown="1">
Čtete referenční příručku vlastností, které je možné přiřadit položkám [flexboxu](css3-flexbox.md).
</div>
```

Totéž jen pro e-booky pomocí `.ebook-only`:

```markdown
<div class="ebook-only" markdown="1">
Čtete referenční příručku vlastností, které je možné přiřadit položkám [flexboxu](css3-flexbox.md).
</div>
```

Pozor, není možné totéž udělat inline pomocí `<span class="ebook-only" markdown="1">`. Nějak to prostě nefunguje.

### Umístění reklamy na webu

Standardně po druhém odstavci. Lze změnit jednou nebo více kotvami `<!-- AdSnippet -->` v obsahu.
