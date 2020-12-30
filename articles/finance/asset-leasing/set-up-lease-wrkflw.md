---
title: Configurare flussi di lavoro di approvazione del leasing
description: L'argomento spiega come configurare un flusso di lavoro di approvazione che verrà eseguito quando viene creato un nuovo leasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 58c0fd781710b7ab8efeaa7a6874f412279a5924
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "4444972"
---
# <a name="set-up-lease-approval-workflows"></a><span data-ttu-id="bd183-103">Configurare flussi di lavoro di approvazione del leasing</span><span class="sxs-lookup"><span data-stu-id="bd183-103">Set up lease approval workflows</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd183-104">L'argomento spiega come configurare un flusso di lavoro di approvazione che verrà eseguito quando viene creato un nuovo leasing.</span><span class="sxs-lookup"><span data-stu-id="bd183-104">The topic explains how to set up an approval workflow that will run when a new lease is created.</span></span> <span data-ttu-id="bd183-105">Per informazioni su come utilizzare il flusso di lavoro, vedi [Utilizza flussi di lavoro di approvazione del leasing](use-create-lease-wrkflw.md).</span><span class="sxs-lookup"><span data-stu-id="bd183-105">For information about how to use the workflow, see [Use lease approval workflows](use-create-lease-wrkflw.md).</span></span> 

1. <span data-ttu-id="bd183-106">Vai a **Leasing cespiti \> Imposta \> Flusso di lavoro di leasing**.</span><span class="sxs-lookup"><span data-stu-id="bd183-106">Go to **Asset leasing \> Setup \> Lease workflow**.</span></span>
2. <span data-ttu-id="bd183-107">Nella pagina **Flusso di lavoro di leasing**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="bd183-107">On the **Lease workflow** page, select **New**.</span></span>
3. <span data-ttu-id="bd183-108">Nella finestra di dialogo che appare, in **Tipo di flusso di lavoro**, seleziona il collegamento **Flusso di lavoro di leasing**.</span><span class="sxs-lookup"><span data-stu-id="bd183-108">In the dialog box that appears, under **Workflow type**, select the **Lease workflow** link.</span></span>

    <span data-ttu-id="bd183-109">L'applicazione viene aperta.</span><span class="sxs-lookup"><span data-stu-id="bd183-109">The application is opened.</span></span> <span data-ttu-id="bd183-110">Dopo l'esecuzione, accedi ad Azure Active Directory (Azure AD) per essere reindirizzato all'applicazione del flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd183-110">After it runs, sign in to Azure Active Directory (Azure AD) to be redirected to the workflow application.</span></span>

4. <span data-ttu-id="bd183-111">Trascina l'elemento **Approvazione flusso di lavoro leasing** nel flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd183-111">Drag the **Lease workflow approval** element onto the workflow.</span></span>
5. <span data-ttu-id="bd183-112">Connetti un nodo da **Inizio** a **Approvazione flusso di lavoro leasing**.</span><span class="sxs-lookup"><span data-stu-id="bd183-112">Connect one node from **Start** to **Lease workflow approval**.</span></span> <span data-ttu-id="bd183-113">Quindi connetti **Approvazione flusso di lavoro leasing** a **Fine**.</span><span class="sxs-lookup"><span data-stu-id="bd183-113">Then connect **Lease workflow approval** to **End**.</span></span>
6. <span data-ttu-id="bd183-114">Fai doppio clic su **Approvazione flusso di lavoro leasing**.</span><span class="sxs-lookup"><span data-stu-id="bd183-114">Double-click **Lease workflow approval**.</span></span>
7. <span data-ttu-id="bd183-115">Seleziona **Proprietà** e poi in **Impostazioni di base**, immetti un nome per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd183-115">Select **Properties**, and then, under **Basic settings**, enter a name for the workflow.</span></span>

    <span data-ttu-id="bd183-116">In questa pagina puoi anche impostare più parametri per il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd183-116">On this page, you can also set more parameters for the workflow.</span></span> <span data-ttu-id="bd183-117">Se hai attivato **Azioni automatiche**, il sistema eseguirà automaticamente un'azione specifica.</span><span class="sxs-lookup"><span data-stu-id="bd183-117">If you've turned on **Automatic actions**, the system will automatically take a specific action.</span></span> <span data-ttu-id="bd183-118">Le notifiche possono essere inviate se specificate nella scheda **Notifiche**. Nella scheda **Impostazioni avanzate**, è possibile specificare un approvatore finale, impostare un limite di tempo e designare azioni specifiche che devono essere completate.</span><span class="sxs-lookup"><span data-stu-id="bd183-118">Notifications can be sent if they are specified on the **Notifications** tab. On the **Advanced settings** tab, you can specify a final approver, set a time limit, and designate specific actions that must be completed.</span></span>

8. <span data-ttu-id="bd183-119">Al termine dell'impostazione dei parametri del flusso di lavoro, seleziona **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bd183-119">When you've finished setting the workflow parameters, select **Close**.</span></span>
9. <span data-ttu-id="bd183-120">Seleziona **Passaggio 1**, quindi seleziona **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="bd183-120">Select **Step 1**, and then select **Properties**.</span></span>
10. <span data-ttu-id="bd183-121">In **Impostazioni di base**, immetti un nome per il passaggio, crea una riga dell'oggetto per l'approvazione e specifica le istruzioni per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="bd183-121">Under **Basic settings**, enter a name for the step, create a subject line for the approval, and specify instructions for the approval.</span></span>
11. <span data-ttu-id="bd183-122">Nella pagina **Assegnazione**, seleziona il tipo di assegnazione.</span><span class="sxs-lookup"><span data-stu-id="bd183-122">On the **Assignment** page, select the assignment type.</span></span>
12. <span data-ttu-id="bd183-123">Per assegnare utenti specifici all'approvazione, seleziona **Utente**, seleziona gli utenti che approvano i leasing, quindi seleziona **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bd183-123">To assign specific users to the approval, select **User**, select the users who approve leases, and then select **Close**.</span></span>
13. <span data-ttu-id="bd183-124">Seleziona **Salva e chiudi** per creare il flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="bd183-124">Select **Save and close** to create the workflow.</span></span> <span data-ttu-id="bd183-125">Quindi, quando richiesto, seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd183-125">Then, when you're prompted, select **OK**.</span></span>
14. <span data-ttu-id="bd183-126">Nella pagina **Crea flusso di lavoro**, seleziona **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bd183-126">On the **Create workflow** page, select **Close**.</span></span>
14. <span data-ttu-id="bd183-127">Seleziona il nuovo flusso di lavoro, quindi seleziona **Versioni**.</span><span class="sxs-lookup"><span data-stu-id="bd183-127">Select the new workflow, and then select **Versions**.</span></span> <span data-ttu-id="bd183-128">Quindi seleziona **Rendi attivo** per verificare che il flusso di lavoro sia attivo.</span><span class="sxs-lookup"><span data-stu-id="bd183-128">Then select **Make active** to ensure that the workflow is active.</span></span>
15. <span data-ttu-id="bd183-129">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="bd183-129">Select **Close**.</span></span> <span data-ttu-id="bd183-130">Viene visualizzata la nuova versione attiva.</span><span class="sxs-lookup"><span data-stu-id="bd183-130">The new active version appears.</span></span>
