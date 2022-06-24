---
title: Stampare il report Pagamento IVA per codice
description: Questo articolo fornisce informazioni sulle impostazioni e le azioni necessarie per stampare il report Pagamento IVA per codice nella valuta contabile o nella valuta del codice IVA.
author: anasyash
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: anasyash
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.openlocfilehash: 9c6b51da41f2aaa3206f8ad97a364a9cd5ca6d49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856656"
---
# <a name="print-the-sales-tax-payment-by-code-report"></a>Stampare il report Pagamento IVA per codice 

[!include [banner](../includes/banner.md)]

Per stampare il report **Pagamento IVA per codice**, andare a **Imposta** \> **Richieste di informazioni e report** \> **Report IVA** \> **Pagamento IVA per codice**. Per impostazione predefinita, gli importi dei report vengono generati nella valuta contabile della persona giuridica per tutti i codici di reporting impostati nella pagina **Codici reporting IVA**.

È inoltre possibile generare questo report in modo che mostri gli importi del pagamento dell'IVA nelle valute dei codici IVA per tutti i codici di reporting assegnati ai codici IVA nella pagina **Codici IVA**.

## <a name="turn-on-the-feature"></a>Attivare la funzionalità

Nell'area di lavoro **Gestione delle funzionalità**, attivare la seguente funzione: **Genera il report Pagamento IVA per codice nella valuta del codice IVA**.

## <a name="run-the-report"></a>Eseguire il report

1. Andare a **Imposta** \> **Richieste di informazioni e report** \> **Report IVA** \> **Pagamento IVA per codice**.
2. Nel campo **Descrizione valuta**, selezionare uno dei seguenti valori:

    - **Valuta di contabilizzazione** - Stampare gli importi del report nella valuta di contabilizzazione.
    - **Valuta del codice IVA** - Stampare gli importi del report nelle valute dei codici IVA.

    ![Finestra di dialogo Pagamento IVA per codice.](media/Sales-tax-payment-by-code.png)

La seguente illustrazione mostra un esempio del report che viene generato. Il report mostra che il codice di segnalazione **101** ha la valuta **Euro** se il campo **Valuta IVA** è impostato su **Euro** per il codice IVA a cui è assegnato il codice di reporting.

![Esempio di report Pagamento IVA per codice.](media/Sales-tax-payment-by-code-2.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]