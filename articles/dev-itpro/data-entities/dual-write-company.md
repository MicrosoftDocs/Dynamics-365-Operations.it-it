---
title: Concetto di società in Common Data Service
description: In questo argomento viene descritta l'integrazione dei dati della società tra Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 6eddd87c3ad3ea9de8aec2874b0514faa65374f1
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789209"
---
## <a name="company-concept-in-common-data-service"></a><span data-ttu-id="3b499-103">Concetto di società in Common Data Service</span><span class="sxs-lookup"><span data-stu-id="3b499-103">Company concept in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="3b499-104">In Microsoft Dynamics 365 for Finance and Operations, il concetto di *società* è un costrutto sia legale che commerciale.</span><span class="sxs-lookup"><span data-stu-id="3b499-104">In Microsoft Dynamics 365 for Finance and Operations, the concept of a *company* is both a legal construct and a business construct.</span></span> <span data-ttu-id="3b499-105">È inoltre un limite di visibilità e di sicurezza per i dati.</span><span class="sxs-lookup"><span data-stu-id="3b499-105">It's also a security and visibility boundary for data.</span></span> <span data-ttu-id="3b499-106">Gli utenti lavorano sempre nel contesto di una singola società e la maggior parte dei dati è oggetto dello striping della società.</span><span class="sxs-lookup"><span data-stu-id="3b499-106">Users always work in the context of a single company, and most of the data is striped by company.</span></span>

<span data-ttu-id="3b499-107">Common Data Service non dispone di un concetto equivalente.</span><span class="sxs-lookup"><span data-stu-id="3b499-107">Common Data Service doesn't have an equivalent concept.</span></span> <span data-ttu-id="3b499-108">Il concetto più vicino è *Business Unit*, ovvero principalmente un limite di visibilità e sicurezza per i dati utente.</span><span class="sxs-lookup"><span data-stu-id="3b499-108">The closest concept is *business unit*, which is primarily a security and visibility boundary for user data.</span></span> <span data-ttu-id="3b499-109">Questo concetto non ha le stesse implicazioni legali o commerciali del concetto di società in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b499-109">This concept doesn't have the same legal or business implications as the company concept in Finance and Operations.</span></span>

<span data-ttu-id="3b499-110">Poiché Business Unit e società non sono equivalenti concetti, non è possibile applicare un mapping di uno-a-uno (1:1) tra loro a scopo dell'integrazione con Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3b499-110">Because business unit and company aren't equivalent concepts, it isn't possible to force a one-to-one (1:1) mapping between them for the purpose of Common Data Service integration.</span></span> <span data-ttu-id="3b499-111">Tuttavia, poiché gli utenti devono, per impostazione predefinita, poter visualizzare gli stessi record in Finance and Operations e Common Data Service, Microsoft ha introdotto una nuova entità in Common Data Service denominata cdm\_Company.</span><span class="sxs-lookup"><span data-stu-id="3b499-111">However, because users must, by default, be able to see the same records in Finance and Operations and Common Data Service, Microsoft has introduced a new entity in Common Data Service that is named cdm\_Company.</span></span> <span data-ttu-id="3b499-112">Questa entità equivale all'entità Società in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b499-112">This entity is equivalent to the Company entity in Finance and Operations.</span></span> <span data-ttu-id="3b499-113">Per contribuire a garantire che la visibilità dei record è equivalente tra Finance and Operations e Common Data Service in modo predefinito, è consigliabile la seguente impostazione per i dati in Common Data Service:</span><span class="sxs-lookup"><span data-stu-id="3b499-113">To help guarantee that visibility of records is equivalent between Finance and Operations and Common Data Service out of the box, we recommend the following setup for data in Common Data Service:</span></span>

+ <span data-ttu-id="3b499-114">Per ogni record di Finance and Operations abilitato per la doppia scrittura, un record cdm\_Company associato viene creato.</span><span class="sxs-lookup"><span data-stu-id="3b499-114">For each Finance and Operations Company record that is enabled for dual-write, an associated cdm\_Company record is created.</span></span>
+ <span data-ttu-id="3b499-115">Quando un record cdm\_Company viene creato e abilitato per la doppia scrittura, una Business Unit predefinito viene creata con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3b499-115">When a cdm\_Company record is created and enabled for dual-write, a default business unit is created that has the same name.</span></span> <span data-ttu-id="3b499-116">Sebbene un team predefinito venga creato automaticamente per tale Business Unit, la Business Unit non viene utilizzata.</span><span class="sxs-lookup"><span data-stu-id="3b499-116">Although a default team is automatically created for that business unit, the business unit isn't used.</span></span>
+ <span data-ttu-id="3b499-117">Un team proprietario distinto viene creato con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="3b499-117">A separate owner team is created that has the same name.</span></span> <span data-ttu-id="3b499-118">Sarà inoltre associato al Business Unit.</span><span class="sxs-lookup"><span data-stu-id="3b499-118">It's also associated with the business unit.</span></span>
+ <span data-ttu-id="3b499-119">Per impostazione predefinita, il proprietario di un record creato in Finance and Operations e oggetto di doppia scrittura in Common Data Service è impostato sul team "DW Owner" collegato alla Business Unit associata.</span><span class="sxs-lookup"><span data-stu-id="3b499-119">By default, the owner of any record that is created in Finance and Operations and dual-written to Common Data Service is set to the "DW Owner" team that is linked to the associated business unit.</span></span>

<span data-ttu-id="3b499-120">Di seguito viene illustrato un esempio di questa impostazione dei dati in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3b499-120">The following illustration shows an example of this data setup in Common Data Service.</span></span>

![Impostazione dei dati in Common Data Service](media/dual-write-company-1.png)

<span data-ttu-id="3b499-122">Grazie a questa configurazione, qualsiasi record di Finance and Operations correlato alla società USMF sarà di proprietà di un team collegato alla Business Unit USMF in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3b499-122">Because of this configuration, any Finance and Operations record that is related to the USMF company will be owned by a team that is linked to the USMF business unit in Common Data Service.</span></span> <span data-ttu-id="3b499-123">Pertanto, qualsiasi utente con diritti di accesso a tale Business Unit tramite un ruolo di sicurezza impostato su visibilità a livello Business Unit potrà visualizzare i record.</span><span class="sxs-lookup"><span data-stu-id="3b499-123">Therefore, any user who has access to that business unit through a security role that is set to business unit–level visibility can now see those records.</span></span> <span data-ttu-id="3b499-124">Nel seguente esempio viene illustrato come i team possono essere utilizzati per fornire l'accesso corretto a tali record.</span><span class="sxs-lookup"><span data-stu-id="3b499-124">The following example shows how teams can be used to provide the correct access to those records.</span></span>

+ <span data-ttu-id="3b499-125">Il ruolo "Sales Manager" viene assegnato ai membri del team "USMF Sales".</span><span class="sxs-lookup"><span data-stu-id="3b499-125">The "Sales Manager" role is assigned to members of the "USMF Sales" team.</span></span>
+ <span data-ttu-id="3b499-126">Gli utenti con il ruolo "Sales Manager" possono accedere a tutti record relativi ai conti appartenenti alla stessa Business Unit di cui sono membri.</span><span class="sxs-lookup"><span data-stu-id="3b499-126">Users who have the "Sales Manager" role can access any account records that are members of the same business unit that they are members of.</span></span>
+ <span data-ttu-id="3b499-127">Il team "USMF Sales" è collegato alla Business Unit USMF menzionata in precedenza.</span><span class="sxs-lookup"><span data-stu-id="3b499-127">The "USMF Sales" team is linked to the USMF business unit that was mentioned earlier.</span></span>
+ <span data-ttu-id="3b499-128">Di conseguenza, i membri del team "USMF Sales" possono visualizzare qualsiasi conto che appartiene all'utente "USMF DW", proveniente dall'entità Società USMF in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3b499-128">Therefore, members of the "USMF Sales" team can see any account that is owned by the "USMF DW" user, which would have come from the USMF Company entity in Finance and Operations.</span></span>

![Come utilizzare i team](media/dual-write-company-2.png)

<span data-ttu-id="3b499-130">Come mostra la figura precedente, questo mapping 1:1 tra Business Unit, società e team è solo un punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="3b499-130">As the preceding illustration shows, this 1:1 mapping between business unit, company, and team is just a starting point.</span></span> <span data-ttu-id="3b499-131">In questo esempio, il nuovo Business Unit "Europe" è stata creata manualmente in Common Data Service come padre sia per DEMF che ESMF.</span><span class="sxs-lookup"><span data-stu-id="3b499-131">In this example, a new "Europe" business unit is manually created in Common Data Service as the parent for both DEMF and ESMF.</span></span> <span data-ttu-id="3b499-132">La nuova Business Unit principale non è correlata alla doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="3b499-132">This new root business unit is unrelated to dual-write.</span></span> <span data-ttu-id="3b499-133">Tuttavia, è possibile utilizzarla per dare ai membri del team "EUR Sales" accesso ai dati dei conti sia in DEMF che in ESMF impostando la visibilità dei dati su **BU padre/figlio** nel ruolo di sicurezza associato.</span><span class="sxs-lookup"><span data-stu-id="3b499-133">However, it can be used to give members of the "EUR Sales" team access to account data in both DEMF and ESMF by setting the data visibility to **Parent/Child BU** in the associated security role.</span></span>

<span data-ttu-id="3b499-134">Argomento finale da discutere è come la doppia scrittura determina a quale team proprietario assegnare i record.</span><span class="sxs-lookup"><span data-stu-id="3b499-134">A final topic to discuss is how dual-write determines which owner team it should assign records to.</span></span> <span data-ttu-id="3b499-135">Questo funzionamento dipende dal campo **Team proprietario predefinito** nel record cdm\_Company.</span><span class="sxs-lookup"><span data-stu-id="3b499-135">This behavior is controlled by the **Default owning team** field on the cdm\_Company record.</span></span> <span data-ttu-id="3b499-136">Quando un record cdm\_Company è abilitato per la doppia scrittura, un plugin crea automaticamente la Business Unit e il team proprietario (se non esiste già) associati e imposta il campo **Team proprietario predefinito**.</span><span class="sxs-lookup"><span data-stu-id="3b499-136">When a cdm\_Company record is enabled for dual-write, a plug-in automatically creates the associated business unit and owner team (if it doesn't already exist), and sets the **Default owning team** field.</span></span> <span data-ttu-id="3b499-137">Il amministratore può modificare questo campo su un valore diverso.</span><span class="sxs-lookup"><span data-stu-id="3b499-137">The admin can change this field to a different value.</span></span> <span data-ttu-id="3b499-138">Tuttavia, l'amministratore non può cancellare il campo finché l'entità è abilitata per la doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="3b499-138">However, the admin can't clear the field as long as the entity is enabled for dual-write.</span></span>

![Campo Team proprietario predefinito](media/dual-write-default-owning-team.jpg)

## <a name="company-striping-and-bootstrapping"></a><span data-ttu-id="3b499-140">Striping e bootstrap della società</span><span class="sxs-lookup"><span data-stu-id="3b499-140">Company striping and bootstrapping</span></span>

<span data-ttu-id="3b499-141">L'integrazione con Common Data Service porta la parità della società utilizzando un identificatore della società per lo striping dei dati.</span><span class="sxs-lookup"><span data-stu-id="3b499-141">Common Data Service integration brings company parity by using a company identifier to stripe data.</span></span> <span data-ttu-id="3b499-142">Come nella seguente figura viene illustrato, tutte le entità specifiche della società vengono estese in modo che abbiano una relazione molti-a-uno (N:1) con l'entità cdm'\_Company.</span><span class="sxs-lookup"><span data-stu-id="3b499-142">As the following illustration shows, all company-specific entities are extended so that they have a many-to-one (N:1) relationship with the cdm\_Company entity.</span></span>

![La relazione N:1 tra un'entità specifica della società e l'entità cdm_Company](media/dual-write-bootstrapping.png)

+ <span data-ttu-id="3b499-144">Per i record, dopo che una società viene aggiunta e salvata, il valore diventa di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="3b499-144">For records, after a company is added and saved, the value becomes read-only.</span></span> <span data-ttu-id="3b499-145">Di conseguenza, gli utenti devono assicurarsi di scegliere la società corretta.</span><span class="sxs-lookup"><span data-stu-id="3b499-145">Therefore, users should make sure that they select the correct company.</span></span>
+ <span data-ttu-id="3b499-146">Solo i record con dati della società sono idonei alla doppia scrittura tra Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3b499-146">Only records that have company data are eligible for dual-write between Finance and Operations and Common Data Service.</span></span>
+ <span data-ttu-id="3b499-147">Per i dati di Common Data Service esistenti, sarà presto disponibile un'esperienza di bootstrap gestita da amministratore.</span><span class="sxs-lookup"><span data-stu-id="3b499-147">For existing Common Data Service data, an admin-led bootstrapping experience will soon be available.</span></span>