---
title: Abilitare le previsioni di cassa
description: Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 763818f70095964d77ff82cf02178367d05eaf23
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109581"
---
# <a name="enable-cash-flow-forecasting"></a>Abilitare le previsioni di cassa

[!include [banner](../includes/banner.md)]

Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Finance Insights.

> [!NOTE]
> Per utilizzare le previsioni di pagamento nel flusso di cassa, devi configurare la funzionalità Previsioni di pagamento del cliente come descritto in [Abilitare le previsioni di pagamento dei clienti](enable-cust-paymnt-prediction.md).
  
1. Apri l'area di lavoro **Gestione funzionalità** e segui questi passaggi:

    1. Selezionare **Controlla aggiornamenti**.
    2. Nella scheda **Tutto**, cerca **Previsioni di cassa**. Se non trovi tale funzionalità, ceca **Previsioni di cassa (anteprima)**. 
    3. Attiva la funzionalità.

2. Vai a **Gestione cassa e banche \> Impostazione di previsione di cassa** e aggiungi i conti di liquidità che dovrebbero essere inclusi nelle previsioni. Configura anche il conto liquidità per i pagamenti nelle schede **Contabilità clienti** e **Contabilità fornitori**. Assicurati di ricalcolare la previsione del flusso di cassa.

    > [!NOTE]
    > Se i conti di liquidità non sono configurati, il flusso di cassa non può essere generato.
    >
    > Per ulteriori informazioni su come impostare Previsione di cassa, vedere [Previsione di cassa](../cash-bank-management/cash-flow-forecasting.md).

3. Vai a **Gestione cassa e banche \> Imposta \> Finance Insights (anteprima) \> Previsioni di cassa (anteprima)** e segui questi passaggi:

    1. Nella scheda **Previsione di cassa**, seleziona **Abilita funzionalità**.
    2. Seleziona **Crea modello di previsione**.

> [!NOTE]
> Il training del modello **Previsione di cassa** richiede dati che coprono più di un anno e contengono 100 o più transazioni. Consigliamo di avere almeno due anni di dati con più di 1.000 transazioni.

Per ulteriori informazioni sulla funzionalità di previsione di cassa, vedi [Previsione di cassa](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
