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
