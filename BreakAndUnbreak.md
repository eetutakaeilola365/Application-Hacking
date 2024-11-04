# Raportti
Tehtävän annot:
a) Murtaudu 010-staff-only. Ks. Karvinen 2024: Hack'n Fix
b) Korjaa 010-staff-only haavoittuvuus lähdekoodista. Osoita testillä, että ratkaisusi toimii.

# A
Avasin Kali-linuxin, menin osoitteeseen: https://terokarvinen.com/hack-n-fix/ ja otin selvää, kuinka saan ratkaistua tehtävän.

Asensin hack-n-fix ohjelman ja purin zip tiedoston unzip teros-challenges.zip, jonka jälkeen etenin hakemistossa komennolla cd challenges/010-staff-only/
Laitoin kyseisen ohjelmiston käyntiin, mutta en heti ymmärtänyt, mihin seuraavat(from flask import Flask, render_template, request # sudo apt-get install python3-flask) komennot laitetaan. 
Pienen yrittämisen jälkeen laitoin ne $ python3 staff-only.py komennon eteen yhteen pötköön, jolloin onnistuin saamaan nettisivun näkymään osoitteessa 127.0.0.1:5000

Seuraavaksi tutkin SQL injektiota, jonka avulla tulen mahdollisesti selvittämään, kuinka saan SUPERADMIN merkkijonon näkyviin nettisivustolla. 
Haluan siis löytää haavoittuvuuden ohjelmistosta ja muokata sitä niin, että napissa lukee reveal admin password ja saan vastaukseksi SUPERADMIN	 merkkijonon.
Menin YouTubeen katsomaan videota aiheesta SQL injection, jonka jälkeen ymmärrän yleisesti, mistä on kyse. 
Menin katsomaan videota SQL injektiosta (https://www.youtube.com/watch?v=2OPVViV-GQk) Ja ensimmäisen minuutin aikana ymmärsin, kuinka tärkeää on käyttää eri salasanoja eri paikoissa. 
Jos yhteen haavoittuvaan nettisivustoon on käytetty samaa salasanaa ja käyttäjänimeä, kuin muihinkin, 
ne voidaan saada tietoon melko helposti ja näin tunkeutuja pääsee kaikkiin muihinkin sovelluksiin kirjautumaan samoilla tunnuksilla, jotka on saatu yhdestä paikasta. 
Katsoin videon ja siinä selitettiin, kuinka SQL injektio toimii. Käytännössä nettisivun salasanaan lisätään SQL koodia, joka mitätöi salasanan ja päästää sisälle. 
Täytyy vain osata SQL kieltä ja ohjelmoinnin perusteet, jonka jälkeen sisäänpääsy haavoittuvaisille nettisivuille on suhteellisen helppoa. Kokeillaan tätä käytännössä. 

Menen osoitteeseen (https://www.youtube.com/watch?v=2OPVViV-GQk) josta saan selville että' OR 1=1 komennolla kyetään murtamaan käyttäjätunnus.
Tätä komentoa ennen kokeilin komentoa '-- ja se ei toiminut, sillä tekstinsyöttö laatikoita on vain yksi. Tämän jälkeen kokeilin komentoa ' OR '1=1 ja sekään ei toiminut.
Onnistuin näillä komennoilla kuitenkin suorittamaan harjoitustehtävät osoitteessa:https://portswigger.net/web-security/sql-injection
En saanut tehtävää ratkaistua mutta opin paljon, kuinka käyttäjätunnus ja salasana voidaan murtaa ja siinä onnistuinkin muissa ympäristöissä. 
Ongelma tehtävää suorittaessa oli se, että en tiennyt, oikealla tavalla laittaa komentoa, kun tekstinsyöttökenttiä oli kahden sijasta yksi.

# B
Menin linuxin terminaalissa staff-only.py nimiseen python tiedostoon ja otin selvää, kuinka ohjelmisto on koodattu. Ohjelmistossa oli merkattu virheet, jotka täytyy korjata. 
Näiden virheiden korjaaminen estää SQL injektiohyökkäykset ja parantaa ohjelmiston tietoturvaa. 
En saanut ohjelmistoa täysin korjattua, mutta olisin korjannut sen niin, että mitään muita kuin numeroita ei voida syöttää tekstikenttään.
Tämä estää '-- ja OR hyökkäykset. Koska en saanut ensimmäistä tehtävää ratkaistua mutta oletan, että edellä mainituilla komennoilla olisi päässyt muokkaamaan tietokantaa, 
testini olisi evännyt pääsyn muokata sql-koodia. 

# Lähteet
https://terokarvinen.com/hack-n-fix/

https://portswigger.net/web-security/sql-injection

https://www.youtube.com/watch?v=2OPVViV-GQk
