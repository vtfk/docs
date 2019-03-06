# (WIP) docs
Utkast til prinsipper og standarder for VTFK

## Versjonering

## Navngivning

## Bruk HTTPS

Nye tjenester må bruke og kreve [HTTPS kryptering](https://en.wikipedia.org/wiki/HTTP_Secure) (med TLS/SSL). HTTPS gir:

* **Sikkerhet**. Innholdet i forespørselen krypteres over Internett.
* **Autentisitet**. En sterkere garanti for at en klient kommuniserer med det virkelige API-et.
* **Personvern**. Forbedret personvern for applikasjoner og brukere som benytter API-et. HTTP-headers og søkestrengparametre (blant annet) vil bli kryptert.
* **Kompatibilitet**. Bredere klient kompatibilitet. For at CORS forespørsler til API-et skal virke på HTTPS nettsteder - ikke bli blokkert som "mixed content" - må disse forespørslene må være over HTTPS.

HTTPS bør konfigureres ved hjelp av moderne beste praksis, herunder koder som det støtter [forward secrecy](http://en.wikipedia.org/wiki/Forward_secrecy), og [HTTP Strict Transport Security](http://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security). **Dette er ikke uttømmende**: Bruk verktøy som [SSL Labs](ssllabs.com/ssltest/analyze.html) til å vurdere API-ets HTTPS konfigurasjon.

For et eksisterende API som går over vanlig HTTP, er første skritt å legge til HTTPS-støtte, og oppdatere dokumentasjonen til å erklære det standard, bruk det i eksempler osv.

Deretter vurder muligheten til å deaktivere eller omdirigere HTTP forespørsler. Se [GSA/api.data.gov#34](https://github.com/GSA/api.data.gov/issues/34) for en diskusjon angående noen av utfordringene ved overgangen fra HTTP->HTTPS.

## Teknisk dokumentasjon

En tjeneste er bare så god som sin dokumentasjon.

Dokumentasjon skal være enkelt å finne, på en nettside som er offentlig tilgjengelig.

Eksemplene bør inneholde fulle forespørsler, og svar.

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
