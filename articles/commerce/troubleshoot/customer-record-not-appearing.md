---
title: I record cliente non vengono visualizzati in Commerce Headquarters
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i record cliente non vengono visualizzati immediatamente in Commerce Headquarters.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: f1ad1f45abbc95cbf6d41b3c8681db781c6c9d23
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268840"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>I record cliente non vengono visualizzati in Commerce Headquarters

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando i record cliente non vengono visualizzati immediatamente in Commerce Headquarters.

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
