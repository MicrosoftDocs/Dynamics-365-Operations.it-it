---
title: Regulatory Configuration Service (RCS) - Eliminare un ambiente RCS
description: Questo argomento spiega come un amministratore di sistema Regulatory Configuration Service (RCS) può eliminare un ambiente RCS e i relativi dati.
author: JaneA07
ms.date: 06/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Global
audience: Application User, System Admin
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: AX 10.0.15
ms.openlocfilehash: 637962cf63bfd8c2330726f33545f939ec91d58d
ms.sourcegitcommit: dbffde1944b9d037124415c28053036c9ef1ecb7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "6295820"
---
# <a name="regulatory-configuration-service-rcs---delete-an-rcs-environment"></a><span data-ttu-id="2e5ac-103">Regulatory Configuration Service (RCS) - Eliminare un ambiente RCS</span><span class="sxs-lookup"><span data-stu-id="2e5ac-103">Regulatory Configuration Service (RCS) - Delete an RCS environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2e5ac-104">Questo argomento spiega come un amministratore di sistema Regulatory Configuration Service (RCS) può eliminare un ambiente RCS e i relativi dati.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-104">This topic explains how a Regulatory Configuration Service (RCS) system administrator can delete an RCS environment and related data.</span></span>

<span data-ttu-id="2e5ac-105">Prima di poter completare le procedure in questo argomento, è necessario soddisfare i seguenti prerequisiti:</span><span class="sxs-lookup"><span data-stu-id="2e5ac-105">Before you can complete the procedure in this topic, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2e5ac-106">Devi avere il ruolo **Amministratore di sistema** assegnato per l'ambiente RCS.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-106">You must have the **System Admin** role assigned to you for the RCS environment.</span></span>
- <span data-ttu-id="2e5ac-107">Il ruolo **Amministratore di sistema** deve avere il ruolo **RCSDeleteEnvironmentDuty** assegnato.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-107">The **System Admin** role must have the **RCSDeleteEnvironmentDuty** role assigned to it.</span></span>

## <a name="delete-an-rcs-environment"></a><span data-ttu-id="2e5ac-108">Eliminare un ambiente RCS</span><span class="sxs-lookup"><span data-stu-id="2e5ac-108">Delete an RCS environment</span></span>

1. <span data-ttu-id="2e5ac-109">Apri RCS e seleziona l'area di lavoro **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-109">Open RCS, and select the **Electronic reporting** workspace tile.</span></span>
2. <span data-ttu-id="2e5ac-110">Nella sezione **Collegamenti correlati** seleziona **Elimina ambiente RCS**.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-110">In the **Related links** section, select **Delete RCS environment**.</span></span>

    ![Collegamento Elimina ambiente RCS nella sezione Collegamenti correlati](media/01_RCS-Delete-Environ-Related-Link.PNG)

3. <span data-ttu-id="2e5ac-112">Nella finestra di dialogo visualizzata, esamina i messaggi sull'ambito dell'eliminazione dell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-112">In the dialog box that appears, review the messages about the scope of environment deletion.</span></span>

    ![Messaggi nella finestra di dialogo Elimina ambiente RCS](media/01_RCS-Delete-Environ-Msg_noGUID.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="2e5ac-114">L'eliminazione di un ambiente RCS non può essere annullata.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-114">Deletion of an RCS environment can't be reversed.</span></span>
    >
    > <span data-ttu-id="2e5ac-115">L'operazione elimina l'ambiente RCS selezionato e tutti i dati correlati, comprese le funzionalità e le configurazioni archiviate nel repository globale.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-115">The operation deletes the selected RCS environment and any related data, including features and configurations that are stored in the Global repository.</span></span> <span data-ttu-id="2e5ac-116">Le funzionalità e le configurazioni condivise con altre organizzazioni verranno annullate ed eliminate se non hanno dipendenze.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-116">Features and configurations that are shared with other organizations will be unshared and deleted if they have no dependencies.</span></span> <span data-ttu-id="2e5ac-117">Le funzionalità e le configurazioni con dipendenze verranno contrassegnate come interrotte.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-117">Features and configurations that have dependencies will be marked as discontinued.</span></span>

4. <span data-ttu-id="2e5ac-118">Nel campo fornito, inserisci il GUID dell'ambiente RCS per confermare che desideri eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-118">In the field that is provided, enter the globally unique identifier (GUID) of the RCS environment to confirm that you want to delete it.</span></span> <span data-ttu-id="2e5ac-119">Il GUID dell'ambiente è incluso nel messaggio di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-119">The environment's GUID is included in the deletion message.</span></span>
5. <span data-ttu-id="2e5ac-120">Seleziona **Elimina ambiente**.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-120">Select **Delete environment**.</span></span>
    
<span data-ttu-id="2e5ac-121">Il tuo ambiente RCS e tutti i dati correlati sono ora eliminati.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-121">Your RCS environment and any related data are now deleted.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2e5ac-122">Dopo aver eliminato un ambiente RCS, non è possibile recuperare i dati.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-122">After you delete an RCS environment, there is no way to recover the data.</span></span> <span data-ttu-id="2e5ac-123">È possibile creare un nuovo ambiente RCS in qualsiasi area RCS disponibile.</span><span class="sxs-lookup"><span data-stu-id="2e5ac-123">A new RCS environment can be created in any available RCS region.</span></span>
