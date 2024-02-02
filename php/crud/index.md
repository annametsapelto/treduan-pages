# CRUD (Create, Read, Update, Delete)

Niin sanotut CRUD-operaatiot ovat tietokantafunktioiden perusta eli käytännössä kaikki muut ovat jollakin tavalla variaatioita näistä eli niissä voi olla esimerkiksi hakuehtoja tms.

## Read eli hakufunktiot

Hakufunktioita on kaksi eli sellainen, joka hakee kaikki tiedot tietokannasta (tai variaationa hakee kaikki tietyin ehdoin) ja sellainen, joka hakee tietyn id:n perusteella tietoja tietokannasta.

Ensin tämän fuktion pitäisi hakea kaikki pelit tietokannasta:

````php
  /**
  * Hakee kaikki pelit taulusta test_games
  */
 function getAllGames() {
     $pdo = connect();
     $sql = "SELECT * FROM test_games";
     $stm = $pdo->query($sql);
     $games = $stm->fetchAll(PDO::FETCH_ASSOC);
     return $games;
 } 
 ````

Funktion kutsu palauttaa taulukon, joka sisältää assosiatiivisia taulukoita. Jos haluamme luoda verkkosivulle listan kaikista noudetuista pelien nimistä, se onnistuu seuraavalla koodilla:

````php
<ul>
<?php 
$games = getAllGames();
foreach($games as $game) {
  echo "<li>" . $game["name"] . "</li>";
}
?>
</ul>
````

 Tämä funktio hakee yhden pelin sen id:n avulla:

 ````php
   /**
  * Palauttaa tietyn pelin
  */
 function getGameById($id) {
     $pdo = connect();
     $sql = "SELECT * FROM test_games WHERE gameid=?";
     $stm = $pdo->prepare($sql);
     $stm->execute([$id]);
     $game = $stm->fetch(PDO::FETCH_ASSOC);
     return $game;
 }  
 ````

 Uuden pelin voi lisätä seuraavalla koodilla (huom, täydennä arvot funktion kutsussa):

 ````php
 function insertNewGame($name, $company, $release) {
    $pdo = connect();
    $sql = "INSERT INTO test_games (`name`, company, `release`) VALUES (?, ?, ?)";
    $stm = $pdo->prepare($sql);
    $ok = $stm->execute([$name, $company, $release]);
    return $ok;
````

Peliä voi muokata seuraavalla koodilla: 

````php
  function updateGame($name, $company, $release, $id) {
    $pdo = connect();
    $sql = "UPDATE test_games SET `name`=?, company=?, `release`=? WHERE gameid=?";
    $stm = $pdo->prepare($sql);
    $ok = $stm->execute([$name, $company, $release, $id]);
    return $ok;
} 
````

Ja seuraava koodi poistaa pelin id:n perusteella:

````php
 /**
  * Poistaa pelin jonka gameid on $id
  */
 function deleteGame($id) {
     $pdo = connect();
     $sql = "DELETE FROM test_games WHERE gameid=?";
     $stm = $pdo->prepare($sql);
     $ok = $stm->execute([$id]);
     return $ok;
 }  
 ````

## Demotehtävä 1

 1. Tulosta kaikki pelit verkkosivulle.
 2. Tulosta kolmas peli verkkosivulle.
 3. Lisää uusi peli.
 4. Muokkaa olemassaolevaa peliä.
 5. Poista viides peli tietokannasta.

### Extra

Hae kaikki pelit jollakin kriteerillä eli muokkaa SQL-koodiin jokin ehto esimerkiksi *company*n mukaan. 

## Demotehtävä 2

Jatka edelliseen tehtävään.
1. Sen sijaan, että tiedot haettaisiin välittömästi, lisää HTML-sivulle nappi, jolla käyttäjä voi hakea kaikki pelit tietokannasta.
2. Lisää sivulle myös lomake, johon voi laittaa numeron, ja nappi, josta sivulle haetaan kyseisen id:n peli, jos se on olemassa.