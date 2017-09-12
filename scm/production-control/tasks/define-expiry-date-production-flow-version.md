--- 
title: Definire una data di scadenza per una versione del flusso di produzione
description: "Per terminare la validità e l'elaborazione di una versione del flusso di produzione in una data specifica o per pianificare la sostituzione di una versione attiva con una nuova versione, è necessario impostare una data di scadenza della versione."
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6fabeb31720a60bf97d08dabf8ed87ac6af7cbf7
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="c13cd-103">Definire una data di scadenza per una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="c13cd-103">Define an expiry date for a production flow version</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c13cd-104">Per terminare la validità e l'elaborazione di una versione del flusso di produzione in una data specifica o per pianificare la sostituzione di una versione attiva con una nuova versione, è necessario impostare una data di scadenza della versione.</span><span class="sxs-lookup"><span data-stu-id="c13cd-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="c13cd-105">Non è necessario disattivare la versione.</span><span class="sxs-lookup"><span data-stu-id="c13cd-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="c13cd-106">Impostare una data di scadenza per terminare una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="c13cd-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="c13cd-107">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="c13cd-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="c13cd-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="c13cd-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="c13cd-109">Selezionare un flusso di produzione con una versione che è già definita.</span><span class="sxs-lookup"><span data-stu-id="c13cd-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="c13cd-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c13cd-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="c13cd-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="c13cd-111">Click Edit.</span></span>
5. <span data-ttu-id="c13cd-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="c13cd-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="c13cd-113">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="c13cd-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="c13cd-114">Per la data di scadenza, una nuova versione non inizierà o verrà attivata.</span><span class="sxs-lookup"><span data-stu-id="c13cd-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="c13cd-115">E non sarà più possibile creare o avviare processi per questo flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="c13cd-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="c13cd-116">È comunque possibile completare i processi avviati dopo la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="c13cd-116">You can still complete started jobs after the expiration date.</span></span>  


