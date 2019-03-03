Ustawianie parametrów sieci
---------------------------

![alt text][network]

[network]: ./network.png "Logo Title Text 2"

1. na 1 z komputerów zainstaluj oprogramowanie ``http-chat`` dostępne pod adresem ``https://github.com/jkanclerz/http-chat``

Wejściowe parametry sieci
-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
|   PC 1 | debian  
| IP - address  |10.0.2.15 | |
| MASKA  |255.255.255.0 | |
|   |  | |
| PC 2  | xubuntu | |
| IP - address  |10.0.2.4 | |
| MASKA  | 255.255.255.0| |

Weryfikacja połączenia

Polecenie
```
curl -X POST -d '{"text": "Hello World"}' http://10.0.2.4:8888
```

Efekt
```
curl: (7) Failed to connect to 10.0.2.4 port 8888: Połączenie odrzucone
```

Statyczna konfiguracja parametrów połączenia
Wejściowe parametry sieci
-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
|   PC 1 |  debian
| IP - address  | 10.0.2.15 | |
| MASKA  | 255.255.255.0 | |
|   |  | |
| PC 2  | xubuntu | |
| IP - address  | 10.0.2.4 | |
| MASKA  | 255.255.0.0 | |

Weryfikacja połączenia

Polecenie
```
curl -X POST -d '{"text": "hej"}' http://10.0.2.15:8888
```

Efekt
```
 % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100    80  100    58  100    22   6444   2444 --:--:-- --:--:-- --:--:--  8888
{
    "last_message_id": 1,
    "messages": [
        [
            "10.0.2.15",
            "hej"
        ]
    ]
}

```

Nowa statyczna konfiguracja 

-------------------------
| Parametr | wartość | komentarz(opcionalny) |
| ------------- |:-------------:| -----:|
|   PC 1 | debian 
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
| Lokalizacja pliku z konfiguracją sieci| | |
| UP -> Wyłączenie interfejsu sieciowego| | |
| DOWN -> Włączenie interfejsu sieciowego| | |
| Sprawdzenie obecnych parametrów | ip addr show| |
| lista wszystkich interfejsów | | |
| Które interfejsy jakie porty słuchają | 8888 | |

