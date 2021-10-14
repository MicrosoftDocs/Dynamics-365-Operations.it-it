---
title: Panoramica dell'integrazione con Microsoft Dynamics 365 Field Service
description: Questo argomento fornisce una panoramica dell'integrazione con Microsoft Dynamics 365 Field Service.
author: Henrikan
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 23661bca91ccd7b7a04c763e60cfca9a99d62bfa
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566457"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Panoramica dell'integrazione con Microsoft Dynamics 365 Field Service

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Supply Chain Management consente la sincronizzazione dei processi aziendali tra Dynamics 365 Supply Chain Management e Dynamics 365 Field Service. Gli scenari di integrazione vengono configurati utilizzando modelli di integrazione dati estendibili e Microsoft Dataverse per abilitare la sincronizzazione dei processi aziendali.
È possibile utilizzare modelli standard per creare progetti di integrazione personalizzati in cui mappare colonne e tabelle personalizzate e standard aggiuntive per ottimizzare l'integrazione e soddisfare esigenze aziendali specifiche. 

L'integrazione di Field Service viene eseguita sulla funzionalità Prospect to Cash esistente.

![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service.](./media/field-service-integration.png)

La prima fase dell'integrazione tra Field Service e Supply Chain Management è incentrata sull'abilitazione degli ordini di lavoro e dei contratti in Field Service in modo che possano essere fatturati in Supply Chain Management. Il flusso supportato inizia in Field Service, dove le informazioni degli ordini di lavoro vengono sincronizzate con Supply Chain Management sotto forma di ordini cliente. In Supply Chain Management gli ordini cliente vengono fatturati per generare documenti fattura. Inoltre, le informazioni contenute nelle fatture di contratto di Field Service vengono sincronizzate con Supply Chain Management. L'integratore di dati Microsoft Dynamics 365 sincronizza i dati utilizzando progetti personalizzabili. È possibile utilizzare modelli standard per creare progetti di integrazione personalizzati in cui mappare colonne personalizzate e standard aggiuntive, nonché tabelle, per ottimizzare l'integrazione e soddisfare requisiti specifici.

La prima fase dell'integrazione tra Field Service e Supply Chain Management consente la sincronizzazione degli elementi seguenti:

- [Sincronizzare prodotti in Supply Chain Management con prodotti in Field Service](field-service-product.md)
- [Sincronizzare ordini di lavoro in Field Service con ordini cliente in Supply Chain Management](field-service-work-order.md)
- [Sincronizzare le fatture del contratto in Field Service con le fatture a testo libero in Supply Chain Management](field-service-invoice.md)

Per visualizzare un esempio di come sincronizzare un ordine di lavoro tra Field Service e Supply Chain Management, guardare il breve video su YouTube [Come sincronizzare un ordine di lavoro con l'integrazione di Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Integrazione con Field Service incluse le informazioni di progetto e di magazzino

La funzionalità aggiuntiva in questa seconda fase è incentrata sulla fornitura ai tecnici sul posto delle informazioni relative alle scorte di Supply Chain Management, che consentono di aggiornare i livelli delle scorte ed effettuare trasferimenti di materiali. Inoltre, con l'integrazione da questi progetti, le società che installano o forniscono assistenza per le merci vendute trarranno vantaggio da un miglior controllo e visibilità del processo di vendita e assistenza.

### <a name="functionality-includes-integration-of"></a>La funzionalità include l'integrazione di:
- Informazioni sul magazzino
- Informazioni su scorte disponibili
- Trasferimenti di scorte
- Rettifiche dell'inventario
- Progetti di Supply Chain Management collegati a ordini di lavoro di Dynamics 365 Field Service
- Gli ordini di lavoro di Dynamics 365 Field Service collegati ai progetti di Supply Chain Management applicano questo numero di progetto agli ordini cliente per consentire la fatturazione dal progetto. 

![Sincronizzazione dei processi aziendali tra Supply Chain Management e Field Service, comprese le informazioni sull'inventario e sul progetto.](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>La seconda fase dell'integrazione tra Field Service e Supply Chain Management consente la sincronizzazione con i seguenti modelli:
- Magazzini (da Supply Chain Management a Field Service) - Magazzini da Supply Chain Management a Field Service [Query avanzata] 
- Inventario prodotti (da Supply Chain Management a Field Service) - Informazioni sul livello delle scorte da Supply Chain Management a Field Service [Query avanzata] 
- Rettifica magazzino (da Field Service a Supply Chain Management) - Rettifiche del magazzino da Field Service a Supply Chain Management [Query avanzata] 
- Trasferimenti scorte (da Field Service a Supply Chain Management) - Trasferimenti di scorte da Field Service a Supply Chain Management [Query avanzata] 
- Progetti (da Supply Chain Management a Field Service) - Elenco dei progetti da Supply Chain Management a Field Service 
- Ordini di lavoro con progetto (da Field Service a Supply Chain Management) - Da ordini di lavoro in Field Service a ordini cliente in Supply Chain Management, con supporto per progetto [Query avanzata] 
- Prodotti Field Service con unità di magazzino (da Supply Chain Management a Field Service) - Da "Prodotti rilasciati di vendita" di Supply Chain Management a "Prodotti" venduti per Field Service, inclusa l'unità di magazzino 

## <a name="system-requirements"></a>Requisiti di sistema

### <a name="system-requirements-for-supply-chain-management"></a>Requisiti di sistema per Supply Chain Management
L'integrazione di Field Service supporta le versioni seguenti:

- Dynamics 365 for Finance and Operations versione 8.1.2 (dicembre 2018) è stata rilasciata nel dicembre 2018 con numero di build 8.1.195 e aggiornamento 22 della piattaforma (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Requisiti di sistema per Field Service
Per utilizzare la soluzione di integrazione di Field Service, è necessario installare i componenti seguenti:

- Field Service (versione 8.2.0.286) o versione successiva su Dynamics 365 9.1.x - Rilasciata nel novembre 2018
- Soluzione Prospect to Cash (P2C) per Dynamics 365, versione 1.15.0.1 o una versione successiva. La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Soluzione di integrazione, progetto e scorte di Field Service per Dynamics 365, versione 2.0.0.0 o una versione successiva. La soluzione può essere scaricata da [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]