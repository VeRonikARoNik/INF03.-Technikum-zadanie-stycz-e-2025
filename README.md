# INF03.-Technikum-zadanie-stycz-e-2025
Nazwa kwalifikacji: Tworzenie i administrowanie stronami i aplikacjami internetowymi oraz bazami danych
Symbol kwalifikacji: INF.03
Numer zadania: 05
Wersja arkusza: SG
e-mail na wykonane zadania:wykonanezadania100@gmail.com
```
-- Zapytanie 1: tylko plik, nr_klienta, liczba_odbitek dla matowych, gdzie liczba_odbitek > 100
SELECT plik, nr_klienta, liczba_odbitek
FROM zamowienia
WHERE rodzaj = 'matowy'
  AND liczba_odbitek > 100;

-- Zapytanie 2: dla klienta o id = 3 trzy wartości zamówień (liczba_odbitek * cena), alias "Do zapłaty"
SELECT z.id_zam,
       z.plik,
       (z.liczba_odbitek * d.cena) AS `Do zapłaty`
FROM zamowienia z
JOIN zdjecia d ON z.rodzaj = d.rodzaj
WHERE z.nr_klienta = 3
ORDER BY z.id_zam
LIMIT 3;

-- Zapytanie 3: suma wszystkich odbitek na papierze błyszczącym
SELECT SUM(liczba_odbitek) AS suma_odbitek
FROM zamowienia
WHERE rodzaj = 'błyszczący';

-- Zapytanie 4: utworzenie konta użytkownika Anna na localhost z hasłem @NNa
CREATE USER 'Anna'@'localhost' IDENTIFIED BY '@NNa';
GRANT ALL PRIVILEGES ON fotografia.* TO 'Anna'@'localhost';
FLUSH PRIVILEGES;
```
