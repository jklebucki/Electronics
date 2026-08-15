# Electronics

Repozytorium zawiera opisy i konfiguracje ukladow Tuya dla dwoch wariantow platformy:

* BK7231N
* ECR6600

Pliki w katalogu glowynm sa wyciagniete z konfiguracji urzadzen i sluza do identyfikacji moduulu, mapowania pinow oraz punktow startowych danych Tuya.

## Dostepne moduly

### BK7231N

Opis dotyczy urzadzenia opartego o modul CBU na BK7231N. Z `BK7231N/info.txt` wynika nastepujace mapowanie:

* Button (channel 1) - P17
* LED (channel 1) - P9
* Bridge Relay On (channel 1) - P7
* Bridge Relay Off (channel 1) - P8
* WiFi LED - P15

Wniosek z konfiguracji: to prosty modul przelaczajacy z przyciskiem, dioda statusu i osobnymi liniami sterowania przekaznikiem.

### ECR6600

Opis dotyczy drugiego wariantu platformy, oznaczonego w danych jako `eswin_ecr6600` / `ECR6600`. Z `info.txt` wynika nastepujace mapowanie:

* BL0937 SEL - P15
* Button (channel 1) - P24
* LED (channel 1) - P0
* BL0937 VI (CF1) - P20
* WiFi LED - P22
* BL0937 ELE (CF) - P14
* Relay (channel 1) - P25

Wniosek z konfiguracji: to modul z pomiarem energii opartym o BL0937, z jednym kanalem przekaznika i osobna dioda WiFi.

## Pliki konfiguracyjne

* `tuya_config.json` - pelny zrzut konfiguracji Tuya dla urzadzenia.
* `info.txt` - opis wyciagniety z konfiguracji glownej.
* `BK7231N/info.txt` - opis wyciagniety z konfiguracji dla wariantu BK7231N.

## Uwagi

* Dla ECR6600 sekcja Tuya zaczyna sie pod adresem `0x1D5000`, co pasuje do domyslnego offsetu dla RTL8720C i ECR6600.
* Dla BK7231N sekcja Tuya zaczyna sie pod adresem `0x1EE000`.
* Katalog `ECR6600/` jest obecnie pusty i moze sluzyc jako miejsce na przyszle pliki dla tej platformy.


