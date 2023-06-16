<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Mairekomendar nga umuna nga i-install ti nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , ken kalpasanna `direnv allow` kalpasan ti iseserrek iti direktorio ( [ti .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) ket automatiko a maipatungpal kalpasan ti iseserrek iti direktorio).

Ti kayatna a sawen ket: Panagpatarus iti Insik iti Hapones, Koreano, Ingles, Ingles a patarus iti amin a dadduma a pagsasao. No kayatmo laeng a suportaran ti Insik ken Ingles, mabalinmo laeng nga isurat `zh: en` .

## kodigo ti sango-ungto

* [kodigo ti sango-ungto](https://github.com/xxai-art/web)
* [Dagiti pakete ti pagsasao para iti pakabuklan ti site](https://github.com/xxai-art/web/tree/main/i18n)
* [Dagiti pakete ti pagsasao para kadagiti modulo ti panaglogin](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Website Multilingual a Dokumentasion](https://github.com/xxai-doc)

Ti pagsasao ti panagprograma iti sango a murdong ket [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , a manginayon kadagiti sumagmamano a tampok a naibatay iti sintaksis ti coffeescript, kitaen [ti ./coffee_plus.md](./coffee_plus.md) .

## Internasionalisasion dagiti website ken dokumento

Build on dagiti sumaganad a 3 a proyekto

* [@w5/mdt nga](https://www.npmjs.com/package/@w5/mdt)

  Ti suffix ket `.mdt` , mabalinmo nga usaren ti sintaksis a kapada ti `<+ ./coffee_plus/import.js>` tapno mangitudo kadagiti akinruar a papeles, ken mangpataud ti markdown babaen ti suffix `.md` .

* [@w5/trmd nga](https://www.npmjs.com/package/@w5/trmd)

  Ti panagipatarus ti Markdown ket saan nga agipatarus kadagiti kodigo ken silpo, ken mangi-cache kadagiti naipatarus a sentensia. No ti patarus ket nabaliwan ngem ti orihinal a teksto ket saan a nabaliwan, ti panangipatungpal manen iti daytoy ket saan a mangsukog ti pannakabalbaliw ti patarus.

* [@w5/i18n nga](https://www.npmjs.com/package/@w5/i18n)

  Dagiti file ti pagsasao para iti panagipatarus kadagiti website a pinartuat `yaml` .

### Dagiti Panangiwanwan ti Automasion ti Panagpatarus ti Dokumento

Kitaen ti pagidulinan ti kodigo [xxai-art/doc](https://github.com/xxai-art/doc)

Mairekomendar nga umuna nga i-install ti nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) , ken kalpasanna `direnv allow` kalpasan ti iseserrek iti direktorio ( [ti .envrc](https://github.com/xxai-art/doc/blob/main/.envrc) ket automatiko a maipatungpal kalpasan ti iseserrek iti direktorio).

Tapno maliklikan ti dakkel a base ti kodigo a naipatarus kadagiti ginasut a pagsasao, nangaramidak iti naisina a base ti kodigo para iti tunggal pagsasao ken nangaramidak iti organisasion a mangidulin iti base ti kodigo

Ti panangisaad ti variable ti aglawlaw `GITHUB_ACCESS_TOKEN` ken kalpasanna ti panagtaray [ti create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) ket automatiko a mangpartuat ti pagidulinan ti kodigo.

Siempre, mabalinmo met nga ikabil dayta iti code base.

Reperensia ti iskrip ti panagipatarus [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Ti kodigo ti iskrip ket naipatarus a kas ti sumaganad:

[ti bunx](https://bun.sh/docs/cli/bunx) ket kasukat ti npx, a naparpartak. Siempre, no awan ti bun installed-mo, mabalinmo nga usaren ketdi `npx` .

`bunx mdt zh` ket mangiparang `.mdt` iti direktorio ti zh a kas `.md` , kitaen ti 2 a naisilpo a papeles iti baba

* [kape_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [kape_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` ket isu ti kangrunaan a kodigo para iti panagipatarus (no addaanka laeng `nodejs` a naikabil, ngem `bun` ken `direnv` ket saan a naikabil, mabalinmo pay nga ipatarayen `npx i18n` tapno agipatarus).

Daytoy ket mangparse [ti i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , ti panagisaad ti `i18n.yml` iti daytoy a dokumento ket kas ti sumaganad:

```
en:
zh: ja ko en
```

Ti kayatna a sawen ket: Panagpatarus iti Insik iti Hapones, Koreano, Ingles, Ingles a patarus iti amin a dadduma a pagsasao. No kayatmo laeng a suportaran ti Insik ken Ingles, mabalinmo laeng nga isurat `zh: en` .

Ti maudi ket [ti gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , a mangikkat ti linaon iti nagbaetan ti kangrunaan a paulo ken ti umuna a subtitulo ti tunggal maysa a pagsasao a `README.md` tapno mangpataud ti panagserrek a `README.md` . Simple unay ti kodigo, mabalinmo a kitaen a mismo.

Ti Google API ket maus-usar para iti libre a panagipatarus. No dika makastrek iti Google, pangngaasim nga i-configure ken i-set ti proxy, kas iti:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Ti iskrip ti panagipatarus ket mangpataudto ti naipatarus a cache iti direktorio `.i18n` , pangngaasi a kitaen daytoy babaen ti `git status` ken inayon daytoy iti pagidulinan ti kodigo tapno maliklikan dagiti maulit-ulit a panagipatarus.

Pangngaasi nga ipatarayen `bunx i18n` tunggal baliwam ti patarus tapno mapabaro ti cache.

No ti orihinal a teksto ken ti patarus ket mabaliwan nga aggigiddan, ti cache ket mariro, isu a no kayatmo a baliwan, mabalinmo laeng a baliwan ti maysa, ken kalpasanna patarayen `bunx i18n` tapno mapabaro ti cache.
