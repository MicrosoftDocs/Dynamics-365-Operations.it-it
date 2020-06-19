---
title: Eliminare una stima di progetto
description: Questo argomento fornisce informazioni sull'eliminazione di una stima di progetto dopo che è stata completata.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: eb323bdeb2a4701cdc9383b8da29e05a4cab107c
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410234"
---
# <a name="eliminate-a-project-estimate"></a><span data-ttu-id="06d3e-103">Eliminare una stima di progetto</span><span class="sxs-lookup"><span data-stu-id="06d3e-103">Eliminate a project estimate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="06d3e-104">Le stime di progetto forniscono un quadro finanziario del lavoro stimato e programmato per un progetto.</span><span class="sxs-lookup"><span data-stu-id="06d3e-104">Project estimates provide the financial view for work that is estimated and scheduled for a project.</span></span> <span data-ttu-id="06d3e-105">Per utilizzare le stime in un progetto, è necessario associare il progetto a un progetto stima.</span><span class="sxs-lookup"><span data-stu-id="06d3e-105">To work with estimates for a project, you must attach the project to an estimate project.</span></span> <span data-ttu-id="06d3e-106">Un progetto stima si basa sempre su un progetto esistente, ma più progetti possono fare riferimento a un singolo progetto stima.</span><span class="sxs-lookup"><span data-stu-id="06d3e-106">An estimate project is always based on an existing project, however multiple projects can refer to a single estimate project.</span></span> <span data-ttu-id="06d3e-107">Solo i progetti a prezzo fisso e di investimento possono essere associati a progetti stima e tali progetti devono appartenere allo stesso gruppo di progetti del progetto stima.</span><span class="sxs-lookup"><span data-stu-id="06d3e-107">Only fixed-price and investment projects can be attached to estimate projects, and those projects must belong to the same project group as the estimate project.</span></span>

<span data-ttu-id="06d3e-108">Per eliminare un progetto stima, è necessario che questo sia stato completato.</span><span class="sxs-lookup"><span data-stu-id="06d3e-108">To eliminate an estimate project, it must be complete.</span></span> <span data-ttu-id="06d3e-109">I seguenti passaggi consentono di eliminare una stima.</span><span class="sxs-lookup"><span data-stu-id="06d3e-109">The following steps explain how to eliminate an estimate.</span></span>

1. <span data-ttu-id="06d3e-110">Passare a **Gestione progetti e contabilità** > **Tutti i progetti** e aprire il progetto.</span><span class="sxs-lookup"><span data-stu-id="06d3e-110">Go to **Project management and accounting** > **All Projects** and open the project.</span></span> 
2. <span data-ttu-id="06d3e-111">Nella scheda **Gestisci**, selezionare **Stime** e nella pagina **Stima** selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="06d3e-111">On the **Manage** tab, select **Estimates**, and on the **Estimate** page select **Eliminate**.</span></span>
3. <span data-ttu-id="06d3e-112">Nella pagina **Elimina stima** della scheda **Generale**, imposta le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="06d3e-112">On the **Eliminate estimate** page on the **General** tab, set the following options:</span></span>

   - <span data-ttu-id="06d3e-113">**Codice periodo**: selezionare il codice del periodo per scegliere i progetti stima appropriati.</span><span class="sxs-lookup"><span data-stu-id="06d3e-113">**Period code**: Select the period code to choose the appropriate estimate projects.</span></span> 
   - <span data-ttu-id="06d3e-114">**Data stima**: selezionare la data di stima appropriata per l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="06d3e-114">**Estimate date**: Select the appropriate estimate date for elimination.</span></span>
   - <span data-ttu-id="06d3e-115">**Elimina con avvisi WIP**: abilitare questa opzione per fornire una notifica quando verrà eliminata una stima associata a un work in progress (WIP).</span><span class="sxs-lookup"><span data-stu-id="06d3e-115">**Eliminate with WIP warnings**: Enable this option to provide notification when an estimate that is associated with a work in progress (WIP) will be eliminated.</span></span> <span data-ttu-id="06d3e-116">Se questa opzione è deselezionata, l'eliminazione non viene effettuata se sono presenti transazioni non stimate.</span><span class="sxs-lookup"><span data-stu-id="06d3e-116">When this option is not enabled, elimination can’t continue if any non-estimated transactions exist.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="06d3e-117">Questa opzione è disponibile solo quando l'eliminazione viene applicata a un progetto stima.</span><span class="sxs-lookup"><span data-stu-id="06d3e-117">This option is available only when elimination is applied to an estimate project.</span></span> <span data-ttu-id="06d3e-118">Non è disponibile se si utilizzano registrazioni periodiche.</span><span class="sxs-lookup"><span data-stu-id="06d3e-118">It is not available if you are using periodic postings.</span></span> <span data-ttu-id="06d3e-119">Questa impostazione funziona con le impostazioni della scheda **Stima** della pagina **Parametri progetto** nel gruppo di campi **Consenti eliminazione in presenza di transazioni non stimate**.</span><span class="sxs-lookup"><span data-stu-id="06d3e-119">This setting works with the settings on the **Estimate** tab on the **Project parameters** page, in the **Allow elimination when non-estimated transactions exist** field group.</span></span>
   - <span data-ttu-id="06d3e-120">**Imposta fase su Finito**: abilitare questa opzione per impostare la fase del progetto stima su **Finito** dopo aver eseguito l'eliminazione.</span><span class="sxs-lookup"><span data-stu-id="06d3e-120">**Set stage to Finished**: Enable this option to set the estimate project’s stage to **Finished** after you run the elimination.</span></span>
   - <span data-ttu-id="06d3e-121">**Stampa elenco stime**: selezionare le informazioni da includere nella stampa dell'elenco delle stime.</span><span class="sxs-lookup"><span data-stu-id="06d3e-121">**Print estimate list**: Select the information to be included when the estimate list is printed.</span></span>
   - <span data-ttu-id="06d3e-122">**Mostra Registro informazioni**: abilitare questa opzione per visualizzare il Registro informazioni.</span><span class="sxs-lookup"><span data-stu-id="06d3e-122">**Show Infolog**: Enable this option to display the Infolog.</span></span>
   - <span data-ttu-id="06d3e-123">**Data di registrazione**: scegliere la data di registrazione contabile della stima.</span><span class="sxs-lookup"><span data-stu-id="06d3e-123">**Posting date**: Choose the ledger posting date of the estimate.</span></span>

4.  <span data-ttu-id="06d3e-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="06d3e-124">Select **OK**.</span></span>
5. <span data-ttu-id="06d3e-125">Al termine del processo di eliminazione, il progetto stima eliminato viene visualizzato con un valore negativo.</span><span class="sxs-lookup"><span data-stu-id="06d3e-125">After the elimination process is complete, the eliminated estimate project is displayed with a negative value.</span></span> 

<span data-ttu-id="06d3e-126">Se una stima è stata eliminata per sbaglio, è possibile selezionare quella stima e quindi **Annulla eliminazione**.</span><span class="sxs-lookup"><span data-stu-id="06d3e-126">If you did not intend to eliminate an estimate, you can select the eliminated estimate and select **Reverse elimination**.</span></span>   
