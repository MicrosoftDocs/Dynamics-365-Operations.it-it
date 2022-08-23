---
title: Abilitare la gestione coerente della modalità di consegna nei canali e-commerce
description: Questo articolo descrive come abilitare la gestione coerente della modalità di consegna per risolvere possibili problemi correlati ai flussi di addebiti nei canali di e-commerce di Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/24/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-02-10
ms.openlocfilehash: 43450c9d380bd57c234bb1c9acfbe296ab115f14
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279652"
---
# <a name="enable-consistent-delivery-mode-handling-in-e-commerce-channels"></a>Abilitare la gestione coerente della modalità di consegna nei canali e-commerce 

[!include [banner](includes/banner.md)]

Questo articolo descrive come abilitare la gestione coerente della modalità di consegna per risolvere possibili problemi correlati ai flussi di addebiti nei canali di e-commerce di Microsoft Dynamics 365 Commerce.

In Dynamics 365 Commerce, gli addebiti a livello di intestazione non ripartiti proporzionalmente non vengono applicati per impostazione predefinita nei canali di e-commerce. Questo comportamento potrebbe causare uno o entrambi i seguenti problemi nei canali di e-commerce:

- Non vengono visualizzati gli addebiti a livello di intestazione non ripartiti proporzionalmente.
- Gli addebiti per le modalità di consegna non sono coerenti tra la modalità di consegna selezionata e il riepilogo dell'ordine di pagamento.

Per risolvere questi problemi, è necessario attivare la funzionalità **Abilita la gestione della modalità di consegna coerente nel canale**. Questa funzionalità fa in modo che gli addebiti a livello di intestazione non ripartiti proporzionalmente vengano visualizzati nei canali di e-commerce e che le informazioni sulla consegna degli ordini cliente siano gestite in modo coerente dallo stesso flusso di lavoro della richiesta.

## <a name="turn-on-the-enable-consistent-delivery-mode-handling-in-channel-feature"></a>Attivare la funzionalità Abilita la gestione della modalità di consegna coerente nel canale

Per abilitare la funzionalità **Abilita la gestione della modalità di consegna coerente nel canale** in Commerce Headquarters, attenersi alla seguente procedura.

1. Apri l'area di lavoro **Gestione funzionalità** (**Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**).
1. Nell'elenco delle funzioni disponibili, cerca e seleziona **Abilita la gestione della modalità di consegna coerente nel canale**.
1. Nel riquadro di destra, seleziona **Abilita ora**.
