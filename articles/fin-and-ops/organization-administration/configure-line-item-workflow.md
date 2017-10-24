---
title: Configurare un flusso di lavoro voci
description: In questo argomento viene descritto come configurare un elemento del flusso di lavoro voci.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d888bf4285a27369b197ed66e5975cc806c640d3
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="configure-a-line-item-workflow"></a>Configurare un flusso di lavoro voci

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come configurare un elemento del flusso di lavoro voci.

Per configurare un elemento del flusso di lavoro voci, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento e scegliere **Proprietà** per aprire la pagina **Proprietà**. Quindi, per configurare le proprietà dell'elemento del flusso di lavoro voci, attenersi alle procedure indicate di seguito.

## <a name="name-the-lineitem-workflow-element"></a>Assegnare un nome all'elemento del flusso di lavoro voci
Per immettere un nome per l'elemento del flusso di lavoro voci, effettuare le operazioni indicate di seguito.

1.  Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2.  Nel campo **Nome** immettere un nome univoco per l'elemento del flusso di lavoro voci.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Specificare se verrà utilizzato lo stesso flusso di lavoro per elaborare tutte le voci.
Per specificare di utilizzare lo stesso flusso di lavoro per elaborare tutte le voci in un documento, attenersi alla procedura indicata di seguito.

1.  Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2.  Se lo stesso flusso di lavoro deve elaborare tutte le voci in un documento, fare clic su **Richiamare un solo flusso di lavoro per tutte le righe**. Selezionare quindi il flusso di lavoro da utilizzare per l'elaborazione delle voci.
3.  Se uno specifico flusso di lavoro deve elaborare voci che soddisfano un set specifico di condizioni, fare clic su **Richiama un flusso di lavoro per ogni voce**. Quindi, per definire il set di condizioni, effettuare le operazioni seguenti:
    1.  Scegliere **Aggiungi**.
    2.  Selezionare la condizione nella tabella.
    3.  Nella scheda **Nome condizione** immettere un nome per il set di condizioni da definire.
    4.  Fare clic su **Aggiungi condizione** per immettere una condizione.
    5.  Immettere altre condizioni, se necessario.
    6.  Per verificare la correttezza della configurazione del set di condizioni immesse, fare clic su **Test**. Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record e fare clic su **Test**. Il sistema valuta il record per determinare se soddisfa le condizioni definite. Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.

    Nella scheda **Flusso di lavoro** selezionare il flusso di lavoro da utilizzare per elaborare le voci che soddisfano il set di condizioni definite.





