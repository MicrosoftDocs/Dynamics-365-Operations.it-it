---
title: Configurare i parametri che influiscono sui rendiconti della vendita al dettaglio
description: In questo argomento sono illustrate le configurazioni per i parametri di Commerce che interessano la modalità di creazione e registrazione dei rendiconti.
author: josaw1
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7892a216d836ebcc297a5b7eb87bc996dd9b91bf
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140839"
---
# <a name="configure-parameters-that-affect-retail-statements"></a><span data-ttu-id="194b2-103">Configurare i parametri che influiscono sui rendiconti della vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="194b2-103">Configure parameters that affect retail statements</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="194b2-104">In questo argomento sono illustrate le configurazioni per i parametri di Commerce che interessano la modalità di creazione e registrazione dei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="194b2-104">This topic demonstrates configurations for Commerce parameters that affect how statements get created and posted.</span></span> <span data-ttu-id="194b2-105">Questa procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="194b2-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="194b2-106">Nel pannello di navigazione, andare a **Moduli > Retail e Commerce > Impostazione sedi centrali > Parametri > Parametri di commercio**.</span><span class="sxs-lookup"><span data-stu-id="194b2-106">In the navigation pane, go to **Modules > Retail and Commerce > Headquarters setup  > Parameters > Commerce parameters**.</span></span>
2. <span data-ttu-id="194b2-107">Selezionare la scheda **Registrazione**.</span><span class="sxs-lookup"><span data-stu-id="194b2-107">Select the **Posting** tab.</span></span>
    - <span data-ttu-id="194b2-108">Selezionare **Sì** se si desidera registrare gli importi di sconto periodici in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="194b2-108">Select **Yes** if you want to post the periodic discount amounts specifically.</span></span>  
    - <span data-ttu-id="194b2-109">Selezionare **Standard** per utilizzare i conti predefiniti o selezionare **Periodico** per definire il conto da utilizzare per ciascuno sconto periodico.</span><span class="sxs-lookup"><span data-stu-id="194b2-109">Select **Standard** to use default accounts, or select **Periodic** if you want to define which account to use for each periodic discount.</span></span>  
      - <span data-ttu-id="194b2-110">Selezionare **Riepilogo** se le righe di scorte devono essere aggregate ove possibile.</span><span class="sxs-lookup"><span data-stu-id="194b2-110">Select **Summary** if inventory lines should get aggregated whenever possible.</span></span>  
      - <span data-ttu-id="194b2-111">Selezionare **Sì** se le fatture e pagamenti devono essere automaticamente liquidati durante il processo di registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="194b2-111">Select **Yes** if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
      - <span data-ttu-id="194b2-112">Selezionare **Sì** se le transazioni deposito in cassaforte devono essere aggregate.</span><span class="sxs-lookup"><span data-stu-id="194b2-112">Select **Yes** if Safe drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="194b2-113">Selezionare **Sì** se le transazioni deposito bancario devono essere aggregate.</span><span class="sxs-lookup"><span data-stu-id="194b2-113">Select **Yes** if Bank drop transactions should get aggregated.</span></span>  
      - <span data-ttu-id="194b2-114">Selezionare **Sì** per attivare l'aggregazione per la registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="194b2-114">Select **Yes** to turn aggregation on for Statement posting.</span></span>  
      - <span data-ttu-id="194b2-115">Selezionare **Sì** per creare ed elaborare gli ordini in parallelo quando i rendiconti vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="194b2-115">Select **Yes** to create and process orders in parallel when statements are posted.</span></span>  
      - <span data-ttu-id="194b2-116">Immettere il numero massimo di ordini da elaborare in ogni attività di processo batch.</span><span class="sxs-lookup"><span data-stu-id="194b2-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="194b2-117">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="194b2-117">Select **Save**.</span></span>

