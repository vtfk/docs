# docs
Utkast til prinsipper og standarder for VTFK

## Versjonering

## Teknisk dokumentasjon

## Bruker dokumentasjon

## Datoformat

Bruk [ISO 8601](https://xkcd.com/1179/) i UTC for både forespørsler og svar.

For datoer ser det slik ut `2015-02-27`. For fullstendige tidspunkt `2015-02-27T10:00:00Z`.

Dette datoformatet brukes over hele nettet, og setter hvert felt i en konsistent rekkefølge.

## Tegnsett

Bruk kun [UTF-8](http://utf8everywhere.org).

Forvent tegn med "smarte anførselstegn" i API-resultatet, selv om de ikke er forventet.

Et API skal fortelle klientene at det forventes UTF-8 ved å inkludere en karaktersett notasjon i `Content-Type` header for svaret.

Et API som returnerer JSON må bruke:

```
Content-Type: application/json; charset=utf-8
```

## Lisenser

Bruk [MIT](LICENSE).

Inkluder [LICENSE](LICENSE)-filen i repoet.
