# Rotas de consumo da api

## Buscar nome da equipe
```yml
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
## Cadastrar noticias 
```yml
http://localhost:8080/news
```
```yml
{
    "news_title":"Titulo da noticias",
    "news_country":"Brasil",
    "news_date":"01/09/2024"
}
```
> Response Body (201 Created)
```yml
{
    "news_id": 1,
    "news_title": "Titulo da noticias",
    "news_country": "Brasil",
    "news_date": "01/09/2024"
}
```
> Exceptions (400 Bad Request)

```yml
{
    "status": "BAD_REQUEST",
    "message": "Titulo não pode estar vazio."
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "País não pode estar vazio."
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "Data não pode estar vazio"
}
```
___
## Buscar todas as noticias ordenado por data mais recente.
```yml
http://localhost:8080/news
```
> Response body (200 OK)
```yml
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
```yml
http://localhost:8080/news/{id}
```
> Response body (200 OK)
```yml
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
```yml
http://localhost:8080/news/{id}
```
```yml
{
    "news_title":"Titulo da noticias atualizado",
    "news_country":"Brasil",
    "news_date":"01/09/2024"
}
```
> Response body (200 ok)
```yml
{
    "news_id": 1,
    "news_title": "Titulo da noticias atualizado",
    "news_country": "Brasil",
    "news_date": "01/09/2024"
}
```
> Exceptions (400 Bad Request)

```yml
{
    "status": "BAD_REQUEST",
    "message": "Titulo não pode estar vazio."
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "País não pode estar vazio."
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "Data não pode estar vazio"
}
```
___
## Deletar noticia por id
```yml
http://localhost:8080/news/{id}
```
> Response (204 No Content)

> Exception (404)
````Nenhum noticia com este id````
___
## Cadastrar esportes 
```yml
http://localhost:8080/sport
```
```yml
{
    "sport_title":"Titulo",
    "sport_team":"Real Madrid",
    "sport_date":"01/01/2023"
}
```
> Response Body (201 Created)
```yml
{
    "sport_id": 1,
    "sport_title": "Titulo",
    "sport_team": "Real Madrid",
    "sport_date": "01/01/2023"
}
```
> Exceptions
```yml
{
    "status": "BAD_REQUEST",
    "message": "Campo titulo não pode estar vazio"
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "Campo nome de time não pode estar vazio"
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "O campo data não pode estar nulo"
}
```
___
## Buscar todos os esportes ordenado por data da postagem
```yml
http://localhost:8080/sport
```
> Response (200 OK)
```yml
[
    {
        "sport_id": 1,
        "sport_title": "Titulo",
        "sport_team": "Real Madrid",
        "sport_date": "01/09/2023",
        "links": [
            {
                "rel": "self",
                "href": "http://localhost:8080/sport/1"
            }
        ]
    },
    {
        "sport_id": 2,
        "sport_title": "Titulo",
        "sport_team": "Real Madrid",
        "sport_date": "01/01/2023",
        "links": [
            {
                "rel": "self",
                "href": "http://localhost:8080/sport/2"
            }
        ]
    }
]
```
___
## Buscar postagem de esporte por id
```yml
http://localhost:8080/sport/{id}
```
> Response body (200 OK)
```yml
{
    "sport_id": 1,
    "sport_title": "Titulo",
    "sport_team": "Real Madrid",
    "sport_date": "01/09/2023",
    "links": [
        {
            "rel": "Lista de esportes",
            "href": "http://localhost:8080/sport"
        }
    ]
}
```
___
## Atualizar postagem de esporte por id
```yml
http://localhost:8080/sport/{id}
```
```yml
{
    "sport_title":"Titulo",
    "sport_team":"Real Madrid",
    "sport_date":"01/01/2023"
}
```
> Response body (200 OK)
```yml
{
    "sport_id": 1,
    "sport_title": "Titulo atualizado",
    "sport_team": "Real Madrid",
    "sport_date": "01/01/2023"
}
```
> Exceptions (400 Bad Request)
```yml
{
    "status": "BAD_REQUEST",
    "message": "Campo titulo não pode estar vazio"
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "Campo nome de time não pode estar vazio"
}
```
```yml
{
    "status": "BAD_REQUEST",
    "message": "O campo data não pode estar nulo"
}
```
## Deletar postagem de esporte por id
```yml
http://localhost:8080/sport/1
```
> Response (204 Not Content)
