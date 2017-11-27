---
title: Prospect to cash
description: L'argomento offre una panoramica della soluzione Prospect to cash tra Dynamics 365 for Finance and Operations, Enterprise edition e Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: it-it
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a>Prospect to cash  

[!include[banner](../includes/banner.md)]

La soluzione Prospect to cash utilizza l'[Integrazione di dati](/common-data-service/entity-reference/dynamics-365-integration) per sincronizzare i dati tra istanze di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition e Dynamics 365 for Sales attraverso il Common Data Service (CDS). I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativi a account, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales. Quando i dati fluiscono tra Finance and Operations e Sales, è possibile eseguire attività di vendita e di marketing in Sales e gestire la compilazione degli ordini con la gestione dell'inventario in Finance and Operations. 

Questa soluzione offre integrazione nelle aree seguenti: 

-   [Gestione degli account in Sales e sincronizzazione in Finance and Operations.](accounts-template-mapping.md)
-   [Gestione dei contatti in Sales e sincronizzazione in Finance and Operations.](contacts-template-mapping.md)
-   [Gestione dei prodotti in Finance and Operations e sincronizzazione in Sales.](products-template-mapping.md)
-   [Creazione di offerte di vendita in Sales e sincronizzazione in Finance and Operations.](sales-quotation-template-mapping.md)
-   [Creazione di ordini cliente in Finance and Operations e sincronizzazione in Sales](sales-order-template-mapping.md)
-   [Creazione di fatture di vendita in Finance and Operations e sincronizzazione in Sales](sales-invoice-template-mapping.md)

Questa soluzione offre una sincronizzazione diretta nelle aree seguenti:

-   [Gestione degli account in Sales e sincronizzazione direttamente da Sales in Finance and Operations.](accounts-template-mapping-direct.md)
-   [Gestione dei prodotti in Finance and Operations e sincronizzazione direttamente in Sales.](products-template-mapping-direct.md)
-   [Gestione dei contatti in Sales e sincronizzazione direttamente con contatti o clienti in Finance and Operations](contacts-template-mapping-direct.md)
-   [Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
-   [Creazione di ordini cliente in Finance and Operations e sincronizzazione direttamente in Sales](sales-order-template-mapping-direct.md)
-  [Sincronizzare intestazioni e righe di ordini cliente direttamente tra Sales e Finance and Operations](sales-order-template-mapping-between-sales-fin.md)
-   [Sincronizzare ordini cliente direttamente tra Sales e Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
-   [Creazione di fatture di vendita in Finance and Operations e sincronizzazione direttamente in Sales](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Requisiti di sistema êr Dynamics 365 for Finance and Operations, Enterprise edition

Per utilizzare la soluzione Prospect to cash, è necessario installare quanto segue:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) con l'aggiornamento 8 della piattaforma (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)

- Aggiornamenti rapidi per Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017).
        
    -  [KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - Questo aggiornamento rapido attiva il supporto per la sincronizzazione dell'ordine cliente alla funzionalità Integrazione dati da Sales in Finance and Operations, insieme ad altri miglioramenti.

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Questo aggiornamento rapido attiva la sincronizzazione della riga dell'ordine cliente alla funzionalità Integrazione dati tra Finance and Operations e Sales.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Questo aggiornamento rapido attiva la sincronizzazione dell'ordine cliente alla funzionalità Integrazione dati tra Finance and Operations e Sales.

**Nota**: è necessario installare solo KB4045570 poiché l'installazione include le modifiche da altri KB.
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>Requisiti di sistema per Microsoft Dynamics 365 for Sales

Per utilizzare la soluzione Prospect to cash, è necessario installare quanto segue:

- Dynamics 365 for Sales versione 1612 (8.2.1.207) (DB 8.2.1.207) online.
- Soluzione Prospect to cash per Dynamics 365 for Sales versione 1.14.0.0 (v14) o versione successiva.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Installare la soluzione Prospect to cash per Sales

- Scaricare il [File ZIP del pacchetto della soluzione Prospect to cash per Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) in CustomerSource.

- Verificare che il file ZIP sia sbloccato di modo che non venga visualizzato il messaggio di errore "Nessun pacchetto trovato per l'importazione" durante l'installazione della soluzione. Per sbloccare il file, procedere come segue:

    -  Fare clic con il pulsante destro del mouse sul file ZIP.
    -  Scegliere **Proprietà** e quindi **Sblocca**. 

- Decomprimere ed eseguire PackageDeployer.exe.

- Installare la soluzione Prospect to cash nell'istanza di Sales.

    - Selezionare il tipo di distribuzione **Office 365**.
    - Selezionare **Mostra avanzate**.
    - Per un'installazione rapida, selezionare **Area**. Se si seleziona **Non so**, il sistema cerca tutte le aree e sarà necessario più tempo per l'installazione.
    - Immettere il **nome utente** e la **password** di un utente amministratore con diritti di installazione.

