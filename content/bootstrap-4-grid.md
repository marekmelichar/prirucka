# Detailně: layout pomocí Bootstrapu 4

Pojďme se do hloubky podívat na nový systém pro tvorbu rozvržení stránky v chystané verzi Bootstrapu.

Ano, Bootstrap 4 je stále v alfa verzi. Nicméně, změny grid systému [chystané do první bety](https://github.com/twbs/bootstrap/issues/21568) jsou jen malinké, takže si troufnu napsat, že tahle stránka zůstane beze změn. Ve čtyřce je možné stáhnout CSS soubor s gridem samostatně, což je další plus. 

Rychlá navigace po stránce: [kontejner](#container), [řádka](#row), [sloupec](#col), [sloupec do mřížky](#col-mrizka), [responzivní sloupec](#col-breakpoint), [posuny](#offset), [push a pull](#push-pull), [změna pořadí](#poradi) a [zarovnávání](#zarovnavani).


## Tvorba layoutu s Bootstrap gridem

Základní struktura rozvržení je stále složená z kontejneru (třída `.container`), řádky (`.row`) a sloupce layoutu (`.col`):

```html
<div class="container">
  <div class="row">
    <div class="col"> <!-- Sloupec rozvržení --> </div>
    <div class="col"> <!-- Sloupec rozvržení --> </div>
  </div>
</div>
```


## Kontejner rozvržení {#container}

Kontejner je obal pro váš layout. Bootstrap má dva typy obalů:

- `.container` je kontejner fixní šířky: má stupně omezené maximální šířkou. Jeho maximální šířky jsou 540px na „small“ šířkách okna, 720px („medium“) 960px („large“) a 1140px („extra large“). 
- `.container-fluid` je pružný, takže se roztahuje do plné šířky okna prohlížeče. Ten asi budete využívat méně často.

Kontejnerů můžete mít na stránce samozřejmě víc. V ukázce je porovnání pružného i fixního kontejneru: [cdpn.io/e/RpYqwK](http://codepen.io/machal/pen/RpYqwK?editors=1000).


## Řádek rozvržení {#row}

Řádky jsou vodorovná seskupení sloupců rozvržení. Na třídu `.row` nesmíte zapomenout, má totiž dvě funkce:

1. Spuštění layoutu. `.row` je [flex kontejner](css3-flexbox-kontejner.md). 
2. Zarovnávání layoutu. Má totiž nastavený záporný vnější okraj.

Při používání Bootstrapu 3 se na `.row` často zapomínalo. Ve čtyřce už bez řádky není možné udělat layout. To je docela hezká tabletka proti zapomnětlivosti. 

Do ukázky se podívejte, co se stane, když řádek omylem vynecháte: [cdpn.io/e/VpGVKm](http://codepen.io/machal/pen/VpGVKm?editors=1000).


## Sloupec: `.col` {#col}

Sloupec je základní stavební jednotka layoutů v Bootstrapu. Nově je ve verzi 4 možné zapsat sloupec jednoduše pomocí prvku s třídou `.col` bez přípony. 

```html
<div class="container">
  <div class="row">
    <div class="col"> <!-- Sloupec rozvržení --> </div>
    <div class="col"> <!-- Sloupec rozvržení --> </div>
  </div>
</div>
```

`.col` má nastaveno `flex-grow: 1`, takže sloupečky budou stejně široké. Viz [vlastnosti flex položky](css3-flexbox-polozky.md). To je prima.

Jen pozor, layout neuvidíte na menších velikostech okna. Flexbox vlastnosti v `.col` jsou nastavené tak, aby zohledňovaly obsah okna. Zažijete to i v ukázce, když si okno zmenšíte pod 260 pixelů: [cdpn.io/e/ZeMmJg](http://codepen.io/machal/pen/ZeMmJg?editors=1000).


## Sloupec zarovnaný do mřížky: `.col-{číslo}` {#col-mrizka}

Bootstrap používá pravidelnou mřížku. Zarovnání do ní je z pohledu uživatele samozřejmě výhodné, proto tyhle třídy použijete velmi často.

Výchozí mřížka je dvanáctisloupcová. K dispozici tedy máte třídy `.col-1` až `.col-12`. 

*TODO obrázek: 12sloupcová mřížka v BS*

```html
<div class="container">
  <div class="row">
    <div class="col-4"> <!-- 1/3 šířky --> </div>
    <div class="col-8"> <!-- 2/3 šířky --> </div>
  </div>
</div>
```

Jistě, že můžete kombinovat mřížku se sloupečky bez přípony:

```html
<div class="container">
  <div class="row">
    <div class="col"> <!-- 1/4 šířky --> </div>  
    <div class="col-6"> <!-- 1/2 šířky --> </div>  
    <div class="col"> <!-- 1/4 šířky --> </div>
  </div>
</div>
```

`.col` třídy se pak díky `flex-grow: 1` dělí rovným dílem o prostor, který zůstává po „mřížkových“ sloupečcích. Opět se tady ale musíte smířit s neposlušností `.col` tříd, které poslouchají pnutí obsahu a ne vždy vám udělají layout tak, jak si ho představujete. [cdpn.io/e/BWOGvq](http://codepen.io/machal/pen/BWOGvq?editors=1000).

[Pokročilým použitím s preprocesorem Sass](https://v4-alpha.getbootstrap.com/layout/grid/#customizing-the-grid) je samozřejmě možné výchozí počet sloupců zmenit. Stačí přenastavit proměnnou `$grid-columns`.


## Sloupec responzivní: `.col-{breakpoint}` {#col-breakpoint}

Abychom mohli udělat různé layouty na různě velkých šířkách okna, nemůžeme žít bez responzivních přípon:

| Body zlomu | Extra small  |  Small  | Medium | Large | Extra large |
| -----------| ------------ |  -----  | ------ | ----- | ----------- |
| Šířka okna | <576px | ≥576px | ≥768px | ≥992px | ≥1200px |
| Třída      | `.col-` | `.col-sm-` |  `.col-md-` |  `.col-lg-` |  `.col-xl-` |

Třídy platí vždy od aktuálně platného bodu zlomu výše. `.col-sm` pak bude například platit od oken šířky 576 pixelů a výše.


```html
<div class="container">
  <div class="row">
  <div class="col-sm-4"> 
    <!-- třetina od „sm“ výše --> 
  </div>  
  <div class="col-sm-8"> 
    <!-- dvě třetiny od „sm“ výše --> 
  </div>
  </div>
</div>
```

Třídy je samozřejmě možné úplně v pohodě kombinovat a dělat různé layouty pro různá rozlišení:

```html
<div class="container">
  <div class="row">
    <div class="col-6 col-sm-4"> 
      <!-- polovina na „xs“, třetina od „sm“ výše --> 
    </div>  
    <div class="col-6 col-sm-8"> 
      <!-- polovina na „xs“, dvě třetiny od „sm“ výše --> 
    </div>
  </div>
</div>
```

Nejlépe to všechno uvidíte v mé další ukázce: [cdpn.io/e/zZJyGN](http://codepen.io/machal/pen/zZJyGN?editors=1000)


## Posuny: `.offset-{breakpoint}` {#offset}

Sloupečky můžete posunovat směrem doleva přidáním vnějšího okraje třídami z rodiny posunů. Tady je třeba sloupec třetinové délky `.col-md-4`, který posouváme o třetinu zleva `offset-md-4`. 

```html
<div class="container">
  <div class="row">
    <div class="col-md-4 offset-md-4"> 
      <!-- posunutý obsah --> 
    </div>  
  </div>
</div>
```

Ve výsledku bude tedy centrovaný. [cdpn.io/e/jBvXmP](http://codepen.io/machal/pen/jBvXmP?editors=1000)


## Push a pull {#push-pull}

Třída `.push-` funguje podobně jako offsety. Prostě v daném bodu zlomu posune prvek o daný počet sloupečků mřížky doprava. `.pull-` dělá pravý opak – posouvá doleva.

Jde to hezky využít pro změnu pořadí prvků:

```html
<div class="container">
  <div class="row">
    <div class="col-md-9 push-md-3"><!-- 1. --></div>  
    <div class="col-md-3 pull-md-9"><!-- 2. --></div>      
  </div>
</div>
```

V příkladu se díky tomu na `md` breakpointu, tedy od šířky okna 768 pixelů, oba sloupce prohodí. `1.` je v kódu první, ale v layoutu bude až na druhém místě. [cdpn.io/e/xqamPp](http://codepen.io/machal/pen/xqamPp?editors=1000)


## Změna pořadí {#poradi}

Kromě výšeuvedených způsobů lze měnit pořadí sloupců layoutu pomocí 

```html
<div class="container">
  <div class="row">
    <div class="col-4"><!-- … --></div>
    <div class="col-4"><!-- … --></div>
    <div class="col-4 flex-first"><!-- V prohlížeči bude první --></div>  
  </div>
</div>
```

Vychází to z flexboxí [vlastnosti `order`](css3-flexbox-polozky.md#order). Ukázka: [cdpn.io/e/dvqrZv](http://codepen.io/machal/pen/dvqrZv?editors=1000)


## Zanořování {#zanorovani}

Velmi užitečné je, že layout můžete zanořovat. Prostě přidejte další řádku layoutu – třídu `.row`:

```html
<div class="container">
  <div class="row">
    <div class="col-9">
      <div class="row">
        <div class="col-sm-6"><!-- … --></div>  
        <div class="col-sm-6"><!-- … --></div>            
      </div>
    </div>  
  </div>
</div>
```

Každá nově vytvořená řádka layoutu se řídí šířkou rodiče. Takže se vám může stát, že zanořený layout opustí celostránkovou dvanáctisloupcovou mřížku. Nemusí vám to vadit, ale raději na to upozorňuji. [cdpn.io/e/xqamzW](http://codepen.io/machal/pen/xqamzW?editors=1000)


## Zarovnávání {#zarovnavani}

Flexbox přinesl do systému pro layout v Bootstrapu 4 kromě jiného také výborné možnosti zarovnání obsahu. Samozřejmě v obou směrech a jak pro celý layout, tak jeho jednotlivé položky.

Zarovnání na vodorovné ose:

| Zarovnání             | Celý layout (`.row`)       |
| ----------------------| ---------------------------|
| Doleva                | `.justify-content-start`   |
| Na střed              | `.justify-content-center`  |
| Doprava               | `.justify-content-end`     |
| Mezery kolem sloupců  | `.justify-content-around`  |
| Mezery mezi sloupci   | `.justify-content-between` |

Vychází to z vlastnosti flex kontejneru [`justify-content`](flexbox-kontejner.md#justify-content). Následuje příklad použití:

```html
<div class="container">
  <div class="row justify-content-between">
    <div class="col-3"> <!-- … --> </div>
    <div class="col-3"> <!-- … --> </div>
  </div>
</div>
```

Pro tenhle kód se první sloupec přilepí doleva a druhý doprava. Volný prostor se totiž rozdělí mezi jednotlivé sloupce (`.justify-content-between`). [cdnp.io/ZeMPbP](http://codepen.io/machal/pen/ZeMPbP?editors=1000)

Zarovnání na svislé ose:

| Zarovnání | Celý layout (`.row`)       |  Sloupec (`.col`)    |
| ----------| ---------------------------|----------------------| 
| Doleva    | `.align-items-start`       |  `.align-self-start` |
| Na střed  | `.align-items-center`      |  `.align-self-center`|
| Doprava   | `.align-items-end`         |  `.align-self-end`   |

Vychází to z vlastností flex kontejneru [`align-items`](flexbox-kontejner.md#align-items) a flex položky [`align-items`](flexbox-polozky.md#align-self). Příklad použití:

```html
<div class="container">
  <div class="row align-items-center">
    <div class="col-3"> <!-- … --> </div>
    <div class="col-3"> <!-- … --> </div>
    <div class="col-3"> <!-- … --> </div>
    <div class="col-3 align-self-end"> <!-- … --> </div>
  </div>
</div>
```
Všechny sloupce layoutu jsou na svislé ose zarovnané doprostřed (`.align-items-center`). Jen tomu poslednímu jsme dopřáli výjimku. Je zarovnaný dole, ke konci svislé osy layoutu (`.align-self-end`). [cdnp.io/XMPGjv](http://codepen.io/machal/pen/XMPGjv?editors=1100)


Odkazy na závěr:

- Sada [ukázek na CodePenu](http://codepen.io/collection/XMjRJk/).
- Dokumentace gridu [na webu Bootstrapu 4](https://v4-alpha.getbootstrap.com/layout/grid/).
- Samostatný [Bootstrap 4 grid ke stažení](https://github.com/twbs/bootstrap/tree/v4-dev/dist/css).
- Naše [školení pokročilého využití Bootstrapu](http://www.vzhurudolu.cz/kurzy/bootstrap).