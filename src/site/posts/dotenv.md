---
tags: ['nodejs', 'javascript']
title: Dotenv
subtitle: Libreria utile per nodejs
date: 2019-09-27
---
Un modo comodo (non il più sicuro [1]) per impostare i valori della propria applicazione è quello di impostarli nel file .env

La comodità è quella di poter escludere il file .env dai push su git così da non condividere i propri dati con il mondo e allo stesso tempo avere un unico file dove avere tutte le variabili e includere quel file per accedere alle stesse.

Un esempio di utilizzo creando i file .env e index.js

```ini
PORT=9999
```
```js
//index.js

require('dotenv').config()
const app = require('http').createServer((req, res) => res.send('Ahoy!'))
const PORT = process.env.PORT
app.listen(PORT, () => {
  console.log(`Server is listening on port ${PORT}`)
})
```

Per lanciare poi il tutto basta dare il seguente comando:

```bash
node index.js
```

Un modo alternativo senza ricorrere al caricamento di dotenv nel file index è quello di caricare il file a riga di comando come nel seguente esempio:

```ini
PORT=9999
```

```js
//index.js

const app = require('http').createServer((req, res) => res.send('Ahoy!'))
const PORT = process.env.PORT
app.listen(PORT, () => {
  console.log(`Server is listening on port ${PORT}`)
})
```

```bash
node -r dotenv/config index.js
```
Ora che abbiamo imparato a caricare le variabile di ambiente la prossima volta vediamo come poter strutturare in maniera pulita un possibile progetto


1 Un modo sicuramente più sicuro sarebbe impostare a runtime nel comando di lancio le eventuali variabili perchè sarebbero visualizzabili solo visualizzando i processi e l'eventuale "history" del terminale.
Esempio:
```bash
PORT=9999 node server.js
```