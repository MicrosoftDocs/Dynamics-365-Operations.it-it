---
title: Informazioni dettagliate pagamenti cliente (anteprima)
description: Questo argomento descrive la capacità di informazioni dettagliate pagamenti che aiuta a migliorare la comprensione delle pratiche di pagamento tipiche dei singoli clienti e può identificare circostanze che giustificano l'avvio di processi di raccolta prima di quanto altrimenti fatto.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/06/2019
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
ms.openlocfilehash: f9f1e4ae4270380c88069723e768fd44ecf8c113
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2773986"
---
# <a name="customer-payment-insights-preview"></a>Informazioni dettagliate pagamenti cliente (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo argomento descrive la capacità di informazioni dettagliate pagamenti che aiuta a migliorare la comprensione delle pratiche di pagamento tipiche dei singoli clienti e può identificare circostanze che giustificano l'avvio di processi di raccolta prima di quanto potrebbe essere altrimenti fatto. 

## <a name="overview"></a>Panoramica

Le organizzazioni scoprono spesso che è difficile prevedere quando i clienti pagano le fatture. Questa mancanza di informazione porta a previsioni del flusso di cassa meno accurate, processi di raccolta che iniziano troppo tardi e ordini che vengono rilasciati a clienti che potrebbero non ricevere il pagamento. Le informazioni dettagliate pagamenti cliente (anteprima) consentono alle organizzazioni di prevedere quando verrà pagata una fattura cliente, aiutando l'organizzazione a creare strategie di raccolta che migliorano la probabilità di essere pagati in tempo. 

## <a name="predictions"></a>Previsioni

Le previsioni di pagamento consentiranno alle organizzazioni di migliorare i propri processi aziendali aiutandole a identificare facilmente le fatture che possono essere pagate in ritardo e ad adottare misure adeguate che aumentano le loro possibilità di essere pagati in tempo.

Utilizzando un modello di Machine Learning che sfrutta fatture storiche, pagamenti e dati dei clienti, Informazioni dettagliate pagamenti cliente (anteprima) prevede in modo più accurato quando un cliente paga una fattura in sospeso.

Per ciascuna la fattura aperta, l'analisi dei pagamenti del cliente (anteprima) stima tre probabilità di pagamento:

-   Probabilità di pagamento effettuato in tempo 
-   Probabilità di pagamento effettuato in ritardo
-   Probabilità di pagamento effettuato molto in ritardo

Per consentire alle organizzazioni di comprendere l'importo totale del pagamento che possono aspettarsi da un cliente in uno dei tre bucket, In tempo, In ritardo e Molto in ritardo, Informazioni dettagliate pagamenti cliente (anteprima) fornisce anche una visione aggregata dei pagamenti previsti.

[![Visualizzazione aggregata delle previsioni di pagamento](./media/graphic-payment-reports.png)](./media/graphic-payment-reports.png)

Inoltre, ciascuna fattura è assegnata una probabilità di pagamento in tempo. Se la probabilità di pagamento in tempo è inferiore al 50%, le fatture vengono contrassegnate con un cerchio rosso per indicare che possono richiedere attenzione per la raccolta. 

[![Elenco delle probabilità di pagamenti](./media/customer-pymnt-probability-list.png)](./media/customer-pymnt-probability-list.png)

Informazioni dettagliate pagamenti cliente (anteprima) fornisce anche informazioni contestuali per spiegare la previsione, ad esempio i principali fattori che hanno influenzato le previsioni, lo stato attuale delle attività con il cliente e i dettagli sul comportamento di pagamento storico del cliente. In molte aziende, il processo di raccolta è stato un'attività reattiva; il processo di raccolta non inizia fino alla scadenza delle fatture. 

Con Informazioni dettagliate pagamenti cliente (anteprima), le organizzazioni possono essere più proattive sulle raccolte. Non devono più attendere che le transazioni scadano per avviare il processo di raccolta. Al contrario, possono utilizzare la capacità di previsione del pagamento per determinare se le raccolte proattive miglioreranno la probabilità di essere pagati in tempo. La previsione di pagamento fornisce inoltre alle aziende le informazioni necessarie per giustificare l'avvio anticipato del processo di raccolta.

## <a name="methodology"></a>Metodologia

Lo sviluppo e la distribuzione di una soluzione AI è difficile. Richiede un team di data scientist, esperti in materia e ingegneri che lavorano per un lungo periodo di tempo per formulare, sviluppare, implementare e mantenere una soluzione AI utilizzabile. Stiamo semplificando la distribuzione e l'utilizzo delle soluzioni AI in Finance. Stiamo preparando soluzioni AI in Finance basate su Microsoft AI Builder. Un utente finale, con il semplice clic del pulsante, può implementare la soluzione AI e iniziare a utilizzare i vantaggi delle previsioni intelligenti. Se un'organizzazione non è soddisfatta della precisione delle previsioni, un utente esperto, sempre utilizzando un solo clic, può accedere all'esperienza dell'estensione AI builder, quindi selezionare o deselezionare i campi utilizzati per generare previsioni. Una volta pronti, possono addestrare e pubblicare le modifiche e il modello appena addestrato verrà automaticamente selezionato per le previsioni in Finance.

## <a name="how-to-get-customer-payment-insights-preview"></a>Come ottenere l'analisi dei pagamenti dei clienti (anteprima)

Inviare un'e-mail a [Informazioni dettagliate pagamenti cliente (anteprima)](mailto:fiap@microsoft.com) se si è interessati a provare Informazioni dettagliate pagamenti cliente (anteprima).

## <a name="privacy-notice"></a>Informativa sulla privacy

Le anteprime (1) possono utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


