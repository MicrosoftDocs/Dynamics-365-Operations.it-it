---
title: Panoramica della pianificazione dei carichi utilizzando il consolidamento hub
description: Questo articolo descrive la funzionalità di consolidamento delle spedizioni in un hub quando si consegnano merci dai magazzini diversi allo stesso cliente o quando merci vengono consegnate da più fornitori allo stesso magazzino.
author: Weijiesa
ms.date: 07/25/2019
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, TMSParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "92273"
- intro-internal
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 055d7c53b771e09002c84c643c45d3da9f71aca0
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676553"
---
# <a name="plan-loads-using-hub-consolidation-overview"></a>Panoramica della pianificazione dei carichi utilizzando il consolidamento hub

[!include [banner](../includes/banner.md)]

Questo articolo descrive la funzionalità di consolidamento delle spedizioni in un hub quando si consegnano merci dai magazzini diversi allo stesso cliente o quando merci vengono consegnate da più fornitori allo stesso magazzino.

Può essere utile consolidare le spedizioni in un hub, quando si consegnano merci dai magazzini diversi allo stesso cliente o quando merci vengono consegnate da più fornitori allo stesso magazzino.

## <a name="building-loads"></a>Allestimento dei carichi
Prima di poter utilizzare il consolidamento di hub, è necessario abilitare l'opzione **Pianificazione in transito** della pagina **Parametri di gestione trasporto**. È inoltre necessario creare gli hub in cui avrà luogo il consolidamento. Il diagramma seguente illustra un esempio di consolidamento di hub. In questo caso, gli ordini cliente da magazzini differenti vanno allo stesso cliente. I carichi di base vengono creati in base agli ordini cliente nel modo consueto, utilizzando la pagina **Workbench pianificazione carico**. Per consolidare i due carichi in un hub prima della consegna al cliente, nella pagina **Workbench pianificazione carico**, nel campo **Ttrasporto**, selezionare **Consolidamento hub**. Quando si seleziona l'hub corretto per ogni carico, i carichi avranno l'hub come la destinazione di consegna. Si avranno anche due "righe richiesta di trasporto" nella sezione **Domanda e offerta** della pagina **Workbench pianificazione carico**. È quindi possibile aggiungere queste due righe al nuovo carico. Questo nuovo carico disporrà di entrambe le righe ordine cliente e sarà dotato dell'hub come indirizzo di prelievo e del cliente A come destinazione di consegna. I tre carichi quindi sono pronti per valutati e indirizzati come qualsiasi altro carico. È possibile selezionare qualsiasi vettore di spedizione suggerito dal sistema per ogni carico. [![Consolidamento hub.](./media/hubconsol.jpg)](./media/hubconsol.jpg) È anche possibile utilizzare lo stesso metodo per consolidare i carichi per più ordini di trasferimento. In questo caso, il cliente A nel diagramma precedente è un magazzino. In alternativa, è possibile consolidare carichi per più ordini fornitore, dove i carichi vengono recapitati da fornitori diversi allo stesso magazzino. È possibile avere più di un hub di consolidamento e consolidare in più hub per più carichi che provengono da magazzini diversi. Dopo aver allestito i carichi di base e utilizzato l'opzione di consolidamento hub, si allestiscono i nuovi carichi utilizzando le righe di richiesta di trasporto consolidata. Quindi si valutano e si indirizzano i carichi.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]