---
title: Consentire agli utenti di ricevere messaggi di posta elettronica correlati ai flussi di lavoro
description: È possibile configurare il sistema per inviare messaggi di posta elettronica agli utenti quando si verificano eventi correlati ai flussi di lavoro.
author: jasongre
manager: AnnBe
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5b7a953ea54286a7e48b392728d2cc9bb2902072
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692820"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a><span data-ttu-id="fef12-103">Consentire agli utenti di ricevere messaggi di posta elettronica correlati ai flussi di lavoro</span><span class="sxs-lookup"><span data-stu-id="fef12-103">Enable users to receive workflow-related email messages</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fef12-104">È possibile configurare il sistema per inviare messaggi di posta elettronica agli utenti quando si verificano eventi correlati ai flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fef12-104">You can configure the system to send email messages to users when workflow-related events occur.</span></span> <span data-ttu-id="fef12-105">Ad esempio, i messaggi di posta elettronica possono essere inviati agli utenti quando i documenti vengono loro assegnati per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="fef12-105">For example, email messages can be sent to users when documents are assigned to them for approval.</span></span> <span data-ttu-id="fef12-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="fef12-106">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="fef12-107">Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti**.</span><span class="sxs-lookup"><span data-stu-id="fef12-107">Go to **Navigation pane > Modules > System administration > Users > Users**.</span></span>
2. <span data-ttu-id="fef12-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="fef12-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="fef12-109">Nel **riquadro azioni** fare clic su **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="fef12-109">On the **Action pane**, click **User options**.</span></span>
4. <span data-ttu-id="fef12-110">Fare clic sulla scheda **Flusso di lavoro**. Assicurarsi che la sezione **Notifiche** sia espansa.</span><span class="sxs-lookup"><span data-stu-id="fef12-110">Click the **Workflow** tab. Make sure that the **Notifications** section is expanded.</span></span> <span data-ttu-id="fef12-111">Nella sezione **Notifiche** è possibile specificare il modo in cui si desidera che l'utente riceva la notifica circa gli eventi correlati ai flussi di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fef12-111">In the **Notifications** section, you can specify how you want the user to be notified about workflow-related events.</span></span>  
5. <span data-ttu-id="fef12-112">Nel campo **Tipo di notifica del flusso di lavoro voci**, selezionare un'opzione.</span><span class="sxs-lookup"><span data-stu-id="fef12-112">In the **Line-item workflow notification type** field, select an option.</span></span>
    - <span data-ttu-id="fef12-113">Raggruppato: notifiche per voci raggruppate in un unico messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fef12-113">Grouped – Notifications for line items are grouped into a single email message.</span></span>
    - <span data-ttu-id="fef12-114">Singolo: viene inviato un messaggio di posta elettronica per ogni voce.</span><span class="sxs-lookup"><span data-stu-id="fef12-114">Individual – An email message is sent for each line item.</span></span>  
    - <span data-ttu-id="fef12-115">Se si desidera che l'utente riceva notifiche nel client, selezionare la casella di controllo **Invia notifiche tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="fef12-115">If you want the user to receive notifications in the client, select the **Send notifications in email** check box.</span></span>  
6. <span data-ttu-id="fef12-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fef12-116">Click **Save**.</span></span>
7. <span data-ttu-id="fef12-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fef12-117">Close the page.</span></span>

> [!NOTE]
> <span data-ttu-id="fef12-118">I modelli di messaggio di posta elettronica per il flusso di lavoro verranno forniti da modelli di messaggio di posta elettronica del sistema o modelli di messaggio di posta elettronica dell'organizzazione a seconda che il flusso di lavoro sia un flusso di lavoro a livello di sistema (non specifico dell'azienda) o a livello di organizzazione (specifico dell'azienda).</span><span class="sxs-lookup"><span data-stu-id="fef12-118">The workflow email templates will be sourced from either system email templates or organization email templates depending on whether the workflow is a system-level (not company specific) or organization-level (company specific) workflow.</span></span>
