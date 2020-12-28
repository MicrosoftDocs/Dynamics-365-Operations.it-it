---
title: Creare persone giuridiche
description: In questo argomento viene descritto come creare persone giuridiche in Microsoft Dynamics 365 Commerce, che deve essere creato e configurato prima di creare canali.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 28cbcc42505f1dc90c420adc812735841541c8e0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413420"
---
# <a name="create-legal-entities"></a><span data-ttu-id="6a556-103">Creare persone giuridiche</span><span class="sxs-lookup"><span data-stu-id="6a556-103">Create legal entities</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6a556-104">In questo argomento viene descritto come creare persone giuridiche in Microsoft Dynamics 365 Commerce, che deve essere creato e configurato prima di creare canali.</span><span class="sxs-lookup"><span data-stu-id="6a556-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

## <a name="overview"></a><span data-ttu-id="6a556-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="6a556-105">Overview</span></span>

<span data-ttu-id="6a556-106">Una persona giuridica è un'organizzazione dotata di una struttura legale istituita o registrata.</span><span class="sxs-lookup"><span data-stu-id="6a556-106">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="6a556-107">Le persone giuridiche possono stipulare contratti e hanno l'obbligo di preparare rendiconti sul loro rendimento.</span><span class="sxs-lookup"><span data-stu-id="6a556-107">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="6a556-108">Una società è un tipo di persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-108">A company is a type of legal entity.</span></span> <span data-ttu-id="6a556-109">Attualmente, le società sono l'unico tipo di persona giuridica che è possibile creare e ogni persona giuridica è associata a un ID società.</span><span class="sxs-lookup"><span data-stu-id="6a556-109">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="6a556-110">Questa associazione esiste perché alcune aree funzionali del programma utilizzano un ID società, o *DataAreaId*, nei loro modelli di dati.</span><span class="sxs-lookup"><span data-stu-id="6a556-110">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="6a556-111">In queste aree funzionali, le società vengono usate come limite per la sicurezza dei dati.</span><span class="sxs-lookup"><span data-stu-id="6a556-111">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="6a556-112">Gli utenti possono accedere solo ai dati della società a cui sono collegati.</span><span class="sxs-lookup"><span data-stu-id="6a556-112">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="6a556-113">Quando si crea un canale, è necessario specificare a quale persona giuridica appartiene quel canale.</span><span class="sxs-lookup"><span data-stu-id="6a556-113">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="6a556-114">Creare una nuova persona giuridica</span><span class="sxs-lookup"><span data-stu-id="6a556-114">Create a new legal entity</span></span>

<span data-ttu-id="6a556-115">Per creare una nuova persona giuridica in Dynamics 365 Commerce, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="6a556-115">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="6a556-116">Nel pannello di navigazione, andare a **Moduli \> Impostazione sedi centrali \> Persone giuridiche**.</span><span class="sxs-lookup"><span data-stu-id="6a556-116">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="6a556-117">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="6a556-117">On the action pane, select **New**.</span></span> <span data-ttu-id="6a556-118">Il riquadro **Nuova persona giuridica** appare sulla destra.</span><span class="sxs-lookup"><span data-stu-id="6a556-118">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="6a556-119">Nel campo **Nome** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="6a556-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="6a556-120">Nel campo **Società** immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="6a556-120">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="6a556-121">Nel campo **Paese**, immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="6a556-121">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="6a556-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a556-122">Select **OK**.</span></span> 

   ![Creazione di persone giuridiche](media/legal-entities.png)

1. <span data-ttu-id="6a556-124">Nella sezione **Generale**, immettere le seguenti informazioni generali sulla persona giuridica:</span><span class="sxs-lookup"><span data-stu-id="6a556-124">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="6a556-125">Immettere un nome di ricerca se è richiesto.</span><span class="sxs-lookup"><span data-stu-id="6a556-125">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="6a556-126">Un nome di ricerca è un nome alternativo che è possibile utilizzare per cercare questa persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-126">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="6a556-127">Scegliere se la persona giuridica viene utilizzata come società di consolidamento.</span><span class="sxs-lookup"><span data-stu-id="6a556-127">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="6a556-128">Scegliere se la persona giuridica viene utilizzata come società di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="6a556-128">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="6a556-129">Selezionare la **lingua predefinita** per l'entità.</span><span class="sxs-lookup"><span data-stu-id="6a556-129">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="6a556-130">Selezionare il **fuso orario** per l'entità.</span><span class="sxs-lookup"><span data-stu-id="6a556-130">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="6a556-131">Nella sezione **Indirizzi** selezionare **Modifica** per immettere informazioni sull'indirizzo ovvero via, numero civico, CAP e città.</span><span class="sxs-lookup"><span data-stu-id="6a556-131">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="6a556-132">Nella sezione **Informazioni contatto** immettere le informazioni sui metodi di comunicazione, ad esempio indirizzi di posta elettronica, URL e numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="6a556-132">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="6a556-133">Nella sezione **Relazione finanziaria** immettere i numeri di registrazione utilizzati per il reporting statutario.</span><span class="sxs-lookup"><span data-stu-id="6a556-133">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="6a556-134">Nella sezione **Numeri di registrazione** immettere le informazioni richieste dalla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-134">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="6a556-135">Nella sezione **Informazioni conto bancario** immettere i conti bancari e i numeri di registrazione relativi alla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-135">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="6a556-136">Nella sezione **Commercio estero e logistica** immettere le informazioni di spedizione relative alla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-136">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="6a556-137">Nella sezione **Sequenze numeriche** è possibile visualizzare le sequenze numeriche associate alla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-137">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="6a556-138">Inizialmente questa sezione sarà vuota.</span><span class="sxs-lookup"><span data-stu-id="6a556-138">This will be empty to start with.</span></span>
1. <span data-ttu-id="6a556-139">Nella sezione **Immagine nel dashboard** visualizzare o modificare l'immagine del dashboard e del logo associata alla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-139">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="6a556-140">Nella sezione **Registrazione fiscale** immettere i numeri di registrazione utilizzati per le dichiarazioni alle autorità fiscali.</span><span class="sxs-lookup"><span data-stu-id="6a556-140">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="6a556-141">Nella sezione **Imposta 1099** immettere le informazioni incluse nel modulo 1099 per la persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-141">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="6a556-142">Nella sezione **Informazioni sull'imposta**, immettere le informazioni sull'imposta per la persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-142">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="6a556-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6a556-143">Select **Save**.</span></span>

<span data-ttu-id="6a556-144">L'immagine seguente illustra un esempio di persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="6a556-144">The following image shows details of an example legal entity.</span></span>

![Sezione generale della persona giuridica](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="6a556-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6a556-146">Additional resources</span></span>

[<span data-ttu-id="6a556-147">Panoramica organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="6a556-147">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="6a556-148">Pianificazione della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="6a556-148">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="6a556-149">Gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="6a556-149">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="6a556-150">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="6a556-150">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="6a556-151">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="6a556-151">Channel setup prerequisites</span></span>](channels-prerequisites.md)
