---
title: Abilitare la previsione di cassa (anteprima)
description: Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Informazioni finanziarie dettagliate .
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 2de75962f5b8a71c8f7138289078b5c669ae1daa
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250580"
---
# <a name="enable-cash-flow-forecasting-preview"></a><span data-ttu-id="4937c-103">Abilitare la previsione di cassa (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4937c-103">Enable cash flow forecasting (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="4937c-104">Questo argomento spiega come attivare la funzionalità Previsioni di cassa in Informazioni finanziarie dettagliate .</span><span class="sxs-lookup"><span data-stu-id="4937c-104">This topic explains how to turn on the Cash flow forecasts feature in Finance Insights.</span></span>

> [!NOTE]
> <span data-ttu-id="4937c-105">Per utilizzare le previsioni di pagamento nel flusso di cassa, devi configurare la funzionalità Previsioni di pagamento del cliente come descritto in [Abilitare le previsioni di pagamento dei clienti](enable-cust-paymnt-prediction.md).</span><span class="sxs-lookup"><span data-stu-id="4937c-105">To use payment predictions in the cash flow, you must set up the Customer payment predictions feature as described in [Enable customer payment predictions](enable-cust-paymnt-prediction.md).</span></span>

1. <span data-ttu-id="4937c-106">Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="4937c-106">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="4937c-107">Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="4937c-107">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="4937c-108">Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].</span><span class="sxs-lookup"><span data-stu-id="4937c-108">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="4937c-109">Se la tua distribuzione di Microsoft Dynamics 365 Finance è una distribuzione di Service Fabric, puoi saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="4937c-109">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="4937c-110">Il team di Informazioni finanziarie dettagliate dovrebbe aver già attivato la versione di anteprima per te.</span><span class="sxs-lookup"><span data-stu-id="4937c-110">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="4937c-111">Se non vedi le funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarle, contatta  <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="4937c-111">If you don't see the features in the **Feature management** workspace, or if experience issues when you try to turn them on, contact <fiap@microsoft.com>.</span></span>
  
2. <span data-ttu-id="4937c-112">Apri l'area di lavoro **Gestione funzionalità** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="4937c-112">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="4937c-113">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="4937c-113">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="4937c-114">Attiva le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="4937c-114">Turn on the following features:</span></span>

        - <span data-ttu-id="4937c-115">Nuovo controllo griglia</span><span class="sxs-lookup"><span data-stu-id="4937c-115">New grid control</span></span>
        - <span data-ttu-id="4937c-116">Raggruppamento in griglie (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4937c-116">Grouping in grids (preview)</span></span> 
        - <span data-ttu-id="4937c-117">Previsioni di pagamento cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4937c-117">Customer payment predictions (preview)</span></span>
        - <span data-ttu-id="4937c-118">Previsioni di cassa (anteprima)</span><span class="sxs-lookup"><span data-stu-id="4937c-118">Cash flow forecasts (preview)</span></span>

3. <span data-ttu-id="4937c-119">Vai a **Gestione cassa e banche \> Impostazione di previsione di cassa** e aggiungi i conti di liquidità che dovrebbero essere inclusi nelle previsioni.</span><span class="sxs-lookup"><span data-stu-id="4937c-119">Go to **Cash and bank management \> Cash flow forecast setup**, and add the liquidity accounts that should be included in the forecasts.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4937c-120">Se i conti di liquidità non sono configurati, il flusso di cassa non può essere generato.</span><span class="sxs-lookup"><span data-stu-id="4937c-120">If liquidity accounts aren't set up, the cash flow can't be generated.</span></span>

4. <span data-ttu-id="4937c-121">Vai a **Gestione cassa e banche \> Imposta \> Informazioni finanziarie dettagliate (anteprima) \> Previsioni di cassa (anteprima)** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="4937c-121">Go to **Cash and bank management \> Setup \> Finance Insights (preview) \> Cash flow forecasts (preview)**, and follow these steps:</span></span>

    1. <span data-ttu-id="4937c-122">Nella scheda **Previsione di cassa**, seleziona **Abilita funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="4937c-122">On the **Cash flow forecast** tab, select **Enable feature**.</span></span>
    2. <span data-ttu-id="4937c-123">Seleziona **Crea modello di previsione**.</span><span class="sxs-lookup"><span data-stu-id="4937c-123">Select **Create prediction model**.</span></span>

<span data-ttu-id="4937c-124">Per ulteriori informazioni sulla funzionalità di previsione di cassa, vedi [Previsione di cassa](cash-flow-forecast-intro.md).</span><span class="sxs-lookup"><span data-stu-id="4937c-124">For more information about the cash flow forecasting capability, see [Cash flow forecasting](cash-flow-forecast-intro.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="4937c-125">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="4937c-125">Privacy notice</span></span>

<span data-ttu-id="4937c-126">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="4937c-126">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]