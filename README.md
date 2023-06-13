# Easy Symposion Web Template

Tato šablona by měla usnadnit tvorbu webových stránek pro budoucí Symposiony, a to jak ty oficiální, tak studentské. S poskytnutým kódem a návodem níže by měl spuštění a provoz zvládnout i programátor-začátečník.

> **Kontakt** <br>
> Kdyby něco, neváhejte mi napsat na _maty *(zavináč)* stanford *(tečka)* edu_.

## 1. Tvorba harmonogramu

Nejprve je potřeba vytvořit Google Tabulku s harmonogramem. Tu je následně možné nasdílet organizátorům z řad učitelů i studentů; její rozhraní je dostatečně intuitivní na to, aby práci v ní zvládl každý. Přímo z ní bude následně číst i webová stránka – úpravy se tak budou živě zobrazovat na webu.

1. Na svém školním Google účtu vytvořte kopii [této šablony](https://docs.google.com/spreadsheets/d/1km1xShFxvSk185FktIXoSYkJ-4zbO6S0ss_gcYeif0Q/edit?usp=sharing).
2. Seznamte se se strukturou tabulky:
      - **Anotace** – Seznam všech bloků (přednášek/workshopů/debat), spolu s organizátory a popisem
      - **Místnosti** – Časový harmonogram, specifikující místo a čas každého z bloků, který je uveden na listu Anotace 
      - **Tisk** – Verze harmonogramu pro tisk

          > **Poznámka**<br>
          > Aby fungovaly odkazy z harmonogramu, musí se názvy jednotlivých bloků v listu _Anotace_ a _Místnosti_ přesně shodovat.

3. Přizvěte konkrétní organizátory pomocí standardního Google rozhraní _Sdílet_. Pozor, za žádných okolností nesdílejte tabulku prostřednictvím odkazu. Tímto způsobem by mohl tabulku upravovat kdokoliv na škole.

> **Poznámka**<br>
> Pro inspiraci se můžete podívat na weby studentských Symposionů z let [2022](https://docs.google.com/spreadsheets/d/1F0_pELbHQQw73UQvZ2LeJwHMKPSmhZfyyvge3XT5NlI/edit?usp=sharing) a [2023](https://docs.google.com/spreadsheets/d/12pkR8C3OD23VjDgllPq2bnGvFIMszh5OWYffoJMYTZs/edit?usp=sharing).

## 2. Tvorba webu

Po přípravě a sdílení tabulky můžete pokračovat k tvorbě samotné webové stránky.

1. Začněte tím, že vytvoříte klon tohoto repozitáře. Tím se Vám vytvoří Váš vlastní GitHub projekt, v němž budete moci základní šablonu adaptovat na aktuální ročník. Seznamte se s jeho strukturou – `index.html` obsahuje kostru webu, `main.js` řeší logiku, primárně tedy stahování dat z tabulky.
2. **Informace a motiv** – Všechny statické informace o akci (datum, čas, organizace), spolu s motivem ročníku, patří do souboru `index.html`, sekce s id `header_info` (řádky 47-57). Aby web ladil s ostatními grafickými materiály, můžete upravit i fontz a barvy, a to konkrétně v tagu `style`, (řádky 16-22).
3. **Propojení tabulky** – Napojení na tabulku provedete v souboru `main.js`, konkrétně na řádcích 3 a 4. Odkazy by měly mířit na patřičný list z tabulky – nejprve _Místnosti_, dále _Anotace_ – a být exportované do CSV.

> **Poznámka**<br>
> Konkrétní list je možné exportovat do CSV následovně. <br>
> 1. Nejprve získejte hlavní odkaz (pro čtení), např: `https://docs.google.com/spreadsheets/d/12pkR8C3OD23VjDgllPq2bnGvFIMszh5OWYffoJMYTZs/edit?usp=sharing`. <br>
> 2. Umažte `/edit?usp=sharing`. <br>
> 3. Přidejte tyto parametry requestu: `/gviz/tq?tqx=out:csv&sheet=Mistnosti`. <br>
> 4. Získáme `https://docs.google.com/spreadsheets/d/12pkR8C3OD23VjDgllPq2bnGvFIMszh5OWYffoJMYTZs/gviz/tq?tqx=out:csv&sheet=Mistnosti`.

## 3. Zveřejnění

Jakmile web řádně otestujete na svém vlastním zařízení, nebude již nic bránit jeho zveřejnění světu. Existují dvě hlavní možnosti, jak web publikovat – na doméně školy či na vlastní doméně.

Pokud volíte variantu školní domény, kontaktujte osobu pověřenou správou webu a s ní domluvte další kroky. Pokud však volíte publikaci na vlastní doméně, můžete využít publikaci skrze [GitHub Hosting](https://pages.github.com/). Stačí si vytvořit repozitář ve tvar `username.github.io`.
