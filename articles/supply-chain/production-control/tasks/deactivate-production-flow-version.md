--- 
title: Disattivare una versione del flusso di produzione
description: "Quando una versione del flusso di produzione attiva non è più necessaria, può essere disattivata."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4a7eee6617e12d59a3d06207f5f6b58c93e28240
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="deactivate-a-production-flow-version"></a>Disattivare una versione del flusso di produzione

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Quando una versione del flusso di produzione attiva non è più necessaria, può essere disattivata. È consigliabile utilizzare questa opzione solo se tutte le regole kanban e attività sono terminate e non verranno attivate di nuovo. Si noti che la data di scadenza di tutte le regole kanban correlate a questa versione del flusso di produzione viene aggiornata alla data e l'ora correnti. 

Per modificare una versione del flusso di produzione attiva, valutare l'opportunità di impostare una data di scadenza per la versione attiva e creare una nuova versione. In questo modo sarà possibile continuare con le operazioni di produzione mentre si prepara la nuova versione e le regole kanban correlate. 

Per fare scadere una versione del flusso di produzione attiva, è necessario impostare una data di scadenza. In tal senso, la disattivazione è più simile a un'eccezione che a una regola. 

Per questa procedura è necessario un flusso di produzione con una versione che può essere disattivata. Non provare questo in un ambiente di produzione a meno che non si sia assolutamente sicuri che la versione è completamente obsoleta.


## <a name="deactivate-a-production-flow-version"></a>Disattivare una versione del flusso di produzione
1. Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Fare clic su Disattiva.
    * Non continuare se non si è assolutamente sicuri che questa versione del flusso di produzione è obsoleta. Se si fa clic su OK tutte le regole kanban attive scadranno e tutte le attività di produzione e rifornimento di questa versione del flusso di produzione verranno immediatamente interrotte.  
6. Fare clic su OK.


