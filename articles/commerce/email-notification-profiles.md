---
title: Impostare un profilo di notifica tramite posta elettronica
description: In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 9e5d90eaf1815bbe54b0bea40d92a0a993a23b75
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113807"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="60a82-103">Impostare un profilo di notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="60a82-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="60a82-104">In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="60a82-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="60a82-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="60a82-105">Overview</span></span>

<span data-ttu-id="60a82-106">Prima di creare canali, è consigliabile impostare un profilo per garantire l'invio di notifiche tramite posta elettronica per vari eventi, come la creazione di ordini, lo stato della spedizione dell'ordine e il mancato pagamento.</span><span class="sxs-lookup"><span data-stu-id="60a82-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="60a82-107">Per ulteriori informazioni di configurazione della posta elettronica, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="60a82-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="60a82-108">Creare un profilo di notifica tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="60a82-108">Create an email notification profile</span></span>

<span data-ttu-id="60a82-109">Per creare un profilo di notifica tramite posta elettronica, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="60a82-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="60a82-110">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="60a82-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="60a82-111">Fare clic su **Nuovo** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="60a82-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="60a82-112">Nel campo **Profilo di notifica tramite posta elettronica**, immettere un nome per identificare il profilo.</span><span class="sxs-lookup"><span data-stu-id="60a82-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="60a82-113">Nel campo **Descrizione** immettere una descrizione pertinente.</span><span class="sxs-lookup"><span data-stu-id="60a82-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="60a82-114">Impostare **Attivo** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="60a82-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="60a82-115">Crea un modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="60a82-115">Create an email template</span></span>

<span data-ttu-id="60a82-116">Prima di poter creare una notifica tramite posta elettronica, è necessario creare un modello e-mail per l'organizzazione che contenga le informazioni di posta elettronica del mittente e il modello e-mail.</span><span class="sxs-lookup"><span data-stu-id="60a82-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="60a82-117">Per creare un modello e-mail attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="60a82-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="60a82-118">Nel pannello di navigazione, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="60a82-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="60a82-119">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="60a82-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="60a82-120">Nel campo **ID posta elettronica**, immettere un ID per facilitare l'identificazione di questo modello.</span><span class="sxs-lookup"><span data-stu-id="60a82-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="60a82-121">Nel campo **Nome mittente** immettere il nome del mittente.</span><span class="sxs-lookup"><span data-stu-id="60a82-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="60a82-122">Nel campo **Descrizione messaggio di posta elettronica** immettere una descrizione pertinente.</span><span class="sxs-lookup"><span data-stu-id="60a82-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="60a82-123">Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="60a82-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="60a82-124">Nella sezione **Generale**, immettere tutte le informazioni facoltative necessarie (come la priorità di posta elettronica).</span><span class="sxs-lookup"><span data-stu-id="60a82-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="60a82-125">Espandere la sezione **Contenuto messaggio posta elettronica** e selezionare **Nuovo** per creare il contenuto del modello.</span><span class="sxs-lookup"><span data-stu-id="60a82-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="60a82-126">Per ogni elemento di contenuto, selezionare la lingua e fornire la riga dell'oggetto dell'e-mail.</span><span class="sxs-lookup"><span data-stu-id="60a82-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="60a82-127">Se l'e-mail avrà un corpo, assicurarsi che la casella **Con corpo** è selezionata.</span><span class="sxs-lookup"><span data-stu-id="60a82-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="60a82-128">Nel riquadro azioni, selezionare **Messaggio di posta elettronica** per fornire un modello di corpo dell'email.</span><span class="sxs-lookup"><span data-stu-id="60a82-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="60a82-129">L'immagine seguente mostra alcune impostazioni di esempio del modello e-mail.</span><span class="sxs-lookup"><span data-stu-id="60a82-129">The following image shows some example email template settings.</span></span>

![Impostazioni del modello di messaggio di posta elettronica](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="60a82-131">Creare un evento e-mail</span><span class="sxs-lookup"><span data-stu-id="60a82-131">Create an email event</span></span>

<span data-ttu-id="60a82-132">Per creare un evento e-mail attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="60a82-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="60a82-133">Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="60a82-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="60a82-134">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="60a82-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="60a82-135">Selezionare il modello e-mail dall'elenco a discesa **ID posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="60a82-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="60a82-136">Selezionare il **Tipo di notifica tramite posta elettronica** appropriato dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="60a82-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="60a82-137">Selezionare la casella di controllo **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="60a82-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="60a82-138">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="60a82-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="60a82-139">L'immagine seguente mostra alcune impostazioni di esempio della notifica di evento.</span><span class="sxs-lookup"><span data-stu-id="60a82-139">The following image shows some example event notification settings.</span></span>

![Impostazioni notifica di eventi](media/email-notification-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="60a82-141">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="60a82-141">Additional resources</span></span>

[<span data-ttu-id="60a82-142">Configurare e inviare messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="60a82-142">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="60a82-143">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="60a82-143">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="60a82-144">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="60a82-144">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="60a82-145">Panoramica organizzazioni e gerarchie organizzative</span><span class="sxs-lookup"><span data-stu-id="60a82-145">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
