# SYLWESTER z Jagiellońska – 2025/2026

Statyczna strona zbudowana w HTML + Tailwind CSS + vanilla JS. Strona wyświetla wspólną listę uczestników oraz pozwala w prosty sposób dopisać się do listy bez potrzeby stawiania serwera.

## Wspólna lista

- Lista uczestników przechowywana jest w publicznym dokumencie JSON na `jsonblob.com`.
- Aktualny endpoint: `https://jsonblob.com/api/jsonBlob/1429230376525684736`.
- Strona cyklicznie (co 15 s) odświeża dane z tego endpointu, a przy dodawaniu/usuwaniu pozycji zapisuje zaktualizowany JSON przez żądanie `PUT`.
- Jeśli chcesz zacząć „od zera”, utwórz nowy blob:

  ```bash
  curl -s -D - -X POST \
    -H "Content-Type: application/json" \
    -d '{"people":[]}' \
    https://jsonblob.com/api/jsonBlob
  ```

  W odpowiedzi nagłówek `Location` wskaże nowy adres. Podmień go w `index.html` w stałej `DATA_URL`.

## Uruchomienie lokalne

Strona jest w pełni statyczna – wystarczy otworzyć `index.html` w przeglądarce lub udostępnić ją na GitHub Pages.
