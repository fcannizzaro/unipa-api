# UnipaAPI
Unipa Unofficial API from [UNIPA in tasca](https://play.google.com/store/apps/details?id=it.aranciaict.unipaintasca)

# CAS

## Authentication
```
url     -> https://cas.unipa.it/sso/v1/tickets,
method  -> POST,
body    -> { username, password }
```

## Ticket
```
url     -> Authentication.response.headers.location,
method  -> POST,
body    -> { service }
```

# Routes

```
url     -> {{service}}?ticket={{ticket}},
method  -> GET,
headers -> { Authorization="UnipaAuth {{key}}" }
```

# Key

**STUDENTI_API_KEY** = ```aq4R51jA3g4af5042yH0aWt58t4a341c34tcRa73```

**STUDENTI_SERVICE_ID** = ```2000000```

Result is (request query + **STUDENTI\_SERVICE\_ID**) encrypted with **STUDENTI\_API\_KEY** (**SHA 256**)

### Sample

```
https://studentiws.unipa.it/v2/libretto.php?lingua=ITA
to_encrypt = lingua=ITA2000000
key = 405610f9c526ac061b765f227f7d600f45d57c677003180160fc278384d10395
```

# Available Routes
@Base https://studentiws.unipa.it/v2

## Menu
```
url   -> /menu.php,
query -> { lingua	}
```

## Libretto
```
url   -> /libretto.php,
query -> { lingua	}
```

## Appelli
```
url   -> /appelli.php,
query -> { 
	lingua,
	matricola,
	cfu,
	cod_corso,
	cod_inse,
	prog_inse,
	stato 
}
```

## Messaggi
```
url   -> /messaggi.php,
query -> {
	lingua,
	ts (yyyy-mm-ddThh:mm:ssZ)
}
```

## Foto
```
url -> /fotoStudente.php,
query -> { matricola }
```

