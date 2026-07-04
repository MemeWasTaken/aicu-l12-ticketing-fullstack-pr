# Backend Rules - L11

## Valori Validi

### Priority

- bassa
- normale
- alta

(Sono definite nel path: server/index.js)

### Source Channel

- email
- telefono
- chat

(Sono definiti nel path: server/index.js)

## Mapping

| priority | sourceChannel | urgencyLabel |
| --- | --- | --- |
| alta | telefono | intervento rapido |
| alta | chat | prioritario |
| alta | email | prioritario |
| normale | telefono | da gestire |
| normale | chat | da gestire |
| normale | email | standard |
| bassa | telefono | monitorare |
| bassa | chat | monitorare |
| bassa | email | monitorare |

## Dati Decisi Dal Server

- `urgencyLabel`: Viene calcolata dal server seguendo la formula "computeUrgencyLabel(priority, sourceChannel) -> urgencyLabel"
- `createdByOperatorId`: Viene preso ottenuto dal server controllando con che profilo siamo loggati (Al momento non è stata implementata l'autenticazione quindi si è già loggati dentro un utente)
- eventuali default: Se non viene specificato altrimenti priority è da impostare su bassa e sourceChannel su email

## Dati Inviati Dal Client

- `title`:
- `description`:
- `priority`:
- `sourceChannel`:

## Fuori Scope

- Autenticazione

## Regola In Forma Di Funzione

```txt
computeUrgencyLabel(priority, sourceChannel) -> urgencyLabel
```

Non duplicare questa regola nel client.
