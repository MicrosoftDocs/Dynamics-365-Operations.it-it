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
ms.openlocfilehash: 11a5792c9c039eb76337309ef2fdb2b994ce191a
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772389"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Integrazione dati quasi in tempo reale con Common Data Service

[!include [banner](../includes/banner.md)]

Nel mondo digitale corrente, gli ecosistemi aziendali utilizzano le applicazioni Microsoft Dynamics 365 nel loro insieme. Poiché i dati di persone, clienti, operazioni e dai dispositivi IoT (Internet of Things, Internet delle Cose) fluiscono in una sola origine, c'è un'opportunità di cicli di feedback digitali. Per ottenere questa esperienza, l'integrazione tra le app Finance and Operations e le applicazioni Dynamics 365 è essenziale. Alcune applicazioni si basano su Common Data Service. L'integrazione tra i dati delle app Finance and Operations e Common Data Service consente ad altre applicazioni di comunicare coerentemente e in modo fluente con Finance and Operations.

Le app Finance and Operations e Common Data Service forniscono la sincronizzazione dei dati quasi in tempo reale tra le app Finance and Operations e altre applicazioni Dynamics 365 tramite un framework di doppia scrittura. La copertura è ampia e riguarda 28 aree dell'applicazione. L'obiettivo è fornire "Un'unica esperienza Dynamics 365" agli utenti tramite flussi integrati di dati che collegano i processi aziendali di tutte le applicazioni.

![Diagramma di panoramica dell'architettura](media/dual-write-overview.jpg)

Le seguenti proposte di valore sono disponibili:

+ [Gerarchia organizzativa in Common Data Service](dual-write-organization.md)
+ [Concetto di società in Common Data Service](dual-write-company.md)
+ [Gestione integrata dei dati dei clienti](dual-write-customer.md)
+ [Contabilità generale integrata](dual-write-ledger.md)
+ [Esperienza prodotto unificata](dual-write-product.md)
+ [Gestione integrata dei dati dei fornitori](dual-write-vendor.md)
+ [Siti e magazzini integrati](dual-write-sites-and-warehouses.md)
+ [Anagrafica fiscale integrata](dual-write-tax.md)

## <a name="system-requirements"></a>Requisiti di sistema

I flussi di dati sincroni, bidirezionali, quasi in tempo reale richiedono le seguenti versioni:

+ Microsoft Dynamics 365 for Finance and Operations versione 10.0.4 (luglio 2019) con aggiornamento della piattaforma 28 o successivo
+ Microsoft Dynamics 365 for Customer Engagement, piattaforma versione 9.1 (4.2) o versione successiva

## <a name="setup-instructions"></a>Istruzioni di impostazione

Seguire questi passaggi per impostare l'integrazione tra le app Finance and Operations e Common Data Service.
    
1. Per l'impostazione del sistema di doppia scrittura, vedere la [guida dettagliata](https://aka.ms/dualwrite-docs) nell'annuncio sull'anteprima della doppia scrittura.
2. Scaricare e installare la soluzione [Integrazione tra Finance and Operations, Common Data Service e Customer Engagement](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) dal gruppo Yammer. Il pacchetto contiene cinque soluzioni:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Seguire l'ordine di esecuzione per [sincronizzare i dati di riferimento iniziali](dual-write-initial.md).
4. Se si verificano problemi di sincronizzazione della doppia scrittura, vedere [Guida alla risoluzione dei problemi di integrazione dei dati](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Non è possibile eseguire la doppia scrittura e [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) in parallelo. Se si sta eseguendo la soluzione Prospect to cash, è necessario disinstallarla. È inoltre necessario disabilitare i modelli di doppia scrittura di cliente e fornitore che fanno parte della soluzione Prospect to cash.
