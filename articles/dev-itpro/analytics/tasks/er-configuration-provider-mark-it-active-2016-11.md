---
title: Creare provider di configurazione e contrassegnarli come attivi
description: I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 13a27c2fec2a2b226e9ae8d5b8f9a61e8b79ceb0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1544911"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a><span data-ttu-id="e49f9-103">Creare provider di configurazione e contrassegnarli come attivi</span><span class="sxs-lookup"><span data-stu-id="e49f9-103">Create configuration providers and mark them as active</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e49f9-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="e49f9-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="e49f9-105">Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="e49f9-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="e49f9-106">In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="e49f9-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="e49f9-107">Creare un provider</span><span class="sxs-lookup"><span data-stu-id="e49f9-107">Create a provider</span></span>
1. <span data-ttu-id="e49f9-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="e49f9-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="e49f9-109">Fare clic su Provider di configurazione.</span><span class="sxs-lookup"><span data-stu-id="e49f9-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="e49f9-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="e49f9-110">Click New.</span></span>
    * <span data-ttu-id="e49f9-111">Un record del provider ha un nome e un URL univoci.</span><span class="sxs-lookup"><span data-stu-id="e49f9-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="e49f9-112">Rivedere il contenuto di questa pagina e ignorare questa procedura se esiste già un record per Litware, Inc. (http://www.litware.com).</span><span class="sxs-lookup"><span data-stu-id="e49f9-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="e49f9-113">Nel campo Nome digitare Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e49f9-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="e49f9-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="e49f9-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="e49f9-115">Nel campo Indirizzo Internet digitare "http://www.litware.com".</span><span class="sxs-lookup"><span data-stu-id="e49f9-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * http://www.litware.com  
6. <span data-ttu-id="e49f9-116">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="e49f9-116">Click Save.</span></span>
7. <span data-ttu-id="e49f9-117">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="e49f9-117">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="e49f9-118">Selezionare il provider come attivo</span><span class="sxs-lookup"><span data-stu-id="e49f9-118">Select as an active provider</span></span>
1. <span data-ttu-id="e49f9-119">Selezionare il provider Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="e49f9-119">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="e49f9-120">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="e49f9-120">Click Set active.</span></span>

