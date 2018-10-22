# PGO2-Broker
Broker information for PGO2

Zie ook documenten in repository-root  

__topics__:
* /votes (Qos1)
* /music (QoS2)

# Payload
Payload is op zich niet belangrijk voor de broker, maar we definiëren hier toch het gebruikte formaat. We gebruiken JSON met volgende velden.

__Music__
*	Titel: string
*	Artiest: string
*	Jaar: integer
*	Song id: integer

__Votes__
*	Timestamp: [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) date & time 
*	Value: integer  
    *	Up = 1
    *	Down = -1
*	Username: string
*	Id: String (UUID)
*	Song id: integer


## Voorbeeld
/votes
```
{
"timestamp": "2018-10-18T14:28:53Z",
"value": 1,
"username": "imre",
"uid": "550e8400-e29b-41d4-a716-446655440000",
"songid": 125
}
```
/music
```
{
"title" : "What is Love",
"artist" : "Haddaway",
"year" : 1993,
"songid" : 125
}

```

# Topic authentication
Vraag user en paswoord aan Imre
