---
title: Disattivare una versione del flusso di produzione
description: Quando una versione del flusso di produzione attiva non è più necessaria, può essere disattivata.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1691dc644e2e191a9e74980784d6dcf741dcd598
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576762"
---
# <a name="deactivate-a-production-flow-version"></a>Disattivare una versione del flusso di produzione

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]