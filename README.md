# Lab9-10 - Programowanie współbieżne w Javie

## Opis projektu

To repozytorium zawiera implementację zadań programistycznych mających na celu rozwinięcie umiejętności programowania w języku Java, ze szczególnym naciskiem na programowanie wielowątkowe i komunikację sieciową typu klient-serwer.

## Struktura projektu

Repozytorium składa się z trzech głównych modułów:

### 1. Lab9 - Przetwarzanie obrazów z wykorzystaniem wielowątkowości

Aplikacja demonstrująca różne podejścia do przetwarzania obrazów z wykorzystaniem wielowątkowości w Javie.

**Główne funkcjonalności:**
- Wczytywanie i zapisywanie obrazów w różnych formatach (JPG, PNG)
- Regulacja jasności obrazu z wykorzystaniem różnych technik wielowątkowości:
  - Przetwarzanie jednowątkowe (baseline)
  - Przetwarzanie wielowątkowe z ręcznym zarządzaniem wątkami
  - Przetwarzanie z wykorzystaniem puli wątków (ExecutorService)
- Obliczanie histogramu kanałów kolorów obrazu (R/G/B)
- Generowanie wizualizacji histogramu
- Pomiar i porównanie wydajności różnych podejść

**Pliki:**
- `Main.java` - punkt wejścia programu, demonstracja różnych technik przetwarzania
- `ImageHandler.java` - klasa implementująca wszystkie operacje na obrazach

**Wykorzystane technologie:**
- Java AWT i ImageIO do operacji na obrazach
- Wielowątkowość z użyciem Thread i ExecutorService
- Synchronizacja wątków

### 2. ServerApp - Serwer TCP z obsługą wielu klientów

Implementacja wielowątkowego serwera TCP umożliwiającego równoczesną obsługę wielu klientów.

**Główne funkcjonalności:**
- Nasłuchiwanie na połączenia przychodzące (port 8080)
- Tworzenie osobnego wątku dla każdego podłączonego klienta
- Broadcast wiadomości - rozsyłanie otrzymanych wiadomości do wszystkich podłączonych klientów
- Zarządzanie listą aktywnych połączeń

**Pliki:**
- `Main.java` - uruchomienie serwera
- `Server.java` - główna klasa serwera z metodą listen() i broadcast()
- `ClientThread.java` - wątek obsługujący pojedynczego klienta

### 3. ClientApp - Klient TCP

Aplikacja kliencka do komunikacji z serwerem.

**Główne funkcjonalności:**
- Nawiązywanie połączenia z serwerem (localhost:8080)
- Wysyłanie wiadomości wprowadzonych przez użytkownika
- Odbieranie i wyświetlanie wiadomości od serwera
- Obsługa komunikacji w osobnym wątku

**Pliki:**
- `Main.java` - punkt wejścia aplikacji klienckiej z obsługą wejścia użytkownika
- `ClientThread.java` - wątek zarządzający połączeniem z serwerem

## Wymagania

- Java Development Kit (JDK) 8 lub nowszy
- Plik obrazu `obraz.jpg` w katalogu lab9 (dla demonstracji przetwarzania obrazów)

## Uruchomienie

### Lab9 - Przetwarzanie obrazów
```bash
cd lab9/src
javac *.java
java Main
```

### ServerApp i ClientApp
1. Uruchom serwer:
```bash
cd serverApp/src
javac *.java
java Main
```

2. Uruchom klienta (w osobnym terminalu):
```bash
cd clientApp/src
javac *.java
java Main
```

## Cele edukacyjne

Projekt został stworzony jako zadanie laboratoryjne mające na celu:
- Naukę programowania wielowątkowego w Javie
- Zrozumienie różnic między różnymi podejściami do wielowątkowości
- Praktyczne zastosowanie ExecutorService i ThreadPool
- Implementację komunikacji sieciowej TCP
- Budowanie aplikacji klient-serwer
- Zarządzanie zasobami współdzielonymi i synchronizację wątków
- Pomiar i porównanie wydajności różnych rozwiązań

## Autor

Projekt wykonany w ramach zajęć laboratoryjnych z programowania.
