---
title: Gruppi oggetti assistenza
description: I gruppi di oggetti sono utili per ordinare e filtrare i dati relativi a oggetti per scopi statistici e di report.
author: YuyuScheller
manager: AnnBe
ms.date: 02/21/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceObjectGroups
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 221b9dae7e83e7f4a535ac60f2a2011533d7861c
ms.openlocfilehash: fa503ac82286099a0eafc7034d169e165b538e2c
ms.contentlocale: it-it
ms.lasthandoff: 02/21/2018

---

# <a name="service-object-groups"></a><span data-ttu-id="eb3bb-103">Gruppi oggetti assistenza</span><span class="sxs-lookup"><span data-stu-id="eb3bb-103">Service object groups</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="eb3bb-104">I gruppi di oggetti sono utili per ordinare e filtrare i dati relativi a oggetti per scopi statistici e di report.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-104">Object groups are useful for sorting and filtering the data about objects for reports and statistics.</span></span> <span data-ttu-id="eb3bb-105">È possibile, ad esempio, raggruppare oggetti in base alla posizione geografica o in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-105">For example, you can group objects by geographical location or by type.</span></span>

## <a name="group-by-geographical-location"></a><span data-ttu-id="eb3bb-106">Raggruppare per posizione geografica</span><span class="sxs-lookup"><span data-stu-id="eb3bb-106">Group by geographical location</span></span>

<span data-ttu-id="eb3bb-107">È possibile utilizzare questo metodo di raggruppamento per visualizzare l'ubicazione dei diversi oggetti per i quali la società fornisce assistenza.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-107">You can use this grouping method to show where the various different objects that your company services are located.</span></span> <span data-ttu-id="eb3bb-108">Il raggruppamento di oggetti per posizione geografica può essere utile anche nel caso in cui sia ad esempio necessario identificare gli oggetti per i quali viene già fornita assistenza in un determinato paese.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-108">Grouping objects by geographical location can also be useful if, for example, you must identify the objects that your company already provides services for in a particular country/region.</span></span>

## <a name="example"></a><span data-ttu-id="eb3bb-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb3bb-109">Example</span></span>

<span data-ttu-id="eb3bb-110">Un cliente belga contatta il centro assistenza della società perché desidera stipulare un contratto di assistenza per un oggetto, denominato ABC.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-110">A customer from Belgium calls your service center and wants to create a service agreement for an object, ABC.</span></span> <span data-ttu-id="eb3bb-111">A tutti gli oggetti per i quali viene fornita assistenza tecnica in Belgio è stato collegato un gruppo di oggetti di tipo posizione geografica, denominato Belgio.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-111">You have attached an object group for geographical location, Belgium, to all objects that are serviced in Belgium.</span></span> <span data-ttu-id="eb3bb-112">Utilizzando questo gruppo come filtro è possibile determinare rapidamente se l'oggetto ABC è già presente come record nel programma o se è necessario impostare un nuovo oggetto.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-112">By using this group as a filter, you can quickly search to see whether you already have a record for ABC in the program, or whether you must set up a new object.</span></span> 

## <a name="group-by-type"></a><span data-ttu-id="eb3bb-113">Raggruppare per tipo</span><span class="sxs-lookup"><span data-stu-id="eb3bb-113">Group by type</span></span>

<span data-ttu-id="eb3bb-114">È possibile utilizzare questo metodo di raggruppamento per visualizzare i tipi di oggetti per i quali la società fornisce assistenza.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-114">You can use this grouping method to show the types of objects that your company services.</span></span> <span data-ttu-id="eb3bb-115">Il raggruppamento di oggetti per tipo può essere utile anche nel caso in cui sia ad esempio necessario creare un nuovo oggetto in base a oggetti simili già presenti nel programma.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-115">Grouping objects by type can also be useful if, for example, you want to create a new object based on similar objects that already exist in the program.</span></span>

## <a name="example"></a><span data-ttu-id="eb3bb-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="eb3bb-116">Example</span></span>

<span data-ttu-id="eb3bb-117">Un cliente contatta la società perché desidera stipulare un contratto di assistenza per un sistema di condizionamento, denominato HIJ.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-117">A customer calls and wants to set up a service agreement for an air conditioning machine, HIJ.</span></span> <span data-ttu-id="eb3bb-118">Sebbene questo sistema non sia già presente nei record della società,</span><span class="sxs-lookup"><span data-stu-id="eb3bb-118">You do not already have a record for this machine.</span></span> <span data-ttu-id="eb3bb-119">è stato definito un gruppo di oggetti denominato Condizionatori e a questo gruppo sono stati collegati tutti gli oggetti condizionatore.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-119">However, you have set up an object group titled Air Conditioners, and you have attached this group to all air conditioning objects.</span></span> <span data-ttu-id="eb3bb-120">Sarà pertanto possibile cercare e identificare rapidamente tutti i sistemi di climatizzazione e utilizzarne il modello di informazioni per creare righe di contratto di assistenza per gli articoli HIJ.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-120">Therefore, you can quickly search for and identify all other air conditioning machines and use the template information from these objects to create service agreement lines for HIJ.</span></span> <span data-ttu-id="eb3bb-121">Questo metodo di utilizzo dei gruppi di oggetti consente di ridurre i tempi necessari per l'impostazione di nuovi oggetti e la determinazione delle attività di assistenza da eseguire.</span><span class="sxs-lookup"><span data-stu-id="eb3bb-121">By using object groups in this manner, you can quickly set up new objects and determine the service tasks that must be performed on them.</span></span> 




