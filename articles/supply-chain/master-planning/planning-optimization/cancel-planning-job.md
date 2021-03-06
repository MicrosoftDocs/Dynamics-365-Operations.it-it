---
title: Annullare un processo di pianificazione
description: In questo argomento viene descritto come annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.
author: ChristianRytt
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: e9cf4902251c3c2b93af12a8ad9bd571930ef769
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833331"
---
# <a name="cancel-a-planning-job"></a>Annullare un processo di pianificazione

[!include [banner](../../includes/banner.md)]

In Microsoft Dynamics 365 Supply Chain Management è possibile annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione. Quando si seleziona **Annulla** nella finestra di dialogo e un processo di ottimizzazione di pianificazione viene attivato direttamente dall'interfaccia utente (non in background), il processo di ottimizzazione di pianificazione non verrà annullato. Anche se si riceve un avviso come "Operazione annullata", sarà comunque necessario utilizzare i seguenti passaggi per annullare un processo di pianificazione con l'ottimizzazione della pianificazione.


Per annullare un processo attivo di pianificazione, effettuare le seguenti operazioni. 

> [!NOTE]
> Solo i processi attivo possono essere annullati.

1. Passare a **Pianificazione generale \> Impostazione \> Piani**.
2. Selezionare un piano appropriato per l'esecuzione di pianificazione.
3. Selezionare **Storico**.
4. Selezionare il processo di pianificazione da annullare.
5. Selezionare **Annulla**.

Lo stato del processo sarà **Annullamento in corso** finché il servizio di ottimizzazione di pianificazione non conferma che il processo è stato annullato. Lo stato quindi diventa **Annullato**.

> [!NOTE]
> Per visualizzare le modifiche di stato, è necessario aggiornare la pagina facendo clic sul pulsante **Aggiorna**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sull'ottimizzazione della pianificazione](planning-optimization-overview.md)

[Introduzione all'ottimizzazione della pianificazione](get-started.md)

[Analisi di adeguatezza dell'ottimizzazione di pianificazione](planning-optimization-fit-analysis.md)

[Visualizzare la cronologia del piano e i log di pianificazione](plan-history-logs.md)

[Applicare i filtri a un piano](plan-filters.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]