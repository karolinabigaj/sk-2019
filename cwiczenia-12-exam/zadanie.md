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
