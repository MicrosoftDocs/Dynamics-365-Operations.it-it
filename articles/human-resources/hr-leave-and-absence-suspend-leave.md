---
title: Sospendi congedo
description: È possibile sospendere un congedo per un dipendente in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c8262fb34175f6f9326d6be82c922b2170fc5a7
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805262"
---
# <a name="suspend-leave"></a>Congedo sospeso

>[!Important]
>La funzionalità indicata in questo articolo è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile sospendere un congedo per un dipendente per interrompere l'elaborazione degli accumuli delle ferie per i tipi di congedo selezionati.

## <a name="suspend-leave-and-absence-for-an-employee"></a>Sospendere congedi e assenze per un dipendente

1. Nel record del dipendente, selezionare **Congedo**.

2. Selezionare **Sospendi congedo**.

3. Selezionare **Nuovo**.

4. Nella finestra di dialogo **Sospendi accumuli di congedi**, selezionare **Tipo di congedo** con la **Data d'inizio** e la **Data di fine** della sospensione.

5. Facoltativamente, è possibile aggiungere un **Commento** per la sospensione. 

Se gli accumuli vengono elaborati mentre il congedo del dipendente è sospeso, non verranno effettuati accumuli per i tipi di congedo sospesi.

> [!NOTE]
> Le richieste di congedo sospendono le richieste di permesso, ma le richieste di permesso non sospendono le richieste di congedo.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Configurare i tipi di congedo e assenza](hr-leave-and-absence-types.md)
- [Accumulare piani di congedo e assenza](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
