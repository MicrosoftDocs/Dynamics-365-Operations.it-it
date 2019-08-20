---
title: Inserire voci registrate nel giornale di registrazione
description: Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cbf7ee8063487303cd4c8d2b76a8b44bacc86193
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846393"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="fe5f0-103">Inserire voci registrate nel giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="fe5f0-103">Journalize posted journal entries</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fe5f0-104">Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="fe5f0-105">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="fe5f0-106">Convalidare le impostazioni per l'inserimento nel giornale di registrazione in Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-106">Validate the settings for journalizing under General ledger > Ledger setup > General ledger parameters.</span></span>
2. <span data-ttu-id="fe5f0-107">Il campo Giornale di registrazione contabile esteso può essere impostato su Sì o No.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-107">The Extended ledger journal field can be set to Yes or No.</span></span> <span data-ttu-id="fe5f0-108">Se Sì, l'output del report verrà diverso.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="fe5f0-109">Selezionare se il periodo può essere chiuso se il processo di inserimento nel giornale di registrazione non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span>
    * <span data-ttu-id="fe5f0-110">Se l'opzione è impostata su Sì, il periodo non può essere chiuso fino al completamento del processo di inserimento nel giornale do registrazione per il periodo.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="fe5f0-111">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-111">Close the page.</span></span>
5. <span data-ttu-id="fe5f0-112">Passare a Contabilità > Attività periodiche > Inserimento nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-112">Go to General ledger > Periodic tasks > Journalizing.</span></span>
6. <span data-ttu-id="fe5f0-113">Fare clic su Filtro.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-113">Click Filter.</span></span>
7. <span data-ttu-id="fe5f0-114">Evidenziare la riga con i criteri di filtro da definire.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="fe5f0-115">Nel campo Criteri immettere o selezionare i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-115">In the Criteria field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="fe5f0-116">Scegliere OK per la pagina del filtro.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-116">Click OK to close the filter page.</span></span>
10. <span data-ttu-id="fe5f0-117">Scegliere OK per avviare il processo di inserimento nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-117">Click OK to start the journalizing process.</span></span>
    * <span data-ttu-id="fe5f0-118">Un report verrà generato dopo che il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="fe5f0-118">A report will be generated after the process is complete.</span></span>  

