# htmlcss-bootstrap-tailwind

Esercizio del tutoraggio di mercoledì 11/11, dopo la lezione su Bootstrap e Tailwind. È la pagina di Pinco Pallo, costruita due volte senza scrivere CSS: una volta con Bootstrap, una volta con Tailwind.

## Cosa devi fare

Ci sono due pagine, `bootstrap.html` e `tailwind.html`. Hanno già tutto l'HTML e i testi, ma nessuna classe: per ora sono pagine senza stile.

Per ogni pagina:

1. **Insieme al docente**: colleghiamo il framework, mettiamo il contenitore della pagina e facciamo la prima card. Segui il docente e scrivi le stesse cose nel tuo file.
2. **Tocca a te**: il resto della pagina, con i passi qui sotto.

Nei file trovi dei commenti `INSIEME AL DOCENTE` e `PASSO N · TOCCA A TE`: ti dicono dove lavorare. **Niente CSS tuo**: niente `<style>`, niente file `.css`, niente `style="..."`. Solo le classi del framework.

## Cosa trovi qui

```
├── bootstrap.html                     ← pagina 1, con Bootstrap
├── tailwind.html                      ← pagina 2, con Tailwind
├── img/                               ← le immagini delle card
├── screenshot-bootstrap-mobile.jpg    ← pagina 1 finita a 400px
├── screenshot-bootstrap-tablet.jpg    ← pagina 1 finita a 800px
├── screenshot-bootstrap-desktop.jpg   ← pagina 1 finita a 1300px
├── screenshot-tailwind-mobile.jpg     ← pagina 2 finita a 400px
├── screenshot-tailwind-tablet.jpg     ← pagina 2 finita a 800px
└── screenshot-tailwind-desktop.jpg    ← pagina 2 finita a 1300px
```

## Come procedere

1. Fai il **fork** di questa repo: bottone **Fork** in alto a destra, lascia il nome `htmlcss-bootstrap-tailwind`. Il fork è la tua consegna: così il docente la vede.
2. Clona il **tuo** fork sul computer (`git clone` con l'indirizzo del tuo fork, non di questa repo).
3. Apri la cartella in Antigravity e la pagina con Live Server. Lavora con l'inspector aperto: la barra dei dispositivi (`Ctrl+Shift+M` su Windows, `Cmd+Shift+M` su Mac) ti fa scrivere la larghezza esatta.
4. Tieni aperta in un'altra scheda la documentazione: [Bootstrap 5.3](https://getbootstrap.com/docs/5.3/getting-started/introduction/) e [Tailwind CSS](https://tailwindcss.com/docs/installation/play-cdn). Le classi si cercano lì.
5. Fai commit e push sul tuo fork quando finisci una pagina.

## Pagina 1: Bootstrap

**Insieme al docente**: il link al CSS di Bootstrap 5.3, il contenitore della pagina e la prima card.

### 1. Le colonne

- **Obiettivo**: le card si mettono in colonna come negli screenshot. Una per riga sotto i 576px, due da 576px, tre da 992px, quattro da 1200px. Tra una card e l'altra c'è spazio, in orizzontale e in verticale.
- **Come verifichi**: prova a 575, 576, 991, 992, 1199 e 1200px. Le colonne cambiano esattamente a quelle larghezze. Nell'inspector, clicca una colonna: nelle regole vedi quella accesa per la larghezza attuale.

<details>
<summary>Suggerimento</summary>

Le classi vanno su due livelli: la riga e le colonne. Le colonne restano tutte uguali, quante per riga lo scrivi una volta sola sulla riga. Ripassa la dispensa, capitolo "I breakpoint: le colonne che cambiano". Le soglie sono quelle di `sm`, `lg` e `xl`.

</details>

### 2. Le altre card e il badge

- **Obiettivo**: le altre cinque card sono uguali alla prima. Nelle card con "Nuovo!" c'è un badge rosso, a pillola, in maiuscolo, a cavallo del bordo in alto a destra della card.
- **Come verifichi**: confronta con lo screenshot. In una riga le card sono alte uguali. Il badge sta sulla sua card, non nell'angolo della pagina.

<details>
<summary>Suggerimento</summary>

Per le card: le classi le hai già, nella prima. Per il badge c'è un componente con quel nome, nella documentazione (Components). Per metterlo nell'angolo cerca le utility di posizione (Utilities > Position): ci sono anche le classi per spostarlo di metà della sua altezza, come il `translate` del 24/10.

</details>

### 3. Il banner

- **Obiettivo**: il banner giallo occupa sempre tutta la riga. Fino a 991px sta sopra tutte le card, da 992px sotto tutte le card. Il testo è in grassetto e centrato, gli angoli arrotondati.
- **Come verifichi**: a 991px il banner è la prima cosa sotto il menu, a 992px l'ultima della pagina. A 1300px è largo quanto le quattro colonne insieme.

<details>
<summary>Suggerimento</summary>

Il div esterno sta nella riga come una colonna, il colore va sul div interno: il gutter è padding. Per tutta la riga, attenzione: `col-12` da 992px non basta, rileggi il capitolo "Le stesse colonne, tre scritture" della dispensa. Per spostarlo, la proprietà è quella di Flexbox: cerca le utility Flex, parte "Order".

</details>

### 4. La navbar

- **Obiettivo**: al posto dell'header c'è una navbar di Bootstrap scura, con "My App" a sinistra e i tre link a destra. Da 576px i link sono in riga, sotto c'è l'hamburger. Il menu resta in alto quando scorri la pagina.
- **Come verifichi**: a 400px clicca l'hamburger: si apre il menu con i tre link, e un altro clic lo chiude. A 576px i link sono in riga, a destra. Scorri la pagina: la navbar resta attaccata in alto e le card le passano sotto.

<details>
<summary>Suggerimento</summary>

Copia l'esempio della pagina Navbar della documentazione e tieni solo quello che ti serve. Il breakpoint dell'hamburger sta nella classe `navbar-expand-…`. Se l'hamburger non si apre, ripassa il capitolo "Collegare Bootstrap con la CDN": il CSS disegna il bottone, ma aprire e chiudere è un comportamento.

</details>

## Pagina 2: Tailwind

**Insieme al docente**: lo script di Tailwind, il contenitore della pagina e la prima card.

### 5. Le colonne

- **Obiettivo**: le card in una griglia, una per riga sotto i 640px, due da 640px, tre da 1024px, quattro da 1280px, con spazio tra le card.
- **Come verifichi**: prova a 639, 640, 1023, 1024, 1279 e 1280px. Nell'inspector, accanto al div delle card c'è il badge `grid`.

<details>
<summary>Suggerimento</summary>

È la Grid di sabato 7/11, scritta con le classi. In Tailwind il breakpoint sta davanti, con i due punti. Dispensa, capitolo "Tailwind: una classe per proprietà".

</details>

### 6. Le altre card e il badge

- **Obiettivo**: le altre cinque card sono uguali alla prima. Il badge "Nuovo!" è rosso, arrotondato, piccolo, in grassetto e in maiuscolo, a cavallo del bordo in alto a destra della sua card.
- **Come verifichi**: confronta con lo screenshot. Il badge sta sulla sua card, non nell'angolo della pagina, e non cambia la posizione del titolo.

<details>
<summary>Suggerimento</summary>

In Tailwind non c'è il componente badge: lo costruisci tu, una proprietà per classe. Il badge si sposta con `position` e gli offset (lezione del 24/10). Se finisce nell'angolo della pagina, chiediti rispetto a chi è posizionato: in Bootstrap la card faceva questo lavoro per te, qui no.

</details>

### 7. Il banner

- **Obiettivo**: il banner giallo occupa sempre tutta la riga, sopra le card fino a 1023px e sotto le card da 1024px. Testo in grassetto e centrato, angoli arrotondati, padding.
- **Come verifichi**: a 1023px è la prima cosa sotto l'header, a 1024px l'ultima della pagina. A 1300px è largo quanto le quattro colonne.

<details>
<summary>Suggerimento</summary>

In CSS era `grid-column: 1 / -1`: cerca come si scrive in Tailwind (Grid Column). Per l'ordine, cerca la pagina "order" della documentazione: confronta i nomi con quelli che hai usato in Bootstrap.

</details>

### 8. L'header

- **Obiettivo**: un header scuro con il testo bianco, "My App" grande a sinistra e i link in riga a destra da 640px in su. Sotto i 640px i link spariscono e si vede solo ☰. L'header resta in alto quando scorri.
- **Come verifichi**: a 639px vedi solo ☰, a 640px solo i link. Scorri la pagina: l'header resta in alto e card e badge gli passano **sotto**. Il ☰ non apre niente, ed è giusto così: Tailwind non ha JavaScript.

<details>
<summary>Suggerimento</summary>

L'header è un flex container: è il flexbox del 29/10. Per far sparire e ricomparire un elemento: `hidden` e il prefisso del breakpoint. Se i badge passano sopra l'header, ripassa `z-index` (lezione del 24/10).

</details>

Per ripassare: [dispensa Bootstrap e Tailwind](https://kb-aiwd.andreadev237.workers.dev/lezioni/css-bootstrap-tailwind) e [dispensa CSS Grid](https://kb-aiwd.andreadev237.workers.dev/lezioni/css-grid).

Se usi l'AI, il file `AGENTS.md` la fa lavorare da tutor: ti fa domande e ti indica dove guardare, senza darti la soluzione.

## Bonus (facoltativo)

- **Bootstrap**: sopra le card, un alert verde che si chiude con la X. Cerca il componente Alert, parte "Dismissing". **Come verifichi**: clicca la X, l'alert sparisce.
- **Tailwind**: al passaggio del mouse il bordo della card diventa blu. Ti serve il prefisso `hover:`, lo stesso del bottone della lezione. **Come verifichi**: passa con il mouse su una card, il bordo cambia colore; togli il mouse, torna grigio.

## Consegna

Nessuna scadenza. Fai push sul tuo fork, poi incolla il link nel canale del corso.
