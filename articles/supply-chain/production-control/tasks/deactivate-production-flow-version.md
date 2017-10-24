--- 
title: Disattivare una versione del flusso di produzione
description: "Quando una versione del flusso di produzione attiva non è più necessaria, può essere disattivata."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 4a7eee6617e12d59a3d06207f5f6b58c93e28240
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="40754-103">Disattivare una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="40754-103">Deactivate a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="40754-104">Quando una versione del flusso di produzione attiva non è più necessaria, può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="40754-104">When an active production flow version is no longer needed, it can be deactivated.</span></span> <span data-ttu-id="40754-105">È consigliabile utilizzare questa opzione solo se tutte le regole kanban e attività sono terminate e non verranno attivate di nuovo.</span><span class="sxs-lookup"><span data-stu-id="40754-105">You should only use this option if all kanban rules and activities have ended and will not be activated again.</span></span> <span data-ttu-id="40754-106">Si noti che la data di scadenza di tutte le regole kanban correlate a questa versione del flusso di produzione viene aggiornata alla data e l'ora correnti.</span><span class="sxs-lookup"><span data-stu-id="40754-106">Note that the expiry date of all kanban rules related to this production flow version will be updated with the current date and time.</span></span> 

<span data-ttu-id="40754-107">Per modificare una versione del flusso di produzione attiva, valutare l'opportunità di impostare una data di scadenza per la versione attiva e creare una nuova versione.</span><span class="sxs-lookup"><span data-stu-id="40754-107">To modify an active production flow version, consider setting an expiry date for the active version and create a new version.</span></span> <span data-ttu-id="40754-108">In questo modo sarà possibile continuare con le operazioni di produzione mentre si prepara la nuova versione e le regole kanban correlate.</span><span class="sxs-lookup"><span data-stu-id="40754-108">This will allow you to continue your production operations while preparing the new version and related kanban rules.</span></span> 

<span data-ttu-id="40754-109">Per fare scadere una versione del flusso di produzione attiva, è necessario impostare una data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="40754-109">To expire an active production flow version, you need to set an expiry date.</span></span> <span data-ttu-id="40754-110">In tal senso, la disattivazione è più simile a un'eccezione che a una regola.</span><span class="sxs-lookup"><span data-stu-id="40754-110">In that sense, deactivation is more like an exception than a rule.</span></span> 

<span data-ttu-id="40754-111">Per questa procedura è necessario un flusso di produzione con una versione che può essere disattivata.</span><span class="sxs-lookup"><span data-stu-id="40754-111">For this procedure you need a production flow with a version that can be deactivated.</span></span> <span data-ttu-id="40754-112">Non provare questo in un ambiente di produzione a meno che non si sia assolutamente sicuri che la versione è completamente obsoleta.</span><span class="sxs-lookup"><span data-stu-id="40754-112">Do not try this in a production environment unless you are 100% positive that the version is fully obsolete.</span></span>


## <a name="deactivate-a-production-flow-version"></a><span data-ttu-id="40754-113">Disattivare una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="40754-113">Deactivate a production flow version</span></span>
1. <span data-ttu-id="40754-114">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="40754-114">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="40754-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="40754-115">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="40754-116">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="40754-116">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="40754-117">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="40754-117">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="40754-118">Fare clic su Disattiva.</span><span class="sxs-lookup"><span data-stu-id="40754-118">Click Deactivate.</span></span>
    * <span data-ttu-id="40754-119">Non continuare se non si è assolutamente sicuri che questa versione del flusso di produzione è obsoleta.</span><span class="sxs-lookup"><span data-stu-id="40754-119">Do not proceed if you are not 100% positive that this production flow version is obsolete.</span></span> <span data-ttu-id="40754-120">Se si fa clic su OK tutte le regole kanban attive scadranno e tutte le attività di produzione e rifornimento di questa versione del flusso di produzione verranno immediatamente interrotte.</span><span class="sxs-lookup"><span data-stu-id="40754-120">Clicking Ok will expire all active kanban rules and put an immediate stop to all production and replenishment activities of this production flow version.</span></span>  
6. <span data-ttu-id="40754-121">Fare clic su OK.</span><span class="sxs-lookup"><span data-stu-id="40754-121">Click OK.</span></span>


