---
title: Cespiti e ordini di lavoro
description: In questo argomento vengono descritti gli ordini di lavoro e i cespiti in Gestione cespiti.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 65adcd07f1649b2e4eb2e2528507bb15631782ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816726"
---
# <a name="work-orders-and-fixed-assets"></a>Cespiti e ordini di lavoro

[!include [banner](../../includes/banner.md)]


In Gestione cespiti, i cespiti possono essere associati a cespiti ed è possibile creare ordini di lavoro per tali cespiti. Se si utilizza questa funzionalità, è possibile ottenere una panoramica completa dei cespiti, dei progetti di investimento correlati e dei costi registrati nei progetti di investimento nei moduli **Gestione progetti e contabilità** e **Cespiti** in Microsoft Dynamics 365 for Finance and Operations.

>[!NOTE]
>Il campo **Numero cespite** viene compilato nel progetto di processo di ordine di lavoro solo se il tipo **Investimento** è selezionato come tipo di progetto nel progetto di processo di ordine di lavoro.

L'illustrazione seguente mostra la relazione tra un progetto di investimento nel modulo **Gestione progetti e contabilità** e un progetto di processo ordine di lavoro.

![Figura 1](media/24-work-orders.png)

Nella seguente procedura viene descritta la relazione tra cespiti, ordini di lavoro, progetti di processo di ordine di lavoro e cespiti.

1. Si crea un cespite che si collega a un cespite.

![Figura 2](media/25-work-orders.png)

2. Quando si impostano tipi di ordine di lavoro nella pagina **Tipi di ordine di lavoro** (**Gestione risorse** > **Impostazione** > **Ordini di lavoro** > **Tipi di ordine di lavoro**), si crea un tipo di ordine di lavoro per la gestione degli investimenti. Vedere anche [Tipi di ordine di lavoro](../setup-for-work-orders/work-order-types.md).

![Figura 3](media/26-work-orders.png)

3. Quando si impostano gruppi di progetti di ordine di lavoro nella scheda **Gruppo di progetti** della pagina **Impostazione del progetto dell'ordine di lavoro** (**Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Impostazione progetto**), si crea una relazione tra il tipo di ordine di lavoro utilizzato per gli investimenti e il gruppo di progetti creato per gli investimenti nella pagina **Gruppi di progetti** page del modulo **Gestione progetti e contabilità** (**Gestione progetti e contabilità** > **Impostazione** > **Registrazione** > **Gruppi di progetti**).

![Figura 4](media/27-work-orders.png)

4. Quando si crea un ordine di lavoro associato a un oggetto cespiti, si seleziona il tipo di ordine di lavoro utilizzato per la gestione degli investimenti, ad esempio **Investimento**.

5. Quando viene creato l'ordine di lavoro, il tipo di ordine di lavoro associato viene visualizzato nella pagina **Tutti gli ordini di lavoro**.

![Figura 5](media/28-work-orders.png)

6. Quando viene creato l'ordine di lavoro, viene creato il progetto correlato all'ordine di lavoro nella pagina **Tutti i progetti** del modulo **Gestione progetti e contabilità** (**Gestione progetti e contabilità** > **Progetti** > **Tutti i progetti**). Per visualizzare le informazioni correlate al progetto, selezionare il collegamento nel campo **ID progetto** della scheda **Generale** della scheda dettaglio **Dettagli riga** nella visualizzazione dei dettagli della pagina **Tutti gli ordini di lavoro** del modulo **Gestione cespiti** (**Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro**).

![Figura 6](media/29-work-orders.png)

7. Per visualizzare una panoramica dei progetti associati a un cespite, selezionare **Cespiti** > **Cespiti** > **Cespiti**, quindi nel campo **Numero cespite**, selezionare il collegamento del cespite per aprire la visualizzazione dei dettagli. Espandere il riquadro **Informazioni correlate** sul lato destro della pagina e selezionare la scheda dettaglio **Progetti associati**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]