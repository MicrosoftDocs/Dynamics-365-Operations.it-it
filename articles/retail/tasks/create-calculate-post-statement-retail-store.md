---
title: Creare, calcolare e registrare rendiconti per un punto vendita al dettaglio
description: In questa argomento vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.
author: jashanno
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 693d1821779d5f7af95b900daa3bb7a2c38a6354
ms.sourcegitcommit: cb63259ad8fa5649ff12bc4a7f195bd1e40bd968
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2019
ms.locfileid: "1755525"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="d9227-103">Creare, calcolare e registrare rendiconti per un punto vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d9227-103">Create, calculate, and post statements for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d9227-104">In questa argomento vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d9227-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="d9227-105">Sono disponibili altri processi batch che è possibile configurare per le stesse attività.</span><span class="sxs-lookup"><span data-stu-id="d9227-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="d9227-106">I passaggi per la configurazione e l'esecuzione dei processi batch sono presenti in altri argomenti.</span><span class="sxs-lookup"><span data-stu-id="d9227-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="d9227-107">Per completare questa procedura, è necessario disporre delle transazioni che sono state completate nel POS e sottoposte al pull in Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d9227-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="d9227-108">Questa registrazione utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="d9227-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="d9227-109">Selezionare **Dati finanziari punto vendita al dettaglio** da home page.</span><span class="sxs-lookup"><span data-stu-id="d9227-109">Select **Retail store financials** from the home page.</span></span>
2. <span data-ttu-id="d9227-110">Selezionare **Nuovo rendiconto**.</span><span class="sxs-lookup"><span data-stu-id="d9227-110">Select **New statement**.</span></span>
3. <span data-ttu-id="d9227-111">Nel campo **Numero punto vendita**, selezionare un'opzione dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d9227-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="d9227-112">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9227-112">Select **OK**.</span></span>
5. <span data-ttu-id="d9227-113">Il gruppo di **impostazione** dispone delle impostazioni che controllano quali transazioni vengono incluse nel rendiconto e come vengono raggruppate nelle righe del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="d9227-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="d9227-114">È possibile aprire il gruppo di **impostazione** e modificare queste impostazioni oppure utilizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="d9227-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="d9227-115">Il campo **Metodo rendiconto** determina come le righe del rendiconto vengono raggruppate.</span><span class="sxs-lookup"><span data-stu-id="d9227-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="d9227-116">Selezionare un membro del personale o un registratore di cassa nel campo **Personale/registratore di cassa** se si desidera calcolare un rendiconto solo per un registratore o un membro del personale specifico.</span><span class="sxs-lookup"><span data-stu-id="d9227-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="d9227-117">Selezionare un'opzione nel campo **Metodo di chiusura**.</span><span class="sxs-lookup"><span data-stu-id="d9227-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="d9227-118">Selezionare **Calcola rendiconto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d9227-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="d9227-119">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d9227-119">Select **Yes**.</span></span>
    - <span data-ttu-id="d9227-120">Dopo il calcolo del rendiconto, è necessario creare le righe con gli importi totali per ciascun metodo di pagamento e metodo di rendiconto utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d9227-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="d9227-121">Immettere un importo conteggiato in ogni riga se è necessario immetterlo o aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="d9227-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="d9227-122">Il campo conteggiato viene popolato con gli importi dei riepiloghi incassi eseguiti nel POS.</span><span class="sxs-lookup"><span data-stu-id="d9227-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="d9227-123">Selezionare **Registra rendiconto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d9227-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="d9227-124">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="d9227-124">Select **Close**.</span></span>
11. <span data-ttu-id="d9227-125">Chiudere il riquadro.</span><span class="sxs-lookup"><span data-stu-id="d9227-125">Close the pane.</span></span>
12. <span data-ttu-id="d9227-126">Nella home page selezionare **Dati finanziari punto vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="d9227-126">At the home page, select **Retail store financials**.</span></span>
13. <span data-ttu-id="d9227-127">Fare clic sulla scheda **Rendiconti registrati**.</span><span class="sxs-lookup"><span data-stu-id="d9227-127">Select the **Posted statements** tab.</span></span>

