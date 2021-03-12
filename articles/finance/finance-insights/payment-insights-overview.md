---
title: Previsioni di pagamento cliente (anteprima)
description: Questo argomento descrive la funzionalità di previsione dei pagamenti che può aiutarti a comprendere meglio le procedure di pagamento tipiche di un cliente. Questa funzionalità può contribuire anche a identificare le circostanze che dovrebbero indurti ad avviare i processi di riscossione prima di quanto potresti altrimenti avviarli.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2019-11-06
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: b321fdc185e175d9fe2673c9f1e16486efd8e798
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645675"
---
# <a name="customer-payment-predictions-preview"></a>Previsioni di pagamento cliente (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento descrive la funzionalità di previsione dei pagamenti che può aiutarti a comprendere meglio le procedure di pagamento tipiche di un cliente. Questa funzionalità può contribuire anche a identificare le circostanze che dovrebbero indurti ad avviare i processi di riscossione prima di quanto potresti altrimenti avviarli.

## <a name="overview"></a>Panoramica

Le organizzazioni scoprono spesso che è difficile prevedere quando i clienti pagano le fatture. Questa mancanza di informazioni dettagliate può causare i seguenti problemi:

- Previsioni dei flussi di cassa meno accurate
- Processi di riscossione che iniziano troppo tardi
- Ordini che vengono rilasciati a clienti che potrebbero essere inadempienti nel pagamento

Le previsioni di pagamento dei clienti (anteprima) aiutano le organizzazioni a prevedere quando verrà pagata una fattura cliente. Pertanto, possono creare strategie di riscossione che contribuiscono ad aumentare la probabilità che vengano pagate in tempo.

## <a name="predictions"></a>Previsioni

Le previsioni di pagamento consentono alle organizzazioni di migliorare i processi aziendali aiutandole a identificare le fatture che potrebbero essere pagate in ritardo. L'organizzazione può utilizzare queste informazioni per intraprendere azioni che aumentano le possibilità di essere pagate in tempo.

La funzionalità Previsioni di pagamento del cliente utilizza un modello di apprendimento automatico per prevedere con maggiore precisione quando un cliente pagherà una fattura in sospeso. Questo modello di apprendimento automatico include dati storici su fatture, pagamenti e clienti.

Per ogni fattura aperta, la funzionalità assegna tre probabilità di pagamento:

- La probabilità che il pagamento sia puntuale
- La probabilità che il pagamento venga effettuato in ritardo
- La probabilità che il pagamento venga effettuato molto in ritardo

La funzionalità fornisce inoltre una visualizzazione aggregata dei pagamenti previsti.

[![Visualizzazione aggregata delle previsioni di pagamento](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

A ciascuna fattura è assegnata una probabilità di pagamento puntuale. Le fatture che hanno una probabilità di pagamento puntuale è inferiore al 50% vengono contrassegnate con un cerchio rosso per indicare che potrebbero richiedere attenzione da parte dell'agente di recupero crediti.

[![Elenco delle probabilità di pagamenti](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

La funzione Previsioni di pagamento del cliente fornisce anche informazioni contestuali per spiegare la previsione. Queste informazioni includono i principali fattori che hanno influenzato la previsione, lo stato attuale dell'azienda con il cliente e dettagli sul comportamento di pagamento storico del cliente.

In molte aziende, il processo di riscossione è stato un'attività reattiva. In altre parole, il processo di riscossione non inizia fino alla scadenza delle fatture. Le previsioni di pagamento dei clienti consentono alle organizzazioni di essere più proattive sulle riscossioni. Non devono più attendere che una transazione scada per avviare il processo di riscossione. Al contrario, possono utilizzare la funzionalità di previsione del pagamento per determinare se le riscossioni proattive miglioreranno la probabilità di pagamento puntuale.

## <a name="methodology"></a>Metodologia

In passato, era generalmente difficile sviluppare e distribuire una soluzione di intelligenza artificiale. Il processo richiedeva un team di data scientist, esperti in materia e ingegneri che lavorano per un lungo periodo di tempo per formulare, sviluppare, implementare e mantenere una soluzione AI utilizzabile. Le previsioni di pagamento dei clienti semplificano la distribuzione e l'utilizzo di una soluzione di intelligenza artificiale in Microsoft Dynamics 365 Finance. Microsoft sta preparando soluzioni di intelligenza artificiale basate su Microsoft AI Builder. Pertanto, gli utenti possono distribuire la soluzione di intelligenza artificiale con un solo clic del mouse per sfruttare i vantaggi delle previsioni intelligenti. Se non sei soddisfatto della precisione delle previsioni, un utente esperto, sempre utilizzando un solo clic, può accedere all'esperienza dell'estensione AI Builder, quindi selezionare o deselezionare i campi utilizzati per generare previsioni. Quando sei pronto, puoi "eseguire il training" del modello e pubblicare le modifiche. Il modello il cui training è stato appena completato verrà automaticamente selezionato per generare le previsioni in Dynamics 365 Finance.

## <a name="release-details"></a>Dettagli del rilascio

È disponibile un'anteprima pubblica di Informazioni dettagliate finanziarie da provare per le distribuzioni negli Stati Uniti, in Europa e nel Regno Unito. Microsoft sta aggiungendo in modo incrementale il supporto per altre aree geografiche.

Le funzionalità di anteprima pubblica possono essere attivate solo negli ambienti sandbox di livello 2. I modelli di configurazione e intelligenza artificiale creati in un ambiente sandbox non possono essere migrati in un ambiente di produzione. Per ulteriori informazioni, vedi [Condizioni integrative per le versioni di anteprima di Microsoft Dynamics 365](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Informativa sulla privacy

Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]