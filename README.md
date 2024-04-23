# Rotas de consumo da api

## Buscar nome da equipe
```json
http://localhost:8080/ajuda
```
> Response body (200 OK)
```json
{
    "nomes": "Daniel, Gean, Kauan, Silvio",
    "projeto": "Canal de notícias"
}
```
___
## Buscar todas as noticias ordenado por data mais recente.
```json
http://localhost:8080/news
```
> Response body (200 OK)
```json
[
    {
        "news_id": 1,
        "news_title": "Titulo da noticias",
        "news_country": "Brasil",
        "news_date": "01/12/2024",
        "links": [
            {
                "rel": "self",
                "href": "http://localhost:8080/news/1"
            }
        ]
    },
    {
        "news_id": 2,
        "news_title": "Titulo da noticias",
        "news_country": "Brasil",
        "news_date": "01/10/2024",
        "links": [
            {
                "rel": "self",
                "href": "http://localhost:8080/news/2"
            }
        ]
    },
    {
        "news_id": 3,
        "news_title": "Titulo da noticias",
        "news_country": "Brasil",
        "news_date": "01/09/2024",
        "links": [
            {
                "rel": "self",
                "href": "http://localhost:8080/news/3"
            }
        ]
    }
]
```
___
## Buscar noticia por id unico
```json
http://localhost:8080/news/{id}
```
> Response body (200 OK)
```json
{
    "news_id": 1,
    "news_title": "Titulo da noticias",
    "news_country": "Brasil",
    "news_date": "01/12/2024",
    "links": [
        {
            "rel": "Todas as noticias",
            "href": "http://localhost:8080/news"
        }
    ]
}
```
> Exeption (404 Not Found)

````Nenhum noticia com este id````
___
## Atualizar noticia por id unico
```json
http://localhost:8080/news/{id}
```
```json
{
    "news_title":"Titulo da noticias atualizado",
    "news_country":"Brasil",
    "news_date":"01/09/2024"
}
```
> Response body (200 ok)
```json
{
    "news_id": 1,
    "news_title": "Titulo da noticias atualizado",
    "news_country": "Brasil",
    "news_date": "01/09/2024"
}
```
___
## Deletar noticia por id
```json
http://localhost:8080/news/{id}
```
> Response (204 No Content)

> Exception (404)
````Nenhum noticia com este id````
