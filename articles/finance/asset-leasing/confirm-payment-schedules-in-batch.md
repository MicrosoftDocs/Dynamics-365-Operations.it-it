---
title: Confermare gli scadenzari pagamenti di Leasing cespite in un batch
description: Questo articolo spiega come confermare più scadenziari pagamenti in un batch.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePaymConfirmationDetails
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: bd75e22f6407d6bc25a78c1dfeacf70022238e94
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895053"
---
# <a name="confirm-asset-leasing-payment-schedules-in-a-batch"></a>Confermare gli scadenzari pagamenti di Leasing cespite in un batch

[!include [banner](../includes/banner.md)]

Questo articolo spiega come confermare più scadenziari pagamenti in un batch. Gli scadenziari di pagamento vengono confermati in base al leasing o tramite il processo batch di conferma. Una scrittura contabile può essere registrata solo a fronte di un leasing con uno scadenzario pagamenti confermato. La conferma dello scadenziario di pagamento serve come approvazione finale delle informazioni finanziarie per il leasing. Tutte le modifiche future alle informazioni finanziarie per il leasing, come i pagamenti e il termine del leasing, costituiscono una rettifica del leasing e dovrebbero essere elaborate in questo modo.

Per confermare più scadenziari di pagamento, segui questi passaggi.

1. Vai a **Leasing cespite \> Periodico \> Batch di conferma**.
2. Nella pagina **Batch di conferma**, seleziona **Batch di conferma**.
3. Nella finestra di dialogo che appare, filtra i libri che desideri confermare.

    - Per confermare tutti i libri in uno specifico gruppo di leasing, seleziona il gruppo nel campo **Gruppo leasing**.
    - Per confermare libri specifici, seleziona i libri nel campo **ID libro**.
    - Per confermare tutti i libri, attiva il parametro **Per tutti i libri**.

Le informazioni per i libri appena confermati sono mostrate nella pagina **Libri confermati**. Dopo la conferma degli scadenziari di pagamento, le scritture contabili di riconoscimento iniziale possono essere registrate a fronte dei leasing.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
