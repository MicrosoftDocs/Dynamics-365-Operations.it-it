---
title: Configurare la gestione delle attività
description: Questo argomento descrive come configurare le funzionalità di gestione delle attività in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 742d49b1b7b46952d0a8bb6c8a33cde2a35d124f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791704"
---
# <a name="configure-task-management"></a>Configurare la gestione delle attività

[!include [banner](includes/banner.md)]

Questo argomento descrive come configurare le funzionalità di gestione delle attività in Microsoft Dynamics 365 Commerce.

Prima che i manager e i dipendenti Dynamics 365 Commerce possano utilizzare le funzionalità di gestione delle attività in Commerce, la gestione delle attività deve essere configurata. I passaggi della configurazione includono la concessione di autorizzazioni a manager e dipendenti, la distribuzione delle autorizzazioni ai clienti del punto vendita (POS), l'impostazione delle notifiche POS e la configurazione del riquadro **Attività** sulla home page di un'applicazione POS.

## <a name="configure-permissions-for-store-managers"></a>Configurare le autorizzazioni per i responsabili punto vendita

Ogni addetto in un determinato negozio può visualizzare tutte le attività assegnate a quel negozio. Possono anche aggiornare lo stato delle attività loro assegnate. Tuttavia, i gestori di negozi devono disporre delle autorizzazioni di gestione delle attività per gestire le attività assegnate al negozio e per creare attività con unico scopo.

Per configurare le autorizzazioni di gestione delle attività per i gestori del negozio, attenersi alla seguente procedura.

1. Passare a **Retail e Commerce \> Dipendenti \> Gruppi di autorizzazioni**.
1. Selezionare un gruppo di autorizzazioni specifico (ad esempio, **Manager**), quindi selezionare **Modifica**.
1. Nella scheda dettaglio **Autorizzazioni**, impostare l'opzione **Consenti gestione attività** su **Sì**.
1. Nella scheda dettaglio **Notifiche** aggiungere l'operazione **Gestione attività** e immettere un valore nel campo **Ordine di visualizzazione**. Ad esempio, inserire **2** se l'operazione **Evasione ordine** ha già un valore **Ordine di visualizzazione** di **1**.
    
> [!NOTE]
> Se una persona non responsabile deve disporre delle autorizzazioni di gestione attività nel POS, è possibile concedere l'autorizzazione alla persona. In alternativa, è possibile creare un nuovo gruppo di autorizzazioni per i non gestori e impostare l'opzione **Consenti gestione attività** su **Sì**.

La seguente illustrazione mostra come configurare le autorizzazioni di gestione delle attività per i gestori del negozio.

![Configurazione delle autorizzazioni di gestione delle attività per i gestori del negozio](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a>Configurare le autorizzazioni per i dipendenti

I dipendenti devono disporre delle autorizzazioni per creare elenchi di attività, gestire criteri di assegnazione e configurare la ricorrenza di qualsiasi elenco di attività. Per configurare queste autorizzazioni, si assegnano i dipendenti al ruolo **Responsabile attività vendita al dettaglio**.

Per configurare le autorizzazioni per un dipendente, effettuare le seguenti operazioni.

1. Passare a **Retail e Commerce \> Dipendenti \> Utenti**.
1. Selezionare un dipendente.
1. Nella scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli**.
1. Nella finestra di dialogo **Assegna ruoli all'utente** selezionare il ruolo **Responsabile attività vendita al dettaglio**, quindi selezionare **OK**.

## <a name="distribute-permissions-to-pos-clients"></a>Distribuire le autorizzazioni ai client POS

Prima che i dipendenti possano utilizzare i client POS, le autorizzazioni devono essere distribuite e sincronizzate con i client.

Per distribuire le autorizzazioni ai client POS, attenersi alla seguente procedura.

1. Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.
1. Selezionare la programmazione della distribuzione **1060** (**Personale**), quindi selezionare **Esegui adesso**.
1. Selezionare la programmazione della distribuzione **1070** (**Configurazione canale**), quindi selezionare **Esegui adesso**.

## <a name="configure-pos-notifications-for-tasks"></a>Configurare le notifiche POS per le attività

La gestione delle attività deve essere configurata in modo tale che le notifiche siano disponibili nell'applicazione POS.

Per configurare le notifiche POS per le attività, effettuare le seguenti operazioni.

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Operazioni POS**.
1. Trovare l'operazione **1400** (**Gestione delle attività**) e selezionare la casella di controllo **Abilita notifiche**.

La seguente illustrazione mostra l'operazione **Gestione delle attività** nella pagina **Operazioni POS**.

![Operazione di gestione delle attività nella pagina Operazioni POS](media/HQ-POS-Tasks-Notifications.png)

Per ulteriori informazioni su come configurare le notifiche POS, vedere [Visualizzare le notifiche degli ordini nel POS](notifications-pos.md).

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a>Configurare il riquadro Attività in una home page dell'applicazione POS

Prima di configurare il riquadro **Attività** sulla home page di un'applicazione POS, vedere [Layout delle schermate per il POS](pos-screen-layouts.md) per informazioni su come configurare e aggiungere nuovi pulsanti a un layout di schermata POS.

Per configurare il riquadro **Attività** in una home page dell'applicazione POS, attenersi alla procedura seguente.

1. Passare a **Retail e Commerce \> Impostazione canale \> Impostazione POS \> POS \> Layout schermo**.
1. Selezionare un layout dello schermo, selezionare una dimensione del layout e selezionare una griglia di pulsanti.
1. Nella scheda dettaglio **Griglie dei pulsanti**, selezionare **Progettazione** per modificare la griglia dei pulsanti selezionata.
1. Aggiungere un riquadro **Attività** alla sezione appropriata della home page.

Nella figura seguente è illustrato un esempio di un riquadro **Attività** nella home page del POS.

![Riquadro attività in una home page del POS](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della gestione attività](task-mgmt-overview.md)

[Creare elenchi di attività e aggiungere attività](task-mgmt-create-lists.md)

[Assegnare elenchi di attività a punti vendita o dipendenti](task-mgmt-assign-lists.md)

[Gestione delle attività in POS](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
