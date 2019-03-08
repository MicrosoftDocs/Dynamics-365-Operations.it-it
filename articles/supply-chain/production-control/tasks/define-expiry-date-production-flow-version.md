---
title: Definire una data di scadenza per una versione del flusso di produzione
description: Per terminare la validità e l'elaborazione di una versione del flusso di produzione in una data specifica o per pianificare la sostituzione di una versione attiva con una nuova versione, è necessario impostare una data di scadenza della versione.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aa0bde90273f9392a36732ed79afdad2eea8bf86
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "323527"
---
# <a name="define-an-expiry-date-for-a-production-flow-version"></a><span data-ttu-id="3b77c-103">Definire una data di scadenza per una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="3b77c-103">Define an expiry date for a production flow version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b77c-104">Per terminare la validità e l'elaborazione di una versione del flusso di produzione in una data specifica o per pianificare la sostituzione di una versione attiva con una nuova versione, è necessario impostare una data di scadenza della versione.</span><span class="sxs-lookup"><span data-stu-id="3b77c-104">To end the validity and the processing of a production flow version on a given date, or to plan replacement of an active version with a new version, you have to set an expiry date on the version.</span></span> <span data-ttu-id="3b77c-105">Non è necessario disattivare la versione.</span><span class="sxs-lookup"><span data-stu-id="3b77c-105">It is not necessary to deactivate the version.</span></span>


## <a name="set-an-expiration-date-to-end-a-production-flow-version"></a><span data-ttu-id="3b77c-106">Impostare una data di scadenza per terminare una versione del flusso di produzione</span><span class="sxs-lookup"><span data-stu-id="3b77c-106">Set an expiration date to end a production flow version</span></span>
1. <span data-ttu-id="3b77c-107">Andare a Controllo produzione > Impostazioni > Flusso di produzione snella > Flussi di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b77c-107">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="3b77c-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="3b77c-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="3b77c-109">Selezionare un flusso di produzione con una versione che è già definita.</span><span class="sxs-lookup"><span data-stu-id="3b77c-109">Select any production flow that has a version that is already defined.</span></span>  
3. <span data-ttu-id="3b77c-110">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b77c-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="3b77c-111">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="3b77c-111">Click Edit.</span></span>
5. <span data-ttu-id="3b77c-112">Nell'elenco contrassegnare la riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="3b77c-112">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="3b77c-113">Nel campo Data di scadenza immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="3b77c-113">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="3b77c-114">Per la data di scadenza, una nuova versione non inizierà o verrà attivata.</span><span class="sxs-lookup"><span data-stu-id="3b77c-114">For the expiration date, a new version will not start or become activated.</span></span> <span data-ttu-id="3b77c-115">E non sarà più possibile creare o avviare processi per questo flusso di produzione.</span><span class="sxs-lookup"><span data-stu-id="3b77c-115">It will also no longer be possible to create or start jobs for this production flow.</span></span> <span data-ttu-id="3b77c-116">È comunque possibile completare i processi avviati dopo la data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="3b77c-116">You can still complete started jobs after the expiration date.</span></span>  

