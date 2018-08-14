---
title: Integrazione con Microsoft Dynamics 365 for Field Service
description: In questo argomento viene fornita una panoramica dell'integrazione con Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a57e23691a6b4d48c6b8dd6d1f61fc9730365b39
ms.openlocfilehash: 0c1268d2fddcf7b28ecfc3197f21e9d30a5a5855
ms.contentlocale: it-it
ms.lasthandoff: 05/31/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integrazione con Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations consente di sincronizzare i processi aziendali tra Finance and Operations e Microsoft Dynamics 365 for Field Service. Gli scenari di integrazione vengono configurati utilizzando modelli di integrazione dati estendibili e Common Data Service (CDS) per abilitare la sincronizzazione dei processi aziendali.

[![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

La prima fase dell'integrazione tra Field Service e Finance and Operations è incentrata sull'abilitazione degli ordini di lavoro e dei contratti in Field Service in modo che possano essere fatturati in Finance and Operations. Il flusso supportato inizia in Field Service, dove le informazioni degli ordini di lavoro vengono sincronizzate con Finance and Operations sotto forma di ordini cliente. In Finance and Operations, gli ordini cliente vengono fatturati per generare documenti fattura. Inoltre, le informazioni contenute nelle fatture di contratto di Field Service vengono sincronizzate con Finance and Operations. L'integratore di dati Microsoft Dynamics 365 sincronizza i dati utilizzando progetti personalizzabili. È possibile utilizzare modelli standard per creare progetti di integrazione personalizzati in cui mappare campi personalizzati e standard aggiuntivi, nonché entità, per ottimizzare l'integrazione e soddisfare requisiti specifici.

La prima fase dell'integrazione tra Field Service e Finance and Operations consente la sincronizzazione degli elementi seguenti:

- [Prodotti in Finance and Operations con prodotti in Field Service che includono informazioni sul tipo di prodotto](field-service-product.md)
- [Ordini di lavoro in Field Service con ordini cliente in Finance and Operations](field-service-work-order.md)
- [Fatture in Field Service con fatture a testo libero in Finance and Operations](field-service-invoice.md)

Per visualizzare un esempio di come sincronizzare un ordine di lavoro tra Field Service e Finance and Operations, guardare il breve video su YouTube [Sincronizzare un ordine di lavoro tra Dynamics 365 for Field Service e Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).

## <a name="system-requirements-for-finance-and-operations"></a>Requisiti di sistema di Finance and Operations
L'integrazione di Field Service supporta le versioni seguenti:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Dynamics 365 for Finance and Operations versione 8.0 (aprile 2018) o successive

- Dynamics 365 for Finance and Operations versione 8.0 (aprile 2018) è stata rilasciata in aprile 2018 con numero di build 8.0.30.8020 e aggiornamento 15 della piattaforma (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Requisiti di sistema per Field Service
Per utilizzare la soluzione di integrazione di Field Service, è necessario installare i componenti seguenti:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 o versioni successive

- Dynamics 365 for Field Service versione 1612 (9.0.1.733) (DB 9.0.1.733) online o una versione successiva.
- Soluzione Prospect to Cash (P2C) per Dynamics 365, versione 1.15.0.1 o una versione successiva. La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Soluzione di integrazione di Field Service per Dynamics 365, versione 1.0.0.0 o una versione successiva. La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).

