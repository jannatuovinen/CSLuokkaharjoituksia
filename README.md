# CSLuokkaharjoituksia
Esimerkkejä ja harjoituksia C# luokista ja olioista

## Luokkien periytyminen
Luokka voi periä toiselta luokalta kenttiä ja metodeja. Luokkaa, jonka ominaisuuksia peritään (inheritance) kutsutaan yliluokaksi (superclass, parent class) ja perivää luokkaa aliluokaksi (subclass, child class). Perimisen keskeinen idea on se, että yliluokassa määriteltyjä ominaisuuksia (kenttiä) ja metodeja ei tarvitse enää määritellä aliluokassa, riittää, että kerrotaan niiden periytyvän yliluokasta. Yliluokalla ja aliluokalla voi olla saman nimisiä metodeja, jotka toimivat eri tavalla. Tätä kutsutaan metodien ylikirjoittamiseksi (method override). Aiemmissa versiossa aliluokassa määritelty metodi, joka on kirjoitettu eri tavalla kuin yliluokassa, syrjäytti aliluokan saman nimiset metodin. Uusimmat kääntäjät eivät kuitenkaan toimi näin. Aliluokan metodi voi myös syrjäyttää yliluokan metodin silloin, kun yliluokan metodi on määritetty virtuaaliseksi (virtual) ja aliluokassa metodi on määritelty syrjäyttäväksi (overload). Toinen vaihtoehto on käyttää aliluokan metodin määrityksessä new-komentoa yliluokan metodin syrjäyttämiseksi. Jos new jätetään pois aliluokka syrjäyttää edelleen yliluokan (toisin kuin dokumentaatiossa lukee). Seuraavassa esimerkissä on kolme luokkaa: yliluokka lemmikinomistajalle ja kaksi aliluokkaa kissanomistajalle ja koiranomistajalle.

```csharp
// Super/Base/Parent class definion
class Hooman
{
    // Define properties of Hooman ie. fields
    public string name = "Essi Esimerkki";
    public int age = 30;
    public string gender = "Emäntä";

    // Default constructor without arguments
    // No need to define, will be created automatically
    public Hooman()
    {

    }
}

// Sub/Deriver/Child class inhertis Hooman class
class CatOwner : Hooman
{
    // Define the method differently in subclass
    public new void SayOpinion()
    { Console.WriteLine("Kissat ovat itsenäisiä ja pitävät hiiret loitolla");
    }
}

Tehtävä1
Rakenna koiranomistajalle perivä luokka ja sille ylikirjoittava SayOpinion-metodi

// Create a new dog owner and call SayOpinion method
DogOwner dogOwner = new DogOwner();
dogOwner.SayOpinion();

```

Perinteisesti metodin ylikirjoittaminen aliluokassa on määritelty käyttämällä komentoja `virtual`ja ´override`:

## Tehtävä 2
Tee yliluokka `Pet` ja sille aliluokka `Hare`. Määrittele metodi Èats`, joka tulostaa ruudulle eläimen ruokavalion. `Pet`-luokassa tyyliin "Syä ruokaa" ja aliluokassa "Syö porkkanoita". Käytä perinteistä määrittelyä virtuaaliseksi metodiksi ja ylikirjoitettavaksi metodiksi.

## Tehtävä 3
Luo uusi sovellus (solution) ja projekti. Asetukset `C#`, `Windows`-alustalle ja `Console`-sovellustyypiksi.
Sovelluksen avulla kerätään tietoa tietoteknisistä laitteista. Kaikille laitteille yhteisiä ominaisuuksia ovat:

1. Hankintapäivä (string)
2. Hankintahinta (double)
3. Takuuaika kuukausina (int)

Kiinnostuksen kohteena ovat tietokoneet, puhelimet ja tabletit. Rakenna näille luokkamääräykset ja periytä yhteiset ominaisuudet
yliluokasta. Muista kommentoida koodia. Mieti mitä metodeja tarvittaisiin esim. jäljellä olevan takuuajan selvittämiseksi. Mieti mitä eroja tietokoneella ja muilla laitetyypeillä on. Tee tietokoneille, puhelimille ja tableteille omat luokat ja mieti, mitä kenttiä aliluokissa pitäisi olla.

Tee tätä tehtävää varten oma Github-repositorio _Laiterekisteri_. Ota se käyttöön Visual Studiossa, jotta voit versioida kirjoittamaasi
