# Secure Coding 2017 - Azonosítás és engedélyezés

## Feladat: OAuth alkalmazása gyakorlatban 

* A Temboo segítségével alapvető információk lekérdezése a felhasználóról.
* A labor során egy Android alkalmazást kell készíteni, amely a Facebook OAuth2 API-ját felhasználva engedélyt kér a felhasználó erőforrásaihoz, majd lekérdez néhány információt a felhasználóról.

## Előkövetelmények a labor teljesítéséhez:

* Facebook account (www.facebook.com) (Aki nem szeretné a labor gépeken megadni a bejelentkezési adatait, vagy nem rendelkezik Facebook fiókkal, akkor használja a laborvezető által adott teszt felhasználót)
* Temboo account (www.temboo.com)

## Áttekintés

<img src="./assets/diagram_1.png" width="650" align="middle">

Az OAuth engedélyezés során általánosságban a felhasználótól engedélyt kérünk az erőfforásainak elérésére, amelyet ha megad, valamilyen engedélyezési kódot kapunk (A-B), az engedélyezési kódot hozzáférési tokenre cseréljük (C-D), majd a hozzáférési token segítségével hozzáférhetünk a felhasználó erőforrásaihoz (E-F).

## Grant típusok, OAuth flow-k

### Authorization Grant

<img src="./assets/diagram_2.png" width="650" align="middle">

Az Authorization Code vagy Server Side Flow szerver alkalmazásokhoz lett kifejlesztve. A felhasználói engedély után a szerver egy Authorization kódot küld, melyet a kliens a Client ID és Client Secret komponensekkel együtt access tokenre cserél (szerver hívásokon keresztül, tehát a hozzáférési token és a Client Secret rejtve marad a felhasználó szemszögéből).

A (többek között Facebook OAuth) folyamat szemléltetésére és kipróbálására nagyon jó felületet nyújt a TEMBOO nevű weboldal:
https://temboo.com

Regisztráció után nyissuk meg a Facebook-hoz kapcsolódó szolgáltatásaikat:
https://temboo.com/library/Library/Facebook/

Kövessük a **Setup Instructions** részben leírtakat (amennyiben nem szeretné a labor során a Facebook fiókját használni, ez a lépés kihagyható, de kísérje figyelemmel a lépéseket!):
* Facebook developer account készítése
* Facebook app készítése **Facebook developer console**-ban
* **Website** platform option választása
* **Site URL** beállítása (http://{accountname}.temboolive.com/callback/)
* **Add product** Facebook Login (Platform legyen Android)
* **Facebook Login > Client OAuth Settings**, Temboo callback URL megadása a **Valid OAuth redirect URIs** mezőbe:

https://{ACCOUNT_NAME}.temboolive.com/callback/
--- |

* **Settings > Basic > App Domains** mezőbe ugyanezt

Ezekkel a beállításokkal a Temboo profilunkat/webalkalmazásunkat kötöttük össze a Facebook alkalmazásunkkal. A Temboo a *Facebook App ID* értékből tudja elindítani a kéréseket a Facebook App felé, a Facebook App pedig a *callback url*-en keresztül tudja a válaszokat visszajuttatni a temboo-nak.

### Implicit Grant
