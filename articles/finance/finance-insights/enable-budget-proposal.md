---
title: Abilitare proposte di budget (anteprima)
description: Questo argomento spiega come attivare la funzionalità Proposta di budget in Finance Insights.
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
ms.openlocfilehash: 948a3e051e5964c5c773cefd90c8587cf833a450
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222536"
---
# <a name="enable-budget-proposals-preview"></a><span data-ttu-id="51d75-103">Abilitare proposte di budget (anteprima)</span><span class="sxs-lookup"><span data-stu-id="51d75-103">Enable budget proposals (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="51d75-104">Questo argomento spiega come attivare la funzionalità Proposta di budget in Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="51d75-104">This topic explains how to turn on the Budget proposal feature in Finance Insights.</span></span>

1. <span data-ttu-id="51d75-105">Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="51d75-105">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="51d75-106">Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="51d75-106">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="51d75-107">Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].</span><span class="sxs-lookup"><span data-stu-id="51d75-107">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('BudgetIntelligentBudgetRegisterProposalFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="51d75-108">Ignora questo passaggio se stai usando la versione 10.0.20 o successiva o una distribuzione di Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="51d75-108">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="51d75-109">Il team di Finance Insights dovrebbe aver già attivato la versione di anteprima per te.</span><span class="sxs-lookup"><span data-stu-id="51d75-109">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="51d75-110">Se non vedi la funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarle, contatta <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="51d75-110">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span>

2. <span data-ttu-id="51d75-111">Apri l'area di lavoro **Gestione funzionalità** e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="51d75-111">Open the **Feature management** workspace, and follow these steps:</span></span>

    1. <span data-ttu-id="51d75-112">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="51d75-112">Select **Check for updates**.</span></span>
    2. <span data-ttu-id="51d75-113">Cerca **Proposta di budget** e attiva tale funzionalità.</span><span class="sxs-lookup"><span data-stu-id="51d75-113">Search for **Budget proposal**, and turn on that feature.</span></span>

3. <span data-ttu-id="51d75-114">Vai a **Impostazione budget \> Imposta \> Budget di base \> Proposta di budget (anteprima)** e seleziona **Abilita funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="51d75-114">Go to **Budgeting \> Setup \> basic Budgeting \> Budget proposal (preview)**, and select **Enable feature**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
