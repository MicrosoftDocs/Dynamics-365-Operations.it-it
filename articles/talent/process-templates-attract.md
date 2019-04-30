---
title: Creare un modello di processo in Attract
description: In questo argomento vengono fornite informazioni sulla creazione di un modello di processo in Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: ca04bb623b9ddd19f02efbf99289461a78ddd7f1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "856625"
---
# <a name="create-a-process-template-in-attract"></a>Creare un modello di processo in Attract

[!include [banner](includes/banner.md)]

Un *modello di processo di assunzione* contiene tutte le attività che devono essere incluse durante il processo di assunzione per una posizione lavorativa. In questo argomento sono descritti gli elementi di un modello di processo in Microsoft Dynamics 365 for Talent: Attract. Viene illustrato anche come creare un modello.

> [!NOTE]
> La creazione del modello fa parte del componente aggiuntivo per l'assunzione a livello globale per Attract.

## <a name="template-management"></a>Gestione modello

Le organizzazioni possono decidere se i membri del team o solo gli amministratori possono creare modelli di processi in Attract. Per configurare la gestione dei modelli, passare a **Interfaccia di amministrazione** \> **Gestione modello**. Affinché i membri del team creino i propri modelli, attivare la gestione modello. Se non si attiva la gestione modello, solo gli amministratori possono creare modelli.

## <a name="default-template"></a>Modello predefinito

Solo gli amministratori possono impostare il modello predefinito. Il modello predefinito viene utilizzato se non è selezionato un modello quando viene creato un processo. Per impostare il modello predefinito, passare a **Interfaccia di amministrazione** \> **Gestione modello**. Nella scheda del modello che dovrebbe essere quello predefinito, selezionare il pulsante con i puntini di sospensione (**...**), quindi selezionare **Imposta come predefinito**.

## <a name="create-a-process-template"></a>Creare un modello di processo

Gli amministratori, i reclutatori e i responsabili delle assunzioni possono creare modelli di processi. Un modello di processo comprende *fasi* e *attività*. Le fasi raggruppano insieme una o più attività. Per impostazione predefinita, ciascun modello di processo ha le attività Prospect, Domanda di lavoro e Offerta. Le fasi contenenti queste attività possono essere rinominate. È possibile aggiungere più fasi selezionando **+ Nuova fase**. È possibile aggiungere attività a una fase uno trascinandole nella fase appropriata o facendo doppio clic su di esse nell'elenco attività.

> [!NOTE]
> I nomi delle fasi sono visibili ai candidati nella pagina **Stato domanda di lavoro**. È opportuno considerare questo fatto quando si scelgono i nomi per le fasi.

Per ulteriori informazioni sulle attività, vedere [Attività del processo di assunzione in Attract](./activities-attract.md).

Per creare un modello di processo di assunzione, attenersi alla procedura seguente.

1. Andare a **Modelli**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome del modello** immettere un nome per il modello, quindi selezionare **Crea**.
4. Nell'elenco **Scegli il processo di approvazione** selezionare **Standard** per richiedere l'approvazione di un processo.
5. Selezionare questa opzione per abilitare o disabilitare i prospect.
6. Facoltativo: Aggiungere o rimuovere fasi.

    - Per aggiungere una fase, selezionare **+ Nuova fase**.
    - Per rimuovere una fase, passare il puntatore sulla fase, quindi fare clic sul pulsante di pattumiera visualizzato.

        > [!NOTE]
        > Le fasi Prospect, Domanda di lavoro e Offerta non possono essere rimosse, ma possono essere rinominate.

7. Facoltativo: Aggiungere o rimuovere attività.

    - Per aggiungere un'attività, trascinarla dall'elenco attività a destra alla fase appropriata. In alternativa, fare doppio clic sull'attività quindi selezionare la fase a cui aggiungerla.
    - Per rimuovere un'attività, espanderla, quindi fare clic sul pulsante di pattumiera nell'intestazione dell'attività.

8. Selezionare **Salva**.
