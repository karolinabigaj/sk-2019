# Zadanie 2

## Projekt sieci lokalnej dla jednostki dydaktycznej uniwersytetu

![budynek](budynek.svg)

### Cel Projektu
  Zaprojektowanie i weryfikacja działania sieci w środowisku testowym. 
  Rozwiązanie zapewnia dostęp do internetu dla wszystkich urządzeńw infrastrukturze.
  
### Założenia projektu

* Sieć zlokalizowana jest w budynku 3 kondygnacyjnym
* Na kążdej z kondygnacji znajdują się laboratoria komputerowe kolejno:
  * poziom 0 
    * 009, 013, 014
  * poziom 1
    * 115, 116, 117, 122
  * poziom 2
    * 201, 202, 203 
* Każde z laboratoriów wyposażone jest w 35 stanowisk dla uczestników kursów
* Jednostka planuje otworzenie kolejnych laboratoriów 017 oraz 204
* Każda kondygnacja wyposażona jest w izolowaną sieć Wi-Fi, udostępniajacą sieć internet podłączonym gościom
  * Sieć Wi-Fi nie pozwala na bezposrednią komunikację z urządzeniami zlokalizowanymi w pozostałej części sieci,
    tj: laboratoria, serwery jednostki
  * Prognozowana maksymalna liczba jednoczesnych urządzeń podłączonych do sieci to ``800``
* Jednostka posiada przyłącze internetowe oraz dysponuje pulą adresów ``188.156.220.160/27``
* Jednostka posiada serwery udostępniajace zasoby do celów dydaktycznych i promocyjnych
  * serwery zlokalizowane są w osobnym pomieszczeniu
  * udostępniają zasoby w sieci publicznej z wykorzystaniem sieci ``188.156.220.160/27``
  * Jeden serwer pełni rolę bramy dla urządzań w sieci lokalnej ``LAN``

### Wstępne założenia

* Każde laboratorium posiada oddzielną podsieć pozwalającą efektywnie zidentyfikować urządzania
  * kondygnacja oraz sala
* Dla uniknięcia zbyt słabego zasięgu sieć WiFi zostanie wyposażona w 4 urządzenia nadawcze na każdej kondygnacji
 

#### zadanie - wymaganai

* Dokonaj podziału i projektu sieci w formie dokumentu w formacie ``MARKDOW`` zawierającego specyfikację tekstową oraz obrazkową
  projektowanej sieci
* Przygotuj prototyp rozwiązania z wykorzystaniem oprogramowania ``VirtualBox`` lub podobnego.
* W specyfikacji uwzględnij wielkości sieci oraz ich adresy
* W specyfikacji uwzględnij konfigurację tablicy routingu
* Dokumentację graficzną stworzonej architektury przygotuj w programie ``DIA`` lub podobnym

# Wykonanie

| Adres sieci |  zakres hostów   | Adres Rozgłoszeniowy | Cel sieci |
| --------- |:-------------|  :---------------|  :---------------|
| ``192.168.0.0/22``    | 1022| 192.168.3.255| Wi-Fi Jednostki|
| ``192.168.4.0/26``    | 62| 192.168.4.63| Laboratorium 009|
| ``192.168.4.64/26``    | 62| 192.168.4.127| Laboratorium 013|
| ``192.168.4.128/26``    | 62| 192.168.4.191| Laboratorium 014|
| ``192.168.4.192/26``    | 62| 192.168.4.255| Wolna pula dla lab 017|
| ``192.168.5.0/26``    | 62| 192.168.5.63| Laboratorium 115|
| ``192.168.5.64/26``    | 62| 192.168.5.127| Laboratorium 116|
| ``192.168.5.128/26``    | 62| 192.168.5.191| Laboratorium 117|
| ``192.168.5.192/26``    | 62| 192.168.5.255| Laboratorium 122||
| ``192.168.6.0/26``    | 62| 192.168.6.63| Laboratorium 201|
| ``192.168.6.64/26``    | 62| 192.168.6.127| Laboratorium 202|
| ``192.168.6.128/26``    | 62| 192.168.6.191| Laboratorium 203|
| ``192.168.6.192/26``    | 62| 192.168.6.255| Wolna pula dla lab 204|
| ``192.168.7.0/29``    | 6| 192.168.7.7| Sieć piętro 0|
| ``192.168.7.8/29``    | 6| 192.168.7.15| Sieć piętro 1|
| ``192.168.7.16/29``    | 6| 192.168.7.23| Sieć piętro 2|
| ``192.168.7.24/29``    | 6| 192.168.7.31| Sieć wewnętrzna jednostki|
| ``188.156.220.160/27``    | 30| 188.156.191.255| Sieć publiczna jednostki|

![diagram](show.png)

1. Mamy wydieloną sieć publiczną, która zawiera router dostępowy do sieci zewnętrznej (uniwersyteckiej), serwery udostępniajace zasoby do celów dydaktycznych i promocyjnych, router sieci Wi-Fi i router główny sieci laboratoryjnych. Każde piętro posiada wydzielony router podłączony do głównego routera i od trzech do czterech routerów w salach laboratoryjnych.
2. Każda sala laboratoryjna posiada poza swoim odrębnym routerem switch i 35 stacji roboczych.
3. Każdy router na piętrze łącznie z głównym routerem będzie mieć ustalony statyczny adres IP, dęki któremu będzie mógł przekazywać połączenie z wewnątrz na zewnątrz. Dzięki takiemu rozwiazaniu stacje robocze będą widzieć komputery tylko ze swojej pracowni, nie zobacza ani komputerów na innych piętrach, ani tych w innych salach.
4. Router - brama zewnętrzna udostępnia wszystkim stacjom roboczym oraz gościom z sieci Wi-Fi dostęp do zewnętrznej sieci (do Internetu). Natomiast dostęp do serwerów z sieci publicznej mają tylko urządzenia z zewnątrz oraz stacje robocze (wszystkie wiadomości z sieci Wi-Fi będą automatycznie przekierowywane na zewnątrz) i dzięki temu zapewniamy wszystkie założenia.
5. Wyżej w tabeli mamy pokazany podział sieci na poszczególne routery, oraz wolne pule zachowane dla możliwego w przyszlości dobudowania laboratoriów na piętrze zerowym i drugim.
6. Dla uniknięcia zbyt słabego zasięgu sieć Wi-Fi zostanie wyposażona w 4 urządzenia nadawcze na każdym piętrze.
