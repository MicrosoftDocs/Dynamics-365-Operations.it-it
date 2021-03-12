---
title: Assegnare elenchi di attività a punti vendita o dipendenti
description: Questo argomento descrive come assegnare elenchi di attività a negozi o dipendenti in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ee924f5bf95d47814e7ca09b392a3d10b5e9b9dc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5006262"
---
# <a name="assign-task-lists-to-stores-or-employees"></a>Assegnare elenchi di attività a punti vendita o dipendenti

[!include [banner](includes/banner.md)]

Questo argomento descrive come assegnare elenchi di attività a negozi o dipendenti in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La gestione delle attività in Dynamics 365 Commerce consente di assegnare un elenco di attività a più negozi o dipendenti o a una combinazione di negozi e dipendenti. Ad esempio, un responsabile regionale di 20 negozi potrebbe voler assegnare l'elenco attività **Preparazione delle festività** per tutti e 20 i negozi.

## <a name="start-the-task-list-assignment-process"></a>Avviare il processo di assegnazione dell'elenco attività

Per avviare il processo di assegnazione di un elenco di attività, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Gestione delle attività \> Amministrazione gestione delle attività**.
1. Selezionare l'elenco delle attività da assegnare.
1. Selezionare **Avvia processo**.
1. Nella finestra di dialogo **Avvia processo**, nella scheda **Generale**, nel campo **Nome processo**, inserire un nome (ad esempio, **Negozi area orientale**).
1. Nel campo **Data stabilita** specificare una data.
1. Per assegnare l'elenco delle attività ai negozi, nella scheda **Punti vendita**, utilizzare il filtro **Gerarchia organizzativa** per trovare e selezionare i negozi.

    Per assegnare l'elenco delle attività ai dipendenti, nella scheda **Lavoratori** trovare e selezionare i dipendenti.

1. Selezionare **OK** per avviare il processo. L'elenco delle attività viene assegnato ai negozi o ai dipendenti selezionati.

La seguente illustrazione mostra un esempio di come trovare e selezionare i negozi nella finestra di dialogo **Avvia processo**.

![Ricerca e selezione di punti vendita nella finestra di dialogo Avvia processo](media/HQ-Assign-Tasks-Lists.png)

## <a name="assign-task-lists-on-a-recurring-basis"></a>Assegnare gli elenchi attività su base ricorrente

A volte i rivenditori hanno attività ricorrenti, come "Elenco di controllo per la chiusura di giovedì" o "Elenco di controllo per il primo giorno del mese". Pertanto, potrebbero voler assegnare l'elenco delle attività su base ricorrente.

1. Andare a **Retail e Commerce \> Gestione delle attività \> Amministrazione gestione delle attività**.
1. Selezionare l'elenco delle attività da assegnare.
1. Selezionare **Avvia processo**.
1. Nella finestra di dialogo **Avvia processo**, nella scheda **Generale**, nel campo **Nome processo**, inserire un nome.
1. Impostare l'opzione **Ricorrenza** su **Sì**.
1. Nel campo **Offset data destinazione ricorrenza in giorni**, immettere un numero di giorni. Ad esempio, se si immette **4**, la data stabilita è la data di ricorrenza più quattro giorni.
1. Nella scheda **Esecuzione in background** selezionare **Ricorrenza**.
1. Nella finestra di dialogo **Definisci ricorrenza**, immettere i criteri di frequenza, quindi selezionare **OK**.

La seguente illustrazione mostra un esempio di come inserire i criteri di frequenza nella finestra di dialogo **Definisci ricorrenza**.

![Immettere i criteri di frequenza nella finestra di dialogo Definisci ricorrenza](media/HQ-Assign-Tasks-Lists-Recurrently.png)

## <a name="track-task-list-status"></a>Tenere traccia dello stato dell'elenco attività

Se si è un responsabile di area o un gestore del negozio, si potrebbe voler tenere traccia dello stato degli elenchi di attività che sono stati assegnati a più negozi o dipendenti. È quindi possibile seguire i negozi o i lavoratori che non hanno completato le attività assegnate in tempo. Il back office di Commerce ti consente di visualizzare lo stato degli elenchi di attività, riassegnare le attività o modificare lo stato di un'attività.

Per tenere traccia dello stato dell'elenco attività per tutte le attività, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Gestione delle attività \> Processi gestione delle attività**.
1. Selezionare la scheda **Tutti gli elenchi di attività** per visualizzare lo stato di tutti gli elenchi di attività assegnati a vari negozi.

Per tenere traccia dello stato dell'elenco attività per tutte le attività assegnate all'utente corrente, attenersi alla seguente procedura.

1. Andare a **Retail e Commerce \> Gestione delle attività \> Processi gestione delle attività**.
1. Selezionare la scheda **Attività personali** o **Tutte le attività** per visualizzare o aggiornare lo stato delle attività assegnate all'utente corrente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della gestione attività](task-mgmt-overview.md)

[Configurare la gestione delle attività](task-mgmt-configure.md)

[Creare elenchi di attività e aggiungere attività](task-mgmt-create-lists.md)

[Gestione delle attività in POS](task-mgmt-POS.md)
