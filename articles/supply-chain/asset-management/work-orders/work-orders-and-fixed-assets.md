---
title: Cespiti e ordini di lavoro
description: In questo argomento vengono descritti gli ordini di lavoro e i cespiti in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f03b7fa073c4e5338b7b5681ba7b8c9fe00a657b
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875729"
---
# <a name="work-orders-and-fixed-assets"></a>Cespiti e ordini di lavoro


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


In Gestione cespiti, i cespiti possono essere associati a cespiti ed è possibile creare ordini di lavoro per tali cespiti. Se si utilizza questa funzionalità, è possibile ottenere una panoramica completa dei cespiti, dei progetti di investimento correlati e dei costi registrati nei progetti di investimento nel modulo **Gestione progetti e contabilità** e nel modulo **Cespiti** in Dynamics 365 for Finance and Operations.

>[!NOTE]
>Il campo **Numero cespite** viene compilato nel progetto di processo di ordine di lavoro solo se il tipo "Investimento" è selezionato come tipo di progetto nel progetto di processo di ordine di lavoro.

![Figura 1](media/24-work-orders.png)

Nella seguente procedura viene descritta la relazione tra cespiti, ordini di lavoro, progetti di processo di ordine di lavoro e cespiti.

1. Si crea un cespite e lo si associa a un cespite, come illustrato nella figura seguente.

![Figura 2](media/25-work-orders.png)

2. Quando si impostano tipi di ordine di lavoro (**Gestione risorse** > **Impostazione** > **Ordini di lavoro** > **Tipi di ordine di lavoro**), si crea un tipo di ordine di lavoro per la gestione degli investimenti. Vedere anche [Tipi di ordine di lavoro](../setup-for-work-orders/work-order-types.md).

![Figura 3](media/26-work-orders.png)

3. Quando si impostano gruppi di progetti di ordine di lavoro (collegamento **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto** > **Gruppo di progetti** ), si crea una relazione tra il tipo di ordine di lavoro utilizzato per gli investimenti e il gruppo di progetti creato per gli investimenti nel modulo **Gestione progetti e contabilità** (**Gestione progetti e contabilità** > **Impostazione** > **Registrazione** > **Gruppi di progetti**).

![Figura 4](media/27-work-orders.png)

4. Quando si crea un ordine di lavoro associato a un oggetto cespiti, si seleziona il tipo di ordine di lavoro utilizzato per la gestione degli investimenti, ad esempio "Investimento".

5. Quando viene creato l'ordine di lavoro, il tipo di ordine di lavoro associato viene visualizzato in **Tutti gli ordini di lavoro**.

![Figura 5](media/28-work-orders.png)

6. Quando l'ordine di lavoro viene creato, il progetto associato all'ordine di lavoro viene creato in **Gestione progetti e contabilità** > **Tutti i progetti**. È possibile visualizzare le informazioni correlate al progetto facendo clic sul collegamento **ID progetto** (in **Gestione cespiti**, aprire l'ordine di lavoro nella visualizzazione Dettagli > Scheda dettaglio **Dettagli riga** > scheda **Generale** > campo **ID progetto**).

![Figura 6](media/29-work-orders.png)

7. In **Cespiti**, è possibile visualizzare una panoramica dei progetti associati a un cespite (**Cespiti** > **Cespiti** > **Cespiti** > fare clic sul cespite nel campo **Numero cespite** > visualizzare i contenuti nel riquadro **Informazioni correlate** > sezione **Progetti associati**).

