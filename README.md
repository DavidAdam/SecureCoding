# Secure Coding 2017 - Azonosítás és engedélyezés

## Feladat: OAuth alkalmazása gyakorlatban 

* A Temboo segítségével alapvető információk lekérdezése a felhasználóról.
* A labor során egy Android alkalmazást kell készíteni, amely a Facebook OAuth2 API-ját felhasználva engedélyt kér a felhasználó erőforrásaihoz, majd lekérdez néhány információt a felhasználóról.

## Előkövetelmények a labor teljesítéséhez:

* Facebook account (www.facebook.com) (Aki nem szeretné a labor gépeken megadni a bejelentkezési adatait, vagy nem rendelkezik Facebook fiókkal, akkor használja a laborvezető által adott teszt felhasználót)
* Temboo account (www.temboo.com)

<img src="./assets/diagram_1.png" width="650" align="middle">

Az OAuth engedélyezés során általánosságban a felhasználótól engedélyt kérünk az erőfforásainak elérésére, amelyet ha megad, valamilyen engedélyezési kódot kapunk (A-B), az engedélyezési kódot hozzáférési tokenre cseréljük (C-D), majd a hozzáférési token segítségével hozzáférhetünk a felhasználó erőforrásaihoz (E-F).

## Grant típusok, OAuth flow-k

### Authorization Grant

### Implicit Grant
