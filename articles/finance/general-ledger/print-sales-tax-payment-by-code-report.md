---
title: Stampare il report Pagamento IVA per codice
description: Questo articolo fornisce informazioni sulle impostazioni e le azioni necessarie per stampare il report Pagamento IVA per codice nella valuta contabile o nella valuta del codice IVA.
author: AdamTrukawka
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: atrukawk
ms.search.validFrom: 2020-04-08
ms.dyn365.ops.version: 10.0.11
ms.search.form: ''
ms.openlocfilehash: ea11826d21b66e6283abf24b3f7b0945e6eb9192
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272370"
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
