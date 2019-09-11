---
title: Tempi di fermo per la manutenzione
description: In questo argomento vengono descritti i tempi di fermo per la manutenzione in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918246"
---
# <a name="maintenance-downtime"></a>Tempi di fermo per la manutenzione


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

È possibile creare registrazioni di tempi di fermo per la manutenzione nel cespite selezionato in un ordine di lavoro. Ciò è utile se si desidera registrare i tempi di fermo per la manutenzione in una o più macchine nell'area di produzione. Innanzitutto, creare i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, ad esempio, guasti e interruzione pianificate. Questa operazione viene eseguita in **Codici motivo dei tempi di fermo per la manutenzione**. Successivamente, è possibile creare registrazioni di tempi di fermo per la manutenzione in **Tempi di fermo per la manutenzione** e aggiungere i codici motivo pertinenti.

## <a name="create-maintenance-downtime-reason-codes"></a>Creare codici motivo dei tempi di fermo per la manutenzione

1. Fare clic **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Codici motivo dei tempi di fermo per la manutenzione**.

2. Fare clic su **Nuovo**.

3. Inserire un ID nel campo **Codici motivo dei tempi di fermo per la manutenzione**.

4. Nel campo **Nome** immettere un nome per il codice motivo.

5. Selezionare la casella di controllo **Includi in KPI** se il codice motivo deve essere incluso nei calcoli KPI dei cespiti. In genere, le interruzioni di produzione pianificate non devono essere incluse nei calcoli KPI poiché non influenzano le prestazioni previste.

6. Fare clic su **Salva**.

![Figura 1](media/15-work-orders.png)


Dopo aver creato i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, è possibile creare registrazioni di tempi di fermo per la manutenzione per ordini di lavoro e cespiti.


## <a name="create-maintenance-downtime-registrations"></a>Creare registrazioni di tempi di fermo per la manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro e fare clic su **Tempi di fermo per la manutenzione**.

3. Fare clic su **Nuovo**.

4. Immettere la data e l'intervallo di tempo per la registrazione di tempi di fermo per la manutenzione nei campi **Da** e **A**.

5. Quando si lascia vuoto il campo **A**, la durata in ore viene immessa automaticamente nel campo **Durata**.

6. Selezionare un codice motivo nel campo **Codice motivo dei tempi di fermo per la manutenzione**.

7. Ripetere i passaggi da 3 a 6 per aggiungere più registrazioni.

8. Fare clic su **Salva**.


![Figura 2](media/16-work-orders.png)


Il calendario utilizzato per calcolare una registrazione di tempi di fermo per la manutenzione dipende dalla selezione nell'impostazione dei cespiti e dei parametri. Se una risorsa è selezionata in un cespite in **Tutti i cespiti** > Scheda dettaglio **Cespite** > campo **Risorsa**, viene utilizzata l'impostazione del calendario per il gruppo di risorse associato, come illustrato nella figura seguente.

![Figura 3](media/17-work-orders.png)


Se non si seleziona una risorsa nel cespite, viene utilizzato il calendario standard selezionato in **Parametri di gestione cespiti**, come illustrato nella figura seguente.

![Figura 4](media/18-work-orders.png)


Fare clic su **Gestione cespiti aziendali** > **Richieste di informazioni** > **Tempi di fermo per la manutenzione** per visualizzare una panoramica di tutte le registrazioni di tempi di fermo per la manutenzione.

>[!NOTE]
>Tutti i calendari utilizzati nel modulo **Gestione cespiti** sono impostati in **Amministrazione organizzazione** > **Impostazione** > **Calendari** > **Calendari**.

