---
title: Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna
description: In questo argomento viene descritto come impostare modelli di posta elettronica personalizzati per i tipi di notifica e le modalità di consegna specifici in Microsoft Dynamics 365 Commerce.
author: stuharg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: faf5fba70bf9297727464e6046806696ab725001
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594975"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="52f8e-103">Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna</span><span class="sxs-lookup"><span data-stu-id="52f8e-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="52f8e-104">In questo argomento viene descritto come impostare modelli di posta elettronica personalizzati per i tipi di notifica e le modalità di consegna specifici in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="52f8e-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="52f8e-105">I messaggi di posta elettronica transazionali ora possono essere personalizzati per la combinazione di un tipo di notifica (ad esempio, **Ordine creato**, **Ordine imballato**, o **Ordine fatturato**) e una modalità di consegna (ad esempio, durante la notte, ritiro in negozio o ritiro piano strada).</span><span class="sxs-lookup"><span data-stu-id="52f8e-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="52f8e-106">I messaggi di posta elettronica transazionali personalizzati consentono ai rivenditori di fornire ai propri clienti esperienze di evasione degli ordini personalizzate in base alla modalità di consegna dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="52f8e-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="52f8e-107">Ad esempio, l'evento "ordine imballato" può essere personalizzato in modo da fornire istruzioni per il ritiro dal piano strada per i clienti che scelgono questo ritiro.</span><span class="sxs-lookup"><span data-stu-id="52f8e-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="52f8e-108">In alternativa, può fornire informazioni sul corriere e sulla consegna per i clienti che scelgono di spedire l'ordine.</span><span class="sxs-lookup"><span data-stu-id="52f8e-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="52f8e-109">Per utilizzare la funzionalità per i messaggi di posta elettronica transazionali personalizzati è necessario prima attivare la funzionalità **Personalizza i modelli di messaggi di posta elettronica transazionali in base alla modalità di consegna** andando in **Aree di lavoro \> Gestione funzionalità** in Commerce headquarters.</span><span class="sxs-lookup"><span data-stu-id="52f8e-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="52f8e-110">I messaggi di posta elettronica possono essere personalizzati in base alla modalità di consegna per i seguenti tipi di notifica:</span><span class="sxs-lookup"><span data-stu-id="52f8e-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="52f8e-111">**Annullamento ordine** - Questo tipo di notifica tramite posta elettronica è nuovo.</span><span class="sxs-lookup"><span data-stu-id="52f8e-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="52f8e-112">**Ordine creato**</span><span class="sxs-lookup"><span data-stu-id="52f8e-112">**Order created**</span></span>
- <span data-ttu-id="52f8e-113">**Ordine confermato**</span><span class="sxs-lookup"><span data-stu-id="52f8e-113">**Order confirmed**</span></span>
- <span data-ttu-id="52f8e-114">**Ordine fatturato** - Questo tipo di notifica tramite posta elettronica è nuovo.</span><span class="sxs-lookup"><span data-stu-id="52f8e-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="52f8e-115">Può essere utilizzato al posto del tipo di notifica **Ordine spedito** che invierà una notifica per qualsiasi evento di fatturazione che abbia una modalità di consegna spedita (non una modalità di consegna ritiro, trasporto o elettronica).</span><span class="sxs-lookup"><span data-stu-id="52f8e-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="52f8e-116">**Ordine ritirato**</span><span class="sxs-lookup"><span data-stu-id="52f8e-116">**Order picked**</span></span>
- <span data-ttu-id="52f8e-117">**Ordine imballato**</span><span class="sxs-lookup"><span data-stu-id="52f8e-117">**Order packed**</span></span>
- <span data-ttu-id="52f8e-118">**Ordine pronto per il ritiro** - Questo tipo di notifica può essere personalizzato in base alla modalità di consegna solo se la funzionalità **Supporto per più modalità di consegna ritiro** è attivata.</span><span class="sxs-lookup"><span data-stu-id="52f8e-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="52f8e-119">In tal caso, questo tipo di notifica è funzionalmente equivalente al tipo di notifica **Ordine imballato**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="52f8e-120">**Pagamento non riuscito**</span><span class="sxs-lookup"><span data-stu-id="52f8e-120">**Payment failed**</span></span>
- <span data-ttu-id="52f8e-121">**Ordine sostitutivo creato**</span><span class="sxs-lookup"><span data-stu-id="52f8e-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="52f8e-122">Configurare modelli di posta elettronica per modalità di consegna specifiche</span><span class="sxs-lookup"><span data-stu-id="52f8e-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="52f8e-123">Per questa procedura, si presume che siano stati già creati i nuovi modelli di messaggi di posta elettronica personalizzati e siano stati aggiunti alla pagina **Modelli di posta elettronica dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="52f8e-124">Per informazioni su come creare e caricare modelli di posta elettronica, vedere [Creare modelli di posta elettronica per eventi transazionali](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="52f8e-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="52f8e-125">Per configurare i modelli di posta elettronica per modalità di consegna specifiche in Commerce headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="52f8e-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="52f8e-126">Andare a **Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="52f8e-127">Sotto **Impostazioni notifica di eventi di vendita al dettaglio**, selezionare un tipo di notifica esistente.</span><span class="sxs-lookup"><span data-stu-id="52f8e-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="52f8e-128">Mentre il tipo di notifica è ancora selezionato, selezionare **Configurare le modalità di consegna**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="52f8e-129">Nella finestra di dialogo **Modalità di consegna**, selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="52f8e-130">Nella nuova riga, nel campo **Modalità di consegna**, selezionare una modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="52f8e-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="52f8e-131">Nel campo **ID posta elettronica** selezionare il modello di messaggio di posta elettronica da mappare alla modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="52f8e-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="52f8e-132">Selezionare la casella di controllo **Attiva**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="52f8e-133">Ripetere i passaggi da 4 a 7 per aggiungere altre modalità di consegna.</span><span class="sxs-lookup"><span data-stu-id="52f8e-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="52f8e-134">Al termine, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="52f8e-135">Quando è presente più di una modalità di consegna tra le righe di un ordine cliente, verrà utilizzato il modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="52f8e-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="52f8e-136">Il modello predefinito è il modello mappato al tipo di notifica nella pagina **Profilo di notifica tramite posta elettronica per Commerce**.</span><span class="sxs-lookup"><span data-stu-id="52f8e-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="52f8e-137">Se un ordine cliente ha una modalità di consegna che non è stata configurata per un modello di posta elettronica personalizzato, verrà utilizzato il modello di posta elettronica predefinito.</span><span class="sxs-lookup"><span data-stu-id="52f8e-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="52f8e-138">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="52f8e-138">Additional resources</span></span>

[<span data-ttu-id="52f8e-139">Creare ordini servizio clienti</span><span class="sxs-lookup"><span data-stu-id="52f8e-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="52f8e-140">Modifica modalità di consegna nel POS</span><span class="sxs-lookup"><span data-stu-id="52f8e-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)
