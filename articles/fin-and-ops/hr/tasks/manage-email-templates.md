---
title: Gestire modelli di messaggi di posta elettronica
description: In questo argomento viene illustrato come gestire i modelli di messaggi di posta elettronica.
author: andreabichsel
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplicationWordBookmark, HRMApplicationEmailTemplate
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3ecfa720dfa9b3ed6ee15ec68498d2a46612a9ae
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867489"
---
# <a name="manage-email-templates"></a><span data-ttu-id="14c61-103">Gestire modelli di messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="14c61-103">Manage email templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="14c61-104">È possibile trasferire le informazioni del database dell'organizzazione ai segnalibri in un nuovo documento e utilizzarlo nei modelli per comunicare efficientemente con i candidati.</span><span class="sxs-lookup"><span data-stu-id="14c61-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="14c61-105">A tale scopo, è necessario creare un modello contenente testo standard e alcuni segnalibri in cui devono essere inseriti i dati.</span><span class="sxs-lookup"><span data-stu-id="14c61-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="14c61-106">Ad esempio, è possibile inserire l'indirizzo e le informazioni sul contatto per un candidato in un documento di Microsoft Word da utilizzare quando si comunica con il candidato.</span><span class="sxs-lookup"><span data-stu-id="14c61-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="14c61-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="14c61-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="14c61-108">Selezionare i segnalibri da utilizzare nei modelli di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="14c61-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="14c61-109">Nel pannello di navigazione, andare a **Moduli > Risorse umane > Selezione del personale > Comunicazioni > Modelli di messaggio di posta elettronica per domande di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="14c61-109">In the navigation pane, go to **Modules > Human Resources > Recruitment > Communication > Application bookmarks**.</span></span>
2. <span data-ttu-id="14c61-110">Nell'elenco trovare e selezionare l'azione di corrispondenza desiderata.</span><span class="sxs-lookup"><span data-stu-id="14c61-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="14c61-111">Selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="14c61-111">Select **Edit**.</span></span>
4. <span data-ttu-id="14c61-112">Selezionare i campi da utilizzare in un modello di messaggio di posta elettronica per l'azione di corrispondenza selezionata e spostarli nei campi di segnalibro.</span><span class="sxs-lookup"><span data-stu-id="14c61-112">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="14c61-113">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="14c61-113">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="14c61-114">Crea un modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="14c61-114">Create an email template</span></span>
1. <span data-ttu-id="14c61-115">Nel pannello di navigazione, andare a **Moduli > Risorse umane > Selezione del personale > Comunicazioni > Modelli di messaggio di posta elettronica per domande di lavoro**.</span><span class="sxs-lookup"><span data-stu-id="14c61-115">In the navigation pane, go to **Modules > Human resources > Recruitment > Communication > Application e-mail templates**.</span></span>
2. <span data-ttu-id="14c61-116">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="14c61-116">Select **New**.</span></span>
3. <span data-ttu-id="14c61-117">Nel campo **Azione corrispondenza** selezionare **Colloquio**.</span><span class="sxs-lookup"><span data-stu-id="14c61-117">In the **Correspondence action** field, select **Interview**.</span></span> <span data-ttu-id="14c61-118">Selezionare l'azione di corrispondenza che contiene i segnalibri da utilizzare per questo tipo di comunicazione di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="14c61-118">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="14c61-119">Digitare un valore nel campo **Modello di messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="14c61-119">In the **E-mail template** field, type a value.</span></span>
5. <span data-ttu-id="14c61-120">Digitare un valore nel campo **Oggetto**.</span><span class="sxs-lookup"><span data-stu-id="14c61-120">In the **Subject** field, type a value.</span></span>
6. <span data-ttu-id="14c61-121">Digitare un valore nel campo **Testo**.</span><span class="sxs-lookup"><span data-stu-id="14c61-121">In the **Text** field, type a value.</span></span>
7. <span data-ttu-id="14c61-122">Trovare e selezionare il campo segnalibro desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="14c61-122">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="14c61-123">Continuare a immettere il messaggio di posta elettronica inserendo i campi segnalibro necessari.</span><span class="sxs-lookup"><span data-stu-id="14c61-123">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
9. <span data-ttu-id="14c61-124">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="14c61-124">Select **Save**.</span></span>

