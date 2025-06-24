# 🚆 MávTrack

Ez a projekt egy valós idejű webes térképes alkalmazás, amely megjeleníti a Magyar Államvasutak (MÁV) vonatainak aktuális helyzetét, sebességét és késését. Az adatok a MÁV GraphQL alapú API-járól származnak, a frontend pedig Leaflet térképkönyvtárat használ.

## ⚠️ Felelősségi nyilatkozat ⚠️

Ez a projekt kizárólag oktatási és demonstrációs célokat szolgál. A megjelenített adatok a MÁV nyilvánosan elérhető, de hivatalosan nem dokumentált API-jából származnak. A szoftver által nyújtott adatok pontosságáért, elérhetőségéért vagy naprakészségéért a szerző nem vállal felelősséget.

A projekt használata saját felelősségre történik. A szerző semmilyen esetben sem vállal felelősséget közvetlen vagy közvetett károkért, amelyek a szoftver használatából erednek.

## 📦 Funkciók

- Percenként frissülő vonathelyzet-térkép
- Késés színkódolás (zöld–sárga–narancs–piros)
- Menetrend és megállók listázása
- Egyszerű Node.js proxy API a CORS-problémák elkerülésére

## 🔧 Előkészületek

Győződj meg róla, hogy a következő eszközök telepítve vannak:

- [Node.js](https://nodejs.org/)

## 🚀 Telepítés és indítás

1. Klónozd a projektet:

   ```bash
   git clone https://github.com/felhasznalo/mav-vonatok-terkep.git
   cd mav-vonatok-terkep
   ```

2. Telepítsd a szükséges csomagokat:

   ```bash
   npm install express axios cors
   ```

3. Indítsd el a Node.js alapú proxyszervert:

   ```bash
   node server.js
   ```

   A szerver futni fog a `http://localhost:3000` címen.

4. Nyisd meg az `index.html` fájlt a böngésződben.

## 🌍 Térkép használata

- A térkép középpontjában Magyarország található.
- A vonatok különböző színekkel jelennek meg a késésük alapján:
  - 🟢 **Zöld**: < 5 perc késés
  - 🟡 **Sárga**: 5–19 perc késés
  - 🟠 **Narancs**: 20–59 perc késés
  - 🔴 **Piros**: ≥ 60 perc késés
- A vonatra kattintva megjelenik:
  - Vonal neve, iránya, sebessége
  - Következő megálló neve
  - Érkezési idő (tervezett és valós)
  - Teljes menetrendi lista, megállónkénti késésekkel
