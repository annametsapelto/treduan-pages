# Linkit

HTML-sivuille t�ytyy usein lis�t� linkkej� joko toisille verkkosivuille tai toiseen kohtaan saman sivun sis�ll�. Linkkiin k�ytet��n tagia ````<a>````. 
Sen sis��n lis�t�� *href*, joka osoittaa haluttuun verkkosivuun. Tagin v�liin kirjoitetaan teksti, jonka halutaan toimivan linkkin�. My�s kuva voi toimia linkkin�.
````html
<a href="https://www.google.com/">Google</a>
````

Jos halutaan, ett� linkist� avataan my�s uusi v�lilehti, tagiin voidaan lis�t� *target="_blank"*. Silloin linkki avautuu uuteen v�lilehteen.
<a href="https://www.google.com/" target="_blank">Google</a>
---

# Kuvat

Kuvia lis�t��n ``<img>`` tagilla. Sit� varten t�ytyy olla kaksi osaa eli reitti kuvan tallennuspaikkaan *src* (source) ja vaihtoehtokuvaus ruudunlukijoita varten, 
tai jos kuvan lataus ei onnistu, *alt* (alternative). 
Sopivat formaatit ovat jpg, png ja gif, muut eiv�t toimi selaimessa. Kuvan kokoa ja muita ominaisuuksia muokataan CSS:ll�, mutta l�ht�kohtaisesti on j�rkev�� valita suunnilleen tarkoitukseen sopiva kuva. 
Jos kuvaa joutuu suurentamaan selaimessa, sen laatu k�rsii. Jos taas se on valtavan paljon suurempi, se vaatii paljon tilaa ja on hitaampi ladata.

````html
<img src="lilies.png" alt="Lily flowers"/>
````

---

# Videot

Verkkosivulle voi my�s lis�t� videoita ``<video>`` tagilla. Sen sis�lle on lis�tt�v� v�hint��n yksi ``<source>`` tag, jolla on ominaisuudet *src* ja *type*, 
mutta voi olla j�rkev�� lis�t� videoon v�litt�m�sti ominaisuuksia, kuten *controls*, jotta sivun k�ytt�j� voi k�ytt�� videota. Lis�ksi videolla voi olla ominaisuuksia, kuten *autoplay*, *muted* tai *loop*. 
Jos haluat ladata videon Youtubesta, siihen on ![erillinen tapansa](https://www.w3schools.com/html/html_youtube.asp). 

````html
<video controls muted>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
  Greetings to all!
</video>
````

---

## Demoteht�v� 1

1. Lis�� omalle sivullesi linkki jollekin toiselle verkkosivulle liittyen esimerkiksi harrastukseesi tai vaikka kouluusi (Tredun sivut ovat https://www.tredu.fi/). 
Tee siit� sellainen, ett� se avautuu toiseen v�lilehteen.
2. Lis�� sivulle kuva joko itsest�si tai liittyen harrastukseesi. Voit k�ytt�� my�s alkuviikosta otettuja kuvia.
3. Kokeile lis�t� sivulle pieni videop�tk�. Nauhoita vaikka parin sekunnin video, jossa sanot "Moi!"