---
title: Abilitare la previsione di cassa (anteprima)
description: Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Finance Insights.
author: ShivamPandey-msft
ms.date: 06/03/2021
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
ms.openlocfilehash: ba8acb2191291e2abed5cabf234c19fe09e6c8ff
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222560"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="c90b7-103">Abilitare la previsione di cassa (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c90b7-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c90b7-104">Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="c90b7-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="c90b7-105">Per utilizzare le previsioni di pagamento nel flusso di cassa, devi configurare la funzionalità Previsioni di pagamento del cliente come descritto in [Abilitare le previsioni di pagamento dei clienti](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="c90b7-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="c90b7-106">Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="c90b7-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="c90b7-107">Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="c90b7-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="c90b7-108">Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].</span><span class="sxs-lookup"><span data-stu-id="c90b7-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="c90b7-109">Ignora questo passaggio se stai usando la versione 10.0.20 o successiva o una distribuzione di Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="c90b7-109">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="c90b7-110">Il team di Finance Insights dovrebbe aver già attivato la versione di anteprima per te.</span><span class="sxs-lookup"><span data-stu-id="c90b7-110">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="c90b7-111">Se non vedi la funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarle, contatta <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="c90b7-111">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="c90b7-112">Apri l'area di lavoro **Gestione funzionalità** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c90b7-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="c90b7-113">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="c90b7-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="c90b7-114">Attiva le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="c90b7-114">Turn on the following features:</span></span>

        - <span data-ttu-id="c90b7-115">Nuovo controllo griglia</span><span class="sxs-lookup"><span data-stu-id="c90b7-115">New grid control</span></span>
        - <span data-ttu-id="c90b7-116">Raggruppamento in griglie (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c90b7-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="c90b7-117">Previsioni di pagamento cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c90b7-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="c90b7-118">Previsioni di cassa (anteprima)</span><span class="sxs-lookup"><span data-stu-id="c90b7-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="c90b7-119">Vai a **Gestione cassa e banche \> Impostazione di previsione di cassa** e aggiungi i conti di liquidità che dovrebbero essere inclusi nelle previsioni.</span><span class="sxs-lookup"><span data-stu-id="c90b7-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c90b7-120">Se i conti di liquidità non sono configurati, il flusso di cassa non può essere generato.</span><span class="sxs-lookup"><span data-stu-id="c90b7-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="c90b7-121">Vai a **Gestione cassa e banche \> Imposta \> Finance Insights (anteprima) \> Previsioni di cassa (anteprima)** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="c90b7-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="c90b7-122">Nella scheda **Previsione di cassa**, seleziona **Abilita funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="c90b7-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="c90b7-123">Seleziona **Crea modello di previsione**.</span><span class="sxs-lookup"><span data-stu-id="c90b7-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="c90b7-124">Per ulteriori informazioni sulla funzionalità di previsione di cassa, vedi [Previsione di cassa](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="c90b7-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
