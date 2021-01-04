---
title: Aggiornamento manuale dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento manuale dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 23a94415a662059ddbd41cc6a0ba9dab24aae44e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4430966"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="460cb-103">Aggiornamento manuale dei contatori di cespiti</span><span class="sxs-lookup"><span data-stu-id="460cb-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="460cb-104">I contatori vengono utilizzati per creare registrazioni su un cespite, ad esempio registrazioni sul numero di ore in cui il cespite è stato in funzione o sulla quantità che è stata prodotta.</span><span class="sxs-lookup"><span data-stu-id="460cb-104">Counters are used to create registrations on an asset, such as registrations about the number of hours that the asset has been in operation or the quantity that has been produced.</span></span>

<span data-ttu-id="460cb-105">Il tipo selezionato per un contatore può essere impostato per ereditare i valori del contatore.</span><span class="sxs-lookup"><span data-stu-id="460cb-105">The counter type that is selected for a counter might be set to inherit counter values.</span></span> <span data-ttu-id="460cb-106">In altre parole, l'opzione **Eredita valori contatore cespiti** è impostata su **Sì** nella scheda dettaglio **Generale** della pagina **Contatori** (**Gestione cespiti** > **Impostazioni** > **Tipi del cespite** > **Contatori**).</span><span class="sxs-lookup"><span data-stu-id="460cb-106">In other words, the **Inherit asset counter values** option is set to **Yes** on the **General** FastTab of the **Counters** page (**Asset management** > **Setup** > **Asset types** > **Counters**).</span></span> <span data-ttu-id="460cb-107">In questo caso, quando si crea una nuova riga per un contatore di quel tipo, ogni cespite figlio che utilizza lo stesso tipo di contatore viene automaticamente aggiornato.</span><span class="sxs-lookup"><span data-stu-id="460cb-107">In this case, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="460cb-108">Nella pagina **Tutti i cespiti** si creano le registrazioni contatore di ore o quantità di un cespite, in base alle letture nel cespite.</span><span class="sxs-lookup"><span data-stu-id="460cb-108">On the **All assets** page, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="460cb-109">Selezionare **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="460cb-109">Select **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="460cb-110">Selezione il cespite e nel riquadro azioni, nella scheda **Cespite**, nel gruppo **Preventivo**, selezionare **Contatori**.</span><span class="sxs-lookup"><span data-stu-id="460cb-110">Select the asset, and then, on the Action Pane, on the **Asset** tab, in the **Preventive** group, select **Counters**.</span></span> <span data-ttu-id="460cb-111">Nella pagina **Contatori cespiti** viene visualizzato un elenco di tutte le registrazioni contatore precedenti effettuate per il cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="460cb-111">The **Asset counters** page shows a list of all previous counter registrations that have been made on the selected asset.</span></span>

3. <span data-ttu-id="460cb-112">Selezionare **Nuovo** per creare una registrazione.</span><span class="sxs-lookup"><span data-stu-id="460cb-112">Select **New** to create a registration.</span></span> <span data-ttu-id="460cb-113">L'ID cespite verrà immesso automaticamente nel campo **Cespite**.</span><span class="sxs-lookup"><span data-stu-id="460cb-113">The asset ID is automatically entered in the **Asset** field.</span></span>

4. <span data-ttu-id="460cb-114">Nel campo **Contatore** selezionare il contatore pertinente.</span><span class="sxs-lookup"><span data-stu-id="460cb-114">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="460cb-115">Solo i contatori relativi al tipo di cespite selezionato nel cespite sono disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="460cb-115">Only counters that are related to the asset type selected on the asset are available for selection.</span></span> <span data-ttu-id="460cb-116">L'unità correlata viene immessa automaticamente nel campo **Unità**.</span><span class="sxs-lookup"><span data-stu-id="460cb-116">The related unit is automatically entered in the **Unit** field.</span></span>

5. <span data-ttu-id="460cb-117">Nel campo **Registrato**, selezionare la data e l'ora della registrazione del contatore.</span><span class="sxs-lookup"><span data-stu-id="460cb-117">In the **Registered** field, select the date and time for the counter registration.</span></span>

6. <span data-ttu-id="460cb-118">Nel campo **Valore**, immettere il numero dell'ultima di registrazione.</span><span class="sxs-lookup"><span data-stu-id="460cb-118">In the **Value** field, enter the number since the last counter registration.</span></span> <span data-ttu-id="460cb-119">In alternativa, nel campo **Valore aggregato**, immettere il numero del conteggio totale.</span><span class="sxs-lookup"><span data-stu-id="460cb-119">Alternatively, in the **Aggregated value** field, enter the total count number.</span></span>

<span data-ttu-id="460cb-120">Notare i punti seguenti:</span><span class="sxs-lookup"><span data-stu-id="460cb-120">Note the following points:</span></span>

- <span data-ttu-id="460cb-121">Se si installa fisicamente un nuovo contatore in un cespite, è necessario registrare la modifica nel cespite nella pagina **Contatori cespiti**.</span><span class="sxs-lookup"><span data-stu-id="460cb-121">If you physically install a new counter on an asset, you must register the change on the asset on the **Asset counters** page.</span></span> <span data-ttu-id="460cb-122">A questo punto, è necessario creare due righe di registrazione con timbro data/ora identico.</span><span class="sxs-lookup"><span data-stu-id="460cb-122">Next, you must create two registration lines that have identical timestamps.</span></span> <span data-ttu-id="460cb-123">La prima riga deve essere per il contatore che si sostituisce.</span><span class="sxs-lookup"><span data-stu-id="460cb-123">The first line must be for the counter that you're replacing.</span></span> <span data-ttu-id="460cb-124">Nella riga relativa al nuovo contatore, selezionare la casella di controllo **Reimposta contatore**.</span><span class="sxs-lookup"><span data-stu-id="460cb-124">On the line that is related to the new counter, select the **Counter reset** check box.</span></span> <span data-ttu-id="460cb-125">Nel campo **Totali**, il conteggio totale è la somma di tutti i valori registrati del contatore in base a quel tipo di contatore.</span><span class="sxs-lookup"><span data-stu-id="460cb-125">In the **Totals** field, the total count number is the sum of the counter totals of all registered values on that counter type.</span></span>

- <span data-ttu-id="460cb-126">Se la casella di controllo **Reimposta contatore** è selezionata in un cespite che utilizza un piano di manutenzione con un tipo di intervallo "Una volta da..." o "Quando...", il contatore è ancora attivo nella riga del nuovo contatore poiché si è creata un riga contatore distinta e si è iniziato con un nuovo contatore.</span><span class="sxs-lookup"><span data-stu-id="460cb-126">If the **Counter reset** check box is selected on an asset using a maintenance plan that has a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line, because you create a separate counter line and start over with a new counter.</span></span>

<span data-ttu-id="460cb-127">Nella figura seguente è illustrato un esempio della pagina **Contatori cespiti**.</span><span class="sxs-lookup"><span data-stu-id="460cb-127">The illustration below shows an example of the **Asset counters** page.</span></span>

![Figura 1](media/11-work-orders.png)

<span data-ttu-id="460cb-129">Nella pagina **Contatori cespiti** (**Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Contatori cespiti**), è possibile eseguire le registrazioni in più cespiti contemporaneamente, secondo le necessità.</span><span class="sxs-lookup"><span data-stu-id="460cb-129">On the **Asset counters** page (**Asset management** > **Inquiries** > **Assets** > **Asset counters**), you can make counter registrations on several assets at the same time, as you require.</span></span>

>[!NOTE]
><span data-ttu-id="460cb-130">È possibile impostare un intervallo per definire gli scostamenti rispetto alle registrazioni manuali.</span><span class="sxs-lookup"><span data-stu-id="460cb-130">You can set up a range to define deviations in manual counter registrations.</span></span> <span data-ttu-id="460cb-131">È inoltre possibile specificare il tipo di messaggio che verrà visualizzato se le registrazioni non rientrano nell'intervallo definito.</span><span class="sxs-lookup"><span data-stu-id="460cb-131">You can also specify the type of message that is shown if registrations are outside the defined range.</span></span> <span data-ttu-id="460cb-132">Per ulteriori informazioni su come impostare i contatori, vedere [Contatori](../setup-for-objects/counters.md).</span><span class="sxs-lookup"><span data-stu-id="460cb-132">For more information about how to set up counters, see [Counters](../setup-for-objects/counters.md).</span></span>

