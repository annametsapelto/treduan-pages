# Harjoitukset 5

Käy tutustumassa JavaScriptin taulukkometodeihin [täällä](https://www.w3schools.com/js/js_array_methods.asp)<base target="_blank">. Tee sitten tehtäviä. Osa liittyy taulukoihin, osa ei.

## Tehtävä 1: Lyhennä sukunimi

Tee tehtävä HTML-sivulle.

Kysy käyttäjältä hänen etunimeään ja sukunimeään lomakkeella. Voit käyttää joko event listeneriä tai nappia ja sen tapahtumaa valitaksesi annetut tiedot.

Tee funktio, joka muuntaa etu- ja sukunimen sisältävän merkkijonon lyhyempään muotoon:

*Esimerkki:*
console.log(lyhenna_nimi("Leevi Syrjakyla"));
Tulostaa: "Leevi S."

Näytä lyhennetty nimi HTML-sivulla.

*Vihje:*
Jaa (split) ensin merkkijono taulukkoon välilyönnin kohdalta.
Lue taulukosta etunimi kokonaan ja sukunimestä vain ensimmäinen merkki, yhdistä takaisin merkkijonoksi (join).

## Tehtävä 2 Käyttäjätunnus

Käytä aiempaa HTML-sivua.

Valitse käyttäjän etunimen ja sukunimen. Tee ensin funktiossa tarkistus, että nimet ovat riittävän pitkät eli niissä on oltava vähintään kaksi kirjainta molemmissa. Käytä *trim()*-funktiota tarkistamaan, että syötteessä ei ole tyhjiä lyöntejä. 

Tee toinen funktio, joka luo käyttäjän nimen avulla käyttäjätunnuksen seuraavasti: alkuosa on tredu ja lisäksi siinä on etu- ja sukunimen kolme ensimmäistä kirjainta, isot kirjaimet muutetaan pieniksi ja ääkköset korvataan ä -> a, ö -> o, å -> o

Tulosta nimi sekä saatu käyttäjätunnus HTML-sivulle.

*Esimerkki:*
nimi: Leevi Syrjäkylä
käyttäjätunnus: treduleesyr

## Tehtävä 3: Kauppalista

Luo lomake, jossa yksi input ottaa vastaan tekstiä ja vieressäoleva ottaa vastaan numeroita. Tarkoitus on ottaa vastaan ostoslista, jossa ensimmäiseen kirjoitetaan tuote ja jälkimmäiseen lukumäärä. Napilla tuotteet lisätään listaan.

Tarkista ensin, ettei tuote ole tyhjä tai sen pituus ole lyhyempi kuin kaksi merkkiä. Jos numero on tyhjä, oletus on yksi kappale. Muuta tuotteen nimi isoille kirjaimille. Näytä tuote ja kappalemäärä listana lomakkeen alla.

Lisää toinen nappi, jolla listan voi tyhjentää.

## Tehtävä 4: Pelilogiikkaa

Tutustu oheisen [pelin koodiin](https://github.com/otredu/js-games/tree/master/game-demo). Kopioi sitten koodi itsellesi. Kokeile muuttaa koodia niin, että esineet liikkuvat eri tavalla (esim. eri erineet eri nopeuksilla) ja/tai pelaaja liikkuu eri tavalla. Lisää peliin pisteenlasku niin, että ruudulla näkyvät pisteet (saat itse päättää paljonko pisteitä kustakin esineestä saa, tuleeko jostain miinuspisteitä jne). Lisää *game over*-ilmoitus kun pisteet menevät alle nollan tai pelaajan "elämät" loppuvat. Voit myös halutessasi tehdä täysin oman pelin hyödyntäen valmista koodia.