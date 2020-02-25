---
title: Integrazione dati quasi in tempo reale con Common Data Service
description: Questo argomento fornisce una panoramica dell'integrazione tra Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019862"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integrazione dati quasi in tempo reale con Common Data Service

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

Nel mondo digitale corrente, gli ecosistemi aziendali utilizzano le applicazioni Microsoft Dynamics 365 nel loro insieme. Poiché i dati di persone, clienti, operazioni e dai dispositivi IoT (Internet of Things, Internet delle Cose) fluiscono in una sola origine, c'è un'opportunità di cicli di feedback digitali. Per ottenere questa esperienza, l'integrazione tra le app Finance and Operations e le applicazioni Dynamics 365 è essenziale. Alcune applicazioni si basano su Common Data Service. L'integrazione tra i dati delle app Finance and Operations e Common Data Service consente ad altre applicazioni di comunicare coerentemente e in modo fluente con Finance and Operations.

Le app Finance and Operations e Common Data Service forniscono la sincronizzazione dei dati quasi in tempo reale tra le app Finance and Operations e altre applicazioni Dynamics 365 tramite un framework di doppia scrittura. La copertura è ampia e riguarda 28 aree dell'applicazione. L'obiettivo è fornire "Un'unica esperienza Dynamics 365" agli utenti tramite flussi integrati di dati che collegano i processi aziendali di tutte le applicazioni.

![Diagramma di panoramica dell'architettura](media/dual-write-overview.jpg)

Le seguenti proposte di valore sono disponibili:

+ [Gerarchia organizzativa in Common Data Service](organization-mapping.md)
+ [Concetto di società in Common Data Service](company-data.md)
+ [Gestione integrata dei dati dei clienti](customer-mapping.md)
+ [Contabilità generale integrata](ledger-mapping.md)
+ [Esperienza prodotto unificata](product-mapping.md)
+ [Gestione integrata dei dati dei fornitori](vendor-mapping.md)
+ [Siti e magazzini integrati](sites-warehouses-mapping.md)
+ [Anagrafica fiscale integrata](tax-mapping.md)

## <a name="system-requirements"></a>Requisiti di sistema

I flussi di dati sincroni, bidirezionali, quasi in tempo reale richiedono le seguenti versioni:

+ Microsoft Dynamics 365 for Finance and Operations versione 10.0.4 (luglio 2019) con aggiornamento della piattaforma 28 o successivo
+ Microsoft Dynamics 365 for Customer Engagement, piattaforma versione 9.1 (4.2) o versione successiva

## <a name="setup-instructions"></a>Istruzioni di impostazione

Per impostare l'integrazione tra le app Finance and Operations e Common Data Service, attenersi alla procedura indicata di seguito.
    
1. Per l'impostazione del sistema di doppia scrittura, vedere la [guida dettagliata](https://aka.ms/dualwrite-docs) nell'annuncio sull'anteprima della doppia scrittura.
2. Scarica e installa la soluzione dal gruppo [Fin Ops and CDS/CE Integration via Dual-Write ](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096)Yammer. Il pacchetto contiene cinque soluzioni:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Seguire l'ordine di esecuzione per [sincronizzare i dati di riferimento iniziali](initial-sync.md).
4. Se si verificano problemi di sincronizzazione della doppia scrittura, vedere [Guida alla risoluzione dei problemi di integrazione dei dati](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Non è possibile eseguire la doppia scrittura e [Prospect to cash](../../../../supply-chain/sales-marketing/prospect-to-cash.md) in parallelo. Se si sta eseguendo la soluzione Prospect to cash, è necessario disinstallarla. È inoltre necessario disabilitare i modelli di doppia scrittura di cliente e fornitore che fanno parte della soluzione Prospect to cash.
