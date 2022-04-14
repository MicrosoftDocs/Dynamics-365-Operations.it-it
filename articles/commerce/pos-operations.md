---
title: Operazioni POS online e offline
description: In questo argomento vengono forniti i dettagli relativi alle operazioni POS in Dynamics 365 Commerce. Specifica dove è possibile richiamare le operazioni nell'applicazione e se sono disponibili in modalità offline.
author: jblucher
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2017-09-27
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 141b57586f5c4588b0b33bd85b584e570e39902f
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462499"
---
# <a name="online-and-offline-point-of-sale-pos-operations"></a>Operazioni POS online e offline

[!include [banner](includes/banner.md)]

La maggior parte delle azioni che gli utenti eseguono nel POS sono considerate operazioni. Le operazioni vengono configurate e gestite nel back office di Dynamics 365 Commerce. Molte operazioni possono essere aggiunte ai pulsanti nella griglia dei pulsanti POS. Gli utenti possono quindi selezionare i pulsanti per richiamare le operazioni ed eseguirne la funzione. Altre operazioni fanno parte dell'applicazione POS principale e vengono richiamate mediante pulsanti sullo schermo o come parte di altri flussi di lavoro o processi.

Nella seguente tabella vengono forniti i dettagli relativi alle operazioni disponibili in Modern POS e POS cloud. La tabella specifica anche dove è possibile richiamare le operazioni nell'applicazione e se sono disponibili quando il POS è in modalità offline.

Alcune operazioni non sono attualmente disponibili in Modern POS o POS cloud. Alcune di queste operazioni sono specifiche dell'applicazione e richiedono ulteriori estensioni e una configurazione aggiuntiva. Altre sono funzionalità di Microsoft Dynamics AX 2012 attualmente non supportate.

Nelle colonne seguenti viene indicato dove è possibile richiamare le operazioni:

- **Griglia dei pulsanti** - L'operazione può essere assegnata ai pulsanti nelle griglie di pulsanti POS, che sono parte di un layout schermo POS.
- **Schermata delle transazioni** - L'operazione può essere richiamata dalle griglie dei pulsanti POS configurate nella schermata delle transazioni POS.
- **Schermata di benvenuto** - L'operazione può essere richiamata dalle griglie dei pulsanti POS configurate nella schermata di benvenuto POS.

> [!NOTE]
> Le operazioni elencate di seguito vengono applicate all'ultima versione di Commerce. È possibile che alcune operazioni siano state modificate o che non siano disponibili nelle versioni precedenti.


| ID | Operazione | Descrizione | Griglia dei pulsanti | Schermata transazione | Schermata di benvenuto | Disponibile offline | Specifica dell'applicazione |
|----|-----------|-------------|-------------|--------------------|----------------|-------------------|-----------------|
| 707 | Attiva dispositivo | Attiva il dispositivo corrente consentendo a un utente autenticato di fornire informazioni sulla connessione e di assegnare un ID dispositivo e registratore. | No | No | No | No | No |
| 134 | Aggiungi rapporto | Consente di aggiungere un rapporto preselezionato a una transazione. Selezionare il rapporto nella pagina **Proprietà pulsanti**. | Sì | Sì | No | Sì | No |
| 135 | Aggiungi rapporto dall'elenco | Consente di aggiungere un rapporto a una transazione selezionandolo in un elenco. | Sì | Sì | Sì | Sì | No |
| 137 | Aggiungere un rapporto a un cliente | Aggiungere un rapporto a un cliente nella pagina **Dettagli cliente**. | No | No | No | Sì | No |
| 138 | Rimuovere il rapporto dal cliente | Rimuovere un rapporto da un cliente nella pagina **Dettagli cliente**. | No | No | No | Sì | No |
| 643 | Aggiungi codice buono sconto | Consente di aggiungere un buono sconto immettendone il codice nel POS. | Sì | Sì | No | Sì | No |
| 141 | Aggiungi spese intestazione | Aggiungere spese varie all'intestazione dell'ordine. | Sì | Sì | No | No| No |
| 141 | Aggiungi spese riga | Aggiungere spese varie a una riga di vendita selezionata. | Sì | Sì | No | No| No |
| 117 | Aggiungi carta fedeltà | Richiede all'utente di immettere un numero di carta fedeltà che verrà aggiunta alla transazione corrente. | Sì | Sì | No | Sì | No |
| 136 | Aggiungi numero di serie | Questa operazione consente all'utente di specificare un numero di serie per il prodotto attualmente selezionato. | Sì | Sì | No | Sì | No |
| 1214 | Aggiungi indirizzo di spedizione | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 519 | Aggiungi alla gift card | Aggiunge denaro alla gift card specificata. | Sì | Sì | No | No | No |
| 6000 | Consenti di ignorare la registrazione fiscale | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 1212 | Deposito bancario | Registra la somma di denaro inviata alla banca insieme ad altre informazioni, ad esempio il numero di busta per trasporto valori. | Sì | Sì | Sì | Sì | No |
| 923 | Verifica totali banca | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 915 | Operazione vuota | Questa operazione rappresenta un pulsante personalizzabile che uno sviluppatore di software può modificare a livello di codice per associarlo a un'operazione specifica richiesta dall'azienda. | Sì | Sì | Sì | Sì | No |
| 1053 | Chiusura forzata turno | Imposta la chiusura forzata per il turno corrente e disconnette l'utente. Un turno con chiusura forzata viene chiuso per ulteriori transazioni ma rimane aperto per le operazioni relative al cassetto, ad esempio rimozione del metodo di pagamento e riepilogo incassi. | Sì | Sì | Sì | No | No |
| 310 | Calcola totale | Quando il calcolo dello sconto viene ritardato, questa operazione avvia il calcolo per la transazione corrente. | Sì | Sì | No | Sì | No |
| 642 | Esegui tutti i prodotti | Imposta la modalità di consegna per tutte le righe su **Esegui**. | Sì | Sì | No | Sì\* | No |
| 641 | Esegui prodotti selezionati | Imposta la modalità di consegna per le righe selezionate su **Esegui**. | Sì | Sì | No | Sì\* | No |
| 647 | Modifica modalità di consegna | Cambiare modalità di consegna per le righe di vendita di spedizione preconfigurate. | Sì | Sì | No | No| No |
| 1215 | Modifica password | Questa operazione consente all'utente del POS di modificare la propria password. | Sì | Sì | Sì | No | No |
| 123 | Modifica unità di misura | Modifica l'unità di misura per la voce selezionata. | Sì | Sì | No | Sì | No |
| 639 | Cancella rappresentante predefinito su transazione | Rimuove il gruppo di vendite con provvigione (rappresentante) dalla transazione. | Sì | Sì | No | Sì | No |
| 106 | Cancella quantità | Reimposta la quantità della riga correntemente selezionata su **1**. | Sì | Sì | No | Sì | No |
| 640 | Cancella rappresentante su riga | Rimuove il gruppo di vendite con provvigione (rappresentante) dalla riga correntemente selezionata. | Sì | Sì | No | Sì | No |
| 121 | Cancella venditore | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 1055 | Chiudi turno | Chiude il turno corrente, stampa un Z-report e disconnette l'utente dal sistema. | Sì | Sì | Sì | No | No |
| 139 | Concludi transazione | Invita l'utente a selezionare il metodo di pagamento | Sì | Sì | No | Sì | No |
| 925 | Copia assegno bancario | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 620 | Crea ordine cliente | Converte la transazione POS in un ordine cliente | Sì | Sì | No | Sì\* | No |
| 621 | Crea offerta | Converte la transazione POS in un'offerta di vendita. | Sì | Sì | No | Sì\* | No |
| 636 | Crea transazione di vendita al dettaglio | Creare una transazione di vendita standard quando il comportamento predefinito del POS è di creare ordini cliente. | Sì | Sì | No | Sì | No |
| 600 | Cliente | Aggiunge il cliente specificato alla transazione. | No | No | No | Sì | No |
| 1100 | Deposito sul conto cliente | Effettuare un pagamento sul conto del cliente. | Sì | Sì | Sì | Sì | Sì |
| 612 | Aggiunta cliente | Creare un nuovo record cliente. | Sì | Sì | Sì | Sì† | No |
| 603 | Cancellazione cliente | Rimuove il cliente dalla transazione corrente. | Sì | Sì | No | Sì | No |
| 602 | Ricerca cliente | Cercare un record cliente accedendo alla pagina di ricerca di clienti nel POS. | Sì | Sì | Sì | Sì | No |
| 609 | Transazioni cliente | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 917 | Stato di connessione al database | Visualizzare le impostazioni di connessione correnti e di passare dalla modalità online a quella offline e viceversa. | Sì | Sì | Sì | Sì | No |
| 1200 | Dichiara importo iniziale | Dichiara l'importo iniziale nel cassetto a inizio giornata o turno. | Sì | Sì | Sì | Sì | No |
| 132 | Sostituzione deposito | Sostituisce il deposito predefinito per gli ordini cliente. | Sì | Sì | No | Sì\* | No |
| 913 | Disabilitazione modalità progettazione | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 912 | Abilitazione modalità progettazione | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 1217 | Disassembla kit | Disassemblare un kit nei relativi prodotti componenti. | Sì | Sì | Sì | Sì | No |
| 624 | Visualizzare gli importi dei rimborsi | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 513 | Visualizza totale | Visualizza il saldo della transazione sullo schermo del cliente. | Sì | Sì | Sì | Sì | No |
| 623 | Modifica cliente | Modifica i dettagli del cliente corrente. | Sì | Sì | No | No | No |
| 614 | Modifica ordine cliente | Richiama l'ordine selezionato in modo da poterlo modificare nel POS. | No | No | No | No | No |
| 615 | Modifica offerta | Richiama l'offerta selezionata in modo da poterla modificare nel POS. | No | No | No | No | No |
| 518 | Conti spese | Registra il denaro rimosso dal cassetto della cassa per le spese occasionali. | Sì | Sì | Sì | Sì | No |
| 919 | Accesso esteso | Assegna o rimuove l'autorizzazione all'accesso tramite la scansione di un codice a barre o il passaggio di una carta. | Sì | Sì | Sì | Sì | No |
| 1201 | Immissione fondo cassa | Aggiungere ulteriore denaro al cassetto o al turno corrente. | Sì | Sì | Sì | Sì | No |
| 1218 | Sblocca forzatamente periferica | Il sistema utilizza questa operazione internamente per sbloccare le periferiche POS. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 520 | Saldo gift card | Visualizza il saldo di una gift card. | Sì | Sì | No | No | No |
| 708 | Disattiva dispositivo | Disattiva il dispositivo corrente, in modo che non possa essere utilizzato come registratore di cassa POS. | No | No | No | No | No |
| 804 | Operazione in entrata | Accedere alle funzionalità di gestione del magazzino del negozio in entrata. | Sì | No | Sì | No| No |
| 517 | Conti ricavi | Registra il denaro messo nel cassetto della cassa per motivi diversi dalla vendita. | Sì | Sì | Sì | Sì | No |
| 801 | Ricerca in magazzino | Cerca le quantità disponibili, in ordinazione e available-to-promise (ATP) per il punto vendita corrente e altre ubicazioni disponibili. | Sì | Sì | Sì | Numero | Numero |
| 806 | Rettifica scorte | Adeguare le scorte in entrata o in uscita dal magazzino del punto vendita utilizzando la rettifica o il giornale di registrazione movimento. | Sì | Sì | Sì | Numero | Numero |
| 807 | Movimento scorte | Spostare gli articoli da un'ubicazione a un'altra in un magazzino del punto vendita. | Sì | Sì | Sì | Numero | Numero |
| 122 | Commento sulla fattura | Immettere un commento sulla transazione corrente. | Sì | Sì | No | Sì | No |
| 511 | Emetti nota credito | Emette una nota di credito per fornire un giustificativo anziché un rimborso. | Sì | Sì | No | No | No |
| 512 | Emetti gift card | Emette una nuova gift card per l'importo specificato. | Sì | Sì | No | No | No |
| 625 | Rilascia carta fedeltà | Emette una carta fedeltà a un cliente in modo che il cliente possa partecipare al programma fedeltà del punto vendita. | Sì | Sì | Sì | No | No |
| 300 | Importo sconto riga | Consente di immettere l'importo di uno sconto per una voce nella transazione. Questa operazione riguarda unicamente gli articoli scontabili e l'importo non può superare i limiti di sconto specificati. | Sì | Sì | No | Sì | No |
| 301 | Percentuale sconto riga | Consente di immettere una percentuale di sconto per una voce nella transazione. Questa operazione riguarda unicamente gli articoli scontabili e l'importo non può superare i limiti di sconto specificati. | Sì | Sì | No | Sì | No |
| 703 | Blocca registratore di cassa | Blocca il registratore corrente di modo che non possa essere utilizzato, ma non disconnette l'utente corrente. | No | No | No | Sì | No |
| 701 | Disconnessione | Disconnette l'utente corrente dal registratore di cassa. | Sì | Sì | Sì | Sì | No |
| 521 | Saldo punti carta fedeltà | Visualizza il saldo dei punti per la carta fedeltà specificata. | Sì | Sì | No | No | No |
| 142 | Gestisci spese | Visualizzare e gestire le spese varie applicate alla transazione. | Sì | Sì | No | No| No |
| 918 | Gestisci turni | Visualizza un elenco di turni attivi, sospesi e con chiusura forzata. | Sì | Sì | Sì | No | No |
| 914 | Riduci a icona la finestra POS | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 1000 | Apri cassetto | Esegue un'operazione "senza vendita" e apre il cassetto attualmente selezionato. | Sì | Sì | Sì | Sì | No |
| 928 | Evasione ordine | Questa operazione consente agli utenti di prelevare, imballare, spedire o richiamare gli ordini per il punto vendita scelto. | Sì | Sì | Sì | No | No |
| 805 | Operazioni in uscita | Accedere alle funzionalità per la gestione delle spedizioni degli ordini di trasferimento in uscita. | Sì | No | Sì | No| No |
| 129 | Forza imposta prodotto riga | Sostituisce l'imposta sulla voce selezionata con un'imposta specificata diversa. | Sì | Sì | No | Sì | No |
| 130 | Forza imposta prodotto riga dall'elenco | Consente di sostituire l'imposta sulla voce selezionata con un'imposta che l'utente seleziona in un elenco. | Sì | Sì | No | Sì | No |
| 127 | Forza imposta di transazione | Sostituisce l'imposta sulla transazione con un'imposta specificata diversa. | Sì | Sì | No | Sì | No |
| 128 | Forza imposta di transazione dall'elenco | Sostituisce l'imposta sulla transazione con l'imposta che l'utente seleziona in un elenco. | Sì | Sì | No | Sì | No |
| 131 | Documento di trasporto | Crea un documento di trasporto per l'ordine selezionato. | No | No | No | No | No |
| 710 | Associa stazione hardware | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 201 | Pagamento con carta | Accetta una carta di credito o debito come metodo di pagamento. | Sì | Sì | No | Sì | No |
| 200 | Pagamento in contanti | Accetta i contanti come metodo di pagamento. | Sì | Sì | No | Sì | No |
| 206 | Pagamento quick cash | Completa la transazione in un singolo tocco e accetta l'importo dovuto in contanti (importo esatto). | Sì | Sì | No | Sì | No |
| 204 | Pagamento con assegno | Consente di accettare un assegno come metodo di pagamento. | Sì | Sì | No | Sì | No |
| 213 | Pagamento con nota credito | Accetta una nota di credito (giustificativo) emessa dal punto vendita. | Sì | Sì | No | No | No |
| 203 | Pagamento in valuta | Consente di accettare il pagamento in varie valute. | Sì | Sì | No | Sì | No |
| 202 | Pagamento in conto cliente | Effettua l'addebito della transazione sul conto del cliente. Questo metodo di pagamento non è valido per i depositi ordine cliente. | Sì | Sì | No | No | No |
| 214 | Pagamento con gift card | Accetta una gift card emessa dal punto vendita. | Sì | Sì | No | No | No |
| 207 | Pagamento con carta fedeltà | Accetta una carta fedeltà per il pagamento e riscatta i punti per i prodotti qualificati. | Sì | Sì | No | No | No |
| 634 | Storico pagamenti | Visualizza lo storico pagamenti del cliente per l'ordine cliente corrente. | Sì | Sì | No | No | No |
| 803 | Prelievo e ricevimento | Apre la pagina **Prelievo e ricevimento**, in cui è possibile selezionare gli ordini da prelevare o ricevere nel punto vendita. | Sì | Sì | Sì | No | No |
| 632 | Preleva tutti i prodotti | Imposta il metodo di evasione su **Ritiro presso punto vendita** per tutte le righe. | Sì | Sì | No | Sì\* | No |
| 631 | Preleva prodotti selezionati | Imposta il metodo di evasione su **Ritiro presso punto vendita** per tutte le righe selezionate. | Sì | Sì | No | Sì\* | No |
| 400 | Menu a comparsa | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 101 | Controllo del prezzo | Questa operazione consente all'utente di cercare il prezzo di un determinato prodotto. | Sì | Sì | Sì | Sì | No |
| 104 | Forzatura prezzo | Consente la forzatura del prezzo di un prodotto, se tale prodotto è stato configurato per consentire tale operazione. | Sì | Sì | No | Sì | No |
| 1058 | Stampa X fiscale | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 1059 | Stampa Z fiscale | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 927 | Stampa etichetta articolo | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 926 | Stampa etichetta scaffale | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 1056 | Stampa X | Stampa un X-report per il turno corrente. | Sì | Sì | Sì | No | No |
| 103 | Commento sul prodotto | Aggiunge un commento alla voce selezionata nella transazione. | Sì | Sì | No | Sì | No |
| 100 | Vendita prodotto | Aggiunge un prodotto specificato alla transazione. | Sì | Sì | Sì | Sì | No |
| 108 | Ricerca prodotto | Cercare un prodotto accedendo alla pagina di ricerca di prodotti nel POS. | Sì | Sì | Sì | Sì | No |
| 633 | Data di scadenza offerta | Visualizzare o modificare la data di scadenza di un'offerta di vendita. | Sì | Sì | No | Sì\* | No |
| 627 | Ricalcola | Ricalcola tutte le righe e le imposte dell'ordine cliente in base alla configurazione corrente. | Sì | Sì | No | Sì\* | No |
| 143 | Ricalcola addebiti | Ricalcolare gli addebiti automatici applicati all'ordine. | Sì | Sì | No | No| No |
| 515 | Richiama ordine | Cercare e richiamare ordini cliente e offerte di vendita. | Sì | Sì | Sì | No | No |
| 504 | Richiama transazione | Richiamare una transazione sospesa in precedenza dal punto vendita corrente. | Sì | Sì | No | Sì‡ | No |
| 305 | Riscatta punti fedeltà | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 635 | Rimborso spese di spedizione | Rimborsare le spese di spedizione per un ordine annullato. | No | No | No | No | No |
| 644 | Rimuovi codice buono sconto | Richiede all'utente di rimuovere i buoni sconto selezionandoli in un elenco di buoni sconto attualmente associati alla transazione. | Sì | Sì | No | Sì | Numero |
| 1057 | Ristampa Z | Ristampa il report Z per il turno precedente. | Sì | Sì | Sì | Numero | Numero |
| 1216 | Immettere una nuova password | Questa operazione consente a un utente che dispone di autorizzazioni per la reimpostazione della password di reimpostare la password di un altro dipendente utilizzando una password temporanea. | Sì | Sì | Sì | No | No |
| 1219 | Aprire un URL nel POS | Aprire un URL configurato dall'amministratore in POS. | Sì | Sì | Sì | Sì | No |
| 109 | Reso prodotto | Consente di effettuare un reso di singoli prodotti. Il prodotto letto tramite scanner successivo viene visualizzato come prodotto reso con un prezzo e una quantità negativi. | Sì | Sì | No | Sì | No |
| 114 | Transazione di reso | Richiama una transazione precedente in base al relativo numero di ricevuta per restituire alcuni o tutti i prodotti. | Sì | Sì | Sì | Sì§ | No |
| 1211 | Deposito in cassaforte | Esegue un deposito in cassaforte per il trasferimento di denaro dal registratore di cassa a una cassaforte. | Sì | Sì | Sì | Sì | No |
| 516 | Fattura di vendita | Questa operazione consente al cliente di effettuare i pagamenti per la fattura di vendita selezionata. | Sì | Sì | No | No | No |
| 502 | Venditore | Impostare il valore di **Incaricato vendite** in un ordine cliente per gli ordini cliente nel POS. | Sì | Sì | No | Sì\* | No |
| 2000 | Gestione programmazione | Questa operazione non è ancora supportata. | Sì | Sì | Sì | No | No |
| 2001 | Richieste di programmazione | Questa operazione non è ancora supportata. | Sì | Sì | Sì | No | No |
| 622 | Cerca ordini | Questa operazione consente agli utenti di preconfigurare i pulsanti del POS per eseguire ricerche per articolo, cliente o categoria. | Sì | Sì | Sì | Sì | No |
| 1213 | Cerca indirizzo di spedizione | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 709 | Seleziona hardware station | Selezionare una stazione hardware in un elenco di stazioni hardware disponibili. | Sì | Sì | Sì | Sì | No |
| 637 | Imposta rappresentante predefinito su transazione | Selezionare uno dei gruppi vendite con provvigione (rappresentanti) come rappresentante predefinito per le righe aggiunte successivamente. | Sì | Sì | No | Sì | No |
| 105 | Imposta quantità | Modifica la quantità di una voce nella transazione. | Sì | Sì | No | Sì | No |
| 638 | Imposta rappresentante su riga | Selezionare uno dei gruppi vendite con provvigione (rappresentanti) per la riga correntemente selezionata. | Sì | Sì | No | Sì | No |
| 630 | Spedisci tutti i prodotti | Imposta la modalità di evasione su **Spedizione** per tutte le voci. | Sì | Sì | No | Sì\* | No |
| 629 | Spedisci prodotti selezionati | Imposta la modalità di evasione su **Spedizione** per tutte le righe selezionate. | Sì | Sì | No | Sì\* | No |
| 115 | Mostra giornale di registrazione | Visualizza il giornale di registrazione del punto vendita. È possibile visualizzare le transazioni, ristampare le ricevute, incluse quelle di gift card, e richiamare i resi. | Sì | Sì | Sì | Sì\*\* | No |
| 802 | Conteggio scorte | Creare o modificare i giornale di registrazione del conteggio scorte per l'inventario fisico o i conteggi di ciclo. | Sì | Sì | Sì | No | No |
| 401 | Sottomenu | Questa operazione consente di accedere a un'altra griglia di pulsanti collegati. | Sì | Sì | Sì | Sì | No |
| 1054 | Sospendi turno | Sospende il turno corrente, di modo che un turno nuovo o diverso possa essere attivato nel registratore di cassa corrente. | Sì | Sì | Sì | No | No |
| 503 | Sospendi transazione | Sospende la transazione di vendita corrente, di modo che possa essere richiamata in seguito nel punto vendita. | Sì | Sì | No | Sì‡ | No |
| 1004 | Registrazione attività | Apre Registrazione attività per registrare passaggi procedurali nel POS. | No | No | No | Sì | No |
| 1052 | Riepilogo incassi | Specificare la quantità di denaro nel cassetto per ogni metodo di pagamento conteggiato. | Sì | Sì | Sì | Sì | No |
| 1210 | Rimozione metodo di pagamento | Rimuovere denaro dal cassetto o dal turno corrente. | Sì | Sì | Sì | Sì | No |
| 920 | Orologio | Marcare le entrate e le uscite durante i turni di lavoro e le pause. | Sì | Sì | Sì | No | No |
| 302 | Importo sconto totale | Immettere l'importo di sconto per la transazione. Questa operazione è valida solo per gli articoli scontabili e l'importo non può superare i limiti di sconto specificati. | Sì | Sì | No | Sì | No |
| 303 | Percentuale sconto totale | Immettere una percentuale di sconto per la transazione. Questa operazione è valida solo per gli articoli scontabili e l'importo non può superare i limiti di sconto specificati. | Sì | Sì | No | Sì | No |
| 501 | Commento transazione | Consente di aggiungere un commento alla transazione corrente. | Sì | Sì | No | Sì | No |
| 922 | Visualizza dettagli prodotto | Apre la pagina dei dettagli dei prodotti per la voce correntemente selezionata. | Sì | Sì | No | Sì | No |
| 1003 | Visualizzazione report | Visualizza i report che sono stati configurati per l'utente corrente. | Sì | Sì | Sì | No | No |
| 921 | Visualizza voci orologio | Visualizza le voci dell'orologio per tutti i lavoratori presso il punto vendita. | Sì | Sì | Sì | No | No |
| 211 | Annulla pagamento | Annulla la riga di pagamento attualmente selezionata nella transazione. | Sì | Sì | No | Sì | No |
| 102 | Annulla prodotto | Annulla la voce attualmente selezionata nella transazione. | Sì | Sì | No | Sì | No |
| 500 | Annulla transazione | Annulla la transazione corrente. | Sì | Sì | No | Sì | No |
| 916 | Windows Workflow Foundation | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No |
| 924 | X-report per carte bancarie | Questa operazione non è supportata. | Non applicabile | Non applicabile | Non applicabile | Non applicabile | Sì |
| 311 | Rimuovere gli sconti di sistema dalle transazioni | Rimuovere tutti gli sconti applicati dal sistema, inclusi gli sconti basati su coupon, dalla transazione. Ciò non rimuove gli sconti manuali. | Sì | Sì | Sì | Sì | No |
| 312 | Riapplicare gli sconti di sistema | Riapplicare gli sconti di sistema sulla transazione se sono stati rimossi utilizzando l'operazione **Rimuovere gli sconti di sistema dalle transazioni**. | Sì | Sì | Sì | Sì | No |

\* L'operazione è disponibile in modalità offline solo quando si crea un ordine cliente o un'offerta di vendita e solo se la creazione offline di ordini cliente e offerte di vendita viene configurata nel profilo funzionalità POS. L'operazione non può essere eseguita quando gli ordini sono creati tramite il servizio in tempo reale, oppure quando gli ordini vengono richiamati o modificati.

† L'operazione può essere eseguita in modalità offline solo quando il POS è configurato per consentire la creazione offline di clienti nel profilo funzionalità POS.

‡ Quando il POS è offline, le transazioni sospese possono essere richiamate solo dal database offline del registratore corrente. Gli utenti non possono sospendere e richiamare transazioni nei registratori.

§ Quando il POS è offline, solo le transazioni nel database offline corrente possono essere richiamate per il reso.

\*\* Quando il POS è offline, solo le transazioni nel database del canale offline corrente sono visualizzabili nel giornale di registrazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
