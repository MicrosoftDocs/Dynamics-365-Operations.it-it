---
title: Consentire agli utenti di ricevere messaggi di posta elettronica correlati ai flussi di lavoro
description: È possibile configurare il sistema per inviare messaggi di posta elettronica agli utenti quando si verificano eventi correlati ai flussi di lavoro.
author: jasongre
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6800d02878123388611d35760123d0215e9d539f
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1560500"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="c48e4-103">Consentire agli utenti di ricevere messaggi di posta elettronica correlati ai flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="c48e4-103">Enable users to receive workflow-related email messages</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c48e4-104">È possibile configurare il sistema per inviare messaggi di posta elettronica agli utenti quando si verificano eventi correlati ai flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c48e4-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="c48e4-105">Ad esempio, i messaggi di posta elettronica possono essere inviati agli utenti quando i documenti vengono loro assegnati per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="c48e4-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="c48e4-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="c48e4-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="c48e4-107">Andare a Amministrazione sistema > Utenti > Utenti.</span><span class="sxs-lookup"><span data-stu-id="c48e4-107">Go to System administration > Users > Users.</span></span>
2. <span data-ttu-id="c48e4-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c48e4-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="c48e4-109">Fare clic su Opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="c48e4-109">Click User options.</span></span>
4. <span data-ttu-id="c48e4-110">Fare clic sulla scheda Flusso di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c48e4-110">Click the Workflow tab.</span></span>
    * <span data-ttu-id="c48e4-111">Assicurarsi che la sezione Notifiche sia espansa.</span><span class="sxs-lookup"><span data-stu-id="c48e4-111">Make sure that the Notifications section is expanded.</span></span>     <span data-ttu-id="c48e4-112">Nella sezione Notifiche è possibile specificare il modo in cui si desidera che l'utente riceva la notifica circa gli eventi correlati ai flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="c48e4-112">In the Notifications section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="c48e4-113">Nel campo Tipo di notifica del flusso di lavoro voci, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="c48e4-113">In the Line-item workflow notification type field, select an option.</span></span>
    * <span data-ttu-id="c48e4-114">Raggruppato: notifiche per voci raggruppate in un unico messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c48e4-114">Grouped – Notifications for line items are grouped into a single email message.</span></span>    <span data-ttu-id="c48e4-115">Singolo: viene inviato un messaggio di posta elettronica per ogni voce.</span><span class="sxs-lookup"><span data-stu-id="c48e4-115">Individual – An email message is sent for each line item.</span></span>  
    * <span data-ttu-id="c48e4-116">Se si desidera che l'utente riceva notifiche nel client, selezionare la casella di controllo Invia notifiche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c48e4-116">If you want the user to receive notifications in the client, select the Send notifications in email check box.</span></span>  
6. <span data-ttu-id="c48e4-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="c48e4-117">Click Save.</span></span>
7. <span data-ttu-id="c48e4-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="c48e4-118">Close the page.</span></span>

