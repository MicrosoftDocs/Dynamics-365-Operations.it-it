---
title: Tempi di fermo per la manutenzione per ordini di lavoro
description: Questo articolo descrive come creare registrazioni di tempi di fermo per la manutenzione nel cespite selezionato in un ordine di lavoro.
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
ms.openlocfilehash: 7a76c0ecefbb8da762ac68cbdd7bb44f68a89894
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851858"
---
# <a name="maintenance-downtime-for-work-orders"></a>Tempi di fermo per la manutenzione per ordini di lavoro

[!include [banner](../../includes/banner.md)]


È possibile creare registrazioni di tempi di fermo per la manutenzione nel cespite selezionato in un ordine di lavoro. Questa funzionalità è utile se si desidera registrare i tempi di fermo per la manutenzione in una o più macchine nell'area di produzione. Innanzitutto, creare i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, ad esempio, **Suddivisione** e **Interruzione pianificata**. Questo passaggio viene eseguito nella pagina **Codici motivo dei tempi di fermo per la manutenzione**. Quindi, è possibile creare registrazioni di tempi di fermo per la manutenzione nella pagina **Tempi di fermo per la manutenzione** e aggiungere i codici motivo dei tempi di fermo per la manutenzione pertinenti.

## <a name="create-maintenance-downtime-reason-codes"></a>Creare codici motivo dei tempi di fermo per la manutenzione

1. Selezionare **Gestione cespiti** > **Impostazione** > **Ordini di lavoro** > **Codici motivo dei tempi di fermo per la manutenzione**.

2. Selezionare **Nuovo**.

3. Nel campo **Codici motivo dei tempi di fermo per la manutenzione**, immettere un ID per il codice motivo dei tempi di fermo per la manutenzione.

4. Nel campo **Nome** immettere un nome.

5. Selezionare la casella di controllo **Includi in KPI** se il codice motivo viene incluso nei calcoli degli indicatori di prestazioni chiave (KPI) per il cespite. In genere, le interruzioni di produzione pianificate non devono essere incluse nei calcoli KPI perché non influenzano le prestazioni previste.

6. Selezionare **Salva**.

Nella figura seguente è illustrato un esempio della pagina **Codici motivo dei tempi di fermo per la manutenzione**.

![Figura 1.](media/15-work-orders.png)

Dopo aver creato i codici motivo dei tempi di fermo per la manutenzione che si desidera utilizzare, è possibile creare registrazioni di tempi di fermo per la manutenzione per ordini di lavoro e cespiti.


## <a name="create-maintenance-downtime-registrations"></a>Creare registrazioni di tempi di fermo per la manutenzione

1. Fare clic su **Gestione cespiti** > **Comune** > **Ordini di lavoro** > **Tutti gli ordini di lavoro** o **Ordini di lavoro attivi**.

2. Selezionare l'ordine di lavoro, quindi nella scheda **Ordine di lavoro**, nel gruppo **Cespite**, selezionare **Tempi di fermo per la manutenzione**.

3. Selezionare **Nuovo**.

4. Nei campi **Dal** e **Al**, definire la data e l'intervallo di tempo per la registrazione dei tempi di inattività per la manutenzione.

>[!NOTE]
>Quando si lascia vuoto il campo **A**, la durata in ore viene immessa automaticamente nel campo **Durata**.

5. Selezionare un codice motivo nel campo **Codice motivo dei tempi di fermo per la manutenzione**.

6. Ripetere i passaggi da 3 a 5 per aggiungere ulteriori registrazioni.

7. Selezionare **Salva**.

Nella figura seguente viene illustrato un esempio di una registrazione dei tempi di fermo per la manutenzione.

![Figura 2.](media/16-work-orders.png)

Il calendario utilizzato per calcolare una registrazione di tempi di fermo per la manutenzione dipende dalla selezione nell'impostazione dei cespiti e dei parametri. Se una risorsa è selezionata in un cespite nel campo **Risorsa** della scheda dettaglio **Cespite** della pagina **Tutti i cespiti**, viene utilizzata l'impostazione del calendario per il gruppo di risorse associato, come illustrato nella figura seguente.

![Figura 3.](media/17-work-orders.png)

Se non si seleziona una risorsa nel cespite, viene utilizzato il calendario standard selezionato nella pagina **Parametri di gestione cespiti**, come illustrato nella figura seguente.

![Figura 4.](media/18-work-orders.png)

Fare clic su **Gestione cespiti** > **Richieste di informazioni** > **Tempi di fermo per la manutenzione** per visualizzare una panoramica di tutte le registrazioni di tempi di fermo per la manutenzione.

>[!NOTE]
>Tutti i calendari utilizzati nel modulo **Gestione cespiti** sono impostati in **Amministrazione organizzazione** > **Impostazione** > **Calendari** > **Calendari**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]