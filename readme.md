
# Vefforritun 1, 2021: Verkefni 5, CSS #3

[Kynning í fyrirlestri](https://youtu.be/mo0OFSHH5HI).

Halda skal áfram með viðmót fyrir Vefforritunarfréttir úr [verkefni 4](https://github.com/vefforritun/vef1-2021-v4/), fréttamiðil sem færir vefforriturum mikilvægar fréttir af faginu. Nú skal setja upp grid og gera vefinn responsive.

Haldið verður áfram með verkefnið í [verkefni 6](https://github.com/vefforritun/vef1-2021-v6/) setur upp tæki og tól: Sass, Stylelint, og browser-sync. Verkefnið verður „refactorað“ til að nota þetta.

## Útlit

Fyrirmynd að útliti er í `fyrirmynd/` möppu. Skjáskot eru tekim í `1500px`, `900px`, og `320px` breiðum Firefox vafra.

### Almennt

Sama gildir og í verkefni 4:

Þar sem allt útlit skal útfæra í einni CSS skrá, skal huga að cascade og erfðum, þó er fullkomlega eðlilegt að endurtaka eigindi, en t.d. fyrir málsgreinar (`<p>`) þarf aðeins að taka fram einu sinni hvert margin þeirra er.

Gefið er „reset“ þ.a. allt `margin` og `padding` frá vafra sé sett í `0`, einnig er `box-sizing: border-box` sett fyrir öll element.

CSS skal vera án villna og **viðvarana** þegar keyrt í gegnum [CSS validator](https://jigsaw.w3.org/css-validator/).

Allar síður skulu vera villulausar ef prófaðar með HTML validator.

### Gildi og stærðir

Sömu gildi og stærðir eiga við:

* Heildar breidd efnis skal vera `1400px`, miðjað á skjánum
* Grunnletur stærð skal vera `16px` þ.a. `1rem == 16px`
* Allt bil í fyrirmynd er hálf, eitt, eða tvöfalt margfeldi af grunnletur stærð
* Gildi fyrir liti eru gefin sem breytur settar í `:root`
* Leturgerðir:
  * Fyrir meginmál: [Inter](https://fonts.google.com/specimen/Inter), Helvetica, Arial, sans-serif
  * Fyrir fyrirsagnir: [Playfair Display](https://fonts.google.com/specimen/Playfair+Display), Georgia, serif
  * Leturþyngdir (e. font weights):
    * Tengill í auglýsingu skal nota þyngd `700`
    * Aðalfyrirsögn skal nota þyngd `600`
    * Tenglar í flokkum skal nota þyngd `400`
    * Birting á dagstíma skal nota þyngd `300`
* Almennt skal aðeins nota hlutfallslegar einingar í breiddir, nema nota þarf `px` gildi til að útfæra birtingu á dagstíma icon

Setja skal upp grind með CSS grid, grind skal vera:

* `12` dálkar
* `30px`  gutter / gap
* `20px` _offset_, þegar vefur er kominn fyrir neðan `max-width` er offset sett sitthvoru megin til að efni „leggist“ ekki utan í vafraglugga

Þessar breytur eru tilteknar í `styles.css`. Gefið er `grid.css` skjal sem setur viðmiðunargrind yfir vefinn.

Vefur skal vera skalanlegur (e. responsive). Miða skal við að:

* Upp að `700px` breiðum skjá fylli allt efni út í skjá, sjá skjáskot `320px.png`.
* Upp að `1000px` breiðum skjá taki nýjustu fréttir 8 dálka en mest lesið 4 dálka, flokkar taki 6 dálka, sjá skjáskot `900px.png`.
* Yfir `1000px` breiðum skjá skuli vefur líta út eins og í verkefni 4, en efni skal passa nákvæmlega innan grindar þar sem allt nema auglýsing tekur 4 dálka, sjá skjáskot `1500px`.

### Takmarkanir

Aðeins skal nota flexbox og CSS grid til að setja upp útlit, þ.e.a.s. **aðeins** `display: flex` og `display: grid`.

Þegar texti fer að taka of mikið pláss er hægt að bæta _soft hyphens_  í efni (`&shy;`) og/eða nota `font-size: clamp(x, y, z);`.

Ekki skal nota önnur gildi fyrir `display` eða `position` eigindi _nema_ til að setja upp texta yfir mynd í auglýsingu.

Í sýnilausn er eftirfarandi notað:

* `@font-face` til að færa inn leturgerðir og tengd eigindi til að eiga við leturgerðir
  * `src`
  * `font-display: swap`
  * `font-family`
  * `font-size`
  * `font-variation-settings`
  * `line-height`
  * `text-decoration`
  * `clamp` fyrir responsive stærð
* CSS breytur, sjá gefnar breytur innan `:root` og `var()` fall
* Flexbox eigindi, t.d.
  * `align-items`
  * `flex-direction`
  * `flex`
  * `justify-content`
  * `order`
* Bakgrunnseigindi:
  * `background-color`
  * `background-image`
  * `background-position`
  * `background-repeat`
  * `background-size`
  * eða shorthand `background`
* Box model eigindi
  * `margin`
  * `border`
  * `padding`
  * `width`, með hlutfallslegum einingum
  * `height`, til að fastsetja hæðir á myndum sem síðan nota `object-fit`
  * `max-width`
* `@media (min-width: XXX)` fyrir brotpunkta
  * `object-fit`
  * `order`
  * `grid-template-rows`
  * `grid-template-columns`
  * `gap`
  * `grid-column`

## Heimasvæði

Setja skal síður upp á [heimasvæði ykkar hjá HÍ](https://uts.hi.is/node/155) undir möppu `.public_html/vefforritun/verkefni5` svo verkefnið verði aðgengilegt á `https://notendur.hi.is/<notendanafn>/vefforritun/verkefni5` þar sem `<notendnafn>` er notendanafnið þitt (t.d. `osk`).

## Mat

* 20% – Snyrtilega uppsett og gilt CSS
* 40% – Grind sett upp með CSS grid
* 40% – Vefur skalanlegur

## Sett fyrir

Verkefni sett fyrir í fyrirlestri mánudaginn 20. september 2021.

## Skil

Skila skal í Canvas í seinasta lagi fyrir lok dags þriðjudaginn 28. september 2021.

Skilaboð skulu innihalda:

* zip skjali með lausn
* slóð á verkefni, best er að setja sem athugasemd _eftir_ að búið er að skila zip skjali

Hver dagur eftir skil dregur verkefni niður um 10%, allt að 20% ef skilað fimmtudaginn 30. september 2021 en þá lokar fyrir skil.

## Einkunn

Leyfilegt er að ræða, og vinna saman að verkefni en **skrifið ykkar eigin lausn**. Ef tvær eða fleiri lausnir eru mjög líkar þarf að færa rök fyrir því, annars munu allir hlutaðeigandi hugsanlega fá 0 fyrir verkefnið.

Sett verða fyrir tíu minni verkefni þar sem átta bestu gilda 5% hvert, samtals 40% af lokaeinkunn.

Sett verða fyrir tvö hópverkefni þar sem hvort um sig gildir 10%, samtals 20% af lokaeinkunn.

## Myndir

Myndir frá [Unsplash](https://unsplash.com/):

* [Max Duzij](https://unsplash.com/@max_duz)
* [Emma Dau](https://unsplash.com/@daugirl)
* [Mika Baumeister](https://unsplash.com/@mbaumi)
* [Alex Kotliarskyi](https://unsplash.com/@frantic)
* [Dzmitry Tselabionak](https://unsplash.com/@tsellobenok)
* [LinkedIn Sales Solutions](https://unsplash.com/@linkedinsalesnavigator)
* [Kyle Hanson](https://unsplash.com/@kyledarrenhanson)
* [Mathew Schwartz](https://unsplash.com/@cadop)

> Útgáfa 0.1
