---
title: Configurare i flussi di lavoro voci
description: In questo articolo viene descritto come configurare un elemento del flusso di lavoro voci.
author: ChrisGarty
ms.date: 11/03/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195833
ms.assetid: 3237347e-71d5-4569-bc9a-0d0fc9410b78
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 511493df4c897c0a8d2c53db2c9c893aa43d3589
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8889238"
---
# <a name="configure-line-item-workflows"></a>Configurare i flussi di lavoro voci

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

In questo articolo viene descritto come configurare un elemento del flusso di lavoro voci.

Per configurare un elemento del flusso di lavoro voci, nell'editor flusso di lavoro fare clic con il pulsante destro del mouse sull'elemento e scegliere **Proprietà** per aprire la pagina **Proprietà**. Quindi, per configurare le proprietà dell'elemento del flusso di lavoro voci, attenersi alle procedure indicate di seguito.

## <a name="name-the-line-item-workflow-element"></a>Assegnare un nome all'elemento del flusso di lavoro voci

Per immettere un nome per l'elemento del flusso di lavoro voci, effettuare le operazioni indicate di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Nel campo **Nome** immettere un nome univoco per l'elemento del flusso di lavoro voci.

## <a name="specify-whether-the-same-workflow-is-used-to-process-all-line-items"></a>Specificare se verrà utilizzato lo stesso flusso di lavoro per elaborare tutte le voci.

Per specificare di utilizzare lo stesso flusso di lavoro per elaborare tutte le voci in un documento, attenersi alla procedura indicata di seguito.

1. Nel riquadro sinistro, fare clic sull'icona **Impostazioni di base**.
2. Se lo stesso flusso di lavoro deve elaborare tutte le voci in un documento, fare clic su **Richiamare un solo flusso di lavoro per tutte le righe**. Selezionare quindi il flusso di lavoro da utilizzare per l'elaborazione delle voci.
3. Se uno specifico flusso di lavoro deve elaborare voci che soddisfano un set specifico di condizioni, fare clic su **Richiama un flusso di lavoro per ogni voce**. Quindi, per definire il set di condizioni, effettuare le operazioni seguenti:

    1. Scegliere **Aggiungi**.
    2. Selezionare la condizione nella tabella.
    3. Nella scheda **Nome condizione** immettere un nome per il set di condizioni da definire.
    4. Fare clic su **Aggiungi condizione** per immettere una condizione.
    5. Immettere altre condizioni, se necessario.
    6. Per verificare la correttezza della configurazione del set di condizioni immesse, fare clic su **Test**. Nella pagina **Test condizione flusso di lavoro**, nell'area **Convalida condizione**, selezionare un record e fare clic su **Test**. Il sistema valuta il record per determinare se soddisfa le condizioni definite. Fare clic su **OK** o su **Annulla** per tornare alla pagina **Proprietà**.

    Nella scheda **Flusso di lavoro** selezionare il flusso di lavoro da utilizzare per elaborare le voci che soddisfano il set di condizioni definite.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]