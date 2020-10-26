---
title: Gruppi oggetti assistenza
description: I gruppi di oggetti sono utili per ordinare e filtrare i dati relativi a oggetti per scopi statistici e di report.
author: ShylaThompson
manager: tfehr
ms.date: 05/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4438487fa234cf093b557bca9455717b2cd3ca0b
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3979234"
---
# <a name="service-object-groups"></a><span data-ttu-id="e3076-103">Gruppi oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="e3076-103">Service object groups</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3076-104">I gruppi di oggetti sono utili per ordinare e filtrare i dati relativi a oggetti per scopi statistici e di report.</span><span class="sxs-lookup"><span data-stu-id="e3076-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="e3076-105">È possibile, ad esempio, raggruppare oggetti in base alla posizione geografica o in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="e3076-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="e3076-106">Raggruppare per posizione geografica</span><span class="sxs-lookup"><span data-stu-id="e3076-106">Group by geographical location</span></span>

<span data-ttu-id="e3076-107">È possibile utilizzare questo metodo di raggruppamento per visualizzare l'ubicazione dei diversi oggetti per i quali la società fornisce assistenza.</span><span class="sxs-lookup"><span data-stu-id="e3076-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="e3076-108">Il raggruppamento di oggetti per posizione geografica può essere utile anche nel caso in cui sia ad esempio necessario identificare gli oggetti per i quali viene già fornita assistenza in un determinato paese.</span><span class="sxs-lookup"><span data-stu-id="e3076-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="e3076-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3076-109">Example</span></span>

<span data-ttu-id="e3076-110">Un cliente belga contatta il centro assistenza della società perché desidera stipulare un contratto di assistenza per un oggetto, denominato ABC.</span><span class="sxs-lookup"><span data-stu-id="e3076-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="e3076-111">A tutti gli oggetti per i quali viene fornita assistenza tecnica in Belgio è stato collegato un gruppo di oggetti di tipo posizione geografica, denominato Belgio.</span><span class="sxs-lookup"><span data-stu-id="e3076-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="e3076-112">Utilizzando questo gruppo come filtro è possibile determinare rapidamente se l'oggetto ABC è già presente come record nel programma o se è necessario impostare un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="e3076-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="e3076-113">Raggruppare per tipo</span><span class="sxs-lookup"><span data-stu-id="e3076-113">Group by type</span></span>

<span data-ttu-id="e3076-114">È possibile utilizzare questo metodo di raggruppamento per visualizzare i tipi di oggetti per i quali la società fornisce assistenza.</span><span class="sxs-lookup"><span data-stu-id="e3076-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="e3076-115">Il raggruppamento di oggetti per tipo può essere utile anche nel caso in cui sia ad esempio necessario creare un nuovo oggetto in base a oggetti simili già presenti nel programma.</span><span class="sxs-lookup"><span data-stu-id="e3076-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="e3076-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="e3076-116">Example</span></span>

<span data-ttu-id="e3076-117">Un cliente contatta la società perché desidera stipulare un contratto di assistenza per un sistema di condizionamento, denominato HIJ.</span><span class="sxs-lookup"><span data-stu-id="e3076-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="e3076-118">Sebbene questo sistema non sia già presente nei record della società,</span><span class="sxs-lookup"><span data-stu-id="e3076-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="e3076-119">è stato definito un gruppo di oggetti denominato Condizionatori e a questo gruppo sono stati collegati tutti gli oggetti condizionatore.</span><span class="sxs-lookup"><span data-stu-id="e3076-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="e3076-120">Sarà pertanto possibile cercare e identificare rapidamente tutti i sistemi di climatizzazione e utilizzarne il modello di informazioni per creare righe di contratto di assistenza per gli articoli HIJ.</span><span class="sxs-lookup"><span data-stu-id="e3076-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="e3076-121">Questo metodo di utilizzo dei gruppi di oggetti consente di ridurre i tempi necessari per l'impostazione di nuovi oggetti e la determinazione delle attività di assistenza da eseguire.</span><span class="sxs-lookup"><span data-stu-id="e3076-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 

## <a name="create-service-object-groups"></a><span data-ttu-id="e3076-122">Creare gruppi di oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="e3076-122">Create service object groups</span></span>

<span data-ttu-id="e3076-123">Creare gruppi a cui è possibile assegnare oggetti assistenza.</span><span class="sxs-lookup"><span data-stu-id="e3076-123">Create groups that you can assign service objects to.</span></span> <span data-ttu-id="e3076-124">Gli oggetti assistenza sono articoli di magazzino e altri prodotti per cui vengono eseguiti i servizi.</span><span class="sxs-lookup"><span data-stu-id="e3076-124">Service objects are inventory items and other products for which services are performed.</span></span> <span data-ttu-id="e3076-125">Raggruppando gli oggetti assistenza, è possibile creare report per oggetti assistenza simili e correlati.</span><span class="sxs-lookup"><span data-stu-id="e3076-125">By grouping service objects, you can create reports for similar and related service objects.</span></span> <span data-ttu-id="e3076-126">Ad esempio, un gruppo di oggetti assistenza potrebbe essere costituito da due oggetti assistenza: un oggetto assistenza è un kit e il secondo oggetto assistenza è l'assistenza per installare il kit.</span><span class="sxs-lookup"><span data-stu-id="e3076-126">For example, a service object group might consist of two service objects: One service object is a kit, and the second service object is the service to install the kit.</span></span>

<span data-ttu-id="e3076-127">Per creare gruppi di oggetti assistenza, effettuare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3076-127">To create service object groups, follow these steps:</span></span>

1. <span data-ttu-id="e3076-128">Fare clic su **Gestione assistenza > Impostazione > Oggetti assistenza > Oggetti assistenza**.</span><span class="sxs-lookup"><span data-stu-id="e3076-128">Click **Service management > Setup > Service objects > Service object groups**.</span></span>

2. <span data-ttu-id="e3076-129">Fare clic su **Nuovo** per creare un nuovo gruppo di oggetti assistenza.</span><span class="sxs-lookup"><span data-stu-id="e3076-129">Click **New** to create a new service object group.</span></span>

3. <span data-ttu-id="e3076-130">Immettere il nome univoco per il gruppo di oggetti assistenza e, facoltativamente, immettere una descrizione.</span><span class="sxs-lookup"><span data-stu-id="e3076-130">Enter a unique name for the service object group and, optionally, a description.</span></span>

<span data-ttu-id="e3076-131">È possibile assegnare gli oggetti assistenza al gruppo utilizzando il modulo **Oggetti assistenza**.</span><span class="sxs-lookup"><span data-stu-id="e3076-131">You can assign service objects to the group by using the **Service objects** form.</span></span> 

## <a name="see-also"></a><span data-ttu-id="e3076-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e3076-132">See also</span></span>

[<span data-ttu-id="e3076-133">Creare oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="e3076-133">Create service objects</span></span>](create-service-objects.md)


