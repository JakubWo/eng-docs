# Struktura Projektu

## Spis treści
- [Schemat](#schemat)
    - [Stacja meteorologiczna](#stacja-meteorologiczna)
    - [RabbitMQ](#rabbitmq)
    - [API](#api)
    - [MongoDB](#mongodb)
    - [Discord](#discord)
    - [Strona Internetowa](#strona-internetowa)


## Schemat

<img src="project_structure.png" alt="project_structure"/>

### Stacja meteorologiczna

Urządzenie zbierające i wysyłające dane meteorologiczne.
W podstawowej wersji projektu była to płytka STM32.
Pobierała dane z otoczenia za pomocą czujnika BME680.
Wysyłała dane przez internet do serwisu kolejkowego za pomocą modemu SIM7070G.

W aktualnej wersji projektu urządzenie zastąpione jest CRON'em,
który cyklicznie wysyła dane kolejne na kolejkę.

### RabbitMQ

Broker wiadomości przesyłanych przez stację meteorologiczną.
Kolejkuje kolejne wiadomości i przesyła je do API.

### API

Ma za zadanie przyjmować dane otrzymywane od RabbitMQ,
zapisywać je w bazie oraz zwracać dane do serwisu www.

Dodatkowo loguje informacje o błędach na serwer Discord.

### MongoDB

Nierelacyjna baza danych składująca każdy otrzymany od urządzenia zbiór pomiarów.

### Discord

Komunikator z programowalnymi pluginami oraz otwartym API,
dzięki czemu został wykorzystany jako miejsce wysyłania logów
oraz powiadamiania programistów o zaistniałych problemach.

### Strona Internetowa

Wystawione na użytek klienta strona zawierająca wykresy z danymi oraz statystyki.
Pozwala również na pobranie rekordów w formacie .csv.
