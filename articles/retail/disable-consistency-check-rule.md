---
title: Disabilitare le regole nel controllo di coerenza per le transazioni di vendita al dettaglio
description: In questo argomento viene descritta la funzionalità per disabilitare le regole del controllo di coerenza per le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.openlocfilehash: 4bf8df2fb9f8f5c33ceb13eb012fb6879f81ec66
ms.sourcegitcommit: bdbca89bd9b328c282ebfb681f75b8f1ed96e7a8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/14/2019
ms.locfileid: "2586299"
---
# <a name="disable-rules-in-the-retail-transaction-consistency-checker"></a>Disabilitare le regole nel controllo di coerenza per le transazioni di vendita al dettaglio 

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Ogni rivenditore può avere scenari e processi aziendali molto specifici. Pertanto, non tutte le regole incluse nel controllo di coerenza per le transazioni di vendita al dettaglio sono applicabili a tutti i rivenditori. Per soddisfare le diverse esigenze, Microsoft Dynamics 365 Retail offre funzionalità utilizzabili per disabilitare le regole che non sono applicabili.

Per visualizzare l'elenco delle regole disponibili nel controllo di coerenza per le transazioni di vendita al dettaglio nel proprio ambiente e visualizzare lo stato di ogni regola, andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Parametri \> Parametri di vendita al dettaglio** e selezionare la scheda **Convalida transazioni**.

Per impostazione predefinita, lo stato di ogni regola è impostato su **Abilitato**. Pertanto, vengono utilizzate tutte le regole per convalidare le transazioni di vendita al dettaglio prima che queste vengano inserite nei relativi rendiconti. Per disabilitare una regola, modificarne lo stato in **Disabilitato**. Le regole disabilitate non vengono prese in considerazione per convalidare le transazioni di vendita al dettaglio durante il processo di calcolo dei rendiconti.

Per ignorare l'intero processo di convalida, indipendentemente da quali regole siano abilitate, andare a **Vendita al dettaglio \> Impostazione sedi centrali \> Parametri \> Parametri di vendita al dettaglio** e, nella scheda **Convalida transazioni**, impostare l'opzione **Disabilita controllo di coerenza per le transazioni di vendita al dettaglio** su **Sì**. Una volta impostata su **No**, questa opzione non può essere impostata nuovamente su **Sì** dall'interfaccia utente.
