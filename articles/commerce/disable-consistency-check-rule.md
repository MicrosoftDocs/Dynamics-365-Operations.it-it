---
title: Disabilitare le regole nel controllo di coerenza per le transazioni di vendita al dettaglio
description: In questo argomento viene descritta la funzionalità per disabilitare le regole del controllo di coerenza per le transazioni in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 10/15/2019
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: ce2abe7e15773edc3122a1bfdf40f3b830e8790e
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792897"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Disabilitare le regole nel controllo di coerenza per le transazioni di vendita al dettaglio 

[!include [banner](../includes/banner.md)]

Ogni rivenditore può avere scenari e processi aziendali molto specifici. Pertanto, non tutte le regole incluse nel controllo di coerenza per le transazioni di commercio sono applicabili a tutti i rivenditori. Per soddisfare le diverse esigenze, Microsoft Dynamics 365 Commerce offre funzionalità che possono essere utilizzate per disabilitare le regole che non sono applicabili.

Per visualizzare l'elenco delle regole disponibili nel controllo di coerenza per le transazioni di vendita al dettaglio nel proprio ambiente e lo stato di ogni regola, andare a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri Commerce** e selezionare la scheda **Convalida transazioni**.

Per impostazione predefinita, lo stato di ogni regola è impostato su **Abilitato**. Pertanto, vengono utilizzate tutte le regole per convalidare le transazioni prima che queste vengano inserite nei relativi rendiconti. Per disabilitare una regola, modificarne lo stato in **Disabilitato**. Le regole disabilitate non vengono prese in considerazione per convalidare le transazioni durante il processo di calcolo dei rendiconti.

Per ignorare l'intero processo di convalida, indipendentemente da quali regole siano abilitate, andare a **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Parametri Commerce** e, nella scheda **Convalida transazioni**, impostare l'opzione **Disabilita controllo di coerenza per le transazioni di commercio** su **Sì**. Una volta impostata su **No**, questa opzione non può essere impostata nuovamente su **Sì** dall'interfaccia utente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]