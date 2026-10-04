# PROBLEM STATEMENT

**Corso di Ingegneria del Software**  
**Candidato:** Antonio Galdo  
**Data:** 4 ottobre 2026

**Titolo Proposto:** *Agency - Sistema gestionale per agenzie di viaggi (specializzate in gruppi)*

---

## Schema

## 1) Dominio del problema

Il progetto ha come obiettivo la progettazione e lo sviluppo di **"Agency"**, un sistema software gestionale ideato per digitalizzare l'intera operatività di un'agenzia di viaggi. Poiché il core business dell’azienda è l'organizzazione e la vendita di **viaggi di gruppo**, il sistema mira a centralizzare e automatizzare il flusso di lavoro che va dalla vendita del pacchetto turistico fino alla reportistica contabile.

Il sistema in essere manca di alcune funzionalità, in particolare del **report contabile**, e presenta delle pecche strutturali che non permettono l'aggiunta e la correzione di alcune funzionalità. È quindi necessario riprogettare il sistema.

Attualmente il sistema:

- **Manca totalmente di un report contabile**, che permetta di visualizzare:
  - le entrate generali di ogni viaggio;
  - le entrate generali dell'azienda;
  - l'inserimento dei costi dei fornitori riferiti ai singoli viaggi;
  - il calcolo del markup di ogni viaggio;
  - il markup medio di tutti i viaggi.

- **Non permette la visione dettagliata di un programma**, attraverso una lista unica contenente:
  - il nome dei partecipanti;
  - i servizi scelti da ogni cliente.

Questo approccio risulta inefficiente in quanto l'azienda, per la parte di reportistica, fa uso di un programma esterno con conseguente duplicazione dei dati: vengono infatti riscritti i dettagli del viaggio, le entrate, gli acconti dei clienti versati e il saldo dei clienti. A questi dati vengono poi integrati i costi al fine di conoscere il markup del viaggio.

Risulta inefficiente inoltre la gestione dei dettagli del viaggio, in quanto gli operatori, attualmente, per conoscere i servizi scelti da ogni cliente devono entrare nella vista del singolo cliente, rendendo il processo lento.

Si rende necessaria la progettazione ex-novo di un sistema integrato, **"Agency"**, che sostituisca l'attuale gestionale, eliminando la necessità di software esterni per la contabilità e ottimizzando l'accesso ai dati operativi per ridurre i tempi di gestione.

---

## 2) Scenari

> Tutti gli scenari possibili avvengono sempre dopo che l’operatore entra nel sistema.

### Scenario 1: Vendita pacchetto e gestione organizzativa

Un cliente entra in agenzia per prenotare il viaggio di gruppo **"Capodanno a Parigi"**, precedentemente creato nel sistema.

L'operatore cerca il cliente tramite una barra di ricerca (nome/email); se non esiste, inserisce rapidamente la nuova anagrafica.

L'operatore seleziona il pacchetto, aggiunge i passeggeri (con relative preferenze per le camere) e registra l'acconto versato.

Immediatamente, il sistema aggiorna la lista passeggeri e la rooming list del viaggio, permettendo al reparto logistica di avere la lista completa e dettagliata in tempo reale con un solo click.

### Scenario 2: Controllo redditività del viaggio

Il manager entra nel dettaglio del viaggio **"Capodanno a Parigi"**.

Visualizza una dashboard dinamica (**Report di Viaggio**) che ha già calcolato automaticamente il totale delle entrate (acconti e saldi dei contratti).

Il manager inserisce i costi sostenuti verso i fornitori (es. costo hotel, costo bus, aerei).

Il sistema calcola istantaneamente il margine netto (**markup**) del singolo viaggio.

Successivamente, passando alla vista **"Reportistica Annuale"**, il manager visualizza il markup medio di tutti i viaggi dell'anno.

---

## 3) Requisiti funzionali

Per soddisfare le esigenze dell’azienda, il sistema dovrà gestire le seguenti macro-aree:

- **Gestione contrattuale e pagamenti:**  
  Creazione automatizzata del contratto per il cliente, comprensivo del dettaglio dei servizi scelti, dell'anagrafica dei partecipanti associati alla prenotazione e del tracciamento dello stato dei pagamenti (acconti e saldi).

- **Logistica e organizzazione del viaggio:**  
  Raccolta dati per ogni singolo viaggio, includendo la generazione delle liste passeggeri, l'esportazione delle liste camere per le strutture alberghiere (rooming list) e il tracciamento dei servizi o escursioni opzionali selezionati.

- **Reportistica di singolo viaggio:**  
  Generazione di un report per ogni viaggio, con il calcolo automatico delle performance economiche (somma delle entrate, totale delle uscite verso i fornitori, numero di contratti stipulati e margine di guadagno netto).

- **Reportistica aziendale (Annuale):**  
  Aggregazione dei dati finanziari globali per fornire una panoramica sulle entrate totali, le uscite complessive e la percentuale di margine operativo generato dall'agenzia.

---

## 4) Requisiti non funzionali

- **Usabilità:**  
  L'interfaccia deve ridurre il numero di click necessari per visualizzare i dettagli di un viaggio rispetto al sistema precedente, attraverso una visualizzazione centralizzata.

- **Sicurezza (Controllo Accessi):**  
  Il sistema deve garantire un accesso basato sui ruoli. Solo gli utenti con ruolo **"Manager"** possono accedere ai moduli di reportistica contabile e visualizzare i markup, mentre gli operatori avranno accesso in lettura/scrittura alla parte logistica e contrattuale.

- **Integrità dei dati:**  
  Le modifiche a contratti o pagamenti pregressi devono riflettersi automaticamente e in tempo reale sui report contabili annuali.

---

## 5) Ambiente di destinazione

- **Architettura:** Applicazione Web (architettura Client-Server).

  Sarà accessibile da qualsiasi postazione (PC o tablet dell'agenzia) tramite un browser web (Chrome), senza necessità di installazione di software locale.

---

## 6) Risultati attesi e scadenze

- **Risultati attesi:** Integrazione della parte contabile e riduzione dei tempi necessari per la visualizzazione dei dettagli del viaggio.

- **Scadenza:** Sarà inserita prossimamente.
