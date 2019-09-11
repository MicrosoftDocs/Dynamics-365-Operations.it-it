---
title: Aggiornamento manuale dei contatori di cespiti
description: In questo argomento viene descritto l'aggiornamento manuale dei contatori di cespiti in Gestione cespiti
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1e7c5ec288404c18b00f9dcd0e66f50744d0aa2f
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875737"
---
# <a name="manual-update-of-asset-counters"></a><span data-ttu-id="d8d75-103">Aggiornamento manuale dei contatori di cespiti</span><span class="sxs-lookup"><span data-stu-id="d8d75-103">Manual update of asset counters</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="d8d75-104">I contatori sono utilizzati per creare registrazioni in un cespite in relazione, ad esempio, al numero di ore in esecuzione o al numero di quantità prodotte.</span><span class="sxs-lookup"><span data-stu-id="d8d75-104">Counters are used to create registrations on an asset regarding, for example, number of hours in operation, or the number of quantities produced.</span></span>

<span data-ttu-id="d8d75-105">Se il tipo di contatore selezionato per un contatore è impostato per ereditare valori di contatore (**Gestione cespiti** > **Impostazione** > **Tipi di cespite** > **Contatori** >  Scheda dettaglio **Generale** > interruttore **Eredita valori contatore cespiti** impostato su "Sì"), quando si crea una nuova riga contatore di quel tipo, ogni cespite figlio che utilizza lo stesso tipo di contatore viene aggiornato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d8d75-105">If the counter type selected for a counter is set to inherit counter values (**Asset management** > **Setup** > **Asset types** > **Counters** > **General** FastTab > **Inherit asset counter values** toggle button set to "Yes"), then, when you create a new counter line of that type, every child asset that uses the same counter type is automatically updated.</span></span>

<span data-ttu-id="d8d75-106">In **Tutti i cespiti** si creano registrazioni contatore di ore o quantità di un cespite, in base alle letture nel cespite.</span><span class="sxs-lookup"><span data-stu-id="d8d75-106">In **All assets**, you create hours or quantity counter registrations on an asset, based on your readings on the asset.</span></span>

1. <span data-ttu-id="d8d75-107">Fare clic su **Gestione cespiti** > **Comune** > **Cespiti** > **Tutti i cespiti**.</span><span class="sxs-lookup"><span data-stu-id="d8d75-107">Click **Asset management** > **Common** > **Assets** > **All assets**.</span></span>

2. <span data-ttu-id="d8d75-108">Selezionare il cespite nell'elenco e fare clic su **Contatori**.</span><span class="sxs-lookup"><span data-stu-id="d8d75-108">Select the asset in the list, and click **Counters**.</span></span> <span data-ttu-id="d8d75-109">Nel modulo **Contatori cespiti**, viene visualizzato un elenco di tutte le registrazioni contatore precedenti del cespite selezionato.</span><span class="sxs-lookup"><span data-stu-id="d8d75-109">In the **Asset counters** form, you see a list of all previous counter registrations on the selected asset.</span></span>

3. <span data-ttu-id="d8d75-110">Fare clic su **Nuovo** per creare una nuova registrazione.</span><span class="sxs-lookup"><span data-stu-id="d8d75-110">Click **New** to create a new registration.</span></span> <span data-ttu-id="d8d75-111">L'ID cespite viene immesso automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d8d75-111">The asset ID is automatically inserted.</span></span>

4. <span data-ttu-id="d8d75-112">Nel campo **Contatore** selezionare il contatore pertinente.</span><span class="sxs-lookup"><span data-stu-id="d8d75-112">In the **Counter** field, select the relevant counter.</span></span> <span data-ttu-id="d8d75-113">Solo i contatori relativi al tipo di cespite selezionato nel cespite sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="d8d75-113">Only counters related to the asset type selected on the asset are available.</span></span> <span data-ttu-id="d8d75-114">L'unità correlata viene immessa automaticamente nel campo **Unità**.</span><span class="sxs-lookup"><span data-stu-id="d8d75-114">The related unit is automatically inserted in the **Unit** field.</span></span>

5. <span data-ttu-id="d8d75-115">Selezionare la data e l'ora per la registrazione contatore.</span><span class="sxs-lookup"><span data-stu-id="d8d75-115">Select date and time for the counter registration.</span></span>

6. <span data-ttu-id="d8d75-116">Nel campo **Valore**, immettere il numero dall'ultima registrazione contatore o, nel campo **Valore aggregato**, immettere il conteggio totale.</span><span class="sxs-lookup"><span data-stu-id="d8d75-116">In the **Value** field, insert the number since the last counter registration, or, in the **Aggregated value** field, insert the total count number.</span></span>

- <span data-ttu-id="d8d75-117">Se si installa fisicamente un nuovo contatore in un cespite, è necessario registrare la modifica nel cespite in **Contatori cespiti**.</span><span class="sxs-lookup"><span data-stu-id="d8d75-117">If you physically install a new counter on an asset, you need to register the change on the asset in **Asset counters**.</span></span> <span data-ttu-id="d8d75-118">Successivamente, è necessario creare due righe di registrazione con timbri data/ora identici e nella riga relativa al nuovo contatore, selezionare la casella di controllo **Reimposta contatore**.</span><span class="sxs-lookup"><span data-stu-id="d8d75-118">Next, you must create two registration lines with identical timestamps, and on the line regarding the new counter, you select the **Counter reset** check box.</span></span> <span data-ttu-id="d8d75-119">Quando si creano due righe di registrazione, la prima deve essere per il contatore che si sostituisce.</span><span class="sxs-lookup"><span data-stu-id="d8d75-119">When you create the two registration lines, the first line must be for the counter that you are replacing.</span></span> <span data-ttu-id="d8d75-120">Nel campo **Totali**, il conteggio totale è la somma di tutti i valori registrati del contatore in base a quel tipo di contatore.</span><span class="sxs-lookup"><span data-stu-id="d8d75-120">In the **Totals** field, the total count number is the sum of the counter total of all registered values on that counter type.</span></span>  
- <span data-ttu-id="d8d75-121">Se la casella di controllo **Reimposta contatore** è selezionata in un cespite che utilizza un piano di manutenzione con un tipo di intervallo "Una volta da..." o "Quando...", il contatore è ancora attivo nella riga del nuovo contatore poiché si è creata un riga contatore distinta e si è iniziato con un nuovo contatore.</span><span class="sxs-lookup"><span data-stu-id="d8d75-121">If the **Counter reset** check box is selected on an asset using a maintenance plan with a "Once from..." or "Once reached..." interval type, the counter is still active on the new counter line because you create a separate counter line and start over with a new counter.</span></span>

![Figura 1](media/11-work-orders.png)


<span data-ttu-id="d8d75-123">Se è necessario eseguire registrazioni contatore in più cespiti, è possibile farlo in **Gestione cespiti** > **Richieste di informazioni** > **Cespiti** > **Contatori cespiti**.</span><span class="sxs-lookup"><span data-stu-id="d8d75-123">If you need to make counter registrations on several assets, that can be done in **Asset management** > **Inquiries** > **Assets** > **Asset counters**.</span></span>

>[!NOTE]
><span data-ttu-id="d8d75-124">È possibile impostare un intervallo per definire gli scostamenti nelle registrazioni contatore manuali e il tipo di messaggio da visualizzare se le registrazioni non rientrano nell'intervallo definito.</span><span class="sxs-lookup"><span data-stu-id="d8d75-124">You can set up a range to define deviations in manual counter registrations, and the type of message that should be displayed if registrations are outside the defined range.</span></span> <span data-ttu-id="d8d75-125">Leggere l'argomento [Contatori](../setup-for-objects/counters.md) relativo all'impostazione di contatori.</span><span class="sxs-lookup"><span data-stu-id="d8d75-125">Refer to the [Counters](../setup-for-objects/counters.md) topic regarding setup of counters.</span></span>
