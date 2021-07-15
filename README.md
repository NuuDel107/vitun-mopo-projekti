# Idea:
	
Lapsille tarkoitettu työntökärry ([esimerkki](https://www.etola.net/wp-content/uploads/punaineniso.234b5e8d-6d40-4b76-9f06-2c657ab21bd8-1.jpg)), jonka taka-akseliin kiinnitetään vahva imurista peräisin oleva DC-moottori. 

Moottoria olisi tarkoitus kauko-ohjata jotenkin, näillä näkymin Raspberry Pi:llä, Arduinolla ja ohjaamiseen tarkoitetulla Android-sovelluksella, joka yhdistetään RasPiin Bluetoothin avulla.

# Työvaiheet / Osa-alueet:

## 1. Moottorin kiinnitys taka-akseliin, toiminnan varmistus

- TÄRKEIN ASIA ENSIN: Onko moottorissa tarpeeksi vääntöä oikeasti liikuttamaan kärryä?
- Kiinnitysmekanismin pitää olla erittäin jykevä, se tulee kokemaan kovia

## 2. Moottorin ohjaus Arduinolla

- Tämän voi tehdä kolmella tavalla:

  - Hankkimalla moottoriohjaimen, joka toimii tarvittavilla jännitteillä (12V, 4A) ja eristää Arduinon

  - Rakentamalla itse samanlaisen moottoriohjaimen: paljon hankalampaa, vaatii tietämystä

  - Käyttämällä pelkkää relettä ohjaamiseen: helppoa, mutta ei voi vaikuttaa vauhtiin tai suuntaan, on käytännössä pelkkä ON-OFF -kytkin

## 3. Arduinon ohjaus Raspberry Pi:llä

- Helppo homma, hoituu USB-yhteyden (josta myös Arduinolle virtaa) ja Python-ohjelman kautta
- RasPille saa virtaa (ehkä) USB-virtapankista

## 4. Raspberry Pi:n ohjaus Bluetoothilla / Android-puhelimella

- RasPin Bluetooth-yhteyden avulla voidaan kommunikoida puhelimen kanssa
- Arduino- ja Bluetooth-kommunikoinnin voi molemmat hoitaa samalla Python-ohjelmalla

- Ongelma: miten Bluetooth yhteyden saa muodostettua, jos RasPi on kärryn sisällä suojassa?
- Hätäjarru: Jos Bluetooth-yhteys katkeaa, kärry pysäyttää moottorin automaattisesti

## 5. Ohjaamiseen tehty Android-sovellus

- Tehdään mahdollisesti React Nativella, käyttäen esim. BLE PLX-kirjastoa
- Ominaisuudet: Bluetooth-yhdistäminen, ohjauspaneeli jolla voi kiihdyttää sekä jarruttaa/peruuttaa (mikäli käytetään moottoriohjainta)

## 6. Elektroniikan kiinnitys ja turvaaminen, varsinkin Arduino ja RasPi

- Kärry tulee osumaan moniin esteisiin ja tärisemään, varsinkin jos se viedään julkisille paikoille
- Osat ja virtapiirit pitää kiinnittää huolellisesti, mieluusti jonkin kotelon sisään (tarkka tapa vielä tuntematon)
