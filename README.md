# CSS Grid - Placing (Umisťování prvků)

## Cíl cvičení
Naučit se pracovat s **explicitním** a **implicitním** umisťováním prvků v CSS Grid layoutu. Budeme kombinovat **absolutní** a **relativní** určení pozice.

## Zadání

V souboru `index.html` najdete připravený HTML kód s 30 položkami v grid containeru. Vaším úkolem je doplnit CSS styly podle následujících požadavků:

### 1. Nastavení grid containeru (`.container`)

- Grid má být tvořen **10 explicitními sloupci**, kde **sudé sloupce jsou dvakrát širší než liché**
  - Použijte `grid-template-columns` s funkcí `repeat()`
  - *Tip*: použij `fr`

- Grid má mít **10 explicitních řádků**, každý o výšce **50px**
  - Použijte `grid-template-rows`
  - *Alternativa*: pro implicitní řádky můžete použít `grid-auto-rows`

### 2. Umístění jednotlivých položek

Doplňte CSS pravidla pro následující explicitně umístěné itemy (ostatní položky budou umístěny implicitně):

#### `.item1`
- Má být umístěn ve **3. až 4. sloupci**, je umístěn **absolutně**
- Použijte vlastnost `grid-column`

#### `.item2`
- Má začínat na **5. sloupci** a pokračovat **až do konce gridu**
- Použijte záporné indexy (`-1`)

#### `.item8`
- Má se **rozpínat přes dva řádky**, je umístěn **relativně**
- Použijte klíčové slovo `span`

#### `.item5`
- Má se rozpínat přes **2 sloupce** a **2 řádky**, je umístěn **relativně**
- Použijte `grid-column` a `grid-row`

#### `.item15`
- Má **zabírat celou šířku gridu**
- Rozpíná se od prvního do posledního sloupce

#### `.item20`
- Má **začínat na 4. řádku** a **rozpínat se přes 3 řádky**
- Použijte kombinaci absolutního a relativního umístění

#### `.item18`
- Má **končit na 8. sloupci** a **rozpínat se přes 4 sloupce zpět**
- Absolutně je určen konec, relativně začátek

## Pojmy

Do gridu se umistují jednotlivé prvky (items) automaticky (implicitně) nebo manuálně (explicitně). Když umisťujeme prvky explicitně, můžeme použít dva přístupy:

### Absolutní umístění (Absolute Placement)
Když přímo určujeme, na kterém řádku nebo sloupci má prvek začínat a končit pomocí čísel grid linií:
```css
.item {
  grid-column: 2 / 4;  /* od 2. do 4. linie */
  grid-row: 1 / 3;     /* od 1. do 3. linie */
}
```

### Relativní umístění (Relative Placement)
Když používáme `span` a necháváme prohlížeč vypočítat pozici a určujeme jen "jak moc" se má prvek rozpínat:
```css
.item {
  grid-column: span 2;  /* rozpíná se přes 2 sloupce */
  grid-row: span 3;     /* rozpíná se přes 3 řádky */
}
```

### Kombinace obou přístupů
```css
.item {
  grid-column: 3 / span 2;  /* začíná na 3. linii a rozpíná se přes 2 sloupce */
  grid-row: span 2 / 5;     /* rozpíná se přes 2 řádky a končí na 5. linii */
}
```

## Tipy

- Grid linie jsou číslovány od 1
- Záporný index `-1` označuje poslední linii
- `span` říká, přes kolik buněk se prvek rozpíná
- `grid-gap` vytváří mezery mezi prvky (už je nastaveno)

## Jak pracovat

1. Otevřete soubor `index.html` v editoru
2. Doplňte CSS pravidla do sekce `<style>`
3. Otevřete soubor v prohlížeči a kontrolujte výsledek
4. Využijte **DevTools** (F12) → záložka Grid pro vizualizaci gridu
