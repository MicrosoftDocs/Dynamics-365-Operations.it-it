---
title: Utilizzare la data e l'ora in Microsoft Dynamics 365 Talent
description: Comprendere cosa aspettarsi quando si utilizzano i campi di data e ora in Microsoft Dynamics 365 Talent. Chiarire cosa aspettarsi quando si interagisce con i dati di data e ora in un modulo in Talent, un'origine esterna o in Common Data Service.
author: Darinkramer
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-06-06
ms.dyn365.ops.version: Talent
ms.openlocfilehash: abd215243cbda68ba3f57b5fa41054a10745d11f
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/03/2019
ms.locfileid: "2551028"
---
# <a name="work-with-date-and-time-in-microsoft-dynamics-365-talent"></a><span data-ttu-id="9734a-104">Utilizzare la data e l'ora in Microsoft Dynamics 365 Talent</span><span class="sxs-lookup"><span data-stu-id="9734a-104">Work with date and time in Microsoft Dynamics 365 Talent</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9734a-105">I campi **Data e ora** sono un concetto fondamentale in Dynamics 365 Talent.</span><span class="sxs-lookup"><span data-stu-id="9734a-105">**Date and Time** fields are a fundamental concept in Dynamics 365 Talent.</span></span> <span data-ttu-id="9734a-106">È importante capire come utilizzare i dati di **Data e ora** in un modulo di Dynamics 365, Common Data Service e di origini esterne.</span><span class="sxs-lookup"><span data-stu-id="9734a-106">It's important to understand how to work with **Date and Time** data in a Dynamics 365 form, Common Data Service, and external sources.</span></span>

## <a name="understanding-the-difference-between-date-and-date-and-time-field-data-types"></a><span data-ttu-id="9734a-107">Differenza tra i tipi di dati dei campi Data e Data e ora</span><span class="sxs-lookup"><span data-stu-id="9734a-107">Understanding the difference between Date and Date and Time field data types</span></span>

<span data-ttu-id="9734a-108">I campi**Data e ora** contengono informazioni sul fuso orario, mentre i campi **Data** no.</span><span class="sxs-lookup"><span data-stu-id="9734a-108">**Date and Time** fields contain time zone information, while **Date** fields don't.</span></span> <span data-ttu-id="9734a-109">I campi **Data** visualizzano le stesse informazioni in tutte le posizioni.</span><span class="sxs-lookup"><span data-stu-id="9734a-109">**Date** fields display the same information in any location.</span></span> <span data-ttu-id="9734a-110">Quando si immette una data nel campo **Data**, Talent scrive la stessa data nel database.</span><span class="sxs-lookup"><span data-stu-id="9734a-110">When you enter a date into a **Date** field, Talent writes that same date to the database.</span></span>

<span data-ttu-id="9734a-111">Quando si visualizzano i dati in un campo **Data e ora**, Talent regola la data e l'ora in base al fuso orario dell'utente impostato nel modulo **Opzioni utente** (**Common > Impostazioni > Opzioni utente**).</span><span class="sxs-lookup"><span data-stu-id="9734a-111">When displaying data in a **Date and Time** field, Talent adjusts the date and time based on the user's time zone set in the **User Options** form (**Common > Setup > User Options**).</span></span> <span data-ttu-id="9734a-112">Le informazioni di data e ora immesse nel campo possono non essere le stesse informazioni scritte nel database.</span><span class="sxs-lookup"><span data-stu-id="9734a-112">The date and time information you enter in the field might not be the same as the information written to the database.</span></span>

<span data-ttu-id="9734a-113">[![Modulo Opzioni utente](./media/useroptionsform.png)](./media/useroptionsform.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-113">[![User options form](./media/useroptionsform.png)](./media/useroptionsform.png)</span></span>

## <a name="understanding-date-and-time-fields-in-forms"></a><span data-ttu-id="9734a-114">Campi Data e ora nei moduli</span><span class="sxs-lookup"><span data-stu-id="9734a-114">Understanding Date and Time fields in forms</span></span> 

<span data-ttu-id="9734a-115">Quando si inseriscono dati in un campo **Data e ora**, i dati visualizzati non sono gli stessi dati memorizzati nel database se il fuso orario dell'utente non è impostato su Coordinated Universal Time (UTC).</span><span class="sxs-lookup"><span data-stu-id="9734a-115">When entering data in a **Date and Time** field, the data displayed on the screen isn't the same as the data stored in the database if the user's time zone isn't set to Coordinated Universal Time (UTC).</span></span> <span data-ttu-id="9734a-116">I dati nei campi **Data e ora** vengono sempre memorizzati come UTC.</span><span class="sxs-lookup"><span data-stu-id="9734a-116">Data in **Date and Time** fields is always stored as UTC.</span></span>

<span data-ttu-id="9734a-117">[![Modulo Lavoratore](./media/worker-form.png)](./media/worker-form.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-117">[![Worker form](./media/worker-form.png)](./media/worker-form.png)</span></span>

## <a name="understand-date-and-time-fields-in-the-database"></a><span data-ttu-id="9734a-118">Campi Data e ora nel database</span><span class="sxs-lookup"><span data-stu-id="9734a-118">Understand Date and Time fields in the database</span></span> 

<span data-ttu-id="9734a-119">Quando Talent scrive un valore di **Data e ora** nel database, memorizza i dati in UTC.</span><span class="sxs-lookup"><span data-stu-id="9734a-119">When Talent writes a **Date and time** value to the database, it stores the data in UTC.</span></span> <span data-ttu-id="9734a-120">Ciò consente agli utenti di visualizzare tutti i dati di **Data e ora** relativi al fuso orario definito nelle opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="9734a-120">This allows users to see any **Date and Time** data relative to the time zone defined in their user options.</span></span>
 
<span data-ttu-id="9734a-121">Nell'esempio precedente, l'ora di inizio è un punto nel tempo, non una data specifica.</span><span class="sxs-lookup"><span data-stu-id="9734a-121">In the example above, the start time is a point in time, not a particular date.</span></span> <span data-ttu-id="9734a-122">Se si modifica il fuso orario dell'utente connesso da GMT +12:00 a GMT UTC, lo stesso record appena creato mostra 04/30/2019 12:00:00 invece di 05/01/2019 12:00:00.</span><span class="sxs-lookup"><span data-stu-id="9734a-122">By changing the time zone of the logged in user from GMT +12:00 to GMT UTC, the same record just created shows 04/30/2019 12:00:00 instead of 05/01/2019 12:00:00.</span></span>
  
<span data-ttu-id="9734a-123">Nell'esempio seguente, l'impiego di un dipendente 000724 diventa attivo alla stessa ora indipendentemente dal fuso orario.</span><span class="sxs-lookup"><span data-stu-id="9734a-123">In the example below, employee 000724’s employment becomes active at the same time regardless of time zone.</span></span> <span data-ttu-id="9734a-124">Il dipendente sarà attivo il 04/30/2019 nel fuso orario GMT, che è lo stesso di 05/01/2019 nel fuso orario GMT+12:00.</span><span class="sxs-lookup"><span data-stu-id="9734a-124">The employee will be active on 04/30/2019 in the GMT time zone, which is the same as 05/01/2019 in GMT+12:00 time zone.</span></span> <span data-ttu-id="9734a-125">Entrambi fanno riferimento allo stesso punto nel tempo e non a una data specifica.</span><span class="sxs-lookup"><span data-stu-id="9734a-125">Both refer to the same point in time and not a particular date.</span></span> 

<span data-ttu-id="9734a-126">[![Modulo Lavoratore](./media/worker-form2.png)](./media/worker-form2.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-126">[![Worker form](./media/worker-form2.png)](./media/worker-form2.png)</span></span>

## <a name="date-and-time-data-in-data-management-framework-excel-common-data-service-and-power-bi"></a><span data-ttu-id="9734a-127">Dati di Data e ora in Data Management Framework, Excel, Common Data Service e Power BI</span><span class="sxs-lookup"><span data-stu-id="9734a-127">Date and Time data in Data Management Framework, Excel, Common Data Service, and Power BI</span></span> 

<span data-ttu-id="9734a-128">La creazione di report in Data Management Framework, componente aggiuntivo di Excel, Common Data Service e Power BI è progettata per interagire con i dati direttamente a livello di database.</span><span class="sxs-lookup"><span data-stu-id="9734a-128">The Data Management Framework, Excel Add-In, Common Data Service, and Power BI reporting are all designed to interact with data directly on the database level.</span></span> <span data-ttu-id="9734a-129">Poiché non c'è un client che regola i dati di **Data e ora** sul fuso orario dell'utente, tutti i valori di **Data e ora** sono in UTC. Per questo motivo si può essere indotti in alcuni errori quando si inseriscono o si visualizzano i dati.</span><span class="sxs-lookup"><span data-stu-id="9734a-129">Since there is no client to adjust **Date and Time** data to the time zone of the user, all **Date and Time** values are in UTC, which can lead to some incorrect assumptions when entering or viewing data.</span></span>  
 
<span data-ttu-id="9734a-130">I database presuppone che i dati di **Data e ora** che vengono inviati tramite DMF, Excel o Common Data Service siano in UTC.</span><span class="sxs-lookup"><span data-stu-id="9734a-130">**Date and Time** data that is submitted via DMF, Excel, or Common Data Service is assumed to be in UTC by the database.</span></span> <span data-ttu-id="9734a-131">Questa impostazione può causare una certa confusione quando il valore inviato di **Data e ora** non viene visualizzato come previsto perché il fuso orario dell'utente che visualizza i dati non è impostato su UTC.</span><span class="sxs-lookup"><span data-stu-id="9734a-131">This can cause some confusion when the submitted **Date and Time** value doesn't display as expected because the user viewing the data doesn't have their user time zone  set to UTC.</span></span> 
 
<span data-ttu-id="9734a-132">La stessa cosa può verificarsi al contrario quando i dati vengono esportati.</span><span class="sxs-lookup"><span data-stu-id="9734a-132">The same thing can happen in reverse when data is exported.</span></span> <span data-ttu-id="9734a-133">I dati di **Data e ora** nell'entità DMF esportata possono essere differenti da quelli visualizzati nel client Dynamics.</span><span class="sxs-lookup"><span data-stu-id="9734a-133">The **Date and Time** data in the exported DMF entity can be different then what is displayed in the Dynamics client.</span></span> 
 
<span data-ttu-id="9734a-134">Quando si utilizzano origini esterne come DMF per visualizzare o creare dati, è importante da tenere presente che i valori di **Data e ora** vengono considerati per impostazione predefinita in UTC, indipendentemente dal fuso orario del computer dell'utente o dalle impostazioni correnti del fuso orario dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9734a-134">When using external sources like DMF to view or author data, it is important to keep in mind that the **Date and Time** values are considered by default to be in UTC regardless of the time zone of the user's computer or their current user time zone settings.</span></span> 

## <a name="examples-of-the-same-record-being-displayed-in-different-product-areas"></a><span data-ttu-id="9734a-135">Esempi dello stesso record che viene visualizzato nelle diverse aree del prodotto</span><span class="sxs-lookup"><span data-stu-id="9734a-135">Examples of the same record being displayed in different product areas</span></span> 

<span data-ttu-id="9734a-136">**Talent con fuso orario impostato su UTC**</span><span class="sxs-lookup"><span data-stu-id="9734a-136">**Talent with user time zone set to UTC**</span></span>

<span data-ttu-id="9734a-137">[![Modulo Lavoratore](./media/worker-form3.png)](./media/worker-form3.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-137">[![Worker form](./media/worker-form3.png)](./media/worker-form3.png)</span></span>

<span data-ttu-id="9734a-138">**Talent con fuso orario impostato su GMT +12:00**</span><span class="sxs-lookup"><span data-stu-id="9734a-138">**Talent with user time zone set to GMT +12:00**</span></span> 

<span data-ttu-id="9734a-139">[![Modulo Lavoratore](./media/worker-form4.png)](./media/worker-form4.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-139">[![Worker form](./media/worker-form4.png)](./media/worker-form4.png)</span></span>

<span data-ttu-id="9734a-140">**Excel tramite OData**</span><span class="sxs-lookup"><span data-stu-id="9734a-140">**Excel Via OData**</span></span>

<span data-ttu-id="9734a-141">[![Excel tramite OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-141">[![Excel Via OData](./media/Excelviaodata.png)](./media/Excelviaodata.png)</span></span>

<span data-ttu-id="9734a-142">**Gestione temporanea DMF**</span><span class="sxs-lookup"><span data-stu-id="9734a-142">**DMF Staging**</span></span>

<span data-ttu-id="9734a-143">[![Gestione temporanea DMF](./media/DMFStaging.png)](./media/DMFStaging.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-143">[![DMF Staging](./media/DMFStaging.png)](./media/DMFStaging.png)</span></span>

<span data-ttu-id="9734a-144">**Esportazione DMF**</span><span class="sxs-lookup"><span data-stu-id="9734a-144">**DMF Export**</span></span>

<span data-ttu-id="9734a-145">[![Gestione temporanea DMF](./media/DMFexport.png)](./media/DMFexport.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-145">[![DMF Staging](./media/DMFexport.png)](./media/DMFexport.png)</span></span>

<span data-ttu-id="9734a-146">**Excel tramite Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="9734a-146">**Excel via Common Data Service**</span></span>

<span data-ttu-id="9734a-147">[![Excel tramite Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span><span class="sxs-lookup"><span data-stu-id="9734a-147">[![Excel via Common Data Service](./media/ExcelCDS.png)](./media/ExcelCDS.png)</span></span>

### <a name="see-also"></a><span data-ttu-id="9734a-148">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9734a-148">See also</span></span>

[<span data-ttu-id="9734a-149">Dai di Data e ora</span><span class="sxs-lookup"><span data-stu-id="9734a-149">Date and time data</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/date-time-zones)<br></br>
[<span data-ttu-id="9734a-150">Fusi orari preferiti dall'utente</span><span class="sxs-lookup"><span data-stu-id="9734a-150">User preferred time zones</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/organization-administration/tasks/set-users-preferred-time-zone) 
