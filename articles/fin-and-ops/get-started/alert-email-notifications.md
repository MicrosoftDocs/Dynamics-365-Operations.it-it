---
title: Notifiche di avviso client tramite posta elettronica
description: In questo argomento vengono fornite informazioni su come impostare le regole per l'invio di notifiche tramite posta elettronica quando si verificano eventi predefiniti.
author: tjvass
manager: AnnBe
ms.date: 02/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: kfend
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: 314f04eec04a75aed058c9c38066738e8758f653
ms.sourcegitcommit: 440ebe14ad26574ba227d23ee8370f6b6110645b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2019
ms.locfileid: "373789"
---
# <a name="client-alert-notifications-by-email"></a><span data-ttu-id="9bcb5-103">Notifiche di avviso client tramite posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9bcb5-103">Client alert notifications by email</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="9bcb5-104">In Microsoft Dynamics 365 for Finance and Operations, è possibile definire regole di avviso personalizzate che monitorano visualizzazioni di dati filtrate e inviano notifiche tramite posta elettronica quando si verificano eventi predefiniti.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-104">In Microsoft Dynamics 365 for Finance and Operations, you can define custom alert rules that monitor filtered views of data and automatically send email notifications when predefined events occur.</span></span> <span data-ttu-id="9bcb5-105">L'opzione per inviare notifiche tramite posta elettronica è disponibile per tutti i tipi di avviso supportati e può anche essere attivata per le regole di avviso esistenti.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-105">The option to send email notifications is available for all supported alert types and can also be turned on for existing alert rules.</span></span>

<span data-ttu-id="9bcb5-106">È possibile utilizzare controlli incorporati per creare regole di avviso che controllano le visualizzazioni filtrate di processi batch di sistema.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-106">You can use built-in controls to create alert rules that monitor the filtered views of system batch jobs.</span></span> <span data-ttu-id="9bcb5-107">Mediante il monitoraggio del valore del campo **Stato**, è anche possibile configurare regole di avviso che inviano messaggi di posta elettronica quando un processo batch non riesce.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-107">By monitoring the value of the **Status** field, you can also configure alert rules that send email when a batch job fails.</span></span> <span data-ttu-id="9bcb5-108">Dopo la creazione di tali regole di avviso, non è più necessario controllare i report per eventuali modifiche ai dati aziendali.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-108">After these alert rules are created, you no longer have to check reports for changes to business data.</span></span> <span data-ttu-id="9bcb5-109">In alternativa, è possibile effettuare il monitoraggio mediante il servizio di rilevamento delle modifiche intelligente di Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-109">Instead, you can let the Finance and Operations intelligent change detection service do the monitoring for you.</span></span>

<span data-ttu-id="9bcb5-110">Gli avvisi client dipendono dal sottosistema di posta elettronica fornito mediante l'integrazione con Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-110">Client alerts depend on the email subsystem that is provided through integration with Microsoft Office.</span></span> <span data-ttu-id="9bcb5-111">Si consiglia di utilizzare il provider SMTP (Simple Mail Transfer Protocol), di modo che la distribuzione della posta elettronica non utilizzi un client di posta elettronica locale.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-111">We recommend that you use the Simple Mail Transfer Protocol (SMTP) provider, so that email distribution doesn't have to rely on a local mail client.</span></span>

<span data-ttu-id="9bcb5-112">Per inviare notifiche tramite posta elettronica, i clienti devono configurare servizi di posta elettronica integrati.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-112">To send notifications by email, customers must configure integrated email services.</span></span> <span data-ttu-id="9bcb5-113">Le notifiche tramite posta elettronica sono inviate ai destinatari per conto dei proprietari degli avvisi.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-113">Email notifications are sent to recipients on behalf of alert owners.</span></span>

<span data-ttu-id="9bcb5-114">Per ulteriori informazioni su come configurare la posta elettronica in Finance and Operations, vedere [Configurare e inviare messaggi di posta elettronica](../organization-administration/configure-email.md).</span><span class="sxs-lookup"><span data-stu-id="9bcb5-114">For more information about how to configure email in Finance and Operations, see [Configure and send email](../organization-administration/configure-email.md).</span></span>

<span data-ttu-id="9bcb5-115">L'immagine seguente illustra la finestra di dialogo **Crea regola di avviso**, che ora include un'opzione **Invia posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-115">The following image shows the **Create alert rule** dialog box, which now includes a **Send email** option.</span></span>

<span data-ttu-id="9bcb5-116">[![Finestra di dialogo Crea regola di avviso in cui l'opzione Invia posta elettronica è impostata su Sì](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span><span class="sxs-lookup"><span data-stu-id="9bcb5-116">[![Create alert rule dialog box, where the Send email option is set to Yes](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)</span></span>

> [!NOTE]
> <span data-ttu-id="9bcb5-117">Quando l'opzione **Invia posta elettronica** è impostata su **Sì**, le notifiche di avviso continueranno a essere consegnate al centro azioni.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-117">When the **Send email** option is set to **Yes**, alert notifications will continue to be delivered from the Action Center.</span></span>

## <a name="alert-notification-email-templates"></a><span data-ttu-id="9bcb5-118">Modelli di messaggio di posta elettronica per notifiche di avviso</span><span class="sxs-lookup"><span data-stu-id="9bcb5-118">Alert notification email templates</span></span>

<span data-ttu-id="9bcb5-119">Il servizio invia notifiche tramite posta elettronica utilizzando modelli di messaggio di posta elettronica predefiniti che consegnano dettagli di base della notifica di avviso.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-119">The service sends email notifications by using predefined email templates that deliver the basic details of the alert notification.</span></span> <span data-ttu-id="9bcb5-120">Queste informazioni includono un collegamento diretto alla pagina in cui la regola di avviso è stata definita.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-120">These details include a direct link to the page where the alert rule was defined.</span></span>

<span data-ttu-id="9bcb5-121">Nell'immagine seguente viene illustrata la struttura delle notifiche di avviso ricevute tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9bcb5-121">The following image show the structure of the alert notifications when they are received by email.</span></span>

<span data-ttu-id="9bcb5-122">[![Notifiche di avviso basate su modelli per la creazione di record, le modifiche ai campi e l'eliminazione di modelli](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span><span class="sxs-lookup"><span data-stu-id="9bcb5-122">[![Template-based alert notifications for record creation, field changes, and template deletion](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)</span></span>