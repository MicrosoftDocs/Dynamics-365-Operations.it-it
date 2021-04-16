---
title: Impostare un profilo di notifica tramite posta elettronica
description: In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7504b2b36f6869f90de196bf32c09e7bdd51e7b5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792659"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="d0272-103">Impostare un profilo di notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d0272-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d0272-104">In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d0272-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="d0272-105">Quando si creano canali, è possibile impostare un profilo di notifica e-mail.</span><span class="sxs-lookup"><span data-stu-id="d0272-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="d0272-106">In tal modo, le e-mail possono essere inviate ai clienti per vari eventi transazionali, come la creazione dell'ordine, lo stato di spedizione dell'ordine e il mancato pagamento.</span><span class="sxs-lookup"><span data-stu-id="d0272-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="d0272-107">Per ulteriori informazioni di configurazione della posta elettronica, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="d0272-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="d0272-108">Creare un profilo di notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d0272-108">Create an email notification profile</span></span>

<span data-ttu-id="d0272-109">Per creare un profilo di notifica tramite posta elettronica, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="d0272-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="d0272-110">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="d0272-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="d0272-111">Fare clic su **Nuovo** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="d0272-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="d0272-112">Nel campo **Profilo di notifica tramite posta elettronica**, immettere un nome per identificare il profilo.</span><span class="sxs-lookup"><span data-stu-id="d0272-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="d0272-113">Nel campo **Descrizione** immettere una descrizione pertinente.</span><span class="sxs-lookup"><span data-stu-id="d0272-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="d0272-114">Impostare **Attivo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="d0272-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="d0272-115">Crea un modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d0272-115">Create an email template</span></span>

<span data-ttu-id="d0272-116">Prima di poter abilitare un tipo di notifica tramite posta elettronica, è necessario creare un modello di posta elettronica dell'organizzazione in Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="d0272-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="d0272-117">Questo modello definisce l'oggetto, il mittente, la lingua predefinita e il corpo del messaggio di posta elettronica per ciascuna lingua che si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="d0272-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="d0272-118">Per creare un modello e-mail attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="d0272-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="d0272-119">Nel pannello di navigazione, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="d0272-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="d0272-120">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="d0272-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="d0272-121">Nel campo **ID posta elettronica**, immettere un ID per facilitare l'identificazione di questo modello.</span><span class="sxs-lookup"><span data-stu-id="d0272-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="d0272-122">Nel campo **Nome mittente** immettere il nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="d0272-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="d0272-123">Nel campo **Descrizione messaggio di posta elettronica** immettere una descrizione pertinente.</span><span class="sxs-lookup"><span data-stu-id="d0272-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="d0272-124">Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="d0272-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="d0272-125">Nella sezione **Generale**, selezionare una lingua predefinita per il modello di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d0272-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="d0272-126">La lingua predefinita verrà utilizzata quando non esiste alcun modello localizzato per la lingua specificata.</span><span class="sxs-lookup"><span data-stu-id="d0272-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="d0272-127">Espandere la sezione **Contenuto messaggio posta elettronica** e selezionare **Nuovo** per creare il contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="d0272-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="d0272-128">Per ogni elemento di contenuto, selezionare la lingua e fornire la riga dell'oggetto dell'e-mail.</span><span class="sxs-lookup"><span data-stu-id="d0272-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="d0272-129">Se l'e-mail avrà un corpo, assicurarsi che la casella **Con corpo** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="d0272-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="d0272-130">Nel riquadro azioni, selezionare **Messaggio di posta elettronica** per fornire un modello di corpo dell'email.</span><span class="sxs-lookup"><span data-stu-id="d0272-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="d0272-131">L'immagine seguente mostra alcune impostazioni di esempio del modello e-mail.</span><span class="sxs-lookup"><span data-stu-id="d0272-131">The following image shows some example email template settings.</span></span>

![Impostazioni del modello di messaggio di posta elettronica](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="d0272-133">Creare un evento e-mail</span><span class="sxs-lookup"><span data-stu-id="d0272-133">Create an email event</span></span>

<span data-ttu-id="d0272-134">Per creare un evento e-mail attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="d0272-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="d0272-135">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="d0272-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="d0272-136">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d0272-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="d0272-137">Selezionare il modello e-mail dall'elenco a discesa **ID posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="d0272-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="d0272-138">Selezionare il **Tipo di notifica tramite posta elettronica** appropriato dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="d0272-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="d0272-139">Selezionare la casella di controllo **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="d0272-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="d0272-140">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d0272-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="d0272-141">L'immagine seguente mostra alcune impostazioni di esempio della notifica di evento.</span><span class="sxs-lookup"><span data-stu-id="d0272-141">The following image shows some example event notification settings.</span></span>

![Impostazioni notifica di eventi](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="d0272-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="d0272-143">Next steps</span></span>

<span data-ttu-id="d0272-144">Prima di poter inviare e-mail, è necessario configurare il servizio di posta in uscita e impostare un processo batch.</span><span class="sxs-lookup"><span data-stu-id="d0272-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="d0272-145">Per ulteriori informazioni, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="d0272-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="d0272-146">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d0272-146">Additional resources</span></span>

[<span data-ttu-id="d0272-147">Configurare e inviare messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d0272-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="d0272-148">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="d0272-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="d0272-149">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="d0272-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="d0272-150">Panoramica organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="d0272-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
