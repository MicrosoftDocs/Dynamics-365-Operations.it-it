---
title: I record cliente non vengono visualizzati in Commerce Headquarters
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i record cliente non vengono visualizzati immediatamente in Commerce Headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f551f94cec71ba7d740756c383b55741e9f8d42e20e63846ea6242383dc3ba32
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6733895"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>I record cliente non vengono visualizzati in Commerce Headquarters

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i record cliente non vengono visualizzati immediatamente in Commerce Headquarters.

## <a name="description"></a>Descrizione

Quando si crea un nuovo record cliente utilizzando il flusso di registrazione nella vetrina e-commerce, il record cliente corrispondente non viene visualizzato immediatamente in Commerce Headquarters.

## <a name="resolution"></a>Risoluzione

### <a name="disable-customer-creation-in-async-mode"></a>Disabilitare la creazione di clienti in modalità asincrona

> [!IMPORTANT]
> Se si disabilita la creazione di clienti in modalità asincrona, le prestazioni del sistema potrebbero risentirne, poiché la creazione di ogni record produrrà una richiesta in tempo reale a Commerce Headquarters. Inoltre, se Commerce Headquarters è inattivo (ad esempio, durante i flussi di manutenzione), qualsiasi nuovo flusso di creazione di clienti produrrà errori.

Per disabilitare la creazione di cliente in modalità asincrona in Commerce Headquarters, seguire questi passaggi.

1. Selezionare **Retail e Commerce \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**.
1. Se non si utilizzando già un profilo di funzionalità per il canale online, crearne uno.
1. Assicurarsi che l'opzione **Crea cliente in modalità asincrona** sia impostata su **No**.
1. Andare a **Retail e Commerce \> Canali \> Punti vendita online**.
1. Selezionare il punto vendita online per cui disabilitare la creazione di clienti in modalità asincrona.
1. Nella scheda **Generale**, assicurarsi che il campo **Profilo funzionalità** sia impostato sul profilo di funzionalità che si sta utilizzando per il canale online.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un tenant B2C in Commerce](../set-up-b2c-tenant.md)
