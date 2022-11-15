---
title: Annullare un processo di pianificazione
description: In questo articolo viene descritto come annullare un processo attivo di pianificazione che utilizza la funzionalità di ottimizzazione di pianificazione.
author: t-benebo
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
ms.author: benebotg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: f5f1f2c8e3e43e36d837ebf989422b0dca7819d6
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2022
ms.locfileid: "9741178"
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]