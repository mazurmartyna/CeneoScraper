# CeneoScraper

## Kod produktu do testów

## Algorytm pobierania opinii o produkcie z serwisu Ceneo
1. Wysłanie żądania dostępu do strony Internetowej z opiniami o produkcie
2. Jeżeli operacja zakończy się pozytywnie, wyodrębnienie z kodu strony opinii o produkcie
3. Dla każdej opinii wyodrębnienie z kodu HTML poszczególnych składowych i przypisanie ich do elementów złożonej struktury danych
4. Jesli istnieje kolejna strona z opiniami, przejście do niej i powtórzenie dla niej kroków 1-4
5. Zapisanie wyników do bazy danych 

## Struktura opinii w serwisie Ceneo.pl
|składowa|zmienna|selektor|
|--------|-------|--------|
|opinia|review|div.js_product-review|
|identyfikator opinii|review_id|['data-entry-id']|
|autor|author|span.user-post__author-name|
|rekomendacja|recommendation|span.user-post__author-recomendation > em|
|liczba gwiazdek|stars|span.user-post__score-count|
|treść opinii|content|div.user-post__text|
|listę zalet|pros|div.review-feature__item--positive|
|listę wad|cons|div.review-feature__item--negative|
|ile osób uznało opinię za przydatną|useful|button.vote-yes > span|
|ile osób uznało opinię za nieprzydatną|unuseful|button.vote-no > span|
|data wystawienia opinii|review_date|span.user-post__published > time::nth-child(1)['datetime']|
|data zakupu produktu|purchase_date|span.user-post__published > time::nth-child(2)['datetime']|

