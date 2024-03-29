---
title: Prospect per uno scenario di liquidazione
description: Questo articolo offre una panoramica della soluzione Prospect to cash tra Dynamics 365 Supply Chain Management e Dynamics 365 Sales.
author: Henrikan
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ea07b40c0a1a7eae7cd167f46796556b1e0ecc46
ms.sourcegitcommit: 12b3dbee905f8b2eb2e6c383c822a0fc9fccf063
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9103596"
---
# <a name="prospect-to-cash"></a>Prospect per uno scenario di liquidazione

[!include [banner](../includes/banner.md)]

La soluzione Prospect to cash consente la sincronizzazione diretta tra Dynamics 365 Supply Chain Management e Dynamics 365 Sales. I modelli Prospect to cash disponibili con la funzionalità Integrazione dati consentono il flusso di dati relativo a conti, contatti, prodotti, offerte di vendita, ordini cliente e fatture di vendita. Quando i dati fluiscono, è possibile eseguire attività di vendita e di marketing in Sales e gestire la compilazione degli ordini utilizzando la gestione dell'inventario di Supply Chain Management. 

Per ulteriori informazioni sull'integrazione di Prospect to cash, vedere il video su YouTube [Prospect to cash integration](https://www.youtube.com/watch?v=AVV9x5x-XCg).

Nella versione corrente, la soluzione Prospect to cash offre i seguenti tipi di sincronizzazione diretta:

- [Sincronizzare conti direttamente da Sales con clienti in Supply Chain Management](accounts-template-mapping-direct.md)
- [Sincronizzare prodotti direttamente da Supply Chain Management con prodotti in Sales](products-template-mapping-direct.md)
- [Sincronizzare contatti direttamente da Sales con contatti o clienti in Supply Chain Management](contacts-template-mapping-direct.md)
- [Sincronizzare intestazioni e righe di offerte di vendita direttamente da Sales in Supply Chain Management…](sales-quotation-template-mapping-sales-fin.md)
- [Sincronizzazione degli ordini cliente direttamente tra Sales e Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)
- [Sincronizzare intestazioni e righe di fatture di vendita direttamente da Supply Chain Management in Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>Requisiti di sistema per Supply Chain Management
L'integrazione Prospect to cash è supportata nelle seguenti versioni:

### <a name="microsoft-dynamics-365-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 per finanza e operazioni, Enterprise Edition 7.3 (dicembre 2017)

- Dynamics 365 per finanza e operazioni, Enterprise Edition (dicembre 2017) - Build applicazione 7.3.11971.56116 con Platform Update 12 (7.0.4709.41129)

### <a name="dynamics-365-finance-enterprise-edition-july-2017"></a>Dynamics 365 Finance, Enterprise edition (luglio 2017)

- Dynamics 365 per finanza e operazioni, Enterprise Edition (July 2017) - Con Platform Update 8 (build applicazione 7.2.11792.56024 con build piattaforma 7.0.4565.16212).
- Sono necessari i seguenti aggiornamenti rapidi:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Sales in Supply Chain Management tramite la funzionalità Integrazione dati. Sono inoltre presenti molti altri miglioramenti.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione delle righe degli ordini cliente da Supply Chain Management in Sales tramite la funzionalità Integrazione dati.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** - Questo hotfix consente la sincronizzazione degli ordini cliente da Supply Chain Management in Sales tramite la funzionalità Integrazione dati.

    > [!NOTE]
    > È necessario installare solo KB4045570 poiché l'installazione include le modifiche di altri aggiornamenti rapidi. 

### <a name="dynamics-365-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 per finanza e operazioni versione 1611 (novembre 2016)

- Dynamics 365 per finanza e operazioni versione 1611 (November 2016) con Platform Update 8 o superiore

- Sono necessari i seguenti aggiornamenti rapidi:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Consente la sincronizzazione degli ordini cliente con l'integratore di dati da Supply Chain Management a Sales. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Consente la sincronizzazione delle righe e delle intestazioni degli ordini cliente con l'integratore di dati da Supply Chain Management a Sales.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - È richiesto il supporto per l'integrazione della soluzione Prospect to cash tramite le entità di dati.
    
    > [!NOTE]
    > Dopo l'installazione degli aggiornamenti rapidi, è necessario attivare il seguente processo batch dal modulo **SalesPopulateProspectToCash**. Questo modulo è nascosto poiché serve una sola volta. Per accedere al modulo, accedere all'ambiente e aggiungere quanto segue all'URL nell'indirizzo del browser: *&mi=action:SalesPopulateProspectToCash*, ad esempio, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. Quando il modulo si apre, fare clic su OK. Il modulo viene popolato con un nuovo campo **LineCreationSequnceNumber** nelle tabelle **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** con valori univoci e l'elenco prodotti verrà aggiornato. Questa operazione è necessaria per il funzionamento dell'integrazione Prospect to cash.


## <a name="system-requirements-for-sales"></a>Requisiti di sistema per Sales

Per utilizzare la soluzione Prospect to cash, è necessario installare i componenti seguenti:

- Dynamics 365 Sales versione 1612 (8.2.1.207) (DB 8.2.1.207) online o una versione successiva
- Soluzione Prospect to Cash per Dynamics 365 Sales, versione 1.15.0.0 o una versione successiva. La soluzione può essere scaricata da AppSource. [Scaricare Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
