# CurrEX - aplikacja Flask do wymiany walut

CurrEX to prosty projekt webowy napisany we Flasku. Pozwala na:

- tworzenie konta użytkownika (rejestracja/logowanie),
- przechowywanie własnych walut w "portfelu",
- dodawanie i wypłacanie środków,
- wymianę walut na inne,
- sprawdzanie aktualnych kursów walut w czasie rzeczywistym (API AlphaVantage),
- pracę z bazą danych SQLite oraz formularzami Flask-WTF.

Projekt powstał jako ćwiczenie backendu we Flasku i integracji z zewnętrznym API.

## Instalacja i uruchomienie

### 1. Pobierz repozytorium
```bash
git clone https://github.com/iMMMMMo/flask-currency-exchange-api-app.git
cd flask-currency-exchange-api-app
```

### 2. Zainstaluj wymagania
```bash
pip install -r requirements.txt
```

### 3. Ustaw zmienne środowiskowe (Windows CMD)
Aplikacja wymaga dwóch kluczy:

- SECRET_KEY - klucz Flaska (dowolnie wygenerowany),
- ALPHAVANTAGE_API_KEY - klucz dostępu do API Alpha Vantage.

Ustawienia:

```bash
set SECRET_KEY=twoj_klucz
set ALPHAVANTAGE_API_KEY=twoj_klucz
```

#### Jak wygenerować SECRET_KEY?

```bash
python
```

W konsoli Pythona:

```python
import secrets
secrets.token_hex(32)
```

Skopiuj wynik do zmiennej SECRET_KEY.

#### Jak wygenerować ALPHAVANTAGE_API_KEY?

Wejdź na stronę: https://www.alphavantage.co/support/#api-key i podaj swój email w celu otrzymania darmowego klucza do API.

Skopiuj wynik do zmiennej ALPHAVANTAGE_API_KEY.

### 4. Uruchomienie projektu

```bash
python run.py
```

## Zawartość projektu
- Flask - logika aplikacji i routing
- Flask-Login - zarządzanie sesją użytkownika
- Flask-WTF - formularze i CSRF
- SQLite (site.db) - baza danych dołączona do repo
- Bootstrap 5 - prosty interfejs
- AlphaVantage API - aktualne kursy walut

Plik site.db został celowo dołączony, aby aplikacja działała od razu po pobraniu bez dodatkowej konfiguracji.

## Funkcjonalności
- Rejestracja i logowanie użytkownika
- Portfel walutowy użytkownika
- Dodawanie / wypłacanie posiadanych walut
- Wymiana walut oparta o aktualny kurs
- Podgląd aktualnego kursu między dowolnymi walutami
- Obsługa błędów i komunikatów (Flash Messages)
