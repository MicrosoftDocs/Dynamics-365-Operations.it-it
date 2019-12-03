---
title: Creazione di ordini basata su inserimento continuo per le transazioni punto vendita al dettaglio
description: In questo argomento viene descritta la creazione di ordini basata su inserimento continuo per le transazioni punto vendita al dettaglio in Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/14/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: deb8399aa401af16b6fe123a433eb21864e178c6
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693091"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions-public-preview"></a>Creazione di ordini basata su inserimento continuo per le transazioni punto vendita al dettaglio (Anteprima pubblica)

[!include [banner](includes/banner.md)]

[!include [banner](includes/preview-banner.md)]

In Dynamics 365 Retail versione 10.0.4 e precedenti, la registrazione dei rendiconti di vendita al dettaglio è un'operazione di fine giornata e tutte le transazioni vengono registrate al termine della giornata. Le transazioni di grandi dimensioni devono quindi essere elaborate in un intervallo di tempo limitato, talvolta creando problemi di carico e blocco ed errori di registrazione dei rendiconti. Inoltre, i rivenditori non possono riconoscere ricavi e pagamenti nei registri durante la giornata.

Con l'anteprima pubblica della creazione di ordini basata su inserimento continuo introdotta in Retail versione 10.0.5, le transazioni vengono elaborate durante la giornata, mentre solo la riconciliazione finanziaria dei metodi di pagamento e di altre transazioni di gestione di cassa viene elaborata al termine della giornata. Questa funzionalità suddivide il carico della creazione di ordini cliente, fatture e pagamenti lungo l'arco della giornata, offrendo prestazioni percepite migliori e la capacità riconoscere i ricavi e i pagamenti nei registri in tempo quasi reale. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Come utilizzare la registrazione basata su inserimento continuo
  
1. Per abilitare la registrazione basata su inserimento continuo delle transazioni di vendita al dettaglio, andare a **Amministrazione sistema > Imposta > Configurazione licenza** e disabilitare la chiave **Rendiconti di vendita al dettaglio**.

2. Nella stessa pagina, abilitare la chiave di licenza **Rendiconti di vendita al dettaglio (inserimento continuo) - Anteprima**. Quando si abilita questa chiave, assicurarsi che non siano presenti rendiconti in attesa di registrazione. 

> [!Important]
> Prima di abilitare la chiave di licenza **Rendiconti di vendita al dettaglio (inserimento continuo) - Anteprima**, assicurarsi che non siano presenti rendiconti in attesa di registrazione.

3. Il documento di rendiconto corrente verrà suddiviso in due diversi tipi, rendiconto transazionale e rendiconto finanziario.

      - Il rendiconto transazionale raccoglierà tutte le transazioni di vendita al dettaglio non registrate e convalidate e creerà, alla frequenza configurata, ordini cliente, fatture di vendita, giornali di registrazione di pagamenti e sconti e transazioni ricavi/spese. È opportuno impostare questo processo su una frequenza di esecuzione elevata, in modo che i documenti vengano creati quando le transazioni di vendita al dettaglio vengono caricate in Retail Headquarters tramite il processo P. Poiché il rendiconto transazionale crea già ordini cliente e fatture di vendita, non è necessario configurare il processo batch **Registra magazzino**. Tuttavia, è ancora possibile utilizzarlo per soddisfare eventuali esigenze aziendali specifiche.  
      
     - Il rendiconto finanziario è progettato per essere creato al termine della giornata e supporta solo il metodo di chiusura **Turno**. Questo rendiconto sarà limitato alla riconciliazione finanziaria e creerà solo i giornali di registrazione per gli importi differenziali tra l'importo conteggiato e l'importo delle transazioni per i diversi metodi di pagamento, insieme ai giornali di registrazione per le altre transazioni di gestione di cassa.   

4. Per calcolare il rendiconto transazionale, scegliere **Vendita al dettaglio > Vendita al dettaglio IT > Registrazione POS > Calcola rendiconti transazionali in batch**. Per registrare i rendiconti transazionali in batch, scegliere **Vendita al dettaglio > Vendita al dettaglio IT > Registrazione POS > Registra rendiconti transazionali in batch**.

5. Per calcolare il rendiconto finanziario, scegliere **Vendita al dettaglio > Vendita al dettaglio IT > Registrazione POS > Calcola rendiconti finanziari in batch**. Per registrare i rendiconti finanziari in batch, scegliere **Vendita al dettaglio > Vendita al dettaglio IT > Registrazione POS > Registra rendiconti finanziari in batch**.

> [!NOTE]
> Le voci di menu **Vendita al dettaglio > Vendita al dettaglio IT > Registrazione POS > Calcola rendiconti in batch** e **Vendita al dettaglio > Vendita al dettaglio IT > Registrazione POS > Registra rendiconti in batch** vengono rimosse con questa nuova funzionalità.

In alternativa, i tipi di rendiconto finanziario e transazionale possono essere creati manualmente. Passare a **Vendita al dettaglio > Canali > Punti vendita al dettaglio** e fare clic su **Rendiconti di vendita al dettaglio**. Fare clic su **Nuovo** e scegliere il tipo di rendiconto che si desidera creare. Nei campi nella pagina **Rendiconti di vendita al dettaglio** e nelle azioni nel gruppo **Rendiconto** della pagina verranno visualizzati i dati e le azioni pertinenti in base al tipo di rendiconto selezionato.
