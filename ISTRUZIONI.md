# Palinsesto serale — istruzioni per l'attività pianificata (v202610281845)

Pubblico: gruppo di amici che la sera si trova in un locale (Bari). L'app "Cassa Locale" legge `tv.json` da questo repository.

## Compito (ogni giorno, ~09:00 ora italiana)
1. Data di oggi in Europe/Rome.
2. Ricerca web della programmazione di STASERA (dalle 20:00 a fine serata) in Italia: digitale terrestre, Sky, NOW, DAZN, Prime Video, Netflix, Disney+, Apple TV+.
   Fonti preferite: guide TV del giorno (staseraintv.com, libero.it «film in TV stasera», comingsoon.it, sorrisi.com, maridacaterini.it), calendari Serie A/coppe (libero.it «calcio in TV oggi», sport.sky.it, dazn.com), rottentomatoes.com.
3. Compila `tv.json` (schema sotto) e copialo in `archivio/AAAA-MM-GG.json`.
4. Commit «palinsesto AAAA-MM-GG» e push su `main`.

## Criteri, in ordine
1. **in_evidenza** (max 5): prima le PARTITE (Serie A, Champions/Europa/Conference, Coppa Italia, Nazionale, top campionati esteri) e i grandi eventi sportivi (F1, MotoGP, tennis top, basket di vertice), con canale esatto; poi programmi di INCHIESTA/attualità (Le Iene, Report, Presa Diretta, Chi l'ha visto?, Piazzapulita, Quarta Repubblica, Striscia…) e lo show di richiamo della serata.
2. **cult** (esattamente 3): film scelti A CASO fra quelli con Tomatometer alto su Rotten Tomatoes (≥ 90%), di intrattenimento (azione, commedia, avventura, thriller, fantascienza, animazione), di qualsiasi epoca. Non serve che siano in onda stasera né indicare dove vederli: solo titolo italiano, anno, `rt` verificato su rottentomatoes.com e una nota.
3. **film_gratis** (max 4): i migliori film in chiaro stasera (Rai, Mediaset, La7, TV8, Nove, Iris, Rai Movie, Cine34, 20, Twentyseven, Italia2…), con giudizio sintetico e `rt` se noto.

## Regole
- Verifica orari, canali, disponibilità streaming e punteggi RT su fonti affidabili; se un dato non è certo, omettilo (mai inventare).
- **Rotazione**: niente titoli di `cult` già proposti negli ultimi 30 giorni (controlla `archivio/`).
- Note: max 12 parole, in italiano.
- Se la ricerca fallisce, NON sovrascrivere `tv.json` con dati vuoti: lascia l'ultimo valido.

## Schema `tv.json`
```json
{
  "giorno": "AAAA-MM-GG",
  "generato": "ISO 8601 con fuso",
  "titolo": "una riga sulla serata",
  "in_evidenza": [{"ora":"20:45","canale":"DAZN","titolo":"Inter – Juventus","tipo":"partita|sport|inchiesta|show","nota":"…"}],
  "cult": [{"titolo":"…","anno":1994,"rt":92,"nota":"…"}],
  "film_gratis": [{"ora":"21:20","canale":"Iris","titolo":"…","anno":1994,"rt":88,"nota":"…"}],
  "fonti": ["url", "url"]
}
```
