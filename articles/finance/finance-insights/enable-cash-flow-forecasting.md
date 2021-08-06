---
title: Abilitare la previsione di cassa (anteprima)
description: Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Finance Insights.
author: ShivamPandey-msft
ms.date: 07/16/2021
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
ms.openlocfilehash: 29118557a1de4d3521f8125395b26471f7f48f3e
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638623"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Abilitare la previsione di cassa (anteprima)

[!include [banner](../includes/banner.md)]

Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Finance Insights.

> [!NOTE]
> Per utilizzare le previsioni di pagamento nel flusso di cassa, devi configurare la funzionalità Previsioni di pagamento del cliente come descritto in [Abilitare le previsioni di pagamento dei clienti](enable-cust-paymnt-prediction.md).

1. Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente. Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox. Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Ignora questo passaggio se stai usando la versione 10.0.20 o successiva o una distribuzione di Service Fabric. Il team di Finance Insights dovrebbe aver già attivato la versione di anteprima per te. Se non vedi la funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarle, contatta <fiap@microsoft.com>.
  
2. Apri l'area di lavoro **Gestione funzionalità** e segui questi passaggi:

    1. Selezionare **Controlla aggiornamenti**.
    2. Attiva le seguenti funzionalità:

        - Nuovo controllo griglia
        - Raggruppamento in griglie (anteprima) 
        - Previsioni di pagamento cliente (anteprima)
        - Previsioni di cassa (anteprima)

3. Vai a **Gestione cassa e banche \> Impostazione di previsione di cassa** e aggiungi i conti di liquidità che dovrebbero essere inclusi nelle previsioni.

    > [!NOTE]
    > Se i conti di liquidità non sono configurati, il flusso di cassa non può essere generato.

4. Vai a **Gestione cassa e banche \> Imposta \> Finance Insights (anteprima) \> Previsioni di cassa (anteprima)** e segui questi passaggi:

    1. Nella scheda **Previsione di cassa**, seleziona **Abilita funzionalità**.
    2. Seleziona **Crea modello di previsione**.

Per ulteriori informazioni sulla funzionalità di previsione di cassa, vedi [Previsione di cassa](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
