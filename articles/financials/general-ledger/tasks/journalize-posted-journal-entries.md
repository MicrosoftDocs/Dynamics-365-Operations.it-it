--- 
title: Inserire voci registrate nel giornale di registrazione
description: Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 490e9a4beda43f6e32b87792b11153c3e8e322d6
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="5065f-103">Inserire voci registrate nel giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="5065f-103">Journalize posted journal entries</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="5065f-104">Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5065f-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="5065f-105">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="5065f-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="5065f-106">Convalidare le impostazioni per l'inserimento nel giornale di registrazione in Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="5065f-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="5065f-107">Il campo Giornale di registrazione contabile esteso può essere impostato su Sì o No.</span><span class="sxs-lookup"><span data-stu-id="5065f-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="5065f-108">Se Sì, l'output del report verrà diverso.</span><span class="sxs-lookup"><span data-stu-id="5065f-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="5065f-109">Selezionare se il periodo può essere chiuso se il processo di inserimento nel giornale di registrazione non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="5065f-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="5065f-110">Se l'opzione è impostata su Sì, il periodo non può essere chiuso fino al completamento del processo di inserimento nel giornale do registrazione per il periodo.</span><span class="sxs-lookup"><span data-stu-id="5065f-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="5065f-111">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5065f-111">Close the page.</span></span>
5. <span data-ttu-id="5065f-112">Passare a Contabilità > Attività periodiche > Inserimento nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5065f-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="5065f-113">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="5065f-113">Click Filter.</span></span>
7. <span data-ttu-id="5065f-114">Evidenziare la riga con i criteri di filtro da definire.</span><span class="sxs-lookup"><span data-stu-id="5065f-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="5065f-115">Nel campo Criteri immettere o selezionare i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="5065f-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="5065f-116">Scegliere OK per la pagina del filtro.</span><span class="sxs-lookup"><span data-stu-id="5065f-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="5065f-117">Scegliere OK per avviare il processo di inserimento nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="5065f-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="5065f-118">Un report verrà generato dopo che il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="5065f-118">A report will be generated after the process is complete.</span></span>  


