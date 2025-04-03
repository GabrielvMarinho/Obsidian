Is an [Interface (Poo)](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Paradigms%2FOOP%2FConcepts%2FInterface%20(Poo)) in [[Spring]] [Framework](obsidian://open?vault=Obsidian&file=Tech%2FProgramming%2FProgramming%20Tools%2FFrameworks%2FFramework) to facilitate how the data is transmitted to the [FrontEnd](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FFRONT-END%2FFrontEnd), dividing in different "pages" of content, just like we see in e-commerces

we can change [Parameters](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FSoftware%20Arquitecture%2FPatterns%20of%20software%2FMicro%20Services%2FPorts) such as
1. page: the page you want to be at
2. size: how many elements for each page 
3. sort: what attribute to show the sequence of elements

the [API](obsidian://open?vault=Obsidian&file=Tech%2FSoftware%2FConcepts%2FBACK-END%2FAPI%2FAPI) is going to send a [JSON](obsidian://open?vault=Obsidian&file=Tech%2FDatabase%2FJSON) file that looks like this

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