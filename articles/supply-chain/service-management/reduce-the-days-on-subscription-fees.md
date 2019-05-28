---
title: Ridurre i giorni delle commissioni di sottoscrizione
description: Per ridurre il numero di giorni di commissione di una sottoscrizione presente, è possibile creare una nuova transazione in cui rimuovere il periodo che non deve più far parte dell'intervallo relativo alle commissioni della sottoscrizione.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 04b183d8fc8083c630bcb4e0e69fb755f8a50f95
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569732"
---
# <a name="reduce-the-days-on-subscription-fees"></a>Ridurre i giorni delle commissioni di sottoscrizione 

[!include [banner](../includes/banner.md)]


Per ridurre il numero di giorni di commissione di una sottoscrizione presente, è possibile creare una nuova transazione in cui rimuovere il periodo che non deve più far parte dell'intervallo relativo alle commissioni della sottoscrizione.

## <a name="reduce-the-days-on-a-subscription-fee"></a>Ridurre i giorni di commissione di una sottoscrizione

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Sottoscrizioni assistenza** \> **Tutte le sottoscrizioni assistenza**. Selezionare la sottoscrizione di assistenza e nel riquadro azioni fare clic su **Commissioni sottoscrizione**.

2.  Nel campo **Tipo di sottoscrizione**, selezionare **Giorni riduzione**.

3.  Utilizzare i campi **Dal** e **Al** per definire l'intervallo di date della commissione di sottoscrizione che si desidera rimuovere dal periodo di commissione, quindi scegliere **OK**.

Per visualizzare la transazione creata, nel modulo **Sottoscrizione** fare clic su , quindi su **Transazioni sbilanciate**.

## <a name="example"></a>Esempio

Se il periodo di una transazione di sottoscrizione va dal primo al 31 gennaio e si desidera ridurre il periodo di 10 giorni, creare una nuova transazione in cui il periodo di riduzione corrisponde ai giorni dal primo al 10 gennaio o dal 5 al 15 gennaio oppure un altro periodo di dieci giorni.

Se inoltre la data impostata nel campo **Dal** del periodo di riduzione corrisponde al 21 gennaio (31 meno 10), nel campo **Al** è possibile impostare una qualsiasi data successiva al 31 gennaio. I 10 giorni verranno comunque rimossi dal periodo della transazione di commissione.

## <a name="see-also"></a>Vedere anche

[Esempio di giorni di riduzione](reduction-days-example.md)

  


