---
title: Gestire il congedo dei dipendenti
description: Gestire il congedo dei dipendenti in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ef671ee42848d079cf1ff9bc2328216df4e9e20
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8888790"
---
# <a name="manage-employee-leave"></a>Gestire il congedo dei dipendenti

>[!Important]
>La funzionalità indicata in questo articolo è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile gestire il congedo di un dipendente per tipo di congedo. Ciò include la scadenza delle iscrizioni congedo e la rettifica dei saldi del tipo di congedo. 

## <a name="adjust-leave-balances"></a>Rettificare i saldi dei congedi

1. Nel record del dipendente, selezionare **Congedo**.

2. Selezionare **Impostazione congedo e assenza**.

3. Selezionare **Rettifica saldo**.

4. Selezionare un valore in **Tipo di congedo**.

5. Inserire un valore in **Importo di rettifica**. 

6. Facoltativamente, è possibile selezionare un valore in **Data**. 

È possibile includere un codice motivo e un commento quando si rettifica il saldo di congedo di un dipendente. 

Ora, quando passi con il mouse su qualsiasi saldo di congedo, vengono mostrate le seguenti informazioni:

- **Disponibile** - Il valore **Totale di quest'anno** meno il valore **Richiesti quest'anno**.
- **Totale di quest'anno** - Tutti gli accantonamenti, le rettifiche e i riporti in avanti dell'anno.
- **Presi quest'anno** - Tutti i congedi approvati.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Gestire le richieste di congedo e assenza](hr-employee-self-service-manage-requests.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
