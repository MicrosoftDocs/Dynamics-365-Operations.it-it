---
title: Prospect to cash
description: Questo argomento offre una panoramica della soluzione Prospect to cash tra Microsoft Dynamics 365 for Finance and Operations, Enterprise edition e Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 11/17/2017
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
ms.sourcegitcommit: 788e64476094e84eb4d438890776306c05b20582
ms.openlocfilehash: 762699cf68ec8a9df5db20d7dd33bc9248f0a36e
ms.contentlocale: it-it
ms.lasthandoff: 12/11/2017

---

# <a name="prospect-to-cash"></a>Prospect to cash

[!include[banner](../includes/banner.md)]

La soluzione Prospect to cash consente la sincronizzazione diretta tra Microsoft Dynamics 365 for Finance and Operations, Enterprise edition e Microsoft Dynamics 365 for Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita tra Finance and Operations e Sales. Quando i dati fluiscono tra Finance and Operations e Sales, è possibile eseguire attività di vendita e di marketing in Sales e gestire la compilazione degli ordini utilizzando la gestione dell'inventario di Finance and Operations.

Nella versione corrente, la soluzione Prospect to cash offre i seguenti tipi di sincronizzazione diretta:

- [Gestione degli account in Sales e sincronizzazione direttamente da Sales in Finance and Operations.](accounts-template-mapping-direct.md)
- [Gestione dei prodotti in Finance and Operations e sincronizzazione direttamente in Sales.](products-template-mapping-direct.md)
- [Gestione dei contatti in Sales e sincronizzazione direttamente con contatti o clienti in Finance and Operations](contacts-template-mapping-direct.md)
- [Sincronizzare offerte di vendita direttamente da Sales in Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
- [Sincronizzare ordini cliente direttamente da Finance and Operations in Sales](sales-order-template-mapping-direct.md)
- [Sincronizzare ordini cliente direttamente tra Sales e Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizzare fatture di vendita direttamente da Finance and Operations in Sales](sales-invoice-template-mapping-direct.md)

Nelle versioni precedenti, la soluzione Prospect to cash offre i seguenti tipi di sincronizzazione non diretta:

- [Gestione degli account in Sales e sincronizzazione in Finance and Operations.](accounts-template-mapping.md)
- [Gestione dei contatti in Sales e sincronizzazione in Finance and Operations.](contacts-template-mapping.md)
- [Gestione dei prodotti in Finance and Operations e sincronizzazione in Sales.](products-template-mapping.md)
- [Creazione di offerte di vendita in Sales e sincronizzazione in Finance and Operations.](sales-quotation-template-mapping.md)
- [Creazione di ordini cliente in Finance and Operations e sincronizzazione in Sales](sales-order-template-mapping.md)
- [Creazione di fatture di vendita in Finance and Operations e sincronizzazione in Sales](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-finance-and-operations"></a>Requisiti di sistema di Finance and Operations

Per utilizzare la soluzione Prospect to cash, è necessario installare i componenti seguenti:

### <a name="july-2017"></a>Luglio 2017 

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (luglio 2017) con l'aggiornamento 8 della piattaforma (build applicazione 7.2.11792.56024 con build piattaforma 7.0.4565.16212)
- I seguenti hotfix per Finance and Operations:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Sales in Finance and Operations tramite la funzionalità Integrazione dati. Sono inoltre presenti molti altri miglioramenti.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione delle righe degli ordini cliente da Finance and Operations in Sales tramite la funzionalità Integrazione dati.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Finance and Operations in Sales tramite la funzionalità Integrazione dati.

    > [!NOTE]
    > È sufficiente installare KB4045570, in quanto l'installazione include le modifiche descritte negli altri articoli della Microsoft Knowledge Base (KB).

### <a name="november-2016-version-1611"></a>Novembre 2016 (versione 1611)

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (novembre 2016) con aggiornamento della piattaforma 8 o successivo

- I seguenti hotfix per Finance and Operations:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Consente la sincronizzazione degli ordini cliente con l'integratore di dati da Microsoft Dynamics 365 for Finance and Operations in Sales 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Consente la sincronizzazione delle righe e delle intestazioni degli ordini cliente con l'integratore di dati da Microsoft Dynamics 365 for Finance and Operations in Sales
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - È richiesto il supporto per l'integrazione della soluzione Prospect to cash tramite le entità di dati
    
    > [!NOTE]
    > Dopo l'installazione degli hotfix, è necessario avviare il seguente processo batch dal modulo SalesPopulateProspectToCash. Questo modulo è nascosto perché serve una sola volta. Per accedere al modulo aggiungere quanto segue all'indirizzo del browser, quando si è connessi all'ambiente: &mi=action:SalesPopulateProspectToCash E.g. https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash Nel modulo che viene aperto fare clic su OK.
    Il modulo viene popolato con un nuovo campo "LineCreationSequnceNumber" nelle tabelle "SalesLine", "SalesQuotationLine" e "CustInvoiceTrans" con valori univoci e l'elenco prodotti aggiornato. Questa operazione è necessaria perché l'integrazione di P2C funzioni con la versione 7.1


## <a name="system-requirements-for-sales"></a>Requisiti di sistema per Sales

Per utilizzare la soluzione Prospect to cash, è necessario installare i componenti seguenti:

- Microsoft Dynamics 365 for Sales versione 1612 (8.2.1.207) (DB 8.2.1.207) online
- Soluzione Prospect to cash per Microsoft Dynamics 365 for Sales versione 1.15.0.0 (v15) o versioni successive 

   > [!NOTE]
   >
   > I modelli con versione 1.0.0.0 e 1.0.0.1 sono supportati nella soluzione Prospect to cash per Microsoft Dynamics 365 for Sales versione 1.14.1.0
   >
   > I modelli con versione 2.0.0.0 e 2.1.0.0 sono supportati nella soluzione Prospect to cash per Microsoft Dynamics 365 for Sales versione 1.15.0.0

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Installare la soluzione Prospect to cash per Sales

1. Scaricare il [File ZIP del pacchetto della soluzione Prospect to cash per Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) da CustomerSource.
2. Assicurarsi che il file ZIP sia sbloccato. In caso contrario, quando si tenta di installare il pacchetto della soluzione, viene visualizzato il messaggio di errore seguente: "Nessun pacchetto per l'importazione trovato." Per sbloccare il file ZIP, fare clic con il pulsante destro del mouse sul file e selezionare **Proprietà**. Selezionare quindi **Sblocca**.
3. Decomprimere il file ZIP ed eseguire il file **PackageDeployer.exe**.
4. Installare la soluzione Prospect to cash nell'istanza di Sales:

    1. Selezionare **Office 365** come tipo di distribuzione.
    2. Selezionare **Mostra avanzate**.
    3. Per un'installazione rapida, selezionare un'area. Se si seleziona **Non so**, il sistema cerca tutte le aree e l'installazione richiede più tempo.
    4. Immettere il nome utente e la password di un utente amministratore con diritti di installazione.

