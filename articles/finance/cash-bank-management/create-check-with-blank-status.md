---
title: Creazione di assegni con stato In bianco
description: In questo argomento viene illustrato come creare assegni in bianco per un conto bancario nella pagina Assegni.
author: abruer
manager: AnnBe
ms.date: 10/26/2017
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 21941
ms.assetid: d7e22bd8-fd0d-47e1-843f-45ab0193ff8d
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2019-09-17
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 47d54524f87cf718b9b41462b5133df267d5dd9e
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570289"
---
# <a name="create-checks-that-have-blank-status"></a><span data-ttu-id="69f56-103">Creazione di assegni con stato In bianco</span><span class="sxs-lookup"><span data-stu-id="69f56-103">Create checks that have Blank status</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="69f56-104">In questo argomento viene illustrato come creare assegni in bianco.</span><span class="sxs-lookup"><span data-stu-id="69f56-104">This topic explains how to create blank checks.</span></span> <span data-ttu-id="69f56-105">Ad esempio, è possibile creare un assegno in bianco per registrare un assegno danneggiato che non può essere utilizzato per il pagamento.</span><span class="sxs-lookup"><span data-stu-id="69f56-105">For example, you might create a blank check to record a check that has been damaged and can't be used for payment.</span></span>

<span data-ttu-id="69f56-106">Nella pagina **Assegni**, eseguire le attività di manutenzione per gli assegni.</span><span class="sxs-lookup"><span data-stu-id="69f56-106">On the **Checks** page, you perform maintenance tasks for checks.</span></span> <span data-ttu-id="69f56-107">Ad esempio, è possibile creare nuovi numeri di assegno ed eliminare gli assegni.</span><span class="sxs-lookup"><span data-stu-id="69f56-107">For example, you can create new check numbers and delete checks.</span></span> <span data-ttu-id="69f56-108">È inoltre possibile creare assegni con stato **In bianco**.</span><span class="sxs-lookup"><span data-stu-id="69f56-108">You can also create checks that have a status of **Blank**.</span></span> <span data-ttu-id="69f56-109">Dopo aver creato gli assegni in bianco, non è possibile eliminarli o riutilizzarli nel sistema.</span><span class="sxs-lookup"><span data-stu-id="69f56-109">After blank checks are created, they can't be deleted or reused in the system.</span></span>

> [!NOTE]
> <span data-ttu-id="69f56-110">Questa funzionalità è disponibile nella pagina **Assegni** solo se viene attivata la funzionalità **Creare assegni in bianco nella pagina Assegni** nella pagina **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="69f56-110">This feature is available on the **Checks** page only if you turn on the **Create checks with a blank status on the Checks page** feature on the **Feature management** page.</span></span> <span data-ttu-id="69f56-111">Se la funzionalità non viene attivata, gli assegni con stato **In bianco** possono essere creati solo dalla finestra di dialogo **Pagamento con assegno** durante il processo di generazione del pagamento in Contabilità fornitori.</span><span class="sxs-lookup"><span data-stu-id="69f56-111">If the feature isn't turned on, checks that have **Blank** status can be created only from the **Payment by check** dialog box during the payment generation process in Accounts payable.</span></span>

<span data-ttu-id="69f56-112">Per aprire la pagina **Assegni**, passare a **Gestione cassa e banche \> Conti bancari \> Conti bancari**, quindi nel riquadro azioni, nella scheda **Gestione di pagamenti**, nel gruppo **Informazioni correlate**, selezionare **Assegni**.</span><span class="sxs-lookup"><span data-stu-id="69f56-112">To open the **Checks** page, go to **Cash and bank management \> Bank accounts \> Bank accounts**, and then, on the Action Pane, on the **Manage payments** tab, in the **Related information** group, select **Checks**.</span></span> <span data-ttu-id="69f56-113">In alternativa, passare a **Gestione cassa e banche \> Richieste di informazioni e report \> Assegni**.</span><span class="sxs-lookup"><span data-stu-id="69f56-113">Alternatively, go to **Cash and bank management \> Inquiries and reports \> Checks**.</span></span>

<span data-ttu-id="69f56-114">Quindi, per creare assegni con stato **In bianco**, selezionare **Crea assegni in bianco** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="69f56-114">Then, to create checks that have **Blank** status, on the Action Pane, select **Create blank checks**.</span></span> <span data-ttu-id="69f56-115">Durante la creazione di assegni in bianco, il conto bancario associato è temporaneamente disattivato.</span><span class="sxs-lookup"><span data-stu-id="69f56-115">While the system is creating blank checks, the associated bank account is temporarily inactivated.</span></span> <span data-ttu-id="69f56-116">In questo modo si riduce il rischio di generare pagamenti nello stesso momento in cui vengono creati assegni in bianco.</span><span class="sxs-lookup"><span data-stu-id="69f56-116">This behavior reduces the risk that payments will be generated at the same time that blank checks are created.</span></span> <span data-ttu-id="69f56-117">Al completamento dell'elaborazione, il conto bancario associato viene riattivato.</span><span class="sxs-lookup"><span data-stu-id="69f56-117">When the processing is completed, the associated bank account is reactivated.</span></span>
