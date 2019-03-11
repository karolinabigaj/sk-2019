Ustawianie parametrów sieci
---------------------------

1. na 1 z komputerów zainstaluj oprogramowanie ``http-chat`` dostępne pod adresem ``https://github.com/jkanclerz/http-chat``
apt-get install git 
git clone https://github.com/jkanclerz/http-chat
apt-get install python
python httpchat.py

Wejściowe parametry sieci
-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
|   PC 1 |  
| IP - address  | 192.168.10.4 | |
| MASKA  | 255.255.255.0 | |
|   |  | |
| PC 2  |  | |
| IP - address  | 192.168.10.5 | |
| MASKA  | 255.255.255.0 | |

Weryfikacja połączenia

Polecenie
```
curl
```

Efekt
```
Komputery dostają od siebie komunikaty
```

Statyczna konfiguracja parametrów połączenia
Wejściowe parametry sieci
-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
|   PC 1 |  
| IP - address  | 192.168.10.10 | |
| MASKA  | 255.255.255.0 | |
|   |  | |
| PC 2  | | |
| IP - address  | 172.16.100.100 | |
| MASKA  | 255.255.0.0 | |

Weryfikacja połączenia

Polecenie
```
```

Efekt
```
```

Nowa statyczna konfiguracja 

-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
|   PC 1 |  
| IP - address  |  | |
| MASKA  |  | |
|   |  | |
| PC 2  |  | |
| IP - address  |  | |
| MASKA  |  | |

Weryfikacja połączenia

Polecenie
```
```

Efekt
```
```

Warto wiedzieć
--------------

-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
| Lokalizacja pliku z konfiguracją sieci| /etc/network/interfaces | |
| UP -> Wyłączenie interfejsu sieciowego| ifup| |
| DOWN -> Włączenie interfejsu sieciowego| ifdown| |
| Sprawdzenie obecnych parametrów | ip a | |
| lista wszystkich interfejsów | ip a | |
| Które interfejsy jakie porty słuchają | | |

