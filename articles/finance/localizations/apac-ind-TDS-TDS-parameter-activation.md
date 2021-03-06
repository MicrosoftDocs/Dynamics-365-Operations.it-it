---
title: Impostare i parametri TDS
description: Questo argomento descrive come impostare i parametri per attivare la funzionalità TDS nelle transazioni specificate. Questo è un passaggio necessario per utilizzare la funzionalità TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: dda276b7d634317aae26728f7d9f51af9ccfb896
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023356"
---
# <a name="set-the-tds-parameters"></a>Impostare i parametri TDS

[!include [banner](../includes/banner.md)]

Questo argomento descrive come impostare i parametri per attivare la funzionalità TDS nelle transazioni specificate. Questo è un passaggio necessario per utilizzare la funzionalità TDS.

1. Passa a **Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**.
2. Nella scheda **Imposte dirette**, nella sezione **Imposta dedotta all'origine**, imposta l'opzione **TDS attiva** su **Sì** per attivare la funzionalità TDS e le relative pagine e campi.
3. Imposta l'opzione **Fattura** su **Sì** per attivare i campi utilizzati per calcolare e detrarre la TDS a livello di fattura.
4. Imposta l'opzione **Pagamento** su **Sì** per attivare i campi utilizzati per calcolare e detrarre la TDS a livello di pagamento.

    [![Scheda Imposte dirette](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. Nella scheda **Sequenze numeriche**, trova la riga in cui il campo **Riferimento** è impostato su **Pagamento ritenuta d'acconto**. Nel campo **Codice sequenza numerica** della riga, seleziona il codice di sequenza numerica. Il codice di sequenza numerica è utilizzato per generare i numeri di giustificativo per il processo di liquidazione TDS periodica.

    > [!NOTE]
    > Per eseguire il processo di liquidazione TDS periodico, vai a **Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Pagamento ritenuta d'acconto**.

    [![Scheda Sequenze numeriche](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Chiudi la pagina.
