# Kurssin suorittaminen ja arvostelu

Kurssilla jaossa 60 pistettä. Pisteet jakautuvat seuraavasti

- Viikkodeadlinet 17p
- Koodikatselmointi 2p
- Dokumentaatio 12p
  - Määrittely
  - Arkkitehtuuri
  - Käyttö/asennusohje
  - Testidokumentti
  - Docstring-dokumentaatio
- Testaus 5p
  - Testit
- Lopullinen ohjelma 24p
  - Toiminnallisuus
  - Koodin laatu

Arvosanaan 1 riittää 30 pistettä, arvosanaan 5 tarvitaan noin 55 pistettä.

Läpipääsyyn vaatimuksena on lisäksi vähintään 10 pistettä lopullisesta ohjelmasta.

## Lopullisesta ohjelmasta annettavat pisteet

Pisteet (yhteensä 24) jakautuvat seuraavasti

- Käyttöliittymä 4p
  - 0p yksinkertainen tekstikäyttöliittymä
  - 1-2p monimutkainen tekstikäyttöliittymä
  - 2-3p yksinkertainen graafinen käyttöliittymä
  - 4p laaja graafinen käyttöliittymä
- Talletetun tiedon käyttö ja tiedon tallettaminen 4p
  - ei pysyväistallennusta
  - 1-2p tiedosto (1p jos ohjelma ainoastaan lukee tiedostoja)
  - 3-4p tietokanta (3p jos ohjelma ainoastaan lukee tietokannasta dataa)
  - 3-4p internet (esim. google docs tai joku muu talletusratkaisu)
  - Pisteytys riippuu käsiteltävän tiedon monimutkaisuudesta
- Sovelluslogiikan kompleksisuus 3p
- Ohjelman laajuus 4p
- Ulkoisten kirjastojen hyödyntäminen 1p
  - Näihin eivät lukeudu mateeriaalissa esitellyt testaukseen, testikattavuuteen, koodin formatointiin, koodin laadun staattisen analyysiin, tai koodin dokumentointiin käytettävät kirjastot
- Koodin laatu 4+1p
  - Kooste [laatuvaatimuksista](https://github.com/mluukkai/ohjelmistotekniikka-syksy-2020/blob/main/web/koodin_laatuvaatimukset.md)
  - 4p hyvät abstraktiot (esim. suunnitellumallien, kuten Repository-suunnittelumallin hyödynnys), selkeä tiedosto- ja hakemistorakenne, helposti testattava ja laajennettava, ei ilmeistä copypastea
  - +1p pylint-sääntöjen noudattaminen kunnossa (muutama sääntörikkomus saatetaan katsoa läpi sormien, kunhan pylintin antama arvosana koodille on vähintään 9.00/10)
- Virheiden käsittely 2p
  - 2p Sovellus toimii konsistentisti, ei kaadu virheellisillä syötteillä, ei heitä poikkeuksia ja antaa järkevät virheilmoitukset
- **Älä jätä sovellukseesi poiskommentoitua koodia**, tai koodia jota sovellus ei käytä (esim. refaktoroinnin myötä turhaksi muuttuneet metodit, luokat, tai funktiot)
  - Jos jätät, vähenevät koodin laadun pisteet -1 tai -2p riippuen kommentoidun/turhan koodin määrästä

### Laajuus ja sovellusogiikan kompleksisuus

- Miten laaja on laaja?
- Kurssin [referenssisovellus](https://github.com/ohjelmistotekniikka-hy/python-todo-app) olisi laajuudeltaan 2 pisteen luokkaa, koska sovelluslogiikaltaan se on kohtalaisen suoraviivainen
- Laajuutta ei voida määritellä tarkasti esimerkiksi luokkien, metodien, tai funktioiden määrällä, laajuus on aina suhteellinen sovelluksen tyyppiin ja kompleksisuuteenkin
- Eräs tapa laajentaa sovellusta ja lisätä sen kompleksisuutta on tehdä siitä _parametrein konfiguroitava ja laajennettava_, esimeerkiksi:
  - Sovelluksen käyttämän tietokantatiedoston nimi ei ole kirjoitettu koodiin vaan on käyttäjän määriteltävissä
  - Pelissä eri vaikueustasojen pelimaailmat eivät ole määritelty koodissa vaan luodaan erillisten tiedostojen perusteella
  - Pacmanissa hirviöiden määrä ei ole ohjelmakoodiin kovakoodattu vakio vaan valittavissa käyttöliittymästä
  - Konfiguroitavuus voidaan toteuttaa joko käyttöliittymän tai [konfiguraatiotiedostojen](./python.md#sovelluksen-konfiguraatiot) avulla

## Testauksesta annettavat pisteet

Täysien pisteiden (5p) edellytys:

- Testattu kattavasti: haarautumakattavuus korkea (noin 70%)
  - Testien pitää testata hyödyllisiä asioita, pelkät testikattavuutta nostavat hyödyttömät (esim. assert-komentoja sisältämättömät) testit eivät tuo pisteitä
- Testaus riittävää sekä yksikkö- että integraatiotasolla
  - Eli yksittäisten luokkien lisäksi on testattava myös monen luokan yhdistelmän tuottavaa toiminnallisuutta
- Sovelluslogiikkaa testataan realistisilla skenaarioilla
- Testit testaavat mielekkäitä asioita
  - Jos testit on tehty ainoastaan testikattavuuden kasvattamiseksi, ei pisteitä ole montaa odotettavissa
- Riippuvuudet käsitelty järkevästi
  - Tietokantaa käyttävissä sovelluksissa testeissä käytössä "testitietokanta". Aiheesta löytyy ohjeita mm. [sovelluksen konfiguraatiot](./python.md#sovelluksen-konfiguraatiot)-osiossa
  - Myös valekomponentit ovat hyviä joissain tilanteissa. Niiden käytöstä on esimerkki [riippuvuuksien injektointi](./python.md#riippuvuuksien-injektointi)-osiossa

## Dokumentaation pisteet

Dokumentaatio tuo yhteensä maksimissaan 12 pistettä, jotka jakautuvat seuraavasti

- Määrittelydokumentti 2p
  - **Päivitetty vastaamaan lopullisen ohjelman toiminnallisuutta**
  - Päivittämätön määrittelydokumentti tuo 0 pistettä
- Arkkitehtuurikuvaus 4p
- Käyttö/asennusohje 1p
  - Arvostelijan tulee pystyä asentamaan ohjelma ja käyttämään sitä ohjeen avulla
- Testausdokumentti 2p
- Docstring-dokumentaatio 2p
  - Suurin osa luokista, metodeista ja funktioista on dokumentoitu docstring-kommenttien avulla
- Repositorio ja README 1p
  - Repositorion ja README:n oletetaan olevan aiempien viikkojen vaatimusten mukainen

[Referenssisovellus](https://github.com/ohjelmistotekniikka-hy/python-todo-app) toimii hyvänä esikuvana dokumentaation suhteen. Koodin dokumentointi tosin on sovelluksessa osittain puutteelista.

**HUOM** älä copy-pastea referenssisovelluksen dokumentaation tekstiä omaan dokumentaatioosi, kirjoita teksti omin sanoin. Tekstin suora kopiointi johtaa hylkäämiseen.

## Harjoitustyön toimivuus

- Koneiden konfiguraatioissa on eroja, ja tällä kurssilla ei riitä että hajoitustyössä tekemäsi sovellus toimii vain omalla koneellasi
- Harjoitustyösi pitää pystyä joka viikko suorittamaan, kääntämään ja testaamaan komentoriviltä käsin laitoksen Linux-koneilla (tai uusimmat päivitykset sisältävällä cubbli-linuxilla), muussa tapauksessa työtä ei tarkasteta ja menetät viikonpalautuksen pisteet.
- Pääset testaamaan ohjelmaasi laitoksen koneella myös kotoa käsin käyttämällä etätyöpöytää https://helpdesk.it.helsinki.fi/ohjeet/tietokone-ja-tulostaminen/tyoasemapalvelu/etakaytettavat-tyopoydat-vdi-ja-vmware tai kirjautumalla ssh:lla palvelimelle melkki.cs.helsinki.fi
