---
title: Chiudere la contabilità generale a fine periodo
description: In questo articolo vengono descritte le attività che vengono completate in genere quando si esegue una chiusura periodo per la contabilità generale.
author: aprilolson
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42a5df1cd1a73462c93012b26f9b9b5c1631f2ce
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878043"
---
# <a name="close-the-general-ledger-at-period-end"></a>Chiudere la contabilità generale a fine periodo

[!include [banner](../includes/banner.md)]

In questo articolo vengono descritte le attività che vengono completate in genere quando si esegue una chiusura periodo per la contabilità generale. 

In Contabilità generale, è possibile completare le procedure di chiusura per un periodo di tempo o un anno. La chiusura di processi consente di preparare il sistema per nuovo periodo. Per prepararsi per un nuovo anno, è necessario eseguire il processo di chiusura di fine anno. Ogni organizzazione ha processi e passaggi diversi che esegue per la fine di un periodo. Di seguito sono riportati alcuni passaggi facoltativi per la fine del periodo:

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

L'area di lavoro **Chiusura periodo finanziario** può essere utilizzata per organizzare e tenere traccia delle attività richieste per vari processi di fine periodo. 


Per ulteriori informazioni, vedere gli argomenti seguenti:
- [Area di lavoro chiusura periodo finanziario](financial-period-close-workspace.md) 
- [Chiusura di fine anno](Year-end-close.md)  
- [Chiusura in massa del periodo fiscale](tasks/mass-financial-period-close.md)






[!INCLUDE[footer-include](../../includes/footer-banner.md)]
