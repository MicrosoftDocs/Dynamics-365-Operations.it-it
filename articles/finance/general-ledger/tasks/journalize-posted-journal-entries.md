---
title: Inserire voci registrate nel giornale di registrazione
description: Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.
author: aprilolson
ms.date: 08/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5028db1db2359a54d565fc299c9a3353a4cf8297
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826156"
---
# <a name="journalize-posted-journal-entries"></a><span data-ttu-id="b4cd1-103">Inserire voci registrate nel giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="b4cd1-103">Journalize posted journal entries</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b4cd1-104">Questa procedura descrive come effettuare inserimenti nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-104">This procedure shows how to journalize posted journal entries.</span></span> <span data-ttu-id="b4cd1-105">Questa procedura utilizza la società di dati dimostrativi USMF.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-105">This procedure uses the USMF demo data company.</span></span>

1. <span data-ttu-id="b4cd1-106">Nel **pannello di navigazione** andare a **Moduli > Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-106">In the **Navigation pane**, go to **Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="b4cd1-107">Il campo **Giornale di registrazione contabile esteso** può essere impostato su Sì o No.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-107">The **Extended ledger journal** field can be set to Yes or No.</span></span> <span data-ttu-id="b4cd1-108">Se Sì, l'output del report verrà diverso.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-108">If Yes, the report output will be different.</span></span>
3. <span data-ttu-id="b4cd1-109">Selezionare se il periodo può essere chiuso se il processo di inserimento nel giornale di registrazione non è stato eseguito.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-109">Select whether the period can be closed if the journalizing process hasn't been run.</span></span> <span data-ttu-id="b4cd1-110">Se l'opzione è impostata su Sì, il periodo non può essere chiuso fino al completamento del processo di inserimento nel giornale do registrazione per il periodo.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-110">If this option is set to Yes, the period cannot be closed until the journalizing process has been completed for that period.</span></span>  
4. <span data-ttu-id="b4cd1-111">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-111">Close the page.</span></span>
5. <span data-ttu-id="b4cd1-112">Nel **pannello di navigazione** andare a **Moduli > Contabilità generale > Attività periodiche > Inserimento nel giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-112">In the **Navigation pane**, go to **Modules > General ledger > Periodic tasks > Journalizing**.</span></span>
6. <span data-ttu-id="b4cd1-113">Fare clic su **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-113">Click **Filter**.</span></span>
7. <span data-ttu-id="b4cd1-114">Evidenziare la riga con i criteri di filtro da definire.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-114">Highlight the row with the filter criteria that you want to define.</span></span>
8. <span data-ttu-id="b4cd1-115">Nel campo **Criteri** immettere o selezionare i criteri di filtro.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-115">In the **Criteria** field, enter or select the filter criteria..</span></span>
9. <span data-ttu-id="b4cd1-116">Scegliere **OK** per la pagina del filtro.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-116">Click **OK** to close the filter page.</span></span>
10. <span data-ttu-id="b4cd1-117">Scegliere **OK** per avviare il processo di inserimento nel giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-117">Click **OK** to start the journalizing process.</span></span> <span data-ttu-id="b4cd1-118">Un report verrà generato dopo che il processo è completato.</span><span class="sxs-lookup"><span data-stu-id="b4cd1-118">A report will be generated after the process is complete.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]