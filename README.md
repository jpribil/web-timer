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
Za běhu drží obrazovku rozsvícenou (Screen Wake Lock, kde je k dispozici)
a zbývající čas se zrcadlí v titulku záložky.

## Spuštění

Otevři `index.html` v prohlížeči. Nic se nebuildí.

Publikace na GitHub Pages: Settings → Pages → Deploy from a branch,
vyber větev a složku `/ (root)`.
