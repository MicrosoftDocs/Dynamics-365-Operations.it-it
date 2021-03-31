---
title: Stati del ciclo di vita del cespite
description: In questo argomento vengono descritti gli stati del ciclo di vita del cespite e i modelli del ciclo di vita in Gestione cespiti.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetLifecycleModelStateNext, EntAssetObjectLifecycleState, EntAssetLifecycleStateUpdate, EntAssetObjectLifecycleModel
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 64be80777991a9fa674ef494cea103a602c7559f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5230130"
---
# <a name="asset-lifecycle-states"></a>Stati del ciclo di vita del cespite

[!include [banner](../../includes/banner.md)]

 

In questo argomento vengono descritti gli stati del ciclo di vita del cespite e i modelli del ciclo di vita in Gestione cespiti. Gli stati del ciclo di vita del cespite vengono utilizzato per definire se un cespite è attivo o inattivo. Ad esempio, è possibile impostare stati del ciclo di vita del cespite come **Creato**, **Attivo** e **Terminato**.

> [!NOTE]
> - Gli stati del ciclo di vita delle richieste sono collegati agli stati del ciclo di vita del cespite. Pertanto, quando una richiesta viene modificato in un nuovo stato del ciclo di vita, il cespite collegato alla richiesta viene modificato in un nuovo stato del ciclo di vita del cespite. Ad esempio, se lo stato del ciclo di vita di una richiesta viene cambiato in **In entrata**, lo stato del ciclo di vita del cespite collegato viene modificato nello stato del ciclo di vita selezionato nel campo **Stato del ciclo di vita in entrata** della scheda dettaglio **Stati del ciclo di vita del cespite** della pagina **Modelli di stato del ciclo di vita del cespite**. 


Gli stati del ciclo di vita del cespite possono essere impostati nei modelli del ciclo di vita del cespite, in cui è possibile definire gli stati del ciclo di vita richiesti per diversi tipi di cespiti. Innanzi tutto si impostano gli stati di ciclo di vita. Successivamente si crea un modello del ciclo di vita e si selezionano gli stati del ciclo di vita per il modello.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Stati del ciclo di vita**.
2. Selezionare **Nuovo** per creare un nuovo stato del ciclo di vita del cespite.
3. Nel campo **Stato del ciclo di vita**, immettere l'ID dello stato del ciclo di vita.
4. Nel campo **Nome** immettere una descrizione.

    Nel campo **Modelli del ciclo di vita** viene visualizzato il numero di modelli del ciclo di vita del cespite che utilizzano lo stato del ciclo di vita del cespite.

5. Impostare l'opzione **Attivo** su **Sì** se questo stato del ciclo di vita deve essere uno stato del ciclo di vita attivo ovvero se ordini di lavoro possono essere creati per i cespiti che sono in questo stato del ciclo di vita.
6. Impostare l'opzione **Elimina righe di calendario aperte** su **Sì** se le righe del calendario aperte del cespite con lo stato del ciclo di vita del cespite **Creato** devono essere eliminate quando sono in questo stato del ciclo di vita. Questa impostazione è utile se si desidera pulire i programmi di manutenzione aperti che non sono più pertinenti per il cespite, ad esempio se il cespite non è più attivo.

> [!NOTE]
> Gli stati del ciclo di vita del cespite, i modelli del ciclo di vita del cespite e i tipi di cespite sono correlati. Vengono utilizzati nello stesso modo come gli stati del ciclo di vita dell'ordine di lavoro, i modelli del ciclo di vita dell'ordine di lavoro e tipi di ordine di lavoro. 


Dopo aver creato gli stati del ciclo di vita del cespite necessari, è possibile impostare gli stati del ciclo di vita nei modelli del ciclo di vita del cespite.

1. Selezionare **Gestione cespiti** \> **Impostazione** \> **Cespiti** \> **Modelli del ciclo di vita**.
2. Selezionare **Nuovo** per creare un nuovo modello del ciclo di vita del cespite.
3. Nel campo **Modello del ciclo di vita**, immettere l'ID dello modello del ciclo di vita.
4. Nel campo **Nome** immettere una descrizione.

    Nel campo **Stati del ciclo di vita** viene visualizzato il numero di stati del ciclo di vita del cespite selezionati nel modello del ciclo di vita del cespite. Nel campo **Tipi di cespite** viene visualizzato il numero di tipi di cespite che utilizzano il modello del ciclo di vita.

5. Nella Scheda dettaglio **Stati del ciclo di vita**, selezionare gli stati del ciclo di vita del cespite che devono essere inclusi nel modello:

    - Per utilizzare uno stato del ciclo di vita per il modello, selezionarlo nella sezione **Stati del ciclo di vita rimanenti** e quindi fare clic sul pulsante freccia destra ![Freccia destra](media/15-setup-for-objects.png) per spostarlo nella sezione **Stati del ciclo di vita selezionati**.
    - Per utilizzare tutti gli stati del ciclo di vita disponibili per il modello, selezionare il pulsante **Tutti gli stati del ciclo di vita disponibili** ![Tutti gli stati del ciclo di vita disponibili](media/20-setup-for-objects.png). Tutti gli stati del ciclo di vita verranno trasferiti nella sezione **Stati del ciclo di vita selezionati**.
    - Per rimuovere uno stato del ciclo di vita dal modello, selezionarlo nella sezione **Stati del ciclo di vita selezionati** e quindi fare clic sul pulsante freccia sinistra ![Freccia sinistra](media/16-setup-for-objects.png) per spostarlo nella sezione **Stati del ciclo di vita rimanenti**.

6. Selezionare **Aggiornamenti stati del ciclo di vita** per definire quali stati del ciclo di vita del cespite possono seguire uno stato selezionato.
7. È possibile utilizzare la Scheda dettaglio **Stato del cespite** per gestire i cespiti ricevuti per la riparazione. Nella sezione **In entrata/in uscita**, è possibile selezionare gli stati del ciclo di vita del cespite per indicare il flusso di lavoro di un cespite ricevuto per la riparazione. Se si offrono cespiti in prestito a clienti o reparti, nella sezione **Prestito**, è possibile selezionare gli stati del ciclo di vita per i cespiti di prestito.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]