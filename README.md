# 📈 Async Crypto Quantitative Trading Bot
![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-success)

## 📋 O Projekcie

Kompletny, modułowy framework do handlu algorytmicznego na rynkach kryptowalut (Binance/Bybit), napisany w nowoczesnym Pythonie z wykorzystaniem **`asyncio`**.

Projekt symuluje działanie "Mini Hedge Fundu", kładąc główny nacisk na **Zarządzanie Ryzykiem (Risk Management)** oraz **Architekturę Zdarzeniową (Event-Driven)**. System obsługuje zarówno tryb symulacji (Paper Trading), jak i handel rzeczywisty (Live Trading) z wykorzystaniem API giełd.

W przeciwieństwie do prostych skryptów, ten bot posiada oddzielne moduły do obsługi danych, logiki strategii, obliczania wielkości pozycji oraz raportowania wyników poprzez Dashboard.

---

## 🚀 Kluczowe Funkcjonalności

### 🧠 Zaawansowana Logika Tradingowa
* **Strategia Hybrydowa:** Połączenie podążania za trendem (EMA Crossover) z wykrywaniem stref wyprzedania/wykupienia (RSI).
* **Wskaźniki:** Obliczane w czasie rzeczywistym przy użyciu biblioteki `pandas-ta`.

### 🛡️ Profesjonalny Risk Management
* **Kryterium Kelly'ego:** Automatyczne dobieranie wielkości pozycji w oparciu o prawdopodobieństwo sukcesu.
* **Dynamiczna Dźwignia:** Obsługa lewarowania (np. 5x, 50x) z bezpiecznikami kapitałowymi.
* **Trailing Stop & Stop Loss:** Zabezpieczanie zysków i twarde ucinanie strat.
* **Analiza Korelacji:** Blokowanie transakcji, jeśli aktywo jest zbyt silnie skorelowane z rynkiem (np. ETH/BTC), co zapobiega nadmiernej ekspozycji.

### 🏗️ Architektura Techniczna
* **Asynchroniczność (Asyncio):** Nireblokujące pobieranie danych, obsługa bazy i wysyłanie zleceń.
* **Walidacja Danych (Pydantic):** Ścisła kontrola typów w plikach konfiguracyjnych (`config_schema.py`).
* **Trwałość Danych (Aiosqlite):** Asynchroniczny zapis transakcji i sygnałów do bazy SQLite.
* **Dashboard Analityczny:** Interaktywny panel w **Streamlit** do analizy wyników i sygnałów na żywo.
* **Powiadomienia:** Integracja z Telegramem i Discordem.

---

## 📂 Struktura Projektu

```bash
├── main.py              # Główny silnik (ExecutionBot) i pętla zdarzeń
├── strategy.py          # Logika decyzyjna (Sygnały BUY/SELL)
├── risk_manager.py      # Obliczanie wielkości pozycji i SL/TP
├── database.py          # Asynchroniczna obsługa SQLite
├── dashboard.py         # Panel wizualizacyjny (Streamlit)
├── backtest.py          # Silnik do testowania na danych historycznych
├── notifier.py          # Obsługa Telegrama i Discorda
├── config.yaml          # Główna konfiguracja (API Keys, Parametry)
└── requirements.txt     # Zależności

