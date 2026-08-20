# Odpočet 90:00

Celostránkový countdown timer. Jedna stránka, jeden soubor, žádné závislosti.

- číslice zabírají přesně 80 % šířky okna (přepočítává se při každé změně velikosti)
- černé pozadí, bílý monospace (JetBrains Mono, fallback na systémový mono)
- formát `mm:ss`, maximum 90:00, aktualizace po sekundě
- start / pauza / reset

## Ovládání

| akce | klávesnice | dotyk / myš |
|---|---|---|
| nastavit čas | číslice (kurzor začíná na minutách), `↑` `↓` | ťuknutí na minuty nebo sekundy, tlačítka `−` `+` |
| přepnout minuty/sekundy | `←` `→`, `Tab` | ťuknutí na příslušnou dvojici číslic |
| start / pauza | `mezerník`, `Enter` | tlačítko Start / Pauza |
| reset | `R`, `Esc` | tlačítko Reset |

Poslední minuta pod 10 sekund zežloutne, po doběhnutí `00:00` bliká.
Zbývající čas se zrcadlí v titulku záložky.

## Displej se za běhu neuspí

Dokud odpočet běží, drží stránka Screen Wake Lock — telefon nezhasne.
Zámek se bere při startu a při každém návratu do popředí, protože Android
ho sám uvolní pokaždé, když se karta schová nebo displej zhasne; proto se
sleduje záměr zvlášť od sentinelu a poslouchá se jeho `release`.
Uvolní se při pauze, resetu i po doběhnutí na `00:00`.

Podmínky: HTTPS (nebo `localhost`), karta v popředí, prohlížeč s podporou
Screen Wake Lock API — Chrome, Edge a Samsung Internet na Androidu ano,
Firefox pro Android zatím ne. Když API chybí nebo je požadavek zamítnut,
odpočet běží dál, jen se displej uspává standardně.

## Spuštění

Otevři `index.html` v prohlížeči. Nic se nebuildí.

Publikace na GitHub Pages: Settings → Pages → Deploy from a branch,
vyber větev a složku `/ (root)`.
