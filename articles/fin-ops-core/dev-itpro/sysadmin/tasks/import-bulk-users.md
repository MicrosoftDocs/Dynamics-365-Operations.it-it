---
title: Importa utenti da Azure Active Directory
description: Questa procedura può essere utilizzata dagli amministratori di sistema per importare manualmente gli utenti selezionati o per importare un numero elevato di utenti da Azure Active Directory.
author: peakerbl
manager: AnnBe
ms.date: 07/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b6666310309817ff30ccb3902721880b829ee0
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4679816"
---
# <a name="import-users-from-azure-active-directory"></a><span data-ttu-id="32c2c-103">Importa utenti da Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="32c2c-103">Import users from Azure Active Directory</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="import-select-users"></a><span data-ttu-id="32c2c-104">Importare seleziona utenti</span><span class="sxs-lookup"><span data-stu-id="32c2c-104">Import select users</span></span>

<span data-ttu-id="32c2c-105">Questa procedura può essere utilizzata dagli amministratori di sistema per importare seleziona utenti da Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="32c2c-105">This procedure can be used by system administrators to import select users from Azure Active Directory (Azure AD).</span></span>

1. <span data-ttu-id="32c2c-106">L'utente verrà importato con la società della sessione corrente come società predefinita.</span><span class="sxs-lookup"><span data-stu-id="32c2c-106">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="32c2c-107">Modificare la società attuale, se applicabile, prima di importare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="32c2c-107">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="32c2c-108">Andare a **Amministrazione sistema > Utenti > Utent** i.</span><span class="sxs-lookup"><span data-stu-id="32c2c-108">Go to **System administration > Users > User** s.</span></span>
3. <span data-ttu-id="32c2c-109">Fare clic su **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-109">Click **Import users**.</span></span>
4. <span data-ttu-id="32c2c-110">Selezionare gli utenti da importare e selezionare **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-110">Select the users that should be imported and select **Import users**.</span></span>

<span data-ttu-id="32c2c-111">Una volta completata l'importazione, sarà necessario assegnare i ruoli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="32c2c-111">After import is completed it will be required to assign roles to users.</span></span>

## <a name="import-users-in-bulk"></a><span data-ttu-id="32c2c-112">Importare utenti in blocco</span><span class="sxs-lookup"><span data-stu-id="32c2c-112">Import users in bulk</span></span>

<span data-ttu-id="32c2c-113">Questa procedura può essere utilizzata dagli amministratori di sistema per importare un numero elevato di utenti da Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32c2c-113">This procedure can be used by system administrators to import a large number of users from Azure Active Directory.</span></span>
<span data-ttu-id="32c2c-114">Notare che non è possibile selezionare gli utenti quando si utilizza l'opzione di importazione batch.</span><span class="sxs-lookup"><span data-stu-id="32c2c-114">Note that it is not possible to select users when using the Batch import option.</span></span>

## <a name="run-the-import-as-a-batch-job"></a><span data-ttu-id="32c2c-115">Eseguire l'importazione come un processo batch</span><span class="sxs-lookup"><span data-stu-id="32c2c-115">Run the import as a batch job</span></span>
1. <span data-ttu-id="32c2c-116">L'utente verrà importato con la società della sessione corrente come società predefinita.</span><span class="sxs-lookup"><span data-stu-id="32c2c-116">User will be imported with the current session company as their default company.</span></span> <span data-ttu-id="32c2c-117">Modificare la società attuale, se applicabile, prima di importare gli utenti.</span><span class="sxs-lookup"><span data-stu-id="32c2c-117">Change current company if applicable before importing users.</span></span>
2. <span data-ttu-id="32c2c-118">Andare a **Amministrazione sistema > Utenti > Utenti**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-118">Go to **System administration > Users > Users**.</span></span>
3. <span data-ttu-id="32c2c-119">Fare clic su **Importazione batch**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-119">Click **Batch import**.</span></span>
4. <span data-ttu-id="32c2c-120">Espandi la sezione **Esecuzione in background**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-120">Expand the **Run in the background** section.</span></span>
4. <span data-ttu-id="32c2c-121">Selezionare \*\*Sì nel campo **Elaborazione batch**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-121">Select \*\*Yes in the **Batch processing** field.</span></span>
6. <span data-ttu-id="32c2c-122">Nel campo **Gruppo batch** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="32c2c-122">In the **Batch group** field, enter or select a value.</span></span> <span data-ttu-id="32c2c-123">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="32c2c-123">This is an optional step.</span></span>  
7. <span data-ttu-id="32c2c-124">Selezionare **Sì** nel campo **Privato**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-124">Select **Yes** in the **Private** field.</span></span> <span data-ttu-id="32c2c-125">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="32c2c-125">This is an optional step.</span></span>  
8. <span data-ttu-id="32c2c-126">Selezionare **Sì** nel campo **Processo critico**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-126">Select **Yes** in the **Critical job** field.</span></span> <span data-ttu-id="32c2c-127">Questo passaggio è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="32c2c-127">bThis is an optional step.</span></span>  
9. <span data-ttu-id="32c2c-128">Selezionare un'opzione nel campo \*\*Categoria di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="32c2c-128">In the \*\*Monitoring category field, select an option.</span></span>
10. <span data-ttu-id="32c2c-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-129">Click **OK**.</span></span>

<span data-ttu-id="32c2c-130">Una volta completata l'importazione, sarà necessario assegnare i ruoli agli utenti.</span><span class="sxs-lookup"><span data-stu-id="32c2c-130">After import is completed, it will be required to assign roles to users.</span></span>

## <a name="run-in-a-sandbox-environment"></a><span data-ttu-id="32c2c-131">Eseguire l'operazione in un ambiente sandbox</span><span class="sxs-lookup"><span data-stu-id="32c2c-131">Run in a sandbox environment</span></span>
1. <span data-ttu-id="32c2c-132">Selezionare **Importazione in batch**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-132">Select **Batch import**.</span></span>
2. <span data-ttu-id="32c2c-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="32c2c-133">Select **OK**.</span></span>
