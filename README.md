Aplikacja Spring Boot ktróa implementuje interfejs REST API do zarządzania zasobami typu "produkt"

## ***Struktura projektu:***
- **product**
  - **product.api**
    - **product.api.request**: Zawiera klasy reprezentujące żądania HTTP, takie jak ProductRequest i UpdateProductRequest.
    - **product.api.response**: Zawiera klasy reprezentujące odpowiedzi HTTP, takie jak ProductResponse.
    - **ProductController**:  kontroler REST, który jest odpowiedzialny za zarządzanie operacjami na produktach w aplikacji.
  - **product.domain**: Zawiera klasę Product, która reprezentuje domenowy model produktu.
  - **product.repository**: Zawiera klasę odpowiedzialną za dostęp do danych ProductRepository, korzystającą ze Spring Data JPA.
  - **product.service**: Zawiera klasę ProductService, która implementuje logikę biznesową związaną z produktami.
  - **product.support**.
    - **product.support.exception**: Zawiera klasy związane z obsługą wyjątków, np. ProductExceptionSupplier.
- **shared.api.response**
  - **ErrorMessageResponse**: klasa używana w REST API do tworzenia odpowiedzi zawierających komunikaty o błędach
 
## ***Endpointy API:***
| Metoda HTTP | Endpoint                                | Opis                                                                       |
|-------------|-----------------------------------------|--------------------------------------------------------------------------------|
| POST        | /api/v1/products                        | Tworzy nowy produkt. W body przyjmuje słownik wartości w formacie JSON z kluczem "name" np: `{ "name": "First Product" }` |
| PUT         | /api/v1/products/{id}                    | Aktualizuje istniejący produkt o podanym ID.  W body przyjmuje słownik wartości w formacie JSON z kluczem "name" np: `{ "name": "First Product" }`  |
| GET         | /api/v1/products/{id}                    | Pobiera informacje o pojedynczym produkcie o podanym ID.                          |
| GET         | /api/v1/products                        | Pobiera listę wszystkich dostępnych produktów.                                  |
| DELETE      | /api/v1/products/{id}                    | Usuwa produkt o podanym ID.                                                     |
