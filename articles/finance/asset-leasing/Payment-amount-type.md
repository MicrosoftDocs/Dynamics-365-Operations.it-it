---
title: Aggiungere i tipi di importo di pagamento
description: Nell'articolo viene descritto come configurare i tipi di importo di pagamento in Leasing cespite.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRevaluation
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 03fc903e6cfe78ef2fed7e3a0744a8f809f6892d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891611"
---
# <a name="add-payment-amount-types"></a>Aggiungere i tipi di importo di pagamento

[!include [banner](../includes/banner.md)]

Nell'articolo viene illustrato come configurare i tipi di importo di pagamento in Leasing cespite. In questo modo è possibile dettagliare l'importo del canone di leasing invece di aggiungere l'importo forfettario nelle righe scadenzario pagamenti.

Per aggiungere i tipi di importo di pagamento effettua le operazioni indicate di seguito.

1. Vai a **Leasing cespiti \> Imposta \> Tipi di importo pagamento**.
2. Selezionare **Nuovo**.
3. Immetti il nuovo tipo di pagamento e una descrizione.

> [!NOTE]
> Per la rivalutazione dell'indice IFRS 16, è necessario creare un tipo di importo di pagamento e contrassegnarlo come **Utilizzato per rivalutazione indice IRFS 16**. Questo tipo di importo di pagamento verrà utilizzato quando il processo di rivalutazione dell'indice viene eseguito rispetto al libro IFRS 16 e prenderà in considerazione le modifiche che si sono verificate a causa del processo di rivalutazione dell'indice.
>
> Quando l'opzione **Suddivisione pagamento** nel leasing è impostata su **sì**, se viene eseguita la rivalutazione dell'indice per l'IFRS 16, ma non esiste un tipo di pagamento per l'IFRS 16, il processo non verrà completato.

È possibile contrassegnare un solo record come **Utilizzato per rivalutazione indice IFRS 16**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
