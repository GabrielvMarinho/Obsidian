Is an [[Interface (Poo)]] in [[Spring]] [[Framework]] to facilitate how the data is transmitted to the [[FrontEnd]], dividing in different "pages" of content, just like we see in e-commerces

we can change [[Parameter]]s such as
1. page: the page you want to be at
2. size: how many elements for each page 
3. sort: what attribute to show the sequence of elements

the [[API]] is going to send a [[JSON]] file that looks like this

```json
{
    "content": [
        {
            "id": 6,
            "numero": 2,
            "titular": "eu",
            "saldo": 12313.0,
            "limite": 1000.0
        },
        {
            "id": 54,
            "numero": 3,
            "titular": "eu",
            "saldo": 12313.0,
            "limite": 1000.0
        },
        {
            "id": 3,
            "numero": 43,
            "titular": "eu",
            "saldo": 333.0,
            "limite": 9.99999999E8
        }
    ],

    "pageable": {
        "pageNumber": 0,
        "pageSize": 10,
        "sort": {
            "empty": false,
            "unsorted": false,
            "sorted": true
        },
        "offset": 0,
        "unpaged": false,
        "paged": true
    },

    "last": true,
    "totalPages": 1,
    "totalElements": 3,
    "size": 10,
    "number": 0,
    "sort": {
        "empty": false,
        "unsorted": false,
        "sorted": true
    },
    "first": true,
    "numberOfElements": 3,
    "empty": false
}
```