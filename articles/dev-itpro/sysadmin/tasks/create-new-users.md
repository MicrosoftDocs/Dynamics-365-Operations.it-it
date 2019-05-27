---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: maertenm
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: margoc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12cf223d262c4e0f2a195e95c83a00fc1a3f07e5
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558713"
---
# <a name="create-new-users"></a><span data-ttu-id="04490-103">Creare nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="04490-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="04490-104">Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="04490-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to perform their jobs.</span></span> <span data-ttu-id="04490-105">Gli amministratori di sistema possono completare questa procedura per aggiungere gli utenti al sistema.</span><span class="sxs-lookup"><span data-stu-id="04490-105">System administrators can complete this procedure to add users to the system.</span></span> <span data-ttu-id="04490-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="04490-106">The demo data company used to create this procedure is USMF.</span></span> 


## <a name="add-a-new-user"></a><span data-ttu-id="04490-107">Aggiungere un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="04490-107">Add a new user</span></span>
1. <span data-ttu-id="04490-108">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="04490-108">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="04490-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="04490-109">Click New.</span></span>
3. <span data-ttu-id="04490-110">Digitare un valore nel campo ID utente.</span><span class="sxs-lookup"><span data-stu-id="04490-110">In the User ID field, type a value.</span></span>
    * <span data-ttu-id="04490-111">Immettere un identificatore univoco per l'utente.</span><span class="sxs-lookup"><span data-stu-id="04490-111">Enter a unique identifier for the user.</span></span> <span data-ttu-id="04490-112">È necessario un ID utente.</span><span class="sxs-lookup"><span data-stu-id="04490-112">A user ID is required.</span></span>  
4. <span data-ttu-id="04490-113">Digitare un valore nel campo Utente.</span><span class="sxs-lookup"><span data-stu-id="04490-113">In the User name field, type a value.</span></span>
    * <span data-ttu-id="04490-114">Immettere il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="04490-114">Enter the user's name.</span></span>  
5. <span data-ttu-id="04490-115">Digitare un valore nel campo Dominio.</span><span class="sxs-lookup"><span data-stu-id="04490-115">In the Domain field, type a value.</span></span>
    * <span data-ttu-id="04490-116">Immettere il dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="04490-116">Enter the user's domain.</span></span>  
6. <span data-ttu-id="04490-117">Digitare un valore nel campo Alias.</span><span class="sxs-lookup"><span data-stu-id="04490-117">In the Alias field, type a value.</span></span>
    * <span data-ttu-id="04490-118">Immettere l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="04490-118">Enter the user's alias.</span></span>  
7. <span data-ttu-id="04490-119">Nel campo Società fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="04490-119">In the Company field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="04490-120">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="04490-120">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="04490-121">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="04490-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="04490-122">Selezionare la società dell'utente</span><span class="sxs-lookup"><span data-stu-id="04490-122">Select the user's company</span></span>  
10. <span data-ttu-id="04490-123">Fare clic su Assegna ruoli.</span><span class="sxs-lookup"><span data-stu-id="04490-123">Click Assign roles.</span></span>
11. <span data-ttu-id="04490-124">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="04490-124">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="04490-125">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="04490-125">Click OK.</span></span>
13. <span data-ttu-id="04490-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="04490-126">Click Save.</span></span>

## <a name="import-users"></a><span data-ttu-id="04490-127">Importa utenti</span><span class="sxs-lookup"><span data-stu-id="04490-127">Import users</span></span>
1. <span data-ttu-id="04490-128">Fare clic su Importa utenti.</span><span class="sxs-lookup"><span data-stu-id="04490-128">Click Import users.</span></span>
2. <span data-ttu-id="04490-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="04490-129">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="04490-130">Fare clic su Importa utenti.</span><span class="sxs-lookup"><span data-stu-id="04490-130">Click Import users.</span></span>
4. <span data-ttu-id="04490-131">Fare clic su Chiudi.</span><span class="sxs-lookup"><span data-stu-id="04490-131">Click Close.</span></span>

