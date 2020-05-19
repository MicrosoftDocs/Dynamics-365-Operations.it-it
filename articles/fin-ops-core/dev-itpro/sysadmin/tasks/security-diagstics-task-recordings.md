---
title: Diagnostica di sicurezza per registrazioni attività
description: Questo argomento fornisce informazioni su come analizzare e gestire i requisiti delle autorizzazione di sicurezza in base a una registrazione attività.
author: Peakerbl
manager: AnnBe
ms.date: 05/05/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: ''
ms.dyn365.ops.version: Version 10.0.9
ms.openlocfilehash: fada3abb9362426c7c9ec33f5d25552edf3ef630
ms.sourcegitcommit: 71fec2553158c332ce4d4bfcedc2c1ab58c1a1a5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "3340677"
---
# <a name="security-diagnostics-for-task-recordings"></a><span data-ttu-id="2942e-103">Diagnostica di sicurezza per registrazioni attività</span><span class="sxs-lookup"><span data-stu-id="2942e-103">Security diagnostics for task recordings</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="before-you-begin"></a><span data-ttu-id="2942e-104">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="2942e-104">Before you begin</span></span>

<span data-ttu-id="2942e-105">Questo argomento fornisce informazioni su come analizzare e gestire i requisiti delle autorizzazione di sicurezza in base a una registrazione attività.</span><span class="sxs-lookup"><span data-stu-id="2942e-105">This topic provides information about how to analyze and manage security permission requirements based on a task recording.</span></span> <span data-ttu-id="2942e-106">Prima di completare i passaggi in questo argomento, è necessario disporre di una registrazione attività del processo aziendale che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="2942e-106">Before you complete the steps in this topic, you must have a task recording of the business process that you want to analyze.</span></span> <span data-ttu-id="2942e-107">Per registrare un processo aziendale, vedere [Risorse registrazione attività](../../user-interface/task-recorder.md).</span><span class="sxs-lookup"><span data-stu-id="2942e-107">To record a business process, see [Task recorder resources](../../user-interface/task-recorder.md).</span></span> 

## <a name="manage-security-for-a-task-recording"></a><span data-ttu-id="2942e-108">Gestire la sicurezza per una registrazione attività</span><span class="sxs-lookup"><span data-stu-id="2942e-108">Manage security for a task recording</span></span>

1. <span data-ttu-id="2942e-109">Andare a **Amministrazione sistema** > **Sicurezza** > **Diagnostica sicurezza per registrazione attività**.</span><span class="sxs-lookup"><span data-stu-id="2942e-109">Go to **System administration** > **Security** > **Security diagnostic for task recording**.</span></span>
2. <span data-ttu-id="2942e-110">Aprire la registrazione attività dalla relativa posizione.</span><span class="sxs-lookup"><span data-stu-id="2942e-110">Open the task recording from its location.</span></span> <span data-ttu-id="2942e-111">Selezionare **Apri dal PC** o **Aprire da Lifecycle Services**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="2942e-111">Select **Open from this PC** or **Open from Lifecycle Services**, and then select **Close**.</span></span>
3. <span data-ttu-id="2942e-112">Verrà aperta la pagina dei **dettagli delle voci del menu Sicurezza** in cui è presente un elenco degli oggetti di sicurezza richiesti per il processo.</span><span class="sxs-lookup"><span data-stu-id="2942e-112">This will open the **Security menu item details** page that lists the security objects required for the process.</span></span>

 > [!NOTE]
 > <span data-ttu-id="2942e-113">Le voci di menu **Azione** e **Output** sono incluse nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2942e-113">The **Action** and **Output** menu items are not included in the list.</span></span>

4. <span data-ttu-id="2942e-114">Nel campo **ID utente** selezionare un utente.</span><span class="sxs-lookup"><span data-stu-id="2942e-114">In the **User ID** field, select a user.</span></span> <span data-ttu-id="2942e-115">Se l'utente non dispone delle autorizzazioni per alcune voci di menu, il campo **Autorizzazioni mancanti** verrà modificato in **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2942e-115">If the user does not have permissions for some menu items, the **Missing permissions** field will update to **Yes**.</span></span>
  
  ![Pagina dei dettagli delle voci del menu Sicurezza](../media/Security-Menu-Item-Details.png)

5. <span data-ttu-id="2942e-117">Selezionare **Aggiungi riferimento** per visualizzare un elenco degli oggetti di sicurezza, inclusi ruoli, compiti e privilegi che concedono l'autorizzazione mancante.</span><span class="sxs-lookup"><span data-stu-id="2942e-117">Select **Add Reference** to see a list of the security objects, including roles, duties, and privileges that grant the missing permission.</span></span>
6. <span data-ttu-id="2942e-118">Selezionare un oggetto di sicurezza dall'elenco:</span><span class="sxs-lookup"><span data-stu-id="2942e-118">Select a security object from the list:</span></span>

    - <span data-ttu-id="2942e-119">Se **Ruolo** è selezionato, selezionare **Aggiungi ruolo a utente**.</span><span class="sxs-lookup"><span data-stu-id="2942e-119">If **Role** is selected, select **Add role to user**.</span></span> <span data-ttu-id="2942e-120">Verrà aperta la pagina **Assegna utenti a ruoli**.</span><span class="sxs-lookup"><span data-stu-id="2942e-120">This will open the **Assign users to roles** page.</span></span> <span data-ttu-id="2942e-121">Per ulteriori informazioni, vedere la pagina [Assegnare gli utenti ai ruoli di sicurezza](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2942e-121">For more information, see [Assign users to security roles](assign-users-security-roles.md) page.</span></span>
    - <span data-ttu-id="2942e-122">Se **Compito** è selezionato, selezionare **Aggiungi compito a ruolo**, selezionare i ruoli a cui deve essere aggiunto il compito, quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="2942e-122">If **Duty** is selected, select **Add duty to role**, select the roles that the duty should be added to, and then select **OK**.</span></span>
    - <span data-ttu-id="2942e-123">Se **Privilegio** è selezionato, selezionare **Aggiungi privilegio a compiti**, selezionare i ruoli a cui deve essere aggiunto il compito, quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="2942e-123">If **Privilege** is selected, select **Add privilege to duties**, select the roles that the duty should be added to, and then select **OK**.</span></span>
