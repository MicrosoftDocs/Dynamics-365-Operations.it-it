---
title: Integrazione con Microsoft Dynamics 365 for Field Service
description: Questo argomento fornisce una panoramica dell'integrazione con Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 02/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: d636e77888fff383849b3a91bf643475a6d516ac
ms.sourcegitcommit: 383a344deb5abf48584ea2ee7774b8dbbbec49b3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2019
ms.locfileid: "377880"
---
# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integrazione con Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations consente la sincronizzazione dei processi aziendali tra Finance and Operations e Microsoft Dynamics 365 for Field Service. Gli scenari di integrazione vengono configurati utilizzando modelli di integrazione dati estendibili e Common Data Service (CDS) per abilitare la sincronizzazione dei processi aziendali.
È possibile utilizzare modelli standard per creare progetti di integrazione personalizzati in cui mappare campi ed entità personalizzati e standard aggiuntivi per ottimizzare l'integrazione e soddisfare esigenze aziendali specifiche. 

L'integrazione di Field Service viene eseguita sulla funzionalità Prospect to Cash esistente.

![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/field-service-integration.png)

La prima fase dell'integrazione tra Field Service e Finance and Operations è incentrata sull'abilitazione degli ordini di lavoro e dei contratti in Field Service in modo che possano essere fatturati in Finance and Operations. Il flusso supportato inizia in Field Service, dove le informazioni degli ordini di lavoro vengono sincronizzate con Finance and Operations sotto forma di ordini cliente. In Finance and Operations, gli ordini cliente vengono fatturati per generare documenti fattura. Inoltre, le informazioni contenute nelle fatture di contratto di Field Service vengono sincronizzate con Finance and Operations. L'integratore di dati Microsoft Dynamics 365 sincronizza i dati utilizzando progetti personalizzabili. È possibile utilizzare modelli standard per creare progetti di integrazione personalizzati in cui mappare campi personalizzati e standard aggiuntivi, nonché entità, per ottimizzare l'integrazione e soddisfare requisiti specifici.

La prima fase dell'integrazione tra Field Service e Finance and Operations consente la sincronizzazione degli elementi seguenti:

- [Prodotti in Finance and Operations con prodotti in Field Service che includono informazioni sul tipo di prodotto](field-service-product.md)
- [Ordini di lavoro in Field Service con ordini cliente in Finance and Operations](field-service-work-order.md)
- [Fatture in Field Service con fatture a testo libero in Finance and Operations](field-service-invoice.md)

Per visualizzare un esempio di come sincronizzare un ordine di lavoro tra Field Service e Finance and Operations, guardare il breve video su YouTube [Come sincronizzare un ordine di lavoro con l'integrazione di Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Integrazione con Microsoft Dynamics 365 for Field Service incluse le informazioni di progetto e di magazzino

La funzionalità aggiuntiva in questa seconda fase è incentrata sulla fornitura ai tecnici sul posto delle informazioni relative alle scorte di Finance and Operations, che consentono di aggiornare i livelli delle scorte ed effettuare trasferimenti di materiali. Inoltre, con l'integrazione da questi progetti, le società che installano o forniscono assistenza per le merci vendute trarranno vantaggio da un miglior controllo e visibilità del processo di vendita e assistenza.

### <a name="functionality-includes-integration-of"></a>La funzionalità include l'integrazione di:
- Informazioni sul magazzino
- Informazioni su scorte disponibili
- Trasferimenti di scorte
- Rettifiche dell'inventario
- Progetti di Dynamics 365 for Finance and Operations collegati a ordini di lavoro di Dynamics 365 for Field Service
- Gli ordini di lavoro di Dynamics 365 for Field Service collegati ai progetti Dynamics 365 for Finance and Operations applicano questo numero di progetto agli ordini cliente di Dynamics 365 for Finance and Operations per consentire la fatturazione dal progetto. 

![Sincronizzazione dei processi aziendali tra Finance and Operations e Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>La seconda fase dell'integrazione tra Field Service e Finance and Operations consente la sincronizzazione con i seguenti modelli:
- Magazzini (da Fin and Ops a Field Service) - Magazzini da Finance and Operations a Field Service [Query avanzata] 
- Inventario prodotti (da Fin and Ops a Field Service) - Informazioni sul livello delle scorte da Finance and Operations a Field Service [Query avanzata] 
- Rettifica magazzino (da Field Service a Fin and Ops) - Rettifiche del magazzino da Field Service a Finance and Operations [Query avanzata] 
- Trasferimenti scorte (da Field Service a Fin and Ops) - Trasferimenti di scorte da Field Service a Finance and Operations [Query avanzata] 
- Progetti (da Fin and Ops a Field Service) - Elenco dei progetti da Finance and Operations a Field Service 
- Ordini di lavoro con progetto (da Field Service a Fin and Ops) - Da ordini di lavoro in Field Service a ordini cliente in Finance and Operations, con supporto per progetto [Query avanzata] 
- Prodotti Field Service con unità di magazzino (da Fin and Ops a Field Service) - Da Prodotti rilasciati di vendita di Finance and Operations a "Prodotti" venduti per Field Service, inclusa l'unità di magazzino 

## <a name="system-requirements"></a>Requisiti di sistema

### <a name="system-requirements-for-finance-and-operations"></a>Requisiti di sistema di Finance and Operations
L'integrazione di Field Service supporta le versioni seguenti:

- Dynamics 365 for Finance and Operations versione 8.1.2 (dicembre 2019) è stata rilasciata nel dicembre 2019 con numero di build 8.1.195 e aggiornamento 22 della piattaforma (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Requisiti di sistema per Field Service
Per utilizzare la soluzione di integrazione di Field Service, è necessario installare i componenti seguenti:

- Field Service for Dynamics 365 (versione 8.2.0.286) o versione successiva su Dynamics 365 9.1.x - Rilasciata nel novembre 2018
- Soluzione Prospect to Cash (P2C) per Dynamics 365, versione 1.15.0.1 o una versione successiva. La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Soluzione di integrazione, progetto e scorte di Field Service per Dynamics 365, versione 2.0.0.0 o una versione successiva. La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).
