--- 
title: Gestire modelli di messaggi di posta elettronica
description: "È possibile trasferire le informazioni del database dell'organizzazione ai segnalibri in un nuovo documento e utilizzarlo nei modelli per comunicare efficientemente con i candidati."
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: f09d18e39c58385cfdbbbbb0ff398d1a11bbcbe0
ms.contentlocale: it-it
ms.lasthandoff: 05/08/2018

---
# <a name="manage-email-templates"></a><span data-ttu-id="9b86c-103">Gestire modelli di messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9b86c-103">Manage email templates</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9b86c-104">È possibile trasferire le informazioni del database dell'organizzazione ai segnalibri in un nuovo documento e utilizzarlo nei modelli per comunicare efficientemente con i candidati.</span><span class="sxs-lookup"><span data-stu-id="9b86c-104">You can transfer information from your organization’s database to the bookmarks in a new document and use it in templates that help you communicate efficiently with applicants and candidates.</span></span> <span data-ttu-id="9b86c-105">A tale scopo, è necessario creare un modello contenente testo standard e alcuni segnalibri in cui devono essere inseriti i dati.</span><span class="sxs-lookup"><span data-stu-id="9b86c-105">To do this, you create a template that contains standard text and some bookmarks where the system data should be inserted.</span></span> <span data-ttu-id="9b86c-106">Ad esempio, è possibile inserire l'indirizzo e le informazioni sul contatto per un candidato in un documento di Microsoft Word da utilizzare quando si comunica con il candidato.</span><span class="sxs-lookup"><span data-stu-id="9b86c-106">For example, you can insert address and contact information for an applicant into a Microsoft Word document that you can use when communicating with that applicant.</span></span> <span data-ttu-id="9b86c-107">La società di dati dimostrativi utilizzata per creare questa procedura è USMF.</span><span class="sxs-lookup"><span data-stu-id="9b86c-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="select-which-bookmarks-to-use-in-your-email-templates"></a><span data-ttu-id="9b86c-108">Selezionare i segnalibri da utilizzare nei modelli di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9b86c-108">Select which bookmarks to use in your email templates</span></span>
1. <span data-ttu-id="9b86c-109">Andare a Segnalibri per domande di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9b86c-109">Go to Application bookmarks.</span></span>
2. <span data-ttu-id="9b86c-110">Nell'elenco trovare e selezionare l'azione di corrispondenza desiderata.</span><span class="sxs-lookup"><span data-stu-id="9b86c-110">In the list, find and select the desired correspondence action.</span></span>
3. <span data-ttu-id="9b86c-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="9b86c-111">Click Edit.</span></span>
4. <span data-ttu-id="9b86c-112">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="9b86c-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="9b86c-113">Selezionare i campi da utilizzare in un modello di messaggio di posta elettronica per l'azione di corrispondenza selezionata e spostarli nei campi di segnalibro.</span><span class="sxs-lookup"><span data-stu-id="9b86c-113">Select the fields you would like to be able to use in an email template for the selected Correspondence action and move them to the Bookmark fields.</span></span>  
5. <span data-ttu-id="9b86c-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9b86c-114">Close the page.</span></span>

## <a name="create-an-email-template"></a><span data-ttu-id="9b86c-115">Creare un modello di messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9b86c-115">Create an email template</span></span>
1. <span data-ttu-id="9b86c-116">Andare a Risorse umane > Selezione del personale > Comunicazioni > Modelli di messaggio di posta elettronica per domande di lavoro.</span><span class="sxs-lookup"><span data-stu-id="9b86c-116">Go to Human resources > Recruitment > Communication > Application e-mail templates.</span></span>
2. <span data-ttu-id="9b86c-117">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="9b86c-117">Click New.</span></span>
3. <span data-ttu-id="9b86c-118">Nel campo Azione corrispondenza selezionare "Colloquio".</span><span class="sxs-lookup"><span data-stu-id="9b86c-118">In the Correspondence action field, select 'Interview'.</span></span>
    * <span data-ttu-id="9b86c-119">Selezionare l'azione di corrispondenza che contiene i segnalibri da utilizzare per questo tipo di comunicazione di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9b86c-119">Select the correspondence action that contains the bookmarks to use for this type of email communication.</span></span>  
4. <span data-ttu-id="9b86c-120">Digitare un valore nel campo Modello di messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9b86c-120">In the E-mail template field, type a value.</span></span>
5. <span data-ttu-id="9b86c-121">Digitare un valore nel campo Oggetto.</span><span class="sxs-lookup"><span data-stu-id="9b86c-121">In the Subject field, type a value.</span></span>
6. <span data-ttu-id="9b86c-122">Digitare un valore nel campo Testo.</span><span class="sxs-lookup"><span data-stu-id="9b86c-122">In the Text field, type a value.</span></span>
7. <span data-ttu-id="9b86c-123">Trovare e selezionare il campo segnalibro desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="9b86c-123">In the list, find and select the desired bookmark field.</span></span>
8. <span data-ttu-id="9b86c-124">Continuare a immettere il messaggio di posta elettronica inserendo i campi segnalibro necessari.</span><span class="sxs-lookup"><span data-stu-id="9b86c-124">Continue typing your email message, inserting the bookmark fields where you need them.</span></span>
    * <span data-ttu-id="9b86c-125">Continuare a immettere il messaggio di posta elettronica inserendo i campi segnalibro dove si desidera.</span><span class="sxs-lookup"><span data-stu-id="9b86c-125">Continue typing your email message inserting the bookmark fields where desired.</span></span>  
9. <span data-ttu-id="9b86c-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="9b86c-126">Click Save.</span></span>


