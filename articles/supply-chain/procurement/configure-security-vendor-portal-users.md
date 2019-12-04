---
title: Sicurezza degli utenti del portale fornitori
description: In questo articolo viene illustrato come configurare la sicurezza dei fornitori esterni che utilizzano il portale fornitori. Queste informazioni si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX.
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 30231
ms.assetid: 3574db17-81c7-4c5a-999b-0098aa0b9cda
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 944b27754e87d80584b7fdfffa46d8af112227e3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2813571"
---
# <a name="vendor-portal-user-security"></a><span data-ttu-id="4aa9d-104">Sicurezza utente del portale fornitori</span><span class="sxs-lookup"><span data-stu-id="4aa9d-104">Vendor portal user security</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4aa9d-105">In questo articolo viene illustrato come configurare la sicurezza dei fornitori esterni che utilizzano il portale fornitori.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-105">This article explains how to set up security for external vendors who use the Vendor portal.</span></span> <span data-ttu-id="4aa9d-106">Queste informazioni si applicano solo alle versioni di febbraio 2016 e maggio 2016 di Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-106">This information applies only to the February 2016 &amp; May 2016 versions of Dynamics AX.</span></span>

<span data-ttu-id="4aa9d-107">La funzionalità portale fornitori è stata sostituita da funzionalità estese di collaborazione fornitore in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-107">The Vendor portal functionality has been replaced by extended vendor collaboration functionality in Dynamics 365 for Operations version 1611.</span></span> <span data-ttu-id="4aa9d-108">Per ulteriori informazioni su come impostare la sicurezza per la collaborazione fornitore, vedere [Impostare e gestire la collaborazione fornitore](set-up-maintain-vendor-collaboration.md).</span><span class="sxs-lookup"><span data-stu-id="4aa9d-108">For more information about setting up security for vendor collaboration, see [Set up and maintain vendor collaboration](set-up-maintain-vendor-collaboration.md).</span></span> <span data-ttu-id="4aa9d-109">Il portale fornitori espone un set limitato di informazioni sugli ordini fornitore per i fornitori esterni.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-109">The Vendor portal exposes a limited set of information about purchase orders (POs) to external vendors.</span></span> <span data-ttu-id="4aa9d-110">È importante impostare correttamente le autorizzazioni utente del portale fornitori in Microsoft Dynamics AX, in modo che i fornitori non abbiano accesso in modo non intenzionale a informazioni aggiuntive nella soluzione Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-110">It's important that you correctly set up user permissions for the Vendor portal in Microsoft Dynamics AX, so that vendors don't have unintended access to additional information in your Dynamics AX installation.</span></span> <span data-ttu-id="4aa9d-111">**Importante**: a differenza degli altri utenti, i fornitori esterni non devono avere il ruolo **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-111">**Important:** Unlike other users, external vendors should not have the **SystemUser** role.</span></span> <span data-ttu-id="4aa9d-112">Il ruolo **SystemUser** consente l'accesso a un set di privilegi non appropriati per gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-112">The **SystemUser** role grants access to a set of privileges that aren't suitable for external users.</span></span>

## <a name="setting-up-a-vendor-portal-user"></a><span data-ttu-id="4aa9d-113">Impostazione di un utente del portale fornitori</span><span class="sxs-lookup"><span data-stu-id="4aa9d-113">Setting up a Vendor portal user</span></span>
<span data-ttu-id="4aa9d-114">Prima di creare un account utente per una persona che utilizzerà il portale fornitori, è necessario impostare il fornitore per consentire collaborazione tramite il portale fornitori.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-114">Before you create a user account for someone who will use the Vendor portal, you must set up the vendor to allow for Vendor portal collaboration.</span></span> <span data-ttu-id="4aa9d-115">Utilizzare il campo **Collaborazione su ordine fornitore** nella scheda **Generale** della pagina **Fornitori**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-115">Use the **Purchase order collaboration** field on the **General** tab on the **Vendors** page.</span></span> <span data-ttu-id="4aa9d-116">I fornitori esterni che utilizzano il portale fornitori devono avere la seguente impostazione:</span><span class="sxs-lookup"><span data-stu-id="4aa9d-116">External vendors that use the Vendor portal must have the following setup:</span></span>

-   <span data-ttu-id="4aa9d-117">Un account utente di Microsoft Azure Active Directory (AAD) deve essere registrato per il fornitore nella pagina **Utenti** in Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-117">A Microsoft Azure Active Directory (AAD) user account must be registered for the vendor on the **Users** page in Dynamics AX.</span></span>
-   <span data-ttu-id="4aa9d-118">Il fornitore deve avere il ruolo di sicurezza **Fornitore (esterno)**, non il ruolo **SystemUser**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-118">The vendor must have the **Vendor (external)** security role, not the **SystemUser** role.</span></span> <span data-ttu-id="4aa9d-119">**Nota:** il ruolo **SystemUser** viene concesso automaticamente quando si crea un nuovo account utente in Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-119">**Note:** The **SystemUser** role is automatically granted when you create a new user account in Dynamics AX.</span></span> <span data-ttu-id="4aa9d-120">Di conseguenza, è necessario rimuovere questo ruolo e verificare il messaggio di avviso ricevuto.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-120">Therefore, you must remove that role and acknowledge the warning message that you receive.</span></span>
-   <span data-ttu-id="4aa9d-121">All'utente fornitore non deve essere concessa l'autorizzazione ad aggiungere ulteriori campi delle tabelle dell'ordine fornitore nella visualizzazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-121">The vendor user should not be granted permission to add additional fields from the PO tables to their view of the PO.</span></span> <span data-ttu-id="4aa9d-122">Nella scheda **Personalizzazione** della scheda **Utenti** impostare l'opzione **Personalizzazione esplicita consentita** per l'utente su **No**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-122">On the **Personalization** tab, on the **Users** tab, set the **Explicit personalization allowed** option for the user to **No**.</span></span>
-   <span data-ttu-id="4aa9d-123">L'account utente deve essere associato a un contatto registrato.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-123">The user account must be associated with a registered contact person.</span></span> <span data-ttu-id="4aa9d-124">Nella pagina **Utenti**, selezionare un contatto nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-124">On the **Users** page, select a contact person in the **Name** field.</span></span> <span data-ttu-id="4aa9d-125">La persona selezionata deve avere il ruolo **Contatto** per il fornitore pertinente.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-125">The person that you select should have the **Contact** role for the relevant vendor.</span></span>

<span data-ttu-id="4aa9d-126">Se la stessa persona richiede l'accesso al portale fornitori per più conti fornitori (magari per persone giuridiche diverse), ogni account utente di tale persona deve essere associato allo stesso contatto registrato.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-126">If the same person requires access to the Vendor portal for multiple vendor accounts (for different legal entities, perhaps), each of that person's user accounts must be associated with the same registered contact person.</span></span> <span data-ttu-id="4aa9d-127">Il ruolo **Fornitore (esterno)** include tutte le funzionalità di base necessarie per utilizzare la funzionalità disponibile nel portale fornitori.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-127">The **Vendor (external)** role includes all the basic capabilities that are required in order to use the functionality that is available in the Vendor portal.</span></span> <span data-ttu-id="4aa9d-128">Questa impostazione garantisce che l'interfaccia utente che l'utente esterno visualizza sia incentrata solo sullo scenario desiderato.</span><span class="sxs-lookup"><span data-stu-id="4aa9d-128">This setup helps guarantee that the user interface that the external user sees is focused on the intended scenario only.</span></span>

<a name="additional-resources"></a><span data-ttu-id="4aa9d-129">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="4aa9d-129">Additional resources</span></span>
--------

[<span data-ttu-id="4aa9d-130">Collaborare con i fornitori tramite il portale fornitori</span><span class="sxs-lookup"><span data-stu-id="4aa9d-130">Collaborate with vendors by using the Vendor portal</span></span>](collaborate-vendors-vendor-portal.md)



