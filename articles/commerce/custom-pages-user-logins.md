---
title: Impostare pagine personalizzate per l'accesso degli utenti
description: In questo argomento viene descritto come creare pagine personalizzate in Microsoft Dynamics 365 Commerce che consentono di gestire accessi personalizzati per gli utenti di tenant business-to-consumer (B2C) di Azure Active Directory (Azure AD).
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3328fad5328ae1954a6749f9a5eebcb71c723698
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477950"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a><span data-ttu-id="e6d3e-103">Impostare pagine personalizzate per l'accesso degli utenti</span><span class="sxs-lookup"><span data-stu-id="e6d3e-103">Set up custom pages for user sign-ins</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e6d3e-104">In questo argomento viene descritto come creare pagine personalizzate in Microsoft Dynamics 365 Commerce che consentono di gestire accessi personalizzati per gli utenti di tenant business-to-consumer (B2C) di Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="e6d3e-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

<span data-ttu-id="e6d3e-105">Per utilizzare pagine personalizzate create in Dynamics 365 Commerce per gestire flussi di accesso utente, è necessario configurare i criteri di Azure AD a cui si farà riferimento nell'ambiente di Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-105">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="e6d3e-106">È possibile configurare i criteri B2C di Azure AD "Iscrizione e accesso", "Modifica del profilo" e "Reimpostazione password" utilizzando l'applicazione B2C Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-106">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="e6d3e-107">È quindi possibile fare riferimento ai nomi di criteri e al tenant B2C di Azure AD B durante il provisioning effettuato per l'ambiente di Commerce utilizzando Microsoft Dynamics Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-107">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="e6d3e-108">Le pagine personalizzate di Commerce possono essere generate utilizzando il modulo Accesso, Iscrizione, Modifica profilo account o Reimpostazione password.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-108">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="e6d3e-109">Agli URL di pagina pubblicati per queste pagine personalizzate è quindi necessario fare riferimento nelle configurazioni dei criteri B2C di Azure AD nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-109">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="e6d3e-110">Impostare criteri B2C</span><span class="sxs-lookup"><span data-stu-id="e6d3e-110">Set up B2C policies</span></span>

<span data-ttu-id="e6d3e-111">Dopo l'impostazione del tenant B2C di Azure AD e l'associazione dello stesso all'ambiente di Commerce, passare alla pagina **Azure AD B2C** nel portale di Azure, quindi scegliere dal menu **Criteri** e selezionare **Flussi utente (criteri)**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-111">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Comando Flussi utente (criteri)](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="e6d3e-113">Ora è possibile configurare i flussi di accesso utente "Iscrizione e accesso", "Modifica profilo" e "Reimpostazione password".</span><span class="sxs-lookup"><span data-stu-id="e6d3e-113">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="e6d3e-114">Configurare il criterio "Iscrizione e accesso"</span><span class="sxs-lookup"><span data-stu-id="e6d3e-114">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="e6d3e-115">Per configurare il criterio "Iscrizione e accesso", effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-115">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-116">Selezionare **Nuovo flusso utente**, quindi nella scheda **Consigliato**, selezionare il criterio **Iscrizione e accesso**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-116">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="e6d3e-117">Immettere un nome per il criterio (ad esempio **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="e6d3e-117">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="e6d3e-118">Nella sezione **Provider di identità**, selezionare i provider di identità da utilizzare per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-118">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="e6d3e-119">È necessario che almeno **Iscrizione posta elettronica** sia selezionato.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-119">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="e6d3e-120">Nella colonna **Raccogli l'attributo**, selezionare le caselle di controllo per **Indirizzo di posta elettronica**, **Nome** e **Cognome**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-120">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="e6d3e-121">Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Provider di identità**, **Cognome** e **ID oggetto utente**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-121">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Attributi e attestazioni selezionati](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="e6d3e-123">Selezionare **OK** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-123">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="e6d3e-124">Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-124">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="e6d3e-125">Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-125">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![La pagina delle proprietà per il nuovo criterio](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="e6d3e-127">Al nome del criterio viene fatto riferimento nell'ambiente di Commerce.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-127">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="e6d3e-128">Il prefisso **B2C\_1\_** verrà incluso nel riferimento. I criteri non possono essere rinominati dopo essere stati creati.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-128">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="e6d3e-129">Se si sostituisce un criterio esistente per l'ambiente di Commerce, è possibile eliminare il criterio originale e creare un nuovo criterio che ha lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-129">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="e6d3e-130">In alternativa, se è già stato eseguito il provisioning dell'ambiente, è possibile inviare il nuovo criterio mediante una richiesta di assistenza.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-130">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="e6d3e-131">Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-131">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="e6d3e-132">Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-132">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="e6d3e-133">Configurare il criterio "Modifica del profilo"</span><span class="sxs-lookup"><span data-stu-id="e6d3e-133">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="e6d3e-134">Per configurare il criterio "Modifica del profilo", effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-134">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-135">Selezionare **Nuovo flusso utente**, quindi nella scheda **Consigliato**, selezionare il criterio **Modifica del profilo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-135">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="e6d3e-136">Immettere un nome per il criterio (ad esempio **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="e6d3e-136">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="e6d3e-137">Nella sezione **Provider di identità**, selezionare i provider di identità da utilizzare per il criterio.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-137">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="e6d3e-138">È necessario che sia selezionato almeno **Accesso all'account locale**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-138">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="e6d3e-139">Nella colonna **Raccogli l'attributo**, selezionare le caselle di controllo per **Indirizzi di posta elettronica** e **Cognome**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-139">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="e6d3e-140">Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Provider di identità**, **Cognome** e **ID oggetto utente**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-140">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="e6d3e-141">Selezionare **OK** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-141">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="e6d3e-142">Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-142">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="e6d3e-143">Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-143">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="e6d3e-144">Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-144">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="e6d3e-145">Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-145">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="e6d3e-146">Configurare il criterio "Reimpostazione password"</span><span class="sxs-lookup"><span data-stu-id="e6d3e-146">Configure the "Password reset" policy</span></span>

<span data-ttu-id="e6d3e-147">Per configurare il criterio "Reimpostazione password", effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-147">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-148">Selezionare **Nuovo flusso utente**, quindi nella scheda **Anteprima**, selezionare il criterio **Reimpostazione password v1.1**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-148">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Il criterio Reimpostazione password v1.1 selezionato nella scheda Anteprima](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="e6d3e-150">Immettere un nome per il criterio (ad esempio **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="e6d3e-150">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="e6d3e-151">Nella sezione **Provider di identità**, selezionare **Reimposta password utilizzando l'indirizzo di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-151">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="e6d3e-152">Nella colonna **Restituisci l'attestazione**, selezionare le caselle di controllo **Indirizzi di posta elettronica**, **Nome**, **Cognome** e **ID oggetto utente**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-152">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Attestazioni selezionate](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="e6d3e-154">Selezionare **OK** per creare il criterio.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-154">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="e6d3e-155">Fare doppio sul nome del nuovo criterio, quindi, nel pannello di navigazione, selezionare **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-155">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="e6d3e-156">Impostare l'opzione **Abilita JavaScript con imposizione del layout di pagina (anteprima)** su **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-156">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="e6d3e-157">Viene visualizzato di nuovo questo criterio per completare la configurazione dopo la creazione delle pagine personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-157">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="e6d3e-158">Per il momento, chiudere il criterio per tornare alla pagina **Flussi utente (criteri)** nel portale di Azure.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-158">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="e6d3e-159">Creare pagine personalizzate</span><span class="sxs-lookup"><span data-stu-id="e6d3e-159">Build the custom pages</span></span>

<span data-ttu-id="e6d3e-160">Per generare pagine personalizzate per gestire gli accessi utente, effettuare le operazioni indicate di seguito.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-160">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-161">Negli strumenti di creazione di Commerce, accedere al proprio sito.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-161">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="e6d3e-162">Creare i seguenti cinque modelli e cinque pagine:</span><span class="sxs-lookup"><span data-stu-id="e6d3e-162">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="e6d3e-163">Un modello **Accesso** e la pagina che utilizza il modulo Accesso.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-163">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="e6d3e-164">Un modello **Iscrizione** e la pagina che utilizza il modulo Iscrizione.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-164">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="e6d3e-165">Un modello **Reimpostazione password** e una pagina che utilizza modulo Reimpostazione password.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-165">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="e6d3e-166">Un modello **Verifica reimpostazione password** e una pagina che utilizza il modulo Verifica reimpostazione password.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-166">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="e6d3e-167">Un modello **Modifica profilo** e la pagina che utilizza il modulo Modifica profilo account</span><span class="sxs-lookup"><span data-stu-id="e6d3e-167">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="e6d3e-168">Quando si creano le pagine, attenersi alle seguenti indicazioni:</span><span class="sxs-lookup"><span data-stu-id="e6d3e-168">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="e6d3e-169">Per ciascuna pagina o modulo, utilizzare il layout e lo stile più appropriati per i requisiti aziendali.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-169">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="e6d3e-170">Pubblicare tutte le pagine e gli URL che devono essere utilizzati nella configurazione B2C di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-170">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="e6d3e-171">Dopo la pubblicazione di pagine e URL raccogliere gli URL che devono essere utilizzati per le configurazioni dei criteri B2C di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-171">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="e6d3e-172">Un suffisso **?preloadscripts=true** viene aggiunto a ogni URL quando utilizzato.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-172">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e6d3e-173">Non riutilizzare intestazioni e piè di pagina universali che hanno collegamenti relativi.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-173">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="e6d3e-174">Poiché queste pagine saranno ospitate nel dominio B2C di Azure AD quando utilizzate, solo gli URL assoluti devono essere utilizzati per tutti i collegamenti.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-174">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="e6d3e-175">Configurare criteri B2C di Azure AD con informazioni sulle pagine personalizzate</span><span class="sxs-lookup"><span data-stu-id="e6d3e-175">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="e6d3e-176">Nel portale di Azure, ritornare alla pagina **Azure AD B2C** quindi nel menu, sotto **Criteri**, selezionare **Flussi utente (criteri)**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-176">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="e6d3e-177">Aggiornare il criterio "Iscrizione e accesso" con informazioni sulle pagine personalizzate</span><span class="sxs-lookup"><span data-stu-id="e6d3e-177">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="e6d3e-178">Aggiornare il criterio "Iscrizione e accesso" con informazioni sulle pagine personalizzate, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-178">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-179">Nel criterio **Iscrizione e accesso** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-179">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="e6d3e-180">Selezionare il layout **Pagina unificata per l'iscrizione o l'accesso**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-180">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="e6d3e-181">Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-181">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="e6d3e-182">Nel campo **URI della pagina personalizzata**, immettere l'URL di accesso completo.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-182">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="e6d3e-183">Includere il suffisso **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-183">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="e6d3e-184">Ad esempio, immettere ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-184">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="e6d3e-185">Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-185">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="e6d3e-186">Selezionare il layout **Pagina di iscrizione dell'account locale**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-186">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="e6d3e-187">Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-187">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="e6d3e-188">Nel campo **URI della pagina personalizzata**, immettere l'URL di iscrizione completo.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-188">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="e6d3e-189">Includere il suffisso **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-189">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="e6d3e-190">Ad esempio, immettere ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-190">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="e6d3e-191">Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-191">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="e6d3e-192">Nella sezione **Attributi utente**, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d3e-192">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="e6d3e-193">Per gli attributi **Indirizzo di posta elettronica**, **Nome** e **Cognome**, selezionare **No** nel campo **Richiede la verifica**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-193">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="e6d3e-194">Per gli attributi **Nome** e **Cognome**, selezionare **No** nel campo **Facoltativo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-194">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Configurazione del criterio Pagina di iscrizione dell'account locale](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="e6d3e-196">Aggiornare il criterio "Modifica profilo" con informazioni sulle pagine personalizzate</span><span class="sxs-lookup"><span data-stu-id="e6d3e-196">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="e6d3e-197">Per aggiornare il criterio "Modifica profilo" con informazioni sulle pagine personalizzate, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-197">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-198">Nel criterio **Modifica profilo** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-198">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="e6d3e-199">Selezionare il layout **Pagina di modifica del profilo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-199">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="e6d3e-200">Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-200">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="e6d3e-201">Nel campo **URI della pagina personalizzata**, immettere l'URL di modifica profilo completo.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-201">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="e6d3e-202">Includere il suffisso **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-202">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="e6d3e-203">Ad esempio, immettere ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-203">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="e6d3e-204">Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-204">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="e6d3e-205">Nella sezione **Attributi utente**, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e6d3e-205">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="e6d3e-206">Per gli attributi **Indirizzo di posta elettronica**, **Nome**, selezionare **No** nel campo **Richiede la verifica**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-206">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="e6d3e-207">Per gli attributi **Nome** e **Cognome**, selezionare **No** nel campo **Facoltativo**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-207">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="e6d3e-208">Aggiornare il criterio "Reimposta password" con informazioni sulle pagine personalizzate</span><span class="sxs-lookup"><span data-stu-id="e6d3e-208">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="e6d3e-209">Per aggiornare il criterio "Reimposta password" con informazioni sulle pagine personalizzate, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-209">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="e6d3e-210">Nel criterio **Reimposta password** configurato in precedenza, nel pannello di navigazione, selezionare **Layout di pagina**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-210">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="e6d3e-211">Selezionare il layout **Pagina nuova password**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-211">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="e6d3e-212">Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-212">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="e6d3e-213">Nel campo **URI della pagina personalizzata**, immettere l'URL di reimpostazione della password completo.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-213">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="e6d3e-214">Includere il suffisso **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-214">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="e6d3e-215">Ad esempio, immettere ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-215">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="e6d3e-216">Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-216">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="e6d3e-217">Selezionare il layout **Pagina Verifica dell'account**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-217">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="e6d3e-218">Impostare l'opzione **Usa contenuto di pagina personalizzato** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-218">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="e6d3e-219">Nel campo **URI della pagina personalizzata**, immettere l'URL di verifica della reimpostazione della password completo.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-219">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="e6d3e-220">Includere il suffisso **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-220">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="e6d3e-221">Ad esempio, immettere ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-221">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="e6d3e-222">Nel campo **Versione del layout di pagina (anteprima)** selezionare **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-222">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="e6d3e-223">Personalizzazione stringhe di testo predefinite per etichette e descrizioni</span><span class="sxs-lookup"><span data-stu-id="e6d3e-223">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="e6d3e-224">Nella libreria di moduli, i moduli Accesso sono precompilati con stringhe di testo predefinite per etichette e descrizioni.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-224">In the module library, sign-in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="e6d3e-225">È possibile personalizzare queste stringhe nel kit SDK aggiornando i valori nel file global.json per il modulo Accesso.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-225">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="e6d3e-226">Ad esempio, il testo predefinito per il collegamento per la password dimenticata è **Password dimenticata?**.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-226">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="e6d3e-227">Quanto seguente mostra questo testo predefinito nella pagina di accesso.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-227">The following shows this default text on the sign-in page.</span></span>

![Testo predefinito per il collegamento per la password dimenticata nella pagina di accesso](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="e6d3e-229">Tuttavia, nel file global.json per il modulo Accesso della libreria di moduli, è possibile modificare il testo in **Hai dimenticato la password?**, come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-229">However, in the global.json file for the module library sign-in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Testo del collegamento aggiornato nel file global.json del modulo Accesso](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="e6d3e-231">Una volta aggiornato il file global.json e pubblicato le modifiche, il nuovo testo del collegamento è visualizzato nel modulo Accesso in Commerce e nella pagina di accesso live.</span><span class="sxs-lookup"><span data-stu-id="e6d3e-231">After you update the global.json file and publish your changes, the new link text appears in the sign-in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6d3e-232">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e6d3e-232">Additional resources</span></span>

[<span data-ttu-id="e6d3e-233">Configurare il proprio nome di dominio</span><span class="sxs-lookup"><span data-stu-id="e6d3e-233">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="e6d3e-234">Distribuire un nuovo tenant di e-commerce</span><span class="sxs-lookup"><span data-stu-id="e6d3e-234">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="e6d3e-235">Creare un sito di e-commerce</span><span class="sxs-lookup"><span data-stu-id="e6d3e-235">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="e6d3e-236">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="e6d3e-236">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="e6d3e-237">Gestire i file robots.txt</span><span class="sxs-lookup"><span data-stu-id="e6d3e-237">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="e6d3e-238">Caricare reindirizzamenti URL in blocco</span><span class="sxs-lookup"><span data-stu-id="e6d3e-238">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="e6d3e-239">Impostare un tenant B2C in Commerce</span><span class="sxs-lookup"><span data-stu-id="e6d3e-239">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="e6d3e-240">Configurare più tenant B2C in un ambiente Commerce</span><span class="sxs-lookup"><span data-stu-id="e6d3e-240">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="e6d3e-241">Aggiungere il supporto per una rete per la distribuzione di contenuti (CDN)</span><span class="sxs-lookup"><span data-stu-id="e6d3e-241">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="e6d3e-242">Abilitare il rilevamento del punto vendita basato sull'ubicazione</span><span class="sxs-lookup"><span data-stu-id="e6d3e-242">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
