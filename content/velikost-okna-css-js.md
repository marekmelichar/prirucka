# Velikost okna prohlížeče v CSS a JavaScriptu: min-width, innerWidth, clientWidth

Na rozdíl od [rozlišení displeje](rozliseni-displeje.md) poskytuje velikost okna pro [responzivní design](https://www.vzhurudolu.cz/responzivni-design) webu velmi zajímavé informace.

Kromě velikosti okna můžeme také mluvit o velikosti [viewportu](viewport-mobily.md). A protože existují minimálně dva různé viewporty – vizuální a layoutový – prohlížeče vracejí v různých vlastnostech různé hodnoty.

<!-- AdSnippet -->

Podívejme se, jak vše zjišťovat v [JavaScriptu](#JS) a [CSS](#CSS).

## JavaScript {#JS}

Prostřednictvím JavaScriptu se nabízejí dvě možnosti. Vybíráme v zásadě podle toho, zda chceme připočítávat rozměry lišty pro rolování stránky.

### Velikost okna s posuvníkem: innerWidth a innerHeight {#JS-innerWidth}

Vrací šířku a výšku okna v CSS pixelech včetně rolovátka (posuvníku nebo „scrollbaru“), pokud je přítomné. 

```js
window.innerWidth
window.innerHeight
```

Kromě okna (`window`) je možné vlastnosti aplikovat i na další podobné objekty: rámy (`frame`) nebo skupinu rámů (`frameset`).

Pokud bychom se bavili [o viewportech](viewport-mobily.md), těmito vlastnostmi z prohlížeče vytáhneme rozměry *vizuálního* viewportu.

V Internet Exploreru to funguje od verze 9, jinak ve všech relevantních prohlížečích. Více informací je [na MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/innerWidth).


### Velikost dokumentu bez posuvníku: clientWidth a clientHeight {#JS-clientWidth}

<!-- AdSnippet -->

Vrací šířku a výšku prvku v CSS pixelech *bez rozměru* rolovátka („scrollbaru“), pokud je přítomné. 

```js
document.documentElement.clientWidth
document.documentElement.clientHeight
```

Kromě dokumentu je možné vlastnost aplikovat na jakýkoliv jiný HTML prvek, který má layout alespoň typu inline.

Pokud bude řeč [o viewportech](viewport-mobily.md), vlastnostmi `clientWidth` a `clientHeight` z prohlížeče vytáhneme rozměry *layoutového* viewportu. Raději připomenu, že pokud na mobilních zařízeních zapomeneme [na meta značku pro viewport](viewport-meta.md), vrátí nám rozměry výchozího viewportu.

Funguje to ve všech prohlížečích. Více informací je [na MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/clientWidth).


### Posuvník, iOS a vyzkoušení {#rozdily-vyzkouseni}

Většina dnešních operačních systémů „scrollbary“ na stránce schovává. Hodnoty `innerWidth` a `clientWidth` aplikované na okno nebo dokument budou díky tomu shodné. 

Jednou z podstatných výjimek jsou desktopové Windows, které posuvníky zobrazují a do `clientWidth` pak nepočítají.

Dalším viditelným odlišením je chování prohlížečů na iOS: Pokud je stránka díky přetečení textu širší než viditelný viewport, Safari počítá `clientWidth` pro celý dokument. Chrome na Androidu naproti tomu v obě hodnoty ponechává stejné.

Rozdíly mezi `innerWidth` a `clientWidth` si můžete vyzkoušet také na mém CodePenu: [cdpn.io/e/rrXNWO](https://codepen.io/machal/pen/rrXNWO/).

<iframe height='300' scrolling='no' title='JavaScript: innerWidth vs. clientWidth' src='//codepen.io/machal/embed/rrXNWO/?height=300&theme-id=502&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/machal/pen/rrXNWO/'>JavaScript: innerWidth vs. clientWidth</a> by Martin Michálek (<a href='https://codepen.io/machal'>@machal</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe> 

Asi už jste pochopili, že v dnešním vývoji webů jsou vlastnosti `innerWidth` a `innerHeight` výhodnější, protože na všech platformách dostanete shodné vypočtená čísla.


## CSS {#CSS}

V CSS máme [Media Queries](css3-media-queries.md), kterými se na šířku nebo výšku ptáme například takto:

```css
/* Minimální šířka */
@media only screen and (min-width: 30em) { … }
/* Maximální výška */
@media only screen and (max-height: 10em) { … }
```

Tyhle hodnoty se v CSS počítají jako velikost viewportu, tedy včetně posuvníků.

<!-- AdSnippet -->









