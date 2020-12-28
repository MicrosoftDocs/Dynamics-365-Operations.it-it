---
title: Impostare un profilo di notifica tramite posta elettronica
description: In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
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
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413369"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="5cca7-103">Impostare un profilo di notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5cca7-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5cca7-104">In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5cca7-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="5cca7-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5cca7-105">Overview</span></span>

<span data-ttu-id="5cca7-106">Prima di creare canali, è consigliabile impostare un profilo per garantire l'invio di notifiche tramite posta elettronica per vari eventi, come la creazione di ordini, lo stato della spedizione dell'ordine e il mancato pagamento.</span><span class="sxs-lookup"><span data-stu-id="5cca7-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="5cca7-107">Per ulteriori informazioni di configurazione della posta elettronica, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="5cca7-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="5cca7-108">Creare un profilo di notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5cca7-108">Create an email notification profile</span></span>

<span data-ttu-id="5cca7-109">Per creare un profilo di notifica tramite posta elettronica, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="5cca7-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="5cca7-110">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="5cca7-111">Fare clic su **Nuovo** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="5cca7-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="5cca7-112">Nel campo **Profilo di notifica tramite posta elettronica**, immettere un nome per identificare il profilo.</span><span class="sxs-lookup"><span data-stu-id="5cca7-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="5cca7-113">Nel campo **Descrizione** immettere una descrizione pertinente.</span><span class="sxs-lookup"><span data-stu-id="5cca7-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="5cca7-114">Impostare **Attivo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="5cca7-115">Crea un modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5cca7-115">Create an email template</span></span>

<span data-ttu-id="5cca7-116">Prima di poter creare una notifica tramite posta elettronica, è necessario creare un modello e-mail per l'organizzazione che contenga le informazioni di posta elettronica del mittente e il modello e-mail.</span><span class="sxs-lookup"><span data-stu-id="5cca7-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="5cca7-117">Per creare un modello e-mail attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="5cca7-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="5cca7-118">Nel pannello di navigazione, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="5cca7-119">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="5cca7-120">Nel campo **ID posta elettronica**, immettere un ID per facilitare l'identificazione di questo modello.</span><span class="sxs-lookup"><span data-stu-id="5cca7-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="5cca7-121">Nel campo **Nome mittente** immettere il nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="5cca7-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="5cca7-122">Nel campo **Descrizione messaggio di posta elettronica** immettere una descrizione pertinente.</span><span class="sxs-lookup"><span data-stu-id="5cca7-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="5cca7-123">Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="5cca7-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="5cca7-124">Nella sezione **Generale**, immettere tutte le informazioni facoltative necessarie (come la priorità di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="5cca7-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="5cca7-125">Espandere la sezione **Contenuto messaggio posta elettronica** e selezionare **Nuovo** per creare il contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="5cca7-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="5cca7-126">Per ogni elemento di contenuto, selezionare la lingua e fornire la riga dell'oggetto dell'e-mail.</span><span class="sxs-lookup"><span data-stu-id="5cca7-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="5cca7-127">Se l'e-mail avrà un corpo, assicurarsi che la casella **Con corpo** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="5cca7-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="5cca7-128">Nel riquadro azioni, selezionare **Messaggio di posta elettronica** per fornire un modello di corpo dell'email.</span><span class="sxs-lookup"><span data-stu-id="5cca7-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="5cca7-129">L'immagine seguente mostra alcune impostazioni di esempio del modello e-mail.</span><span class="sxs-lookup"><span data-stu-id="5cca7-129">The following image shows some example email template settings.</span></span>

![Impostazioni del modello di messaggio di posta elettronica](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="5cca7-131">Creare un evento e-mail</span><span class="sxs-lookup"><span data-stu-id="5cca7-131">Create an email event</span></span>

<span data-ttu-id="5cca7-132">Per creare un evento e-mail attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="5cca7-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="5cca7-133">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="5cca7-134">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="5cca7-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="5cca7-135">Selezionare il modello e-mail dall'elenco a discesa **ID posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="5cca7-136">Selezionare il **Tipo di notifica tramite posta elettronica** appropriato dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="5cca7-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="5cca7-137">Selezionare la casella di controllo **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="5cca7-138">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5cca7-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="5cca7-139">L'immagine seguente mostra alcune impostazioni di esempio della notifica di evento.</span><span class="sxs-lookup"><span data-stu-id="5cca7-139">The following image shows some example event notification settings.</span></span>

![Impostazioni notifica di eventi](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="5cca7-141">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="5cca7-141">Next steps</span></span>

<span data-ttu-id="5cca7-142">Prima di poter inviare e-mail, è necessario configurare il servizio di posta in uscita e impostare un processo batch.</span><span class="sxs-lookup"><span data-stu-id="5cca7-142">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="5cca7-143">Per ulteriori informazioni, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="5cca7-143">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="5cca7-144">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="5cca7-144">Additional resources</span></span>

[<span data-ttu-id="5cca7-145">Configurare e inviare messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5cca7-145">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="5cca7-146">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="5cca7-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="5cca7-147">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="5cca7-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="5cca7-148">Panoramica organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="5cca7-148">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
