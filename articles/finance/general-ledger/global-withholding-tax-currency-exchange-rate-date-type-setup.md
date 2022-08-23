---
title: Abilitare l'impostazione globale del tipo di data e del tipo di tasso di cambio valutario della ritenuta d'acconto
description: Questo articolo descrive come abilitare l'impostazione globale del tipo di data e del tipo di tasso di cambio valutario della ritenuta d'acconto.
author: kailiang
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 41f12a33651c14439f3a59c5c2f2d34019dada2d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229959"
---
# <a name="enable-the-global-withholding-tax-currency-exchange-rate-type-and-date-type-setup"></a>Abilitare l'impostazione globale del tipo di data e del tipo di tasso di cambio valutario della ritenuta d'acconto

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

Questo articolo descrive come abilitare l'impostazione globale del tipo di data e del tipo di tasso di cambio valutario della ritenuta d'acconto. Ora puoi selezionare un tipo di tasso di cambio dedicato e un tipo di data di calcolo del tasso di cambio per la valuta della ritenuta d'acconto. Queste selezioni determinano il tasso di cambio della valuta estera utilizzato per calcolare l'importo della ritenuta d'acconto, nella valuta della ritenuta d'acconto, nelle transazioni di pagamento.

Questa funzionalità è disponibile in Microsoft Dynamics 365 Finance versione 10.0.29 e successive.

1. Andare a **Imposta** \> **Impostazione** \> **Parametri** \> **Parametri di contabilità generale**.
2. Nella scheda **Ritenuta d'acconto**, imposta l'opzione **Abilita valuta ritenuta d'acconto avanzata** su **Sì**.
3. Nel campo **Tipo di tasso di cambio**, seleziona un tipo di tasso di cambio per la valuta della ritenuta d'acconto.
4. Nel campo **Tipo data di calcolo**, seleziona un tipo di data di calcolo che determina il tasso di cambio valutario della ritenuta d'acconto:

    - **Data di pagamento**: determina il tasso di cambio in base alla data di registrazione del giornale di registrazione pagamenti.
    - **Data fattura**: determina il tasso di cambio in base alla data della fattura del giornale di registrazione fatture. Se la data della fattura del giustificativo è vuota, verrà utilizzata la data di registrazione della fattura. 
    - **Data documento**: determina il tasso di cambio in base alla data del documento del giornale di registrazione pagamenti. Se la data del documento del giustificativo è vuota, verrà utilizzata la data del pagamento.

5. Seleziona **Salva**.

Se la valuta della transazione è diversa dalla valuta della ritenuta d'acconto definita nel codice della ritenuta d'acconto, l'importo nella valuta della ritenuta d'acconto sarà calcolato dalla valuta della transazione in base alle impostazioni precedenti, e sarà registrato nelle transazioni della ritenuta d'acconto registrate.
