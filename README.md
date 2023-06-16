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

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Sufiks je `.mdt` , možete koristiti sintaksu sličnu `<+ ./coffee_plus/import.js>` za upućivanje na vanjske datoteke i generirati markdown sa sufiksom `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown prijevod neće prevoditi kodove i veze, već će keširati prevedene rečenice. Ako je prijevod izmijenjen, ali originalni tekst nije izmijenjen, njegovo ponovno izvršavanje neće prepisati izmjenu prijevoda.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Jezički fajlovi za prevođenje `yaml` generiranih web stranica.

### Uputstva za automatizaciju prevođenja dokumenata

Vidi repozitorijum [xxai-art/doc](https://github.com/xxai-art/doc)

Preporučljivo je prvo instalirati nodejs, [direnv](https://direnv.net) i [bun](https://github.com/oven-sh/bun) , a zatim pokrenuti `direnv allow` nakon ulaska u direktorij.

Kako bih izbjegao prevelika skladišta prevedena na stotine jezika, napravio sam zasebno skladište kodova za svaki jezik i stvorio organizaciju za skladištenje ovog skladišta

Postavljanje varijable okruženja `GITHUB_ACCESS_TOKEN` i zatim pokretanje [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) će automatski kreirati skladište.

Naravno, možete ga staviti i u skladište.

Referenca skripte prijevoda [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Kod skripte se tumači na sljedeći način:

[bunx](https://bun.sh/docs/cli/bunx) je zamjena za npx, koji je brži. Naravno, ako nemate instaliranu bundu, umjesto toga možete koristiti `npx` .

`bunx mdt zh` prikazuje `.mdt` u zh direktoriju kao `.md` , pogledajte 2 povezana fajla ispod

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` je osnovni kod za prevođenje (ako imate instaliran samo `nodejs` , ali `bun` i `direnv` nisu instalirani, možete pokrenuti i `npx i18n` za prevođenje).

On će analizirati [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , konfiguracija `i18n.yml` u ovom dokumentu je sljedeća:

```
en:
zh: ja ko en
```

Značenje je: kineski prijevod na japanski, korejski, engleski, engleski prijevod na sve ostale jezike. Ako želite da podržavate samo kineski i engleski, možete samo napisati `zh: en` .

Posljednji je [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , koji izdvaja sadržaj između glavnog naslova i prvog podnaslova `README.md` svakog jezika za generiranje unosa `README.md` . Kod je vrlo jednostavan, možete ga pogledati i sami.

Google API se koristi za besplatno prevođenje. Ako ne možete pristupiti Googleu, konfigurirajte i postavite proxy, kao što je:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Skripta za prevođenje će generirati keš prijevoda u `.i18n` direktoriju, provjerite ga sa `git status` i dodajte ga u spremište koda kako biste izbjegli ponovljene prijevode.
