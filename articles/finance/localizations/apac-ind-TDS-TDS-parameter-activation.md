---
title: Impostare i parametri TDS
description: Questo articolo descrive come impostare i parametri per attivare la funzionalità TDS nelle transazioni specificate. Questo è un passaggio necessario per utilizzare la funzionalità TDS.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3390cad6979858fbff73769d0d25132ba18a2157
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8865615"
---
# <a name="set-the-tds-parameters"></a>Impostare i parametri TDS

[!include [banner](../includes/banner.md)]

Questo articolo descrive come impostare i parametri per attivare la funzionalità TDS nelle transazioni specificate. Questo è un passaggio necessario per utilizzare la funzionalità TDS.

1. Passa a **Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**.
2. Nella scheda **Imposte dirette**, nella sezione **Imposta dedotta all'origine**, imposta l'opzione **TDS attiva** su **Sì** per attivare la funzionalità TDS e le relative pagine e campi.
3. Imposta l'opzione **Fattura** su **Sì** per attivare i campi utilizzati per calcolare e detrarre la TDS a livello di fattura.
4. Imposta l'opzione **Pagamento** su **Sì** per attivare i campi utilizzati per calcolare e detrarre la TDS a livello di pagamento.

    [![Scheda Imposte dirette.](./media/apac-ind-TDS-1.png)](./media/apac-ind-TDS-1.png)

5. Nella scheda **Sequenze numeriche**, trova la riga in cui il campo **Riferimento** è impostato su **Pagamento ritenuta d'acconto**. Nel campo **Codice sequenza numerica** della riga, seleziona il codice di sequenza numerica. Il codice di sequenza numerica è utilizzato per generare i numeri di giustificativo per il processo di liquidazione TDS periodica.

    > [!NOTE]
    > Per eseguire il processo di liquidazione TDS periodico, vai a **Imposta \> Dichiarazioni \> Ritenuta d'acconto \> Pagamento ritenuta d'acconto**.

    [![Scheda Sequenze numeriche.](./media/apac-ind-TDS-2.png)](./media/apac-ind-TDS-2.png)

6. Chiudere la pagina.
