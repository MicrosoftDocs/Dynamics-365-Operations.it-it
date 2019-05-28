---
title: Analisi dei pagamenti dei clienti (anteprima)
description: Questo argomento descrive come le analisi dei pagamenti dei clienti possono aiutare a prevedere quando una fattura verrà pagata e aiutare le organizzazioni a creare strategie di ottimizzazione che migliorano le probabilità di pagamenti tempestivi.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-04-02
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 9e722db6302d7ef51c01601cde245d4f4a333eba
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566249"
---
# <a name="customer-payment-insights-preview"></a>Analisi dei pagamenti dei clienti (anteprima)

[!include[banner](../includes/banner.md)]

> [!IMPORTANT]
> Questa funzionalità fa parte di una versione di destinazione ed è disponibile soltanto per gli utenti che hanno scelto l'anteprima privata. Questa funzionalità verrà inclusa in una prossima versione a disponibilità generale.

# <a name="overview"></a>Panoramica

Le organizzazioni scoprono spesso che è difficile prevedere quando un cliente pagherà le fatture. Questa mancanza di informazioni può condurre a previsioni di cassa non corrette, a processi inefficienti della raccolta e a possibilità di ordini che vengono emessi ai clienti che possono comportare un rischio di credito. L'analisi dei pagamenti del cliente (anteprima) utilizza Machine Learning per prevedere quando la fattura verrà pagata. Fornisce inoltre strategie di ottimizzazione che possono essere adattate di ottimizzare la probabilità che i clienti paghino con puntualità.

## <a name="predictions"></a>Previsioni

Le previsioni di pagamento consentono alle organizzazioni di migliorare i processi aziendali aiutando a:

-   Identificare facilmente le fatture che si prevede che verranno pagate in ritardo.
-   Adottare le misurazioni appropriate per migliorare le possibilità di ottenere il pagamento puntualmente.

L'analisi dei pagamenti del cliente (anteprima) utilizza Machine Learning per prevedere quando la fattura verrà pagata. Utilizza i dati storici di fatture, pagamenti e cliente per creare un modello di Machine Learning che venga usato per prevedere quando una fattura verrà pagata.

Per ciascuna la fattura aperta, l'analisi dei pagamenti del cliente (anteprima) stima tre probabilità di pagamento:

-  Probabilità che il pagamento venga effettuato con puntualità (entro la data di scadenza della fattura).
-  Probabilità che il pagamento venga effettuato entro 30 giorni dalla data di scadenza della fattura.
-  Probabilità che il pagamento venga effettuato dopo 30 giorni dalla data di scadenza della fattura.

Probabilità che i pagamenti vengano visualizzati nella sezione previsione.

[![Previsioni di pagamento](./media/Predictions-sm2.png)](./media/Predictions-sm2.png)

A ogni fattura viene inoltre assegnata una probabilità vincente di pagamento utilizzando uno dei tre scenari di probabilità di pagamento definite sopra. Lo scenario con la più alta probabilità di pagamento è lo scenario vincente.


Ad esempio, supponiamo che per una fattura la previsione mostri una probabilità del 71% che la fattura venga pagata puntualmente, una probabilità del 13% che venga pagata entro 30 giorni dalla data di scadenza e una probabilità del 16% che venga pagata dopo 30 giorni dalla data di scadenza. La probabilità più alta indica che la fattura rientrerà nello scenario di puntualità, pertanto la fattura verrà etichettata con la probabilità di essere pagata puntualmente.

[![Previsioni di pagamento](./media/payment-predict.png)](./media/payment-predict.png)

## <a name="optimization-strategies"></a>Strategie di ottimizzazione

Oltre alle previsioni di pagamento, l'analisi dei pagamenti del cliente (anteprima) può utilizzare le strategie di ottimizzazione per migliorare le possibilità di ottenere il pagamento puntuale. In questo modo le organizzazioni eseguono l'analisi "What if" consentendo agli utenti di regolare i parametri di fattura e di cliente e quindi di confrontare l'effetto corrispondente sulla probabilità di ricevere il pagamento delle fatture in tempo.

Ad esempio, per un'organizzazione può essere opportuno valutare gli effetti di aggiornamento dello sconto di cassa nelle fatture sulla probabilità di ricevere il pagamento in tempo. Quando le fatture vengono ottimizzate per utilizzare il nuovo sconto, gli utenti possono esaminare gli effetti dell'applicazione dello sconto sulla probabilità di ricevere i pagamenti per le fatture in tempo. Se il costo dell'applicazione dello sconto è minimo confrontato con il vantaggio di ricevere il pagamento in tempo, l'organizzazione può scegliere di applicare lo sconto selezionato a tutti i futuri ordini aperti.

> [!NOTE] 
> Attualmente, solo lo sconto è disponibile come strategia di ottimizzazione per l'analisi dei pagamenti del cliente (anteprima).

[![Previsioni ottimizzate](./media/optimized-pay.png)](./media/optimized-pay.png)

## <a name="how-to-get-customer-payment-insights-preview"></a>Come ottenere l'analisi dei pagamenti dei clienti (anteprima)

Se si desidera provare l'analisi dei pagamenti del cliente (anteprima), inviare un'e-mail al [team dell'anteprima di analisi finanziaria](mailto:fiap@microsoft.com). 

## <a name="privacy-statement"></a>Informativa sulla privacy

Le anteprime archiviano i dati dei clienti negli Stati Uniti. Inoltre, le anteprime (1) possono utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 for Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.
