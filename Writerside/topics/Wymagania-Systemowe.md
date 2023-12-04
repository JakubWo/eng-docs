# Wymagania Systemowe

## Spis treści
- [Wymagania (etap I)](#wymagania-etap-i)
  - [Zbieranie danych meteorologicznych](#zbieranie-danych-meteorologicznych)
    - [Optymalizacja zużycia energii](#optymalizacja-zu-ycia-energii)
    - [Czujnii](#czujniki)
  - [Prezentacja danych](#prezentacja-danych)
    - [Wykresy](#wykresy)
    - [Wykresy w czasie rzeczywistym](#wykresy-w-czasie-rzeczywistym)
    - [Dostęp do starych danych statystycznych](#dost-p-do-starych-danych-statystycznych)
    - [Podstawowa statystyka danych](#podstawowa-statystyka-danych)
    - [Dynamiczne dostosowywanie się do czujników](#dynamiczne-dostosowywanie-si-do-czujnik-w)
- [Wymagania (etap II)](#wymagania-etap-ii)
  - [API](#api)
    - [Otwarte API](#otwarte-api)
    - [Dokumentacja API](#dokumentacja-api)
    - [Zmiana technologii](#zmiana-technologii)
  - [Zmiana systemu zbierania danych meteorologicznych](#zmiana-systemu-zbierania-danych-meteorologicznych)
  - [Zmiana MQTT na RabbitMQ](#zmiana-mqtt-na-rabbitmq)
  - [Implementacja dockera](#implementacja-dockera)

## Wymagania (etap I)

Etap pierwszy odbył się w ramach pracy inżynierskiej

### Zbieranie danych meteorologicznych

Stworzenie urządzenia pobierającego dane na temat pogody. 
Urządzenie ma działać w sposób ciągły przesyłając dane na serwer.

#### Optymalizacja zużycia energii

Urządzenie ma mieć zredukowane zużycie energii do minimum. 
Ma działać na akumulator.

#### Czujniki

Urządzenie ma zbierać różne odczyty danych meteorologicznych, ma więc mieć więcej niż jeden czujnik.

### Prezentacja danych

Dane mają być dostępne do odczytu na publicznej stronie WWW.

#### Wykresy

Dane zebrane za pomocą urządzenia mają być prezentowane na wykresach dwuwymiarowych. 

#### Wykresy w czasie rzeczywistym

Wykresy mają być zawsze aktualne i pobierać dynamicznie dane bez potrzeby odświeżania strony.

#### Dostęp do starych danych statystycznych

Strona powinna dostarczać widok pozwalający na pobranie historycznych danych z całego okresu ich zbierania.

#### Podstawowa statystyka danych

Strona powinna przedstawiać prostą statystykę danych w postaci podsumowania na dany okres.

#### Dynamiczne dostosowywanie się do czujników

Strona ma automatycznie dostosowywać się do otrzymanych danych. 
W razie zmiany czujnika, bądź jego dołożenia strona powinna to wykryć automatycznie i zaprezentować dodatkowy wykres.

## Wymagania (etap II)

### API

#### Otwarte API

API ma być otwarte na świat. Każdy ma mieć opcje pobierania danych meteorologiczych. 

#### Dokumentacja API

Utworzenie publicznej dokumentacji akcji API pozwalającej zapoznać się z nią nowym użytkownikom.

#### Zmiana technologii

Zmiana technologii z django i python na symfony i php.

### Zmiana systemu zbierania danych meteorologicznych

W ramach ułatwienia testów i oduzależnieniu aplikacji od urządzenia stacjonarnego,
należy dodać możliwość generacji i/lub pobierania danych z internetu.  

### Zmiana MQTT na RabbitMQ

Zmiana technologii pośrednika z MQTT na RabbitMQ.

### Implementacja dockera

Należy zaimplemenować Dockera w każdej aplikacji, aby ułatwić pracę deweloperom.
