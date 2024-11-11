# H3 No strings attached

## A
Menin Kotitehtävien sivulle ja latasin sitä kautta ezbin-challenges.zip tiedoston, jonka jälkeen avasin sen. 
Koitin avata sen, mutta käyttämällä komentoa $strings passtr | less, mutta näkymä näytti vain tyhjää. 
Tällöin tajusin, että minun täytyy ladata strings-ohjelma, jonka avulla näen sisällön. Latasin strings ohjelman komennolla $sudo apt-get install binutils. 
(katsoin netistä osoitteesta: https://ioflood.com/blog/install-strings-command-linux/). 
![h3a1](https://github.com/user-attachments/assets/23ac351b-d6bd-492a-aab7-c453ea1c1d0d)

Käytin komentoa $strings passtr | less uudestaan ja nyt sain näkyviin passtr:n tiedot. 

![h3a2](https://github.com/user-attachments/assets/796c792b-9896-437a-8125-426feb059646)

Tehtävänantona oli etsiä oikea salasana ja lippu, jotka löysin kohdasta: what's the password? syöttämällä komennon $ strings passtr | grep -i 'flag'.
Oikea salasana on sala-hakkeri-123 ja lipun löydettyäni sain merkkijonon FLAG{Tero-d75ee66af0a68663f15539ec0f46e3b1}

![h3a3](https://github.com/user-attachments/assets/d54a5474-c44a-4752-a9ca-ca09348e8cab)

## B
Menin passtr.c nimiseen tiedostoon komennolla $ sudo less passtr.c, 
ja huomasin, miten tiedosto on koodattu. Muokkasin ohjelmaa ($ sudo nano passtr.c) siten, 
että salasana on piilotetummassa muodossa.

![h3b1](https://github.com/user-attachments/assets/d353a345-d120-4a22-933c-b0699ef7fcaa)

Testasin ohjelmaa komennolla ./passtr ja kirjoitettuani salasanan sala-hakkeri-321 sain testin onnistumaan. Avattuani passtr ohjelman 
strings komennolla (strings passtr | less), salasana kuitenkin näkyi selkästi, joten en saanut tehtävää täysin suoritettua.

![h3a3](https://github.com/user-attachments/assets/4a9c414d-d32d-41ab-9210-161dcc19084d)

## C
Tehtävän anto oli sama kuin A osassa. Kuitenkin tällä kerralla salasana ei ollut näkyvillä, kun suoritti komennon $ strings packd | less.
Yritin saada salasanan näkyviin käyttämällä komentoa $ strings packd | grep -i 'salasana, password', siinä kuitenkin onnistumatta.
Sain uuden idean, joka oli muuttaa tiedosto kryptisestä binaari kielestä luettavaksi teksti tiedostoksi. Löysin osoitteesta www.rapidtables.com string to numbers kääntäjän ja numbers to text kääntäjän. 
Sain käännettyä kryptisen tekstin nolliksi ja ykkösiksi mutta en saanut enää binaari numeroita käännettyä luettavaksi tekstiksi.

![h3c1](https://github.com/user-attachments/assets/70f79ed9-1226-4e88-8784-8708105b02ae)

![h3c2](https://github.com/user-attachments/assets/661599d6-6ec8-47e2-9216-a86686eb4aa1)


## Lähteet
https://terokarvinen.com/application-hacking/#laksyt
www.rapidtables.com 
https://ioflood.com/blog/install-strings-command-linux/
https://chatgpt.com/gpts

