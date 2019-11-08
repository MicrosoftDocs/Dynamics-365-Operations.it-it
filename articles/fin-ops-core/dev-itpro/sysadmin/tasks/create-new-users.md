---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: maertenm
manager: AnnBe
ms.date: 10/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3c347a34a389c32d005cc8086c4a1349ecb8a698
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "2570523"
---
# <a name="create-new-users"></a><span data-ttu-id="9eb6c-103">Creare nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="9eb6c-103">Create new users</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9eb6c-104">Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="9eb6c-105">Associare un utente a una licenza (solo nuovi tipi di licenza)</span><span class="sxs-lookup"><span data-stu-id="9eb6c-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="9eb6c-106">Per i clienti in uno dei nuovi tipi di licenza aggiunti nell'ottobre 2019, gli utenti devono essere associati a una licenza.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="9eb6c-107">Gli utenti associati a una licenza vengono aggiunti automaticamente come utenti del sistema che non hanno un ruolo al loro primo accesso.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span> <span data-ttu-id="9eb6c-108">Gli utenti non associati a una licenza ricevono un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-108">Users who aren't associated with a licence receive a warning message.</span></span>

<span data-ttu-id="9eb6c-109">Gli amministratori di sistema possono [assegnare licenze a utenti](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide) nell'[interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="9eb6c-109">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="9eb6c-110">Aggiungere un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="9eb6c-110">Add a new user</span></span>
1. <span data-ttu-id="9eb6c-111">Selezionare **Amministrazione sistema \> Utenti \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-111">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="9eb6c-112">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-112">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="9eb6c-113">Nel campo **ID utente** immettere un identificatore univoco per l'utente.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-113">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="9eb6c-114">È necessario un ID utente.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-114">A user ID is required.</span></span>  
4. <span data-ttu-id="9eb6c-115">Nel campo **Nome utente** immettere il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-115">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="9eb6c-116">Nel campo **Dominio** immettere il dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-116">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="9eb6c-117">Nel campo **Alias**, immettere l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-117">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="9eb6c-118">Nel campo **Società**, selezionare la società desiderata.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-118">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="9eb6c-119">Nella Scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli** per [assegnare utenti a ruoli di sicurezza](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="9eb6c-119">On the **User's roles** FastTab, select **Assign roles** to [assign users to security roles](assign-users-security-roles.md)</span></span>
9. <span data-ttu-id="9eb6c-120">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-120">Select **OK**.</span></span>
10. <span data-ttu-id="9eb6c-121">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-121">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="9eb6c-122">Importa utenti</span><span class="sxs-lookup"><span data-stu-id="9eb6c-122">Import users</span></span>
1. <span data-ttu-id="9eb6c-123">Nel riquadro azioni, selezionare **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-123">On the Action Pane, select **Import users**.</span></span>
2. <span data-ttu-id="9eb6c-124">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-124">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="9eb6c-125">Selezionare **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-125">Select **Import users**.</span></span>
4. <span data-ttu-id="9eb6c-126">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="9eb6c-126">Select **Close**.</span></span>

