---
title: Abilitare proposte di budget (anteprima)
description: Questo argomento spiega come attivare la funzionalità Proposta di budget in Informazioni finanziarie dettagliate .
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
ms.openlocfilehash: 3a2060d082ed55e3b6fac506898916942ccc9db7
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208487"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="07bde-103">Abilitare proposte di budget (anteprima)</span><span class="sxs-lookup"><span data-stu-id="07bde-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="07bde-104">Questo argomento spiega come attivare la funzionalità Proposta di budget in Informazioni finanziarie dettagliate .</span><span class="sxs-lookup"><span data-stu-id="07bde-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="07bde-105">Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="07bde-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="07bde-106">Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="07bde-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="07bde-107">Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].</span><span class="sxs-lookup"><span data-stu-id="07bde-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="07bde-108">Se la tua distribuzione di Microsoft Dynamics 365 Finance è una distribuzione di Service Fabric, puoi saltare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="07bde-108">If your deployment of Microsoft Dynamics 365 Finance is a Service Fabric deployment, you can skip this step.</span></span> <span data-ttu-id="07bde-109">Il team di Informazioni finanziarie dettagliate dovrebbe aver già attivato la versione di anteprima per te.</span><span class="sxs-lookup"><span data-stu-id="07bde-109">The Finance Insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="07bde-110">Se non vedi la funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarla, invia un messaggio e-mail al [team dell'anteprima dell'app Informazioni finanziarie dettagliate](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="07bde-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, send email to the [Finance Insights App Preview team](mailto:fiap@microsoft.com).</span></span>

2. <span data-ttu-id="07bde-111">Apri l'area di lavoro **Gestione funzionalità** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="07bde-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="07bde-112">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="07bde-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="07bde-113">Cerca **Proposta di budget** e attiva tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="07bde-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="07bde-114">Vai a **Impostazione budget \> Imposta \> Budget di base \> Proposta di budget (anteprima)** e seleziona **Abilita funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="07bde-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

#### <a name="privacy-notice"></a><span data-ttu-id="07bde-115">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="07bde-115">Privacy notice</span></span>
<span data-ttu-id="07bde-116">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="07bde-116">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]