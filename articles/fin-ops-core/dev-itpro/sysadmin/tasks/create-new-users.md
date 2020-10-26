---
title: Creare nuovi utenti
description: Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.
author: maertenm
manager: AnnBe
ms.date: 06/08/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysDataAreaSelectLookup, SysSecUserAddRoles, SysUserMSODSUserImport
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e84130ff2b1cf83b7d2b95eefc72175dc57743c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982504"
---
# <a name="create-new-users"></a><span data-ttu-id="01765-103">Creare nuovi utenti</span><span class="sxs-lookup"><span data-stu-id="01765-103">Create new users</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="01765-104">Gli utenti sono dipendenti interni dell'organizzazione o clienti e fornitori esterni, che richiedono l'accesso al sistema per l'esecuzione dei processi.</span><span class="sxs-lookup"><span data-stu-id="01765-104">Users are internal employees of your organization, or external customers and vendors, who require access to the system to do their jobs.</span></span>

## <a name="associate-a-user-with-a-license-new-license-types-only"></a><span data-ttu-id="01765-105">Associare un utente a una licenza (solo nuovi tipi di licenza)</span><span class="sxs-lookup"><span data-stu-id="01765-105">Associate a user with a license (new license types only)</span></span>
<span data-ttu-id="01765-106">Per i clienti in uno dei nuovi tipi di licenza aggiunti nell'ottobre 2019, gli utenti devono essere associati a una licenza.</span><span class="sxs-lookup"><span data-stu-id="01765-106">For customers who are on one of the new license types that were added in October 2019, users must be associated with a license.</span></span> <span data-ttu-id="01765-107">Gli utenti associati a una licenza vengono aggiunti automaticamente come utenti del sistema che non hanno un ruolo al loro primo accesso.</span><span class="sxs-lookup"><span data-stu-id="01765-107">Users who are associated with a license are automatically added as system users who have no roles the first time that they sign in.</span></span>

<span data-ttu-id="01765-108">Gli amministratori di sistema possono [assegnare licenze a utenti](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide) nell'[interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="01765-108">System admins can [assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide) in the [Microsoft 365 admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center?view=o365-worldwide).</span></span>

## <a name="associate-an-external-user-with-a-license-new-license-types-only"></a><span data-ttu-id="01765-109">Associare un utente esterno a una licenza (solo nuovi tipi di licenza)</span><span class="sxs-lookup"><span data-stu-id="01765-109">Associate an external user with a license (new license types only)</span></span>
<span data-ttu-id="01765-110">Gli utenti esterni al tenant in cui è stato distribuito l'ambiente devono essere rappresentati nella directory del tenant host ( Azure Active Directory (Azure AD)) di modo che possano essere assegnate le licenze.</span><span class="sxs-lookup"><span data-stu-id="01765-110">Users external to the tenant that the environment was deployed into need to be represented in the host tenant directory (Azure Active Directory (Azure AD)) so that they can be assigned licenses.</span></span> <span data-ttu-id="01765-111">Tali utenti esterni devono essere aggiunti al tenant in Azure AD come utenti guest e devono quindi esservi assegnate le licenze appropriate.</span><span class="sxs-lookup"><span data-stu-id="01765-111">Those external users should be added to the tenant in Azure AD as guest users and then assigned the appropriate licenses.</span></span> <span data-ttu-id="01765-112">Per ulteriori informazioni, vedere [Aggiungere utenti di collaborazione B2B Azure Active Directory nel portale di Azure ](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span><span class="sxs-lookup"><span data-stu-id="01765-112">For more information, see [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="01765-113">Aggiungere un nuovo utente</span><span class="sxs-lookup"><span data-stu-id="01765-113">Add a new user</span></span>
1. <span data-ttu-id="01765-114">Selezionare **Amministrazione sistema \> Utenti \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="01765-114">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="01765-115">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="01765-115">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="01765-116">Nel campo **ID utente** immettere un identificatore univoco per l'utente.</span><span class="sxs-lookup"><span data-stu-id="01765-116">In the **User ID** field, enter a unique identifier for the user.</span></span> <span data-ttu-id="01765-117">È necessario un ID utente.</span><span class="sxs-lookup"><span data-stu-id="01765-117">A user ID is required.</span></span>  
4. <span data-ttu-id="01765-118">Nel campo **Nome utente** immettere il nome dell'utente.</span><span class="sxs-lookup"><span data-stu-id="01765-118">In the **User name** field, enter the user's name.</span></span>  
5. <span data-ttu-id="01765-119">Nel campo **Dominio** immettere il dominio dell'utente.</span><span class="sxs-lookup"><span data-stu-id="01765-119">In the **Domain** field, enter the user's domain.</span></span>  
6. <span data-ttu-id="01765-120">Nel campo **Alias**, immettere l'alias dell'utente.</span><span class="sxs-lookup"><span data-stu-id="01765-120">In the **Alias** field, enter the user's alias.</span></span>  
7. <span data-ttu-id="01765-121">Nel campo **Società**, selezionare la società desiderata.</span><span class="sxs-lookup"><span data-stu-id="01765-121">In the **Company** field, select the desired company.</span></span> 
8. <span data-ttu-id="01765-122">Nella Scheda dettaglio **Ruoli utente**, selezionare **Assegna ruoli** per assegnare utenti a ruoli di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="01765-122">On the **User's roles** FastTab, select **Assign roles** to assign users to security roles.</span></span> <span data-ttu-id="01765-123">Per ulteriori informazioni, vedere [Assegnare utenti a ruoli di sicurezza](assign-users-security-roles.md).</span><span class="sxs-lookup"><span data-stu-id="01765-123">For more information, see [Assign users to security roles](assign-users-security-roles.md).</span></span>
9. <span data-ttu-id="01765-124">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="01765-124">Select **OK**.</span></span>
10. <span data-ttu-id="01765-125">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="01765-125">Select **Save**.</span></span>

## <a name="import-users"></a><span data-ttu-id="01765-126">Importa utenti</span><span class="sxs-lookup"><span data-stu-id="01765-126">Import users</span></span>
1. <span data-ttu-id="01765-127">Selezionare **Amministrazione sistema \> Utenti \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="01765-127">Go to **System administration \> Users \> Users**.</span></span>
2. <span data-ttu-id="01765-128">Nel riquadro azioni, selezionare **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="01765-128">On the Action Pane, select **Import users**.</span></span>
3. <span data-ttu-id="01765-129">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="01765-129">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="01765-130">Selezionare **Importa utenti**.</span><span class="sxs-lookup"><span data-stu-id="01765-130">Select **Import users**.</span></span>
5. <span data-ttu-id="01765-131">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="01765-131">Select **Close**.</span></span>

