# Kalkulator CAS

Kalkulator naukowy w przeglądarce w duchu Casio ClassPad II FX-CP400: System Algebra
Komputerowej (CAS), wykresy funkcji, macierze i statystyka. Aplikacja PWA — działa offline
po instalacji (Chrome/Edge: „Zainstaluj", iOS: Udostępnij → Do ekranu początkowego).

## Zakładki

- **KALKULATOR** — dokładne wyniki (ułamki, pierwiastki, π), DEG/RAD, liczby zespolone,
  historia, klawiatura 4-panelowa, zmienne i funkcje użytkownika (`f(x)=x^2`), komendy CAS:
  `solve`, `nsolve`, `diff`, `integrate`, `limit`, `sum`, `prod`, `expand`, `factor`,
  `simplify`, `taylor`, `odesolve`, `det([a,b;c,d])`, `inv([...])`.
- **WYKRESY** — y=f(x), krzywe parametryczne, biegunowe, równania różniczkowe y'=f(x,y)
  (Runge-Kotta 4); pan/zoom/trace; miejsca zerowe, ekstrema, przecięcia, całka, tabela wartości.
- **MACIERZE** — det, odwrotność, A·X=B, wartości własne, liczby zespolone w komórkach.
- **STATYSTYKA** — opisowa + histogram, regresje (r, R², prognoza), rozkłady
  (normalny, dwumianowy, Poissona), kombinatoryka (BigInt).

## Uruchomienie

Statycznie — wystarczy dowolny serwer HTTP (np. `python3 -m http.server`).
Testy silnika: `node tests/run-tests.js` (99 testów).

Dokumentacja funkcji: [DOKUMENTACJA-CAS.md](DOKUMENTACJA-CAS.md).

## Technologia

Vanilla JS + [mathjs](https://mathjs.org/) (Apache-2.0) i
[nerdamer](https://github.com/jiggzson/nerdamer) (MIT) — obie wbudowane w repo (`vendor/`),
offline. CAS liczy w Web Workerze z timeoutem; silnik (`js/engine.js`) współdzielony
z Node do testów.
