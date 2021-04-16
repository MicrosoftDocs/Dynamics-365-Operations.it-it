---
title: Creare, calcolare e registrare rendiconti per un punto vendita al dettaglio
description: In questa argomento vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.
author: jashanno
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailStatementTable
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 58900ca4d3f6893689822a8cc5657d8c91772f65
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798539"
---
# <a name="create-calculate-and-post-statements-for-a-retail-store"></a><span data-ttu-id="9df39-103">Creare, calcolare e registrare rendiconti per un punto vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="9df39-103">Create, calculate, and post statements for a retail store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9df39-104">In questa argomento vengono descritti i passaggi manuali per creare, calcolare e registrare il rendiconto di un punto vendita.</span><span class="sxs-lookup"><span data-stu-id="9df39-104">This topic describes the manual steps for creating, calculating, and posting a statement for a store.</span></span> <span data-ttu-id="9df39-105">Sono disponibili altri processi batch che è possibile configurare per le stesse attività.</span><span class="sxs-lookup"><span data-stu-id="9df39-105">There are also batch jobs that can be configured for the same tasks.</span></span> <span data-ttu-id="9df39-106">I passaggi per la configurazione e l'esecuzione dei processi batch sono presenti in altri argomenti.</span><span class="sxs-lookup"><span data-stu-id="9df39-106">The steps for configuring and running the batch jobs can be found in other topics.</span></span> <span data-ttu-id="9df39-107">Per completare questa procedura, è necessario disporre delle transazioni che sono state completate nel POS e sottoposte al pull in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9df39-107">To complete this procedure, you must have transactions that were completed in POS and then pulled into Dynamics 365 Commerce.</span></span> <span data-ttu-id="9df39-108">Questa registrazione utilizza i dati dimostrativi della società USRT.</span><span class="sxs-lookup"><span data-stu-id="9df39-108">This recording uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="9df39-109">Selezionare **Dati finanziari punto vendita** da home page.</span><span class="sxs-lookup"><span data-stu-id="9df39-109">Select **Store financials** from the home page.</span></span>
2. <span data-ttu-id="9df39-110">Selezionare **Nuovo rendiconto**.</span><span class="sxs-lookup"><span data-stu-id="9df39-110">Select **New statement**.</span></span>
3. <span data-ttu-id="9df39-111">Nel campo **Numero punto vendita**, selezionare un'opzione dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="9df39-111">In the **Store number** field, select a option from the drop-down.</span></span>
4. <span data-ttu-id="9df39-112">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9df39-112">Select **OK**.</span></span>
5. <span data-ttu-id="9df39-113">Il gruppo di **impostazione** dispone delle impostazioni che controllano quali transazioni vengono incluse nel rendiconto e come vengono raggruppate nelle righe del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="9df39-113">The **Setup** group has the settings that control what transactions are included in the statement and how they are grouped into statement lines.</span></span> <span data-ttu-id="9df39-114">È possibile aprire il gruppo di **impostazione** e modificare queste impostazioni oppure utilizzare le impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="9df39-114">You can open the **Setup** group and change these settings, or you can use the defaults.</span></span>  
    - <span data-ttu-id="9df39-115">Il campo **Metodo rendiconto** determina come le righe del rendiconto vengono raggruppate.</span><span class="sxs-lookup"><span data-stu-id="9df39-115">The **Statement method** field defines how the statement lines will be grouped.</span></span>  
    - <span data-ttu-id="9df39-116">Selezionare un membro del personale o un registratore di cassa nel campo **Personale/registratore di cassa** se si desidera calcolare un rendiconto solo per un registratore o un membro del personale specifico.</span><span class="sxs-lookup"><span data-stu-id="9df39-116">Select a staff member or a register in the **staff/register** field if you want to calculate a statement only for the specific staff member or register.</span></span>  
6. <span data-ttu-id="9df39-117">Selezionare un'opzione nel campo **Metodo di chiusura**.</span><span class="sxs-lookup"><span data-stu-id="9df39-117">In the **Closing method** field, select an option.</span></span>
7. <span data-ttu-id="9df39-118">Selezionare **Calcola rendiconto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="9df39-118">Select **Calculate statement** from the Action Pane.</span></span>
8. <span data-ttu-id="9df39-119">Selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="9df39-119">Select **Yes**.</span></span>
    - <span data-ttu-id="9df39-120">Dopo il calcolo del rendiconto, è necessario creare le righe con gli importi totali per ciascun metodo di pagamento e metodo di rendiconto utilizzato.</span><span class="sxs-lookup"><span data-stu-id="9df39-120">After calculating the statement, there should be lines created with total amounts for each payment method and statement method that was used.</span></span>  
    - <span data-ttu-id="9df39-121">Immettere un importo conteggiato in ogni riga se è necessario immetterlo o aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="9df39-121">Enter a counted amount in each line if it needs to be entered or updated.</span></span> <span data-ttu-id="9df39-122">Il campo conteggiato viene popolato con gli importi dei riepiloghi incassi eseguiti nel POS.</span><span class="sxs-lookup"><span data-stu-id="9df39-122">The counted field is populated with amounts from tender declarations done in POS.</span></span>  
9. <span data-ttu-id="9df39-123">Selezionare **Registra rendiconto** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="9df39-123">Select **Post statement** from the Action Pane.</span></span>
10. <span data-ttu-id="9df39-124">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="9df39-124">Select **Close**.</span></span>
11. <span data-ttu-id="9df39-125">Chiudere il riquadro.</span><span class="sxs-lookup"><span data-stu-id="9df39-125">Close the pane.</span></span>
12. <span data-ttu-id="9df39-126">Nella home page selezionare **Dati finanziari punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="9df39-126">At the home page, select **Store financials**.</span></span>
13. <span data-ttu-id="9df39-127">Fare clic sulla scheda **Rendiconti registrati**.</span><span class="sxs-lookup"><span data-stu-id="9df39-127">Select the **Posted statements** tab.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]