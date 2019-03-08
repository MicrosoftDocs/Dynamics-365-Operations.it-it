---
title: " Creare, calcolare e registrare un rendiconto per un punto vendita al dettaglio"
description: In questa procedura vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.
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
ms.openlocfilehash: 9ea30e7e008bfcce77a7ee2f4d7d01a6cf1ababc
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "354393"
---
# <a name="create-calculate-and-post-a-statement-for-a-retail-store"></a><span data-ttu-id="90e77-103"> Creare, calcolare e registrare un rendiconto per un punto vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="90e77-103">Create, calculate, and post a statement for a retail store</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="90e77-104">In questa procedura vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="90e77-104">This procedure walks through the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="90e77-105">Sono disponibili altri processi batch che è possibile configurare per le stesse attività.</span><span class="sxs-lookup"><span data-stu-id="90e77-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="90e77-106">I passaggi per la configurazione e l'esecuzione dei processi batch sono presenti in altri argomenti.</span><span class="sxs-lookup"><span data-stu-id="90e77-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="90e77-107">Per completare questa procedura, è necessario disporre delle transazioni che sono state completate nel POS e sottoposte al pull in Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="90e77-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics AX.</span></span> <span data-ttu-id="90e77-108">Questa registrazione utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="90e77-108">This recording uses the USRT company in demo data.</span></span> <span data-ttu-id="90e77-109">Questa procedura può fare riferimento a Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="90e77-109">This procedure may refer to Microsoft Dynamics AX.</span></span> <span data-ttu-id="90e77-110">Notare che Dynamics AX è ora denominato Microsoft Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="90e77-110">Please note that Dynamics AX is now called Microsoft Dynamics 365 for Operations.</span></span>

1. <span data-ttu-id="90e77-111">Passare a Tutte le aree di lavoro </span><span class="sxs-lookup"><span data-stu-id="90e77-111">Go to All workspaces > ..</span></span> <span data-ttu-id="90e77-112">> Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="90e77-112">> Retail store financials.</span></span>
2. <span data-ttu-id="90e77-113">Fare clic su Nuovo rendiconto.</span><span class="sxs-lookup"><span data-stu-id="90e77-113">Click New statement.</span></span>
3. <span data-ttu-id="90e77-114">Nel campo Numero punto vendita fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="90e77-114">In the Store number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="90e77-115">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="90e77-115">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="90e77-116">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="90e77-116">Click OK.</span></span>
    * <span data-ttu-id="90e77-117">Il gruppo di impostazione dispone delle impostazioni che controllano quali transazioni vengono incluse nel rendiconto e come vengono raggruppate le linee del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="90e77-117">The Setup group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="90e77-118">È possibile aprire il gruppo di impostazione e modificare queste impostazioni oppure utilizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="90e77-118">You can open the Setup group and change these settings, or you can use the defaults.</span></span>  
    * <span data-ttu-id="90e77-119">Il campo Metodo rendiconto determina come le linee del rendiconto vengono raggruppate.</span><span class="sxs-lookup"><span data-stu-id="90e77-119">The Statement method field defines how the statement lines will be grouped.</span></span>  
    * <span data-ttu-id="90e77-120">Selezionare i membri del personale o un registratore di cassa se si desidera calcolare un rendiconto solo per un registratore o un membro del personale specifico.</span><span class="sxs-lookup"><span data-stu-id="90e77-120">Select a staff member or a register if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="90e77-121">Selezionare un'opzione nel campo Metodo di chiusura.</span><span class="sxs-lookup"><span data-stu-id="90e77-121">In the Closing method field, select an option.</span></span>
7. <span data-ttu-id="90e77-122">Fare clic su Calcola rendiconto.</span><span class="sxs-lookup"><span data-stu-id="90e77-122">Click Calculate statement.</span></span>
8. <span data-ttu-id="90e77-123">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="90e77-123">Click Yes.</span></span>
    * <span data-ttu-id="90e77-124">Dopo il calcolo del rendiconto, è necessario creare le righe con gli importi totali per ciascun metodo di pagamento e metodo di rendiconto utilizzato.</span><span class="sxs-lookup"><span data-stu-id="90e77-124">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    * <span data-ttu-id="90e77-125">Immettere un importo conteggiato in ogni riga se è necessario immetterlo o aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="90e77-125">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="90e77-126">Il campo conteggiato viene popolato con gli importi dei riepiloghi incassi eseguiti nel POS.</span><span class="sxs-lookup"><span data-stu-id="90e77-126">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="90e77-127">Fare clic su Registra rendiconto.</span><span class="sxs-lookup"><span data-stu-id="90e77-127">Click Post statement.</span></span>
10. <span data-ttu-id="90e77-128">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="90e77-128">Click Close.</span></span>
11. <span data-ttu-id="90e77-129">Andare a Vendita al dettaglio e commercio > Canali > Dati finanziari punto vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="90e77-129">Go to Retail and commerce > Channels > Retail store financials.</span></span>
12. <span data-ttu-id="90e77-130">Fare clic sulla scheda Rendiconti registrati.</span><span class="sxs-lookup"><span data-stu-id="90e77-130">Click the Posted statements tab.</span></span>

