---
title: Eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura
description: Questo articolo illustra come eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 02/01/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-26
ms.openlocfilehash: 8e5c11e535bd61e9955a4abf1491e88991ee40f1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894268"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura

[!include [banner](../../includes/banner.md)]

La soluzione Prospect to cash disponibile per Data Integrator non è compatibile con la doppia scrittura. Il motivo è l'indice msdynce_AccountNumber nella tabella dei conti che fa parte della soluzione Prospect to cash. Se questo indice esiste, non è possibile creare lo stesso numero di conto cliente in due persone giuridiche diverse. Puoi scegliere di ricominciare da capo con la doppia scrittura migrando i dati Prospect to cash da Data Integrator alla doppia scrittura oppure puoi installare l'ultima versione "dormiente" della soluzione Prospect to cash. In questo articolo vengono descritti entrambi gli approcci.

## <a name="install-the-last-dorman-version-of-the-data-integrator-prospect-to-cash-solution"></a>Installare l'ultima versione "dormiente" della soluzione Prospect to cash di Data Integrator

**P2C Version 15.0.0.2** è considerata l'ultima versione "dormiente" della soluzione Prospect to cash di Data Integrator. Puoi scaricarla da [FastTrack for Dynamics 365](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/tree/master/Dual-write/P2C).

Devi installarla manualmente. Dopo l'installazione, tutto rimane esattamente lo stesso, tranne che l'indice msdynce_AccountNumber viene rimosso.

## <a name="steps-to-migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Passaggi per eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura

Per eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura, seguire questi passaggi.

1. Eseguire i processi di integrazione dei dati Prospect to cash per eseguire un'ultima sincronizzazione completa. In questo modo, ti assicuri che entrambi i sistemi (app per finanza e operazioni e app di interazione con i clienti) abbiano tutti i dati.
2. Per contribuire a prevenire la potenziale perdita di dati, esportare i dati Prospect to cash da Microsoft Dynamics 365 Sales in un file Excel o in un file CSV (valori delimitati da virgole). Esporta i dati dalle seguenti entità:

    - [Conto](#account-table)
    - [Contatto](#contact-table)
    - [Fattura](#invoice-table)
    - Prodotti di fatturazione
    - [Ordine](#order-table)
    - [Ordina prodotti](#order-products-table)
    - [Prodotti](#products-table)
    - [Offerta](#quote-and-quote-product-tables)
    - [Prodotti di offerta](#quote-and-quote-product-tables)

3. Disinstallare la soluzione Prospect to cash dall'ambiente Sales. Questo passaggio rimuove le colonne e i dati corrispondenti introdotti dalla soluzione Prospect to cash.
4. Installare la soluzione a doppia scrittura.
5. Creare una connessione a doppia scrittura tra l'app per finanza e operazioni e l'app di interazione con i clienti per una o più persone giuridiche.
6. Abilitare i mapping di tabelle a doppia scrittura ed eseguire la sincronizzazione iniziale per i dati di riferimento obbligatori. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md). Esempi di dati obbligatori includono gruppi di clienti, termini di pagamento e programmi di pagamento. Non abilitare i mapping a doppia scrittura per le tabelle che richiedono l'inizializzazione, come le tabelle account, offerta, riga preventivo, ordine e riga ordine.
7. Nell'app di interazione con i clienti, passare a **Impostazioni avanzate \> Impostazioni di sistema \> Gestione dati \> Regole di rilevamento duplicati** e disabilitare tutte le regole.
8. Inizializzare le tabelle elencate nel passaggio 2. Per istruzioni, vedi le sezioni rimanenti di questo articolo.
9. Aprire l'app per finanza e operazioni e abilitare i mapping di tabella, come i mapping account, offerta, riga di offerta, ordine e riga ordine. Quindi eseguire la sincronizzazione iniziale. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md). Questo processo sincronizzerà ulteriori informazioni dall'app per finanza e operazioni, come stato di elaborazione, indirizzi di spedizione e fatturazione, siti e magazzini.

## <a name="account-table"></a>Tabella account

1. Nella colonna **Azienda**, immettere il nome dell'azienda, ad esempio **USMF**.
2. Nella colonna **Tipo di relazione**, immetti **Cliente** come valore statico. È consigliabile non classificare ogni record di account come cliente nella logica di business.
3. Nella colonna **ID gruppo clienti**, immettere il numero del gruppo di clienti dall'app per finanza e operazioni. Il valore predefinito della soluzione Prospect to cash è **10**.
4. Se stai utilizzando la soluzione Prospect to cash senza alcuna personalizzazione di **Numero di conto**, immetti un valore per **Numero di conto** nella colonna **Numero parte**. Se sono presenti personalizzazioni e non conosci il numero parte, estrai queste informazioni dall'app per finanza e operazioni.

## <a name="contact-table"></a>Tabella dei contatti

1. Nella colonna **Azienda**, immettere il nome dell'azienda, ad esempio **USMF**.
2. Impostare le seguenti colonne, in base al valore **IsActiveCustomer** nel file CSV:

    - Se **IsActiveCustomer** è impostato su **Sì** nel file CSV, imposta la colonna **Vendibile** su **Sì**. Nella colonna **ID gruppo clienti**, immettere il numero del gruppo di clienti dall'app per finanza e operazioni. Il valore predefinito della soluzione Prospect to cash è **10**.
    - If **IsActiveCustomer** è impostato su **No** nel file CSV, impostare la colonna **Vendibile** su **No** e impostare la colonna **Contatta For** su **Cliente**.

3. Se stai utilizzando la soluzione Prospect to cash senza alcuna personalizzazione di **Numero di contatto**, impostare le seguenti colonne:

    - Eseguire la migrazione del numero di contatto dal file CSV (**msdynce\_contactnumber**) al numero di contatto nella tabella **Contatto** (**msdyn\_contactnumber**).
    - Utilizzare i valori dalla tabella **Numero di contatto** nella colonna **Numero parte**.
    - Utilizzare i valori dalla tabella **Numero di contatto** nella colonna **Numero conto/ID contatto**.

## <a name="invoice-table"></a>Tabella delle fatture

Perché i dati della tabella **Fattura** sono progetti per un flusso unidirezionale, dall'app per finanza e operazioni all'app di interazione con i clienti, l'inizializzazione non è necessaria. Eseguire la sincronizzazione iniziale per migrare tutti i dati richiesti dall'app per finanza e operazioni all'app di interazione con i clienti. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).

## <a name="order-table"></a>Tabella degli ordini

1. Nella colonna **Azienda**, immettere il nome dell'azienda, ad esempio **USMF**.
2. Copiare il valore della colonna **ID ordine** nel file CSV nella colonna **Numero ordine di vendita**.
3. Copiare il valore della colonna **Cliente** nel file CSV nella colonna **Numero cliente fattura**.
4. Copiare il valore dell colonna **Spedisci a paese** nel file CSV nella colonna **Spedisci a paese**. Esempi di questo valore includono **US** e **Stati Uniti**.
5. Impostare la colonna **Data di ricevimento richiesta**. Se non stai utilizzando una data di ricevuta, utilizza le colonne **Data di consegna richiesta**, **Data di completamento** e **Data di invio** nel file CSV. Un esempio di questo valore è **2020-03-27T00: 00: 00Z**.
6. Impostare la colonna **Lingua**. Un esempio di questo valore è **en-us**.
7. Impostare la colonna **Tipo di ordine** utilizzando la colonna **Basato sull'articolo**.

## <a name="order-products-table"></a>Tabella prodotti ordine

- Nella colonna **Azienda**, immettere il nome dell'azienda, ad esempio **USMF**.

## <a name="products-table"></a>Tabella prodotti

Perché i dati della tabella **Prodotti** sono progetti per un flusso unidirezionale, dall'app per finanza e operazioni all'app di interazione con i clienti, l'inizializzazione non è necessaria. Eseguire la sincronizzazione iniziale per migrare tutti i dati richiesti dall'app per finanza e operazioni all'app di interazione con i clienti. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tabelle di offerta e prodotti offerta

Per la tabella **Offerta**, segui le istruzioni nella sezione [Tabella degli ordini](#order-table) precedente in questo articolo. Per la tabella **Prodotto offerta**, seguire le istruzioni nella sezione [Tabella dei prodotti ordini](#order-products-table) precedente in questo argomento.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
