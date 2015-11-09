Viikkoharjoitus 4: MapReduce
----------------------------

MapReduce on suurten datamäärien prosessointiin tarkoitettu ohjelmointimalli.
Google App Engine tarjoaa oman MapReduce-ympäristönsä.

Siihen voi tutustua vaikka [App Enginen MapReduce-dokumentaatiosta](https://github.com/GoogleCloudPlatform/appengine-mapreduce/wiki).
Python-spesifistä ohjeistusta on [luvussa 3](https://github.com/GoogleCloudPlatform/appengine-mapreduce/wiki/3.1-Creating-and-Running-a-Job).

[App Enginen MapReduce Python-kirjasto](https://github.com/GoogleCloudPlatform/appengine-mapreduce) pitää itse käsin lisätä projektiin. Tähän projektiin se on jo lisätty hakemistoon `mapreduce`. 

App Enginen MapReduce-toteutuksessa on [erilaisia tapoja lukea syötettä ja kirjoittaa tuloksia](https://github.com/GoogleCloudPlatform/appengine-mapreduce/wiki/3.4-Readers-and-Writers).
Tässä harjoituksessa voi esimerkiksi lukea käyttäen `DatastoreInputReader`:ia ja kirjoittaa tulokset `GoogleCloudStorageOutputWriter`:illä Cloud Storageen.

## Tehtävä: laske eläinten saalistajien lukumäärä MapReducella
1. [Toisessa viikkoharjoituksessa](https://github.com/Palpo/palpo_viikkoharkka2) tallennettiin eläimiä Datastore-tietokantaan. Voit jatkaa joko omasta 2. harjoituksen toteutuksestasi tai kloonata tämän repositorion, johon on jo valmiiksi lisätty [mapreduce-kirjasto](https://github.com/GoogleCloudPlatform/appengine-mapreduce).
2. Laske MapReducen avulla kunkin eläimen saalistajien lukumäärä. Eli se kuinka monta kertaa kukin eläin esiintyy muiden eläinten saaliseläimenä.
3. Tulosten esittämiseen ei tässä tarvitse keskittyä. Voit katsoa ne vaikka SDK:n [kehityskonsolin]( http://localhost:8000) Blobstore Viewerillä (jos tallensit käyttäen `GoogleCloudStorageOutputWriter`:iä). Tai App Enginessä ajaessasi [sen kehityskonsolista](https://console.developers.google.com/).

HUOM1: Tämä tehtävä ei nyt ole erityisen hyvä esimerkki MapReducen käytöstä. Ensinnäkin dataa on niin vähän, että MapReducen käytössä ei ole mitään järkeä; saman voisi tehdä tietokantakyselyinkin.

HUOM2: Jos tallensit DataStoreen kaksisuuntaiset saalistaja-saalis-linkit (tässä esimerkissä ei), on MapReduce-ajo triviaalihko. (Hakujen tehokkuuden takia moinen tietokantarakenne voisi olla järkeväkin.) Mieti kuitenkin tässäkin tapauksessa, että miten suorittaisit MapReducen jos DataStoressa olisi vain yksisuuntaiset linkit saalistaja->saalis (kuten tässä esimerkissä).
