---
title: Eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura
description: Questo argomento illustra come eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-01-04
ms.openlocfilehash: f1478f0246e7f1ff8bd72232cbaf4c2034cf4edb
ms.sourcegitcommit: 6af7b37b1c8950ad706e684cc13a79e662985b34
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2021
ms.locfileid: "4959848"
---
# <a name="migrate-prospect-to-cash-data-from-data-integrator-to-dual-write"></a>Eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura

[!include [banner](../../includes/banner.md)]

Per eseguire la migrazione dei dati Prospect to cash da Integrazione dei dati a doppia scrittura, seguire questi passaggi.

1. Eseguire i processi di integrazione dei dati Prospect to cash per eseguire un'ultima sincronizzazione completa. In questo modo, ti assicuri che entrambi i sistemi (app Finance and Operations e app di interazione con i clienti) abbiano tutti i dati.
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
5. Creare una connessione a doppia scrittura tra l'app Finance and Operations e l'app di interazione con i clienti per una o più persone giuridiche.
6. Abilitare i mapping di tabelle a doppia scrittura ed eseguire la sincronizzazione iniziale per i dati di riferimento obbligatori. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md). Esempi di dati obbligatori includono gruppi di clienti, termini di pagamento e programmi di pagamento. Non abilitare i mapping a doppia scrittura per le tabelle che richiedono l'inizializzazione, come le tabelle account, offerta, riga preventivo, ordine e riga ordine.
7. Nell'app di interazione con i clienti, passare a **Impostazioni avanzate \> Impostazioni di sistema \> Gestione dati \> Regole di rilevamento duplicati** e disabilitare tutte le regole.
8. Inizializzare le tabelle elencate nel passaggio 2. Per istruzioni, vedere le sezioni rimanenti di questo argomento.
9. Aprire l'app Finance and Operations e abilitare i mapping di tabella, come i mapping account, offerta, riga di offerta, ordine e riga ordine. Quindi eseguire la sincronizzazione iniziale. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md). Questo processo sincronizzerà ulteriori informazioni dall'app Finance and Operations, come stato di elaborazione, indirizzi di spedizione e fatturazione, siti e magazzini.

## <a name="account-table"></a>Tabella account

1. Nella colonna **Azienda**, immettere il nome dell'azienda, ad esempio **USMF**.
2. Nella colonna **Tipo di relazione**, immetti **Cliente** come valore statico. È consigliabile non classificare ogni record di account come cliente nella logica di business.
3. Nella colonna **ID gruppo clienti**, immettere il numero del gruppo di clienti dall'app Finance and Operations. Il valore predefinito della soluzione Prospect to cash è **10**.
4. Se stai utilizzando la soluzione Prospect to cash senza alcuna personalizzazione di **Numero di conto**, immetti un valore per **Numero di conto** nella colonna **Numero parte**. Se sono presenti personalizzazioni e non conosci il numero parte, estrai queste informazioni dall'app Finance and Operations.

## <a name="contact-table"></a>Tabella dei contatti

1. Nella colonna **Azienda**, immettere il nome dell'azienda, ad esempio **USMF**.
2. Impostare le seguenti colonne, in base al valore **IsActiveCustomer** nel file CSV:

    - Se **IsActiveCustomer** è impostato su **Sì** nel file CSV, imposta la colonna **Vendibile** su **Sì**. Nella colonna **ID gruppo clienti**, immettere il numero del gruppo di clienti dall'app Finance and Operations. Il valore predefinito della soluzione Prospect to cash è **10**.
    - If **IsActiveCustomer** è impostato su **No** nel file CSV, impostare la colonna **Vendibile** su **No** e impostare la colonna **Contatta For** su **Cliente**.

3. Se stai utilizzando la soluzione Prospect to cash senza alcuna personalizzazione di **Numero di contatto**, impostare le seguenti colonne:

    - Eseguire la migrazione del numero di contatto dal file CSV (**msdynce\_contactnumber**) al numero di contatto nella tabella **Contatto** (**msdyn\_contactnumber**).
    - Utilizzare i valori dalla tabella **Numero di contatto** nella colonna **Numero parte**.
    - Utilizzare i valori dalla tabella **Numero di contatto** nella colonna **Numero conto/ID contatto**.

## <a name="invoice-table"></a>Tabella delle fatture

Perché i dati della tabella **Fattura** sono progetti per un flusso unidirezionale, dall'app Finance and Operations all'app di interazione con i clienti, l'inizializzazione non è necessaria. Eseguire la sincronizzazione iniziale per migrare tutti i dati richiesti dall'app Finance and Operations all'app di interazione con i clienti. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).

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

Perché i dati della tabella **Prodotti** sono progetti per un flusso unidirezionale, dall'app Finance and Operations all'app di interazione con i clienti, l'inizializzazione non è necessaria. Eseguire la sincronizzazione iniziale per migrare tutti i dati richiesti dall'app Finance and Operations all'app di interazione con i clienti. Per ulteriori informazioni, vedere [Considerazioni per la sincronizzazione iniziale](initial-sync-guidance.md).

## <a name="quote-and-quote-product-tables"></a>Tabelle di offerta e prodotti offerta

Per la tabella **Offerta**, seguire le istruzioni nella sezione [Tabella degli ordini](#order-table) precedente in questo argomento. Per la tabella **Prodotto offerta**, seguire le istruzioni nella sezione [Tabella dei prodotti ordini](#order-products-table) precedente in questo argomento.
