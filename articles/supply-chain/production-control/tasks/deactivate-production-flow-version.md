---
title: Disattivare una versione del flusso di produzione
description: Quando una versione del flusso di produzione attiva non è più necessaria, può essere disattivata.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 488f5d9e1137be2686f3f3056f4c4543766a16799a2f0484c3c4f0f9f3d456ad
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726779"
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