<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Dio koda web stranice je otvorenog koda, dobrodošli da pomognete u optimizaciji prijevoda.

## front-end kod

* [front-end kod](https://github.com/xxai-art/web)
* [Jezički paketi za web lokaciju u cjelini](https://github.com/xxai-art/web/tree/main/i18n)
* [Jezički paketi za module za prijavu](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Višejezična dokumentacija web stranice](https://github.com/xxai-doc)

Front-end programski jezik je [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , koji dodaje neke funkcije zasnovane na kafeskript sintaksi, pogledajte [./coffee_plus.md](./coffee_plus.md) .

## Internacionalizacija web stranica i dokumenata

Nadogradite sljedeća 3 projekta

### [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

Predložak za označavanje, sa sufiksom `.mdt` , može se odnositi na vanjske datoteke sa sintaksom sličnom `<+ ./coffee_plus/import.js>` .

[@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

Markdown prijevod neće prevoditi kodove i veze, već će keširati prevedene rečenice. Ako je prijevod izmijenjen, ali originalni tekst nije izmijenjen, njegovo ponovno izvršavanje neće prepisati izmjenu prijevoda.

[@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

Jezički fajlovi za prevođenje `yaml` generiranih web stranica.
