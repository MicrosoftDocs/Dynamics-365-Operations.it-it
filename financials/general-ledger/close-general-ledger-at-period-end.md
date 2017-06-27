---
title: "Chiudere la contabilità generale a fine periodo"
description: "In questo argomento vengono descritte le attività che vengono completate in genere quando si esegue una chiusura periodo per la contabilità generale."
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 81d687cc16ef43442c8c1c166cc6f0d8b171e28f
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="close-the-general-ledger-at-period-end"></a>Chiudere la contabilità generale a fine periodo

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritte le attività che vengono completate in genere quando si esegue una chiusura periodo per la contabilità generale. 

In Contabilità generale, è possibile completare le procedure di chiusura per un periodo di tempo o un anno. La chiusura di processi consente di preparare il sistema per nuovo periodo. Per preparare il sistema per un nuovo anno, è necessario eseguire il processo di chiusura di fine anno. Ogni organizzazione ha processi e passaggi diversi che esegue per la fine di un periodo. Di seguito sono riportati alcuni passaggi facoltativi per la fine del periodo:

-   Completare tutte le attività per tutti gli altri moduli, ad esempio Contabilità clienti, Contabilità fornitori e Inventario.
-   Verificare che tutte i giornali di registrazione siano stati registrati.
-   Eseguire la rivalutazione valuta estera per generare tutti gli eventuali importi di perdite o profitti non realizzati.
-   Liquidare le transazioni per ogni conto CoGe.
-   Elaborare le eventuali allocazioni necessarie.
-   Registrare manualmente le rettifiche di fine periodo.
-   Inserire transazioni nel giornale di registrazione e revisionare il report **Giornale di registrazione contabile**.
-   Eseguire un consolidamento utilizzando una società di consolidamento o report finanziari.
-   Generare rendiconti finanziari di fine periodo utilizzando i report finanziari.
-   Impostare i periodi contabili su **In attesa** in modo che non vengano eseguite ulteriori registrazioni. Per un maggiore controllo, è inoltre possibile limitare un periodo a un gruppo di utenti specifico durante l'esecuzione delle attività di fine periodo. Non è consigliabile impostare i periodi su **Chiuso in modo permanente** poiché non è possibile riaprire un periodo che è stato chiuso.

L'area di lavoro Chiusura periodo finanziario può essere utilizzata per organizzare e tenere traccia delle attività richieste per vari processi di fine periodo. Fare riferimento agli argomenti [Area di lavoro Chiusura periodo finanziario](financial-period-close-workspace.md) e [Chiusura di fine anno](Year-end-close.md) per ulteriori informazioni. 






