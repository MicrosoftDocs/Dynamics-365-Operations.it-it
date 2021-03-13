---
title: Informazioni sui campi di data e ora
description: Comprendere cosa aspettarsi quando si utilizzano i campi di data e ora in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d843eb8cefcd0f2f45c8956cd451f88ca6336efb
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130449"
---
# <a name="understand-date-and-time-fields"></a><span data-ttu-id="fd5b5-103">Informazioni sui campi di data e ora</span><span class="sxs-lookup"><span data-stu-id="fd5b5-103">Understand Date and Time fields</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="fd5b5-104">I campi **Data e ora** sono un concetto fondamentale in Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-104">**Date and Time** fields are a fundamental concept in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="fd5b5-105">È importante capire come utilizzare i dati di **Data e ora** nei moduli, in Dataverse e in origini esterne.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-105">It's important to understand how to work with **Date and Time** data in forms, Dataverse, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="fd5b5-106">Differenza tra i tipi di dati dei campi Data e Data e ora</span><span class="sxs-lookup"><span data-stu-id="fd5b5-106">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="fd5b5-107">I campi **Data e ora** contengono informazioni sul fuso orario, mentre i campi **Data** no.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-107">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="fd5b5-108">I campi **Data** visualizzano le stesse informazioni in tutte le posizioni.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-108">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="fd5b5-109">Quando si immette una data nel campo **Data**, Human Resources scrive la stessa data nel database.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-109">When you enter a date into a **Date** field, Human Resources writes that same date to the database.</span></span>

<span data-ttu-id="fd5b5-110">Quando si visualizzano i dati in un campo **Data e ora**, Human Resources regola la data e l'ora in base al fuso orario dell'utente impostato nel modulo **Opzioni utente** (**Common > Impostazioni > Opzioni utente**).</span><span class="sxs-lookup"><span data-stu-id="fd5b5-110">When displaying data in a **Date and Time** field, Human Resources adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="fd5b5-111">Le informazioni di data e ora immesse nel campo possono non essere le stesse informazioni scritte nel database.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-111">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="fd5b5-112">[![Modulo Opzioni utente](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-112">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="fd5b5-113">Campi Data e ora nei moduli</span><span class="sxs-lookup"><span data-stu-id="fd5b5-113">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="fd5b5-114">I dati **Data e ora** visualizzati non sono gli stessi dati memorizzati nel database se il fuso orario dell'utente non è impostato su Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="fd5b5-114">**Date and Time** data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="fd5b5-115">I dati nei campi **Data e ora** vengono sempre memorizzati come UTC.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-115">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="fd5b5-116">[![Modulo lavoratore UTC](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-116">[![Worker form UTC](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="fd5b5-117">Campi Data e ora nel database</span><span class="sxs-lookup"><span data-stu-id="fd5b5-117">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="fd5b5-118">Quando Human Resources scrive un valore di **Data e ora** nel database, memorizza i dati in UTC.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-118">When Human Resources writes a **Date and Time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="fd5b5-119">Ciò consente agli utenti di visualizzare tutti i dati di **Data e ora** relativi al fuso orario definito nelle opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-119">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="fd5b5-120">Nell'esempio precedente, l'ora di inizio è un punto nel tempo, non una data specifica.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-120">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="fd5b5-121">Se si modifica il fuso orario dell'utente connesso da GMT +12:00 a GMT UTC, lo stesso record mostra 04/30/2019 12:00:00 invece di 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-121">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="fd5b5-122">Nell'esempio seguente, l'impiego di un dipendente 000724 diventa attivo alla stessa ora indipendentemente dal fuso orario.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-122">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="fd5b5-123">Il dipendente sarà attivo il 04/30/2019 nel fuso orario GMT, che è lo stesso di 05/01/2019 nel fuso orario GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-123">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="fd5b5-124">Entrambi fanno riferimento allo stesso punto nel tempo e non a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-124">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="fd5b5-125">[![Modulo lavoratore GMT](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-125">[![Worker form GMT](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-dataverse-and-power-bi"></a><span data-ttu-id="fd5b5-126">Dati di Data e ora in Data Management Framework, Excel, Dataverse e Power BI</span><span class="sxs-lookup"><span data-stu-id="fd5b5-126">Date and Time data in Data Management Framework, Excel, Dataverse, and Power BI</span></span> 

<span data-ttu-id="fd5b5-127">La creazione di report in Data Management Framework, componente aggiuntivo di Excel, Dataverse e Power BI è progettata per interagire con i dati direttamente a livello di database.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-127">The Data Management Framework, Excel Add-In, Dataverse, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="fd5b5-128">Poiché non c'è un client che regola i dati di **Data e ora** sul fuso orario dell'utente, tutti i valori di **Data e ora** sono in UTC. Per questo motivo si può essere indotti in alcuni errori quando si inseriscono o si visualizzano i dati.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-128">Since there's no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="fd5b5-129">I database presuppone che i dati di **Data e ora** che vengono inviati tramite DMF, Excel o Dataverse siano in UTC.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-129">**Date and Time** data submitted via DMF, Excel, or Dataverse is assumed to be in UTC by the database.</span></span> <span data-ttu-id="fd5b5-130">Questa impostazione può causare una certa confusione quando il valore inviato di **Data e ora** non viene visualizzato come previsto perché il fuso orario dell'utente che visualizza i dati non è impostato su UTC.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-130">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="fd5b5-131">La stessa cosa può verificarsi al contrario quando i dati vengono esportati.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-131">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="fd5b5-132">I dati di **Data e ora** nell'entità DMF esportata possono essere differenti da quelli visualizzati nel client Dynamics.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-132">The **Date and Time** data in the exported DMF entity can be different than what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="fd5b5-133">Quando si utilizzano origini esterne come DMF per visualizzare o creare dati, tenere presente che i valori di **Data e ora** vengono considerati per impostazione predefinita in UTC, indipendentemente dal fuso orario del computer dell'utente o dalle impostazioni correnti del fuso orario dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fd5b5-133">When using external sources like DMF to view or author data, keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="fd5b5-134">Esempi dello stesso record che viene visualizzato nelle diverse aree del prodotto</span><span class="sxs-lookup"><span data-stu-id="fd5b5-134">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="fd5b5-135">**Human Resources con fuso orario impostato su UTC**</span><span class="sxs-lookup"><span data-stu-id="fd5b5-135">**Human Resources with user time zone set to UTC**</span></span>

<span data-ttu-id="fd5b5-136">[![Modulo lavoratore impostato su UTC](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-136">[![Worker form set to UTC](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="fd5b5-137">**Human Resources con fuso orario impostato su GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="fd5b5-137">**Human Resources with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="fd5b5-138">[![Modulo lavoratore impostato su GMT](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-138">[![Worker form set to GMT](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="fd5b5-139">**Excel tramite OData**</span><span class="sxs-lookup"><span data-stu-id="fd5b5-139">**Excel Via OData**</span></span>

<span data-ttu-id="fd5b5-140">[![Excel tramite OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-140">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="fd5b5-141">**Gestione temporanea DMF**</span><span class="sxs-lookup"><span data-stu-id="fd5b5-141">**DMF Staging**</span></span>

<span data-ttu-id="fd5b5-142">[![Gestione temporanea DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-142">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="fd5b5-143">**Esportazione DMF**</span><span class="sxs-lookup"><span data-stu-id="fd5b5-143">**DMF Export**</span></span>

<span data-ttu-id="fd5b5-144">[![Esportazione DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-144">[![DMF Export](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="fd5b5-145">**Excel tramite Dataverse**</span><span class="sxs-lookup"><span data-stu-id="fd5b5-145">**Excel via Dataverse**</span></span>

<span data-ttu-id="fd5b5-146">[![Excel tramite Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="fd5b5-146">[![Excel via Dataverse](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

## <a name="see-also"></a><span data-ttu-id="fd5b5-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd5b5-147">See also</span></span>

[<span data-ttu-id="fd5b5-148">Dai di Data e ora</span><span class="sxs-lookup"><span data-stu-id="fd5b5-148">Date and time data</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="fd5b5-149">Fusi orari preferiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="fd5b5-149">User preferred time zones</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
