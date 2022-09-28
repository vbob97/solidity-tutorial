# Solidity Tutorial

serve per creare smart contracts sulla blockchain di ethereum

## Dipendenze

i casi d’uso sono sostanzialmente due

- Online Remix → non ha bisogno di dipendenze
- Installare in locale

nel secondo caso abbiamo bisogno di :

- node js
- ganache → simulatore di ethereum , crea una finta blockchain per testare in locale
- truffle
- metamusk → serve per vedere i wallet di ganache

# Get Started

per prima cosa si inizializza un progetto creando una cartella, dopo di che si importa in vscode e con il terminale si lancia il seguente comando:

```bash
truffle init
```

questo comando genera 3 cartelle ed un file di configurazione js, in particolare abbiamo :

- contracts → e la cartella in cui andremo ad inserire i file .sol , che appunto saranno i file in cui andremo ad inserire il nostro codice
- migrations → andremo a scrivere un file js che ci permette di fare il deployment verso la blockchain di ganache
- test → servira per avere fail appunto di test , per controllo bug
- truffle-config.js e il file che ci serve per specificare versione di solidity e blockchain in cui vogliamo deployare

Avviare ganache, e schiacciare su quickstart → questo genererà una blockchain sul nostro pc. Analizzando la schermata principale di ganache abbiamo :

- address → identifica il public address degli account
- balance → identifica i 100 eth che possiede un account
- per ogni account si può vedere la private key di ogni account

Un ‘altro passo fondamentale è quello di settare indirizzo e porta di ganache nel file di config

in particolare si deve andare a de-commentare queasta parte:

```jsx
development: {
      host: "127.0.0.1",     // Localhost (default: none)
      port: 7545,             // Standard Ethereum port (default: none)
      network_id: "*",       // Any network (default: none)
     },
```

# WorkFlow

creiamo un contratto di prova per capire qual’è il workflow. Per prima cosa si procede con la creazione del file *“MyContract.sol”,*  in questo file non metteremo nient’altro che il nome del contract (avremo solo la definizone , niente corpo) e la versione di solidity. Abbiamo bisogno di  creare il file migration, deve avere un nome formato da un numero progressivo e deplyment…

## Interagire con il contract

per interagire con il contract per prima cosa bisogna entrare nella console di truffle digitando 

```bash
truffle console
```

una volta dentro bisognera scrivere questa cosa:

```jsx
MyContract.deployed().then(function(i){contract=i;})
```

è una promise → se questa funzione viene eseguita  quello che succede che i sara proprio il contratto di qunseguenza abbiamo creato una variabile contract nella funzione a cui andiamo ad assegnare il contratto mycontract
