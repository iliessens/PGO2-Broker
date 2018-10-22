# PGO2-Broker
Broker information for PGO2

Zie ook documenten in repository-root  

__topics__:
* /votes (Qos1)
* /music (QoS2)

⚠ Indien je op een verkeerd topic pub/sub doet of met verkeerde credentials zal je vaak **geen foutmelding** krijgen. De berichten worden echter NIET verstuurd/ontvangen.  
Gebruik de mosquitto_sub en mosquitto_sub tools om te testen (beschikbaar op server A)

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

# MQTT to Mongo
Is een Node JS script dat de MQTT berichten in de MongoDB plaatst.  
Configuratie staat in config.js  
Uitvoeren met ``node server.js``  
Wordt als deamon uitgevoerd via PM2-framework.  
